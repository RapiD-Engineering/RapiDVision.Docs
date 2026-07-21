# Calibrating a Robot

Robot calibration is done from the **Lane Manager**, on the tile for the robot lane you want to calibrate.

For delta pickers, triangulation is typically used to align vision coordinates with robot coordinates. This requires three detected positions to be entered in the robot software.

## Prerequisites

- The vision system must be connected and appear in **Lane Manager**.
- The system must have a lane configured with type **Robot**. See [Lane Manager](lane-manager.md) for how to add and connect a robot lane.

## Calibration Steps

1. Open **Lane Manager** from the navigation menu.
2. On the card for your vision system, find the tile for your **Robot** lane.
3. Place 3 uniform items in the camera's field of view (rings are commonly used).
4. On the robot lane's tile, select the **Calibrate robot** icon.
5. In the **Robot** dialog, select **Calibrate Robot**.

The system detects the 3 items and shows the result image together with the list of detected point coordinates in the dialog.

## Robot-Side Calibration

Use the detected points shown in the **Robot** dialog to complete the remaining robot-side calibration steps together with your robot supplier or system integrator.

## Robot Stringbuilder

The **Robot** dialog also has a **Robot stringbuilder** section. Use it to choose which data fields (for example position, orientation, weight, label) are sent to the robot for each detection, and in what order:

1. Move the fields you want to send from the available list to the selected list.
2. Reorder the selected fields as needed.
3. Select **Save**.
