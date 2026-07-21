# Lane Manager

**Lane Manager** is where you configure and monitor the physical lanes (conveyors) connected to a vision system: adding and editing conveyors, calibrating robots, watching live status, and reviewing recipe log warnings.

Open **Lane Manager** from the navigation menu. It shows one card per connected vision system. If no vision system is connected, the page shows a "No systems connected" message.

Each system's card can be expanded or collapsed with the arrow in its header, and has three buttons:

| Button | Description |
|---|---|
| **Refresh** | Re-reads the current lane configuration and live status from the system. |
| **Save** | Saves any conveyor/lane changes you made to the system. |
| **Add Conveyor** | Opens the conveyor editor to add a new lane. |

Inside each system's card is a grid of tiles, one per configured lane.

## Lane Types

Each lane has a type, chosen when it's created:

| Type | What it shows and does |
|---|---|
| **Basic** | A vision-only lane. Shows a description and a **Recent recipe log warnings** feed (see below). |
| **Weighing** | A lane with a weighing module. Shows live gross weight, connection status, a **Tare** button, a **Calibrate** button (scale calibration — unrelated to camera or robot calibration), and a recent issues feed. |
| **Pneumatic Sorting** | A lane with a pneumatic actuator. Shows the live up/down relay state, a **Move up / Move down** button, configured output and relay IP, and a recent issues feed. |
| **Marel Sorter** | A lane connected to a Marel sorter over Modbus. Shows connection status, IP/register info, a recent writes feed, and a recent issues feed. |
| **Robot** | A lane that sends detections to a robot picker. Shows connection status, the live encoder value, Modulo Min/Max, IP/Port, a recent sends feed, a recent issues feed, and a **Calibrate robot** action. |

Every lane with a drive also shows a connection badge and a speed stepper. A shared unit selector lets you choose the unit (for example mm/s) used for speed readouts across every lane.

## Adding a Lane

1. Open **Lane Manager**.
2. On the card for your vision system, select **Add Conveyor**.
3. Choose the lane **Type**: Basic, Weighing, Pneumatic Sorting, Marel Sorter, or Robot.
4. Fill in the common fields — Name, Description, and the grid position (Row, Column, and span).
5. Fill in the type-specific fields, for example:
   - **Weighing**: IP address, Port, Slave ID, start/stop distance, auto-tare.
   - **Pneumatic Sorting**: trigger distance, sorting output index, relay IP/Port/Slave ID, and the up/down relay outputs.
   - **Marel Sorter**: IP address, Port, Slave ID, register, write delay.
   - **Robot**: IP address, Port, Modulo Min, Modulo Max, and Pulse per mm.
6. Select **Save** in the dialog.
7. Select **Save** on the system's card to send the updated lane configuration to the device.

## Editing a Lane

1. Open **Lane Manager**.
2. On the lane's tile, select the cog icon.
3. Update the fields as needed.
4. Select **Save** in the dialog, then select **Save** on the system's card.

## Deleting a Lane

1. Open **Lane Manager**.
2. On the lane's tile, select the trash icon.
3. Confirm the deletion.
4. Select **Save** on the system's card.

## Calibrating a Robot Lane

Robot lanes have a **Calibrate robot** icon on their tile. See [Calibrating a Robot](calibrating-a-robot.md) for the full calibration steps, and the **Robot stringbuilder** section for choosing which detection data is sent to the robot.

## Recipe Log Warnings

On **Basic** lanes, the **Recent recipe log warnings** feed lists products whose detected spot(s) were too small, or scored too low, to match a defect condition in the active [Sorting Recipe](sorting-recipes.md). Select the eye icon next to a warning to open the product's detail: its image, measurements, and the individual spots that were detected.

Use these warnings to spot near-misses and decide whether your recipe's defect thresholds need adjusting.
