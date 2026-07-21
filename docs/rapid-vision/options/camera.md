# Options — Camera

The **Camera** tab configures the selected camera's type, resolution, image adjustments, and lighting.

!!! note
    Pixel-to-millimeter calibration isn't done here — that's the **Calibrate Camera** toolbar button, covered in [Camera Calibration](../camera-calibration.md).

## General

| Field | Description |
|---|---|
| **Camera Type** | Intel RealSense, ZED Stereo, Default, Microsoft Kinect, Video File, Galaxy Camera, Rolling Line-Scan (Basler), Area-Scan (Basler), or None. Changes which fields below apply. |
| **Resolution** | Options depend on the Camera Type (see below). |
| **Connected Cameras** | The list of detected camera IDs. Use the refresh icon to re-scan, and the up/down icons to reorder. |
| **Flip frames (X-axis)** / **Flip frames (Y-axis)** | Mirrors the image on that axis. |
| **Auto Exposure** | Lets the camera manage exposure automatically. |
| **Auto Whitebalance** | Lets the camera manage white balance automatically. |

**Resolution options by Camera Type:**

| Camera Type | Options |
|---|---|
| Intel RealSense | 640×480, 1280×720 |
| ZED Stereo | 1280×720, 1920×1080, 2560×1440 |
| Galaxy Camera | 2048×1536 (fixed) |
| Rolling Line-Scan (Basler) | Computed from the Linescan Frame height / Line height sliders below |
| Area-Scan (Basler) | 2448×2048 (fixed) |
| Default | 640×480, 1280×720, 1920×1080, 3840×2160 |
| Everything else (Video File, Microsoft Kinect, None) | 1280×720 |

## Image Adjustment

Which sliders appear depends on the selected Camera Type:

| Camera Type group | Sliders |
|---|---|
| Intel RealSense, Default, None | Exposure (100–10000), Saturation (0–100), Brightness (-64–64), Contrast (0–100), Sharpness (0–100), White Balance Red/Green/Blue (2800–6500), Gain (0–128) |
| Galaxy Camera, Rolling Line-Scan (Basler), Area-Scan (Basler) | Exposure (10–50000), White Balance Red/Green/Blue (1–15), Gain (1–12) |
| Video File | Exposure, Saturation, Brightness, Contrast, Sharpness, White Balance Red/Green/Blue, Gain (all 1–100) |

Area-Scan and Rolling Line-Scan (Basler) also show an **Offset X** / **Offset Y** pair (0–500) alongside the group above.

ZED Stereo and Microsoft Kinect have no dedicated image-adjustment sliders.

## Always Shown

These fields are shown regardless of camera type:

| Field | Range | Notes |
|---|---|---|
| **Linescan Line height** | 1–50 | Only meaningful for line-scan cameras. |
| **Linescan Frame height** | 100–5000 | Only meaningful for line-scan cameras. |
| **Linescan Encoder Divider** | 1–250 | Only meaningful for line-scan cameras. |
| **Light1** / **Light2** | 0–100 | Applies to the whole system, not per Top/Bottom camera. |
| **Light3** | 0–100 | Applies to the whole system, not per Top/Bottom camera. |

## Reset to Default

The page toolbar's **Reset to default** button resets image-adjustment values to sensible defaults for the current Camera Type:

| Camera Type | Reset values |
|---|---|
| Intel RealSense | Brightness 0, Contrast 50, Sharpness 50, Saturation 64, Exposure 78, Gain 64, White Balance Red 4600 |
| Galaxy Camera | Exposure 2000, Gain 10.0, Auto Whitebalance on, White Balance Red/Green/Blue 1.5/1.0/2.0 |
| Rolling Line-Scan (Basler) | Exposure 100.0, Gain 1.0, Linescan Line height 10, Linescan Frame height 3500 |
| Area-Scan (Basler) | Exposure 100.0, Gain 1.0 |
| Video File, ZED Stereo, Microsoft Kinect, Default, None | No change |
