# Sorting Recipes

!!! note
    This page is shared with the RapiD Vision Desktop client — the underlying screen is the same component, just reached from Explorer's own **Sorting Recipes** navigation item instead of Desktop's **Sortings**.

A **sorting recipe** tells RapiD Vision what to do with each product it inspects. As every product passes under the camera, the system checks it against the recipe's rules and decides which **output** (lane, bin, or robot destination) it should go to — for example "Grade A", "Grade B", or "Reject".

Recipes belong to a **Vision Configuration**. A configuration can have several recipes saved for it (for example one recipe per customer or product spec), but only one recipe can be **active** on the device at a time.

## How Sorting Recipes Work

A recipe is made up of one or more **Sorting Items**. Each Sorting Item represents a single output and defines the rules a product must meet to be sent there:

- A **Main Condition** — the primary rule, based on the product itself (label, weight, size).
- Optional **Defect Conditions** — extra rules based on defects/spots found on the product by the vision system.

When a product is inspected, RapiD Vision compares it against every Sorting Item in the active recipe and collects all the items it matches:

- If it matches **exactly one** Sorting Item, that item's output is used.
- If it matches **more than one**, the item with the highest priority (lowest **Priority** number) wins. If two items have the same priority, the one listed first in the recipe wins.
- If it matches **none**, the product falls back to the first Sorting Item in the recipe. It's good practice to make your first item a catch-all (for example "Reject" or "Ungraded") so nothing is routed unexpectedly.

## Sorting Items

Each Sorting Item has:

| Field | Description |
|---|---|
| **Output** | The output number, assigned automatically based on the item's position in the list (1, 2, 3, …). |
| **Description** | A short label for the output, for example "Grade A" or "Reject". |
| **Logo Color** | The color the device's status logo lights up when a product is sent to this output, useful for spotting sorting results at a glance. |
| **Priority** | Used to break ties when a product matches more than one Sorting Item. Lower numbers win. |

## Main Conditions

The Main Condition sets the primary rule for an output — typically the size or weight range a good product should fall into. It supports:

- **Label** — the product class this rule applies to. Leave this at **No Label** to match any product.
- **Weight Range (g)** — minimum and maximum weight.
- **Length Range (mm)** and **Width Range (mm)** — minimum and maximum measured dimensions.
- **Area Range (mm²)** — minimum and maximum measured surface area.
- **Min Score (%)** — the minimum AI confidence required for a match.
- **Density (g/cm³)** — used together with weight and area for products graded by density.

## Defect Conditions

Defect Conditions let a recipe route products based on blemishes or defects the vision system detects, in addition to (or instead of) the Main Condition. Each Defect Condition supports:

- **Label** — the type of defect it applies to.
- **Area Range (mm²)** — the size range of the defect spot.
- **Min Score (%)** — the minimum AI confidence required for the defect to count.
- **Combine area of same defects** — when enabled, all spots of this defect type on a single product are added together (and their scores averaged) before checking against the area and score range, instead of checking each spot separately. Use this when many small defects of the same type together should be treated as one larger problem.

A product only needs to trigger **one** Defect Condition on a Sorting Item to be routed to that item's output.

## Creating a Sorting Recipe

1. Open **Sorting Recipes** from the navigation menu.
2. Select **Add**.
3. On the **General** page, enter a **Recipe Name**.
4. Go to the **Sorting Items** page and select **Add Sorting** for each output you need (for example "Reject", "Grade A", "Grade B"). For each item, set a **Description**, **Logo Color**, and **Priority**. Use the up/down arrows to reorder items — reordering renumbers the outputs automatically.
5. Go to the **Main Conditions** page, select a Sorting Item from the dropdown, and select **Edit**. Set the weight, length, width, area, score, and density ranges for that output, then select **Apply**.
6. Repeat step 5 for every Sorting Item.
7. If your configuration includes defect detection, go to the **Defect Conditions** page, select a Sorting Item, and select **Add Defect** to add one or more defect rules for that output. Configure each defect, then select **Apply**.
8. Review the live preview on the right of the dialog, then select **Save**.

## Editing a Sorting Recipe

1. Open **Sorting Recipes**.
2. Select the recipe card, then select **Edit**.
3. Make your changes across the **General**, **Sorting Items**, **Main Conditions**, and **Defect Conditions** pages.
4. Select **Save**.

If you edit the recipe that is currently active, the changes take effect on the device immediately — no restart required.

## Activating a Sorting Recipe

Only one recipe can run on the device at a time.

1. Open **Sorting Recipes**.
2. Select the recipe you want to use.
3. Select **Activate** and confirm.

The device remembers the last active recipe for each Vision Configuration, so switching back to a configuration later automatically reselects the recipe you were using.

## Deleting a Sorting Recipe

1. Open **Sorting Recipes**.
2. Select the recipe card you want to remove.
3. Select **Delete** and confirm.

## Recipe Log Warnings

Sometimes a defect spot is detected but is too small, or scores too low, to match any Defect Condition in the active recipe. RapiD Vision still logs these as **recipe log warnings** so you can review near-misses and decide whether your recipe's thresholds need adjusting. You can review these from the RapiD Vision Desktop client's [Lane Manager](../rapid-vision/lane-manager.md).
