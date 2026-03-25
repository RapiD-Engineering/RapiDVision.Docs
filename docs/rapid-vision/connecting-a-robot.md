# Connecting a Robot

RapiDVision can communicate with an external robot over Ethernet.

Use this setup to send detection results from the vision system to your robot controller.

## Steps

1. Connect the vision system to the robot controller with an Ethernet cable.
2. Open **Settings** and go to the **Advanced** tab.
3. Set **Sorter type** to **Robot**.
4. Enter the robot **IP address**.
5. Enter the robot **Port**.

## Encoder Settings (Optional)

If your robot provides encoder signaling to the vision system, configure it through the socket connection settings:

1. Enter the encoder **Min Modulo** value.
2. Enter the encoder **Max Modulo** value.
3. Enable **Modulo Check** when the modulo range is finite.

## Verify the Connection

- Confirm the robot is reachable on the configured IP address and port.
- Confirm the vision system can send data without socket errors.
- Run a small test batch to validate end-to-end robot communication.


