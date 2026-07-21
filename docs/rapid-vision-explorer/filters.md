# Filters

**Filters** define the quality issues RapiD Vision Explorer looks for when it analyzes inspected products. They drive two things: the **claim calculations** shown on the Data page, and the **claim reports** you generate from an order.

Filters are shared across your whole company (not tied to a single order), and are managed from the **Reportfilters** page.

!!! note
    Filters are separate from a RapiD Vision device's **Sorting Recipes**. Sorting Recipes decide where the machine physically routes a product in real time. Filters are evaluated independently by Explorer/the API against the same product data, purely to calculate downgrades and claim values — the two can disagree on a given product.

## How Filters Work

Every Filter has a **type**, chosen when it's created and fixed afterward:

| Filter type | Matches when |
|---|---|
| **Segmentation** | A defect spot on a product has the filter's **Label**, and its area, width, and height fall within the filter's thresholds. |
| **Classification** | The product's own label equals the filter's **Label**. |
| **Color** | The product's matched custom color falls within the filter's min/max color range. |

Each Filter also has:

- **Multiplier %** — how heavily a match on this filter counts toward the claim value (see [Calculations](#how-filters-drive-calculations) below).
- **Multipliers per supplier** — optional overrides of the Multiplier % for specific suppliers.
- **Defects** — whether a match on this filter should count toward a claim at all. Non-defect filters are still tracked and shown, but never add to the claim value.
- **Active** — inactive filters are ignored everywhere until re-enabled.

## Creating a Filter

1. Open **Reportfilters** from the navigation menu.
2. Select **Add**.
3. Choose the **Filtertype**: Segmentation, Classification, or Color. This can't be changed later.
4. For Segmentation or Classification, choose the **Label** it should match.
5. Set the **Multiplier %**.
6. If a specific supplier needs a different weighting, select **+** under **Multipliers per supplier**, pick the supplier, and set their Multiplier %.
7. Check **Defects** if a match should count toward the claim value.
8. For a **Segmentation** filter, set **Maximal Area (cm²)**, **Minimal Width (cm)**, and **Minimal Height (cm)**.
9. For a **Color** filter, set the **Min Color Threshold** and **Max Color Threshold**.
10. Select **Add Filter** to save.

## Editing, Deleting, and Enabling Filters

- Select a filter card and select **Edit** to change it (the Filtertype can no longer be changed), then select **Edit Filter** to save.
- Select one or more filter cards and select **Delete** to remove them.
- Select one or more filter cards and use **Disable/Enable** to toggle whether they're used, or **Enable All** to turn every filter back on.
- **Reset to default** restores your company's default filters. This affects every user, so confirm carefully.

After adding, editing, deleting, or toggling a filter, select **Recalculate** to reprocess the last 30 days of orders with the updated filters.

## How Filters Drive Calculations

When you select an Order, Order Rule, or Batch on the **Data** page, Explorer checks every active Filter against the products in it:

1. For each product, every matching Filter is recorded (label, spot area/width/height, or color, depending on filter type).
2. The percentage of products that matched a given filter is that filter's **downgrade percentage**.
3. For filters marked **Defects**, the downgrade percentage is weighted by the filter's Multiplier % (using a supplier-specific override when one applies to that batch's supplier) to produce a **claim percentage**, which is then applied to the order rule's price to produce a **claim value**.
4. Claim values roll up from Order Rule to Order, giving you a total claim value and claim percentage per order.

Filters that aren't marked as Defects are still shown (so you can see how often they occur), but never contribute to the claim value.

## How Filters Are Used in Claim Reports

1. On the **Data** page, select an **Order** and select **Generate Report**.
2. In the Report Previewer, tick which **Orderrules** to include. Order rules that were already claimed show a **Claimed** badge; you can still adjust their price per unit from there if needed.
3. Choose a **Report Logo**, a **Report Strategy** (how multiple defect spots on one product are counted — largest spot only, every spot, or combined surface area of same-label spots), and how many product images to include.
4. Under **Multipliers**, you can adjust any defect filter's Multiplier % directly — the PDF preview updates immediately.
5. Choose which product images to include from the images list.
6. Select **Generate**, pick where to save the PDF, and confirm marking the included order rules as **Claimed**.

The generated report includes a table per defect label (downgrade %, multiplier %, claim %, and claim value), subtotals per label, and a grand total claim value for the order. If you chose to include a data link, a shareable link to the selected product images is added to the report, and the report is recorded in your claim history.
