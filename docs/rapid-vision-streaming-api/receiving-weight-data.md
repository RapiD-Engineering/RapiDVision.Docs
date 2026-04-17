# Receiving Weight Data via SignalR

Minimal example for an external client connecting to a RapiDVision device to receive weight data.

## Prerequisites

- The RapiDVision Relay Server is running and accessible (e.g. `https://relay.example.com`)
- You know the **device name** of the target device (e.g. `"MYDEVICE"`)
- You have an Azure Entra ID (Azure AD) access token with the correct scope for the SignalR relay:
  ```
  api://<RAPIDRELAYSERVERSCOPE>/ws
  ```
  Replace `<RAPIDRELAYSERVERSCOPE>` with the Application (client) ID of the relay server app registration. Acquire this token using MSAL or any OAuth 2.0 flow against the RapiDVision tenant.
- Install the SignalR client package:
  ```
  dotnet add package Microsoft.AspNetCore.SignalR.Client
  ```

## How It Works

```
External Client  ──SignalR──▶  Relay Server (ClientHub)  ◀──SignalR──  Device (DeviceHub)
                                     │                                       │
                 ◀── WeightData ─────┘                    SendWeightData ────┘
```

1. The client connects to `/clienthub` and registers with a unique client ID.
2. The device sends weight data via `SendWeightData` on the DeviceHub.
3. The relay forwards it to the client as a `"WeightData"` event.

## Minimal C# Example

```csharp
using Microsoft.AspNetCore.SignalR.Client;

var relayUrl = "https://relay.example.com";
var deviceName = "MYDEVICE";
var clientId = $"{Environment.MachineName}_{Guid.NewGuid():N}";

// Acquire a token with the SignalR scope before connecting.
// Replace this with your own token acquisition logic (e.g. MSAL).
string accessToken = await GetAccessTokenAsync(["api://<RAPIDRELAYSERVERSCOPE>/ws"]);

// 1. Build the connection with the access token
var connection = new HubConnectionBuilder()
    .WithUrl($"{relayUrl}/clienthub", options =>
    {
        options.AccessTokenProvider = () => Task.FromResult<string?>(accessToken);
    })
    .WithAutomaticReconnect()
    .Build();

// 2. Listen for weight data
connection.On("WeightData", (string data, string machine, string requestId) =>
{
    Console.WriteLine($"[{machine}] Weight data: {data}");
    // data is a JSON string – deserialize to your model as needed
});

// 3. Connect and register
await connection.StartAsync();
await connection.InvokeAsync("RegisterClient", clientId);

Console.WriteLine($"Listening for weight data from {deviceName}. Press Enter to stop.");
Console.ReadLine();

// 4. Clean up
await connection.StopAsync();
await connection.DisposeAsync();
```

## Notes

- **Heartbeat**: For long-running connections, send periodic heartbeats to prevent the device from cleaning up your session:
  ```csharp
  // Every ~20 seconds
  await connection.InvokeAsync("ClientHeartbeat", deviceName, clientId);
  ```
- **Reconnection**: `WithAutomaticReconnect` handles transient disconnects. After reconnecting, re-call `RegisterClient`.
- The `data` parameter in the `WeightData` event is a JSON-serialized string. Deserialize it into your own model matching the device's weight data schema.
