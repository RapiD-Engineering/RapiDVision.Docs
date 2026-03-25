# Calibrating a Robot

Robot calibration is configured from the **Calibration** page in the RapiD Vision Client.

For delta pickers, triangulation is typically used to align vision coordinates with robot coordinates.
This requires three detected positions to be entered in the robot software.

## Vision Calibration Steps

1. Use a **Classic Vision** configuration.
2. Go to **Settings** and select **Calibrate**.
3. Make sure the canvas is empty before continuing.
4. Place 3 uniform items in the camera field of view (rings are commonly used).
5. In the calibration page, select **Calibrate Robot**.

After calibration, the system generates an image where the three detections are numbered.
Use these numbered points in the robot controller to complete triangulation.

## Robot-Side Calibration

Complete the remaining robot-side calibration steps together with your robot supplier or system integrator.
