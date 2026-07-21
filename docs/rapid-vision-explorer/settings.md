# Settings

The **Settings** page configures how RapiD Vision Explorer displays and calculates data. Except where noted, these settings apply company-wide, to every user — not just your own account.

## Save and Recalculate

Two buttons are always available at the top of the page:

- **Save** — saves your changes. Since these settings apply to everyone, Explorer asks you to confirm: "Are you sure you want to save the settings, this applies to all users?"
- **Recalculate** — reprocesses the last 30 days of data using your current [Filters](filters.md) and these settings. A small warning icon lights up on this button whenever there's an unsaved change that affects calculations (like Report Strategy).

!!! note
    Always select **Save** before **Recalculate**. Recalculating uses whatever settings were last saved to the server — not changes you've made on screen but haven't saved yet.

If you navigate away from the page with unsaved changes, Explorer asks whether you want to save them first.

## User Preferences

| Setting | Description |
|---|---|
| **Language** | English, Dutch, Norwegian, or German. Changing this restarts the app. Unlike every other setting on this page, **Language is local to your device** — it isn't shared with other users. |

## Styling

These set the default appearance of detection overlays on newly displayed product images (on the [Data](data.md) page and elsewhere).

| Setting | Description | Default |
|---|---|---|
| **Draw mode** | Whether to draw every AI detection, or only detections that match an active filter. | Draws all detections |
| **Boxes Visible** | Show bounding boxes around detections. | Off |
| **Contour Visible** | Show each detection's outline. | On |
| **Contour fill Visible** | Fill each detection's outline. | On |
| **Legend Visible** | Show the color legend for detected labels. | On |
| **Labels Visible** | Show text labels on detections. | On |
| **Detection label fontsize** | Size of the detection text labels (12–24). | 12 |

## Report

These control what's included when you generate a claim report — see [Filters](filters.md#how-filters-are-used-in-claim-reports) for the full report flow.

| Setting | Description | Default |
|---|---|---|
| **Report Logo** | Upload an image to use as your report's logo instead of the default RapiD Vision logo. | — |
| **Report Strategy** | How multiple defect spots on one product are counted: use only the largest detection per image, report every detection separately, or combine the surface area of same-label detections into a single value. | Report all detections per image |
| **Data availabilty in days** | How many days a product's images stay available before Explorer marks them as **Expired** in the image panel. | 90 |
| **Include Link to data in report** | Add a link to the source images in generated reports. | On |
| **Include images without detections** | Include product images that have no detections at all. | Off |
| **Include images of bottom** | Include bottom-camera images. | On |
| **Only include products with both top and bottom images** | Only include products that have both a top and a bottom image. | On |

!!! note
    Don't confuse **Data availabilty in days** above with **Generated Links to images expire after** below — they sound similar but control different things. The first is how long an image itself stays available before Explorer treats it as expired; the second is how long a shareable report link stays valid.

## Data

| Setting | Description | Default |
|---|---|---|
| **Auto ordered chronologically** | Orders the Data page's grid chronologically. | On |
| **Claim Percentage Threshold** | Order/Order Rule rows on the Data page with a claim percentage above this start to show a red tint. | 3 |
| **Claim Percentage Threshold Upper** | Rows with a claim percentage at or above this show a solid red tint. | 10 |
| **Minimal amount of images** | Minimum number of images required before a claim percentage is calculated. | 100 |
| **Generated Links to images expire after** | How many days the shareable image link included in a claim report (when **Include Link to data in report** is on) stays valid before it expires. | 14 |
| **Custom Fields** | The custom fields (matching fields in your ERP data, for example Suppliers, Farmers, Packingstations) that appear as extra grouping buttons on the [Data](data.md) page. Select **Add** to type a new field name, or the delete icon next to a field to remove it — removal has no confirmation prompt. | Suppliers, Farmers, Packingstations |
