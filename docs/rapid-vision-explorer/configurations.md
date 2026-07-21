# Vision Configurations

!!! note
    This page is shared with the RapiD Vision Desktop client — the underlying screen is the same component, reached from Explorer's own **Configurations** navigation item.

A **Vision Configuration** defines how a vision system inspects products: which detectors run (top camera, bottom camera, and optional post-processing detectors for defects), which AI model each detector uses, and how captured images are stored. [Sorting Recipes](sorting-recipes.md) are created inside a Vision Configuration and use its detected labels and defects to route products.

A system can have several configurations saved (for example one per product type), but only one can be **active** on a device at a time.

## How Vision Configurations Work

Each configuration can enable up to four detectors:

- **Top Detector** — the main detector for the top camera. Enabled by default.
- **Bottom Detector** — an optional detector for a bottom camera.
- **Post-Processor Top** / **Post-Processor Bottom** — optional secondary detectors that run after the main detector, typically used for defect detection.

Each detector has its own **Task Type**:

| Task Type | Use |
|---|---|
| **Classic** | Traditional (non-AI) blob/contour detection. Choose this if you want to use Filter Range/Erosion-based calibration, as described in [Camera Calibration](../rapid-vision/camera-calibration.md) on the RapiD Vision Desktop client. |
| **Segmentation** | AI segmentation that produces pixel-level masks. |
| **Boxes** | AI object detection using bounding boxes. |
| **Oriented Boxes** | AI object detection using oriented bounding boxes. |
| **Text Prompts** | Detects objects described by a text prompt (YOLOE/SAM). |
| **Detect Anything** | Prompt-free detection (YOLOE/SAM). |

Detectors using Segmentation, Boxes, or Oriented Boxes also need an AI **Model** selected. Classic, Text Prompts, and Detect Anything detectors don't use a selectable model.

## Configuration Fields

**General**

| Field | Description |
|---|---|
| **Configuration Name** | The name shown on the configuration's card. |
| **Thumbnail** | An optional image (jpg/png) shown on the card. |
| **Enable 3D Vision** | Turns on 3D vision for this configuration. |
| **Use Top/Bottom Detector**, **Use Post-Processor Top/Bottom** | Enables the corresponding detector page. |

**Per detector (Top/Bottom Detector, Post-Processor Top/Bottom)**

| Field | Description |
|---|---|
| **Task Type** | See the table above. |
| **Tracker Type** | Not shown for post-processor detectors. |
| **Model** | Only shown when the Task Type requires a model. |
| **Model Image Size** | 480, 640, 1024, or 1280. |
| **Score Threshold (%)** | Minimum AI confidence to count as a detection. |
| **Use Retina Masks** | Higher accuracy segmentation masks, at the cost of more computation. |
| **Video (for testing)** | Only on Top/Bottom Detector pages — lets you test against a recorded video instead of a live camera. |

**Storage**

| Field | Description |
|---|---|
| **Store images in cloud** | Uploads captured images to the cloud. |
| **Only store images with defects in cloud** | Only relevant when cloud storage is enabled. |
| **Store images locally** | Keeps captured images on the device. |

## Creating a Vision Configuration

1. Open **Configurations** from the navigation menu.
2. Select **Add**.
3. On the **General** page, enter a **Configuration Name**, optionally upload a **Thumbnail**, and enable **Enable 3D Vision** if needed.
4. Check which detectors you need: **Use Top Detector** (on by default), **Use Bottom Detector**, **Use Post-Processor Top**, **Use Post-Processor Bottom**.
5. For each detector you enabled, go to its page and set the **Task Type**, **Tracker Type** (not for post-processors), **Model** (if required), **Model Image Size**, **Score Threshold**, and **Use Retina Masks**. Set a **Video (for testing)** on the Top/Bottom Detector pages if you want to test without a live camera.
6. Go to the **Storage** page and choose whether to store images in the cloud and/or locally.
7. Select **Save**.

## Editing a Vision Configuration

1. Open **Configurations**.
2. Select the configuration's card, then select **Edit**.
3. Update any of the **General**, detector, or **Storage** pages.
4. Select **Save**.

## Activating a Vision Configuration

Only one configuration can be active on a device at a time.

1. Open **Configurations**.
2. Select the configuration you want to use.
3. Select **Activate** and confirm.

Activating a configuration also reselects a sorting recipe for it — the one that was last active for that configuration, or its first recipe if it has no previously active one.

## Deleting a Vision Configuration

1. Open **Configurations**.
2. Select the configuration's card (it must not be the active one).
3. Select **Delete** and confirm.

## Calibrating a Configuration

Camera calibration isn't done from Explorer — it's separate from the configuration editor and is done from the RapiD Vision Desktop client's **Options** page once a Classic-detector configuration is active. See [Camera Calibration](../rapid-vision/camera-calibration.md).

!!! note
    Adding, editing, and deleting configurations may not be available in every build — if the **Add**, **Edit**, or **Delete** buttons are greyed out for you, check with your system integrator. **Activate** and uploading configuration files are always available once a vision system is connected.
