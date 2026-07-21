# Options — Filters

The **Filters** tab shows a live preview of the selected camera and lets you tune the basic detection thresholds used by Classic Vision.

## Fields

| Field | Description |
|---|---|
| **Filter range** | 0–255. The core detection threshold. |
| **Erosion** | 0–100. Used to separate touching or slightly overlapping blobs. |
| **Minimal Area** | The minimum blob size (in pixels) to count as a detection. |
| **Release Field** | 0–100. The field where detections are tracked and judged — once a detection leaves this field, it's processed. Shown on the preview as a green rectangle. |
| **Overlap Field** | 0–100. Only shown when **Camera Frame Stackmode** (in the page toolbar) is set to Vertical Stack or Horizontal Stack. Shown on the preview as a yellow dashed rectangle. |

Select **Calibrate** to calibrate the filter threshold against what's currently in view.

## Live Preview

The live camera image updates as you adjust these sliders, so you can see the effect immediately — use it to confirm the Release Field (and Overlap Field, if visible) covers the area you expect before selecting **Save** on the Options page.
