# Data

The **Data** page is where you browse Orders, Order Rules, and Batches, review the images and defects behind them, and see the charts driving your claim calculations.

## Layout

- **Left** — a toggle to choose what you're viewing, and the data grid (or the Active Batch live view) below it. Selected rows show a strip of product images at the bottom.
- **Top right** — the **Summary** panel for whatever's selected, with a **Generate Report** button when viewing Orders.
- **Bottom right** — the **Chart** panel.

## Choosing What to View

Use the toggle buttons at the top of the page to switch between:

- **Orders**
- **OrderRules**
- **Batches**
- **Active Batch** — a live view of the most recent order, rule, and batch (see below).

If your company has configured custom analytics fields, an extra toggle button appears for each one — selecting it groups Order Rules by that field's value instead of listing them individually.

## The Grid

Columns are generated automatically for whichever type you're viewing:

| Type | Columns |
|---|---|
| **Orders** | Status, Invoice, PO Number, Created On, Last Change, Price (€), Weight (kg), Product Count, Claim (€), Claim (%), Defects (avg), Suppliers |
| **OrderRules** | Status, Order, PO Number, Description, Created On, Last Change, Price (€), Price Per Unit, Weight (kg), Claim (€), Claim (%), Product Count, Defects (avg), Suppliers |
| **Batches** | Batch ID, Description, Start Time, End Time, Product Count, Net Weight, Supplier, Defects, Defects (Classification), Defects (Colors) |

Any custom fields your company has configured are appended as extra columns. Rows are tinted when their claim percentage crosses your configured thresholds.

- Select a column header to sort by it. Columns can be reordered and resized, and your layout is remembered.
- Right-click the grid header to show or hide individual columns.
- Use the search box to search the current item type by text.
- Use the period selector (with the **◄ / ►** buttons) to move between Hour, Day, Week, Month, Year, or **All** — this sets the date range the grid loads. Selecting All loads everything with no date bound.
- Open the **⋮** menu for **Recalculate** (reruns the claim calculations for every visible row with the current Filters) and **Export ▸ Excel** / **Export ▸ Json** (saves the currently loaded rows to a file).

## Drilling Down (Summary Panel)

Select a row to load its details into the **Summary** panel:

- A field-by-field summary for that Order, Order Rule, or Batch (matching the grid's columns, plus a few extras — for example an Order's summary includes Totalprice, Totalweight, Claimvalue, and Claimpercentage).
- A **Rules** or **Batches** list of the selected item's children — select one to jump straight to it.
- A **Go to Order** / **Go to Order rule** button to move back up a level.

This is how you move between Orders → Order Rules → Batches — there's no drill-down on the grid itself, only through the Summary panel.

For Orders, the Summary panel also has a **Generate Report** button — see [Filters](filters.md#how-filters-are-used-in-claim-reports) for the full claim report flow.

## Active Batch

Selecting **Active Batch** replaces the grid with a live view of your most recent activity: connected cards for the latest Order, its latest Order Rule, and its latest Batch, refreshing automatically. A header shows the refresh interval and the time of the last update. The Summary, Chart, and product image panels all update to match, live.

## Product Images

Once a row is selected, its product images appear as a thumbnail strip below the grid. Hover a thumbnail to flip between its top and bottom camera image.

- **File** — **Save All** or **Save All With Defects**, each for All images, Top only, or Bottom only.
- **View** — a **Side priority** switch, choosing whether thumbnails default to showing the top or bottom camera image.
- **Sort** — opens the Sort dialog:
  - **Amount of Images to show** — 25, 50, 100, or 250.
  - **Sort Type** — Severity, Filter, or Defect. Choosing Filter or Defect shows a checklist to include only specific filters or defect types.
  - Select **Apply** to reload the images, or **Reset to default** for Severity / 25.

Select a thumbnail to open the full product viewer:

- Top and bottom camera images, stacked, each showing its detected spots.
- Scroll to zoom, drag to pan.
- **◄ / ►** to move to the previous/next product.
- Toggle **Boxes**, **Contour**, **Fill**, **Legend**, and **Text** to control which overlay layers are drawn, and switch between the **Top Image** / **Bottom Image** tabs.
- A **Colors** panel showing the product's average color.
- A **File** menu with **Save**, **Save With Defects**, and **Delete**.

## Charts

The chart panel cycles automatically between two charts every 5 seconds — use the pips at the top to jump to one directly, or the pause button to stop auto-cycling.

- **Defects** — a bar chart of your active Segmentation [Filters](filters.md), grouped by area range, with one colored series per defect label. The bars show the downgrade percentage for that defect/area combination.
- **Sorting Distributions** — a pie chart of how the selected item's products were split across the device's sorting outputs, labeled and colored using the active [Sorting Recipe](sorting-recipes.md).

Both charts reflect whichever row is currently selected in the grid.
