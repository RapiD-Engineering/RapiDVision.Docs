# Reporting

A **claim report** summarizes the quality issues found in an Order's inspected products, calculates a claim value against the supplier using your active [Filters](filters.md), and produces a shareable PDF you can send to them.

## Prerequisites

- The Order must have at least one Order Rule with inspected products.
- Set up the [Filters](filters.md) that describe the defects you want to claim on.
- Review your default report options in [Settings](settings.md) (Report Logo, Report Strategy, image inclusion rules, link expiration) — you can still override most of these for an individual report.

## Generating a Report

1. Open [Data](data.md) and switch to **Orders**.
2. Select the Order you want to report on.
3. Select **Generate Report**. This opens the Report Previewer.
4. Under **Orderrules**, tick which Order Rules to include. Rules that were already claimed show a **Claimed** badge; you can still adjust their price from there — select the "Price per unit is: {value}" button to open **Change Price per unit**.
5. Optionally choose a different **Report Logo** for this report.
6. Choose a **Report Strategy** for this report (how multiple defect spots on one product are counted — this can be different from your default).
7. Choose how many product images to include from **Number of products to export** (25, 100, 1000, or All).
8. Toggle **Include Link to data in report** if you want a shareable link to the source images embedded in the PDF.
9. Under **Multipliers**, adjust any defect filter's Multiplier % for this report — the PDF preview updates immediately as you change it.
10. Under the reported images list, use **Select All** / **Deselect All**, or tick/untick individual product photos to include.
11. Review the live PDF preview on the right (use the page controls to page through it).
12. Select **Generate**, then choose where to save the PDF.
13. If you enabled **Include Link to data in report**, Explorer uploads the selected images and embeds a shareable link in the report.
14. Confirm marking the included Order Rule(s) as **Claimed** when prompted.

The report opens automatically once it's generated.

## What's in the Report

- A header with the report title ("Processing Report {Order name}") and your logo.
- An info block: PO Number, Date of processing, and Value (the total price of the included Order Rules), plus any custom fields you've configured (**Suppliers** is shown as **Exporter** in the report).
- One table per defect label — grouped by filter type and area range — listing the area range, **Downgrades (%)**, **Multiplier (%)**, **Claim (%)**, and **Claim value (€)**, with a subtotal per label.
- A grand **Total** claim value for the whole report.
- If you included a data link, a line linking to the selected images.

## Reviewing Past Reports

Every generated report is recorded to your claim history. Open **History** from the navigation menu to browse past reports, grouped by month with a running total per month. Each entry shows the Order name, PO Number, claim value, claimed date, and who created it, plus:

- Select the PDF icon to download and reopen the report.
- Select the clipboard icon to copy the shareable image link (shown only while it hasn't expired — once it expires, select **Refresh Link** to generate a new one).
- Right-click an entry and select **Delete** to remove it from your claim history.
