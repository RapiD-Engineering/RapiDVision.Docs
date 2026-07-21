# Options

**Options** is RapiD Vision's own settings screen, where you tune a connected vision system's camera, detection, and lane setup. It's split into five tabs — [Filters](filters.md), [Camera](camera.md), [Advanced](advanced.md), [Lanes](lanes.md), and [Style](style.md) — each covered in its own chapter.

!!! note
    This is different from **RapiD Vision Explorer**'s own Settings page, which configures claim reporting and analytics rather than the vision system itself.

## Toolbar

The following controls sit above the tabs and stay visible no matter which tab you're on:

| Control | Description |
|---|---|
| **Save** | Saves every tab's changes for the selected system. See "How changes take effect" below. |
| Instance selector | Chooses which connected vision system you're editing. |
| **Configuration** | Top or Bottom — chooses which camera's settings the Filters, Camera, and Lanes tabs show and edit. |
| **Reset to default** | Resets the Camera tab's fields to their defaults for the current camera type. |
| **Calibrate Camera** | Opens the camera calibration dialog — see [Camera Calibration](../camera-calibration.md). |
| **Restart Camera** | Restarts the camera. |
| **Camera Frame Stackmode** | No Stacking, Vertical Stack, or Horizontal Stack — affects how the Filters tab's Overlap Field is used. |

## How Changes Take Effect

Almost everything on this page applies to the live system **immediately** as you change it — you don't need to select Save to see the effect. However, those live changes aren't saved to the device until you select **Save**, which persists every tab at once. If you close the page or restart without saving, your changes are lost.

!!! tip
    Change something, confirm it looks right on the live camera feed, then select **Save** before moving on.

Opening the **Filters** or **Camera** tab pauses normal detection processing on the device while you're on it; moving to any other tab (or leaving the page) resumes it.
