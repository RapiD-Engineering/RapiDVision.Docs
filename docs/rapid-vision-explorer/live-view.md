# Live View

!!! note
    This page is shared with the RapiD Vision Desktop client — the underlying screen is the same component, just reached from Explorer's own **Live View** navigation item instead of Desktop's **Home**.

**Live View** shows a live tile for every vision system currently connected to the client.

## Layout

Each connected system gets its own tile, arranged automatically in a grid. Every tile's header shows:

- The system's **Machine** name and **Active Batch**.
- An **Info** summary of the system's diagnostics (camera/light/sensor status, temperatures, and similar health indicators).
- The active **Configuration** and **Sorting Recipe** names.
- An AI prompt box, shown only when the active detector supports text-prompt detection.
- A collapse toggle, to shrink a tile you don't need to watch right now down to a small chip.

Above the tiles, a command bar has a **Refresh** button, a **Stream** selector (see below), and an instance selector for choosing which connected system(s) to show.

## Stream Types

Use the **Stream** dropdown on a tile to choose what it displays:

| Stream | Shows |
|---|---|
| **Live** | The top camera's live feed. Scroll to zoom, drag to pan. |
| **Live bottom** | The bottom camera's live feed (only available if the configuration uses a bottom detector). |
| **Live multi** | Top and bottom camera feeds side by side. |
| **Detections** | A per-lane view of detected products/spots with their measurements (position, length, sorting output, angle, weight, volume, height, area, and any matched custom color). |
| **Diagnostics** | Live charts instead of video. Choose a **Graph type** and **Time period** from the extra dropdowns that appear for this stream. |

## Tile Actions

Select the **⋮** menu on a tile for:

- **Restart Machine** — restarts the vision system, after confirmation.
- **Trigger Batch** — manually ends the current batch and starts a new one.
- **Reset Ecomode** — clears eco mode / wakes the system up.
- **Change Configuration** — jumps to [Vision Configurations](vision-configurations.md).
- **Change Sorting Recipe** — jumps to [Sorting Recipes](sorting-recipes.md).
- **Record Video** — opens the **Record Video** dialog.

### Recording a Video

1. Select **Record Video** from a tile's **⋮** menu.
2. Choose the **Camera** (Top or Bottom) and a **Duration** (30, 60, 120, or 180 seconds).
3. Optionally enable **Include detection overlays** to draw the configured detection overlays into the video, instead of recording the raw camera image.
4. Select **Start Recording**. The tile shows a recording indicator and countdown; select **Stop Recording** to end it early.
5. Once the recording finishes uploading, choose where to save the resulting `.mp4` file.

## System Notifications

An expandable **System Notifications** panel in the bottom corner lists active alerts for the connected systems. Each notification has a resolve button once you've addressed it.

## Cabinet Open / Eco Mode

If a system's cabinet is open, or it's in eco mode, its tile replaces the video with a status message instead of a live stream until the condition clears.

## Related Settings

The appearance of detection overlays (bounding boxes, contours, colors, and similar) and camera exposure/gain/lighting aren't configured from Explorer — they're set on the RapiD Vision Desktop client, from **Options ▸ Style** and **Options ▸ Camera**. See [Detection Stream Styling](../rapid-vision/detection-stream-styling.md) and [Camera Settings](../rapid-vision/camera-settings.md).
