# Options — Advanced

The **Advanced** tab covers system behavior that most users won't need to touch day-to-day, grouped into several sections.

## General Options

| Field | Description |
|---|---|
| **EcoMode trigger** | What puts the system into eco mode. |
| **Lights Always on** | Keeps the lights on instead of only during detection. |
| **Dirty lens detector** | Enables blur/dirty-lens detection. |
| **Encoder Max Idle Time (s)** | How long the encoder can be idle before it's considered stalled. |
| **Phidget Server IP** | IP address of the Phidget server. |
| **Start Time for Bottom Detection checks (ms)** | Delay before checking for a bottom-camera detection match. |
| **Total time to check for Bottom Detection (ms)** | Duration of that check window. |
| **Encoder Source** | None, Robot, Phidget, or Camera. |

## Angle Options

| Field | Description |
|---|---|
| **Angle calculation method** | Shortest Line, Longest Line, Shortest Angle, Fillet (Head), or Fillet (Tail). |
| **Box calculation method** | Axis Aligned, Minimal Area, or Longest Side — how the product's bounding box is computed. |
| **Axis Mode** | Bounding Box or Convex Hull. |
| **Angle offset** | A fixed offset applied to the calculated angle. |
| **Flip Angle** | Flips the calculated angle. |

## Batch Options

| Field | Description |
|---|---|
| **Batch Poll Trigger** | Disabled, No Detections for X Seconds, Poll ERP Every X Seconds, or Manual Trigger. |
| **No detection trigger (seconds)** | Only shown when the trigger is "No Detections for X Seconds." |
| **ERP poll interval (seconds)** | Only shown when the trigger is "Poll ERP Every X Seconds." |

## Flags

| Field | Description |
|---|---|
| **Use phidgets** | Enables Phidget hardware integration. |
| **Use ERP** | Enables ERP integration. |
| **DemoMode** | Runs the system in demo mode. |
| **Detections Streaming** | Streams live detections. |

## Conveyor Options

| Field | Description |
|---|---|
| **Conveyor direction** | Up, Right, Down, or Left. |

## Detection Options

| Field | Description |
|---|---|
| **Polygon approximation** | Controls how closely detected contours are simplified. |
| **Delay** | Time between a frame being captured by the camera and received by the PC. |
| **Max detections per frame** | 5, 10, 15, or 20 — the maximum number of detections stored at once in the release field. |

## Tracker

| Field | Description |
|---|---|
| **Location difference** | Maximum position difference between detections in consecutive frames for the tracker to treat them as the same object. |
| **Translation difference** | Maximum translation difference between detections in consecutive frames for the same purpose. |

## Extra Options

| Field | Description |
|---|---|
| **Storage limit (GB)** | Maximum local storage the system may use. |
| **Backend Startup delay in seconds** | Delay before the backend starts up. |
