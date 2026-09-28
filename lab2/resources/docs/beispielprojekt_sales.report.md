# Beispielprojekt_sales Report

## Overview

The report presents a sales overview for Northwind Retail Group and a supporting KPI table. The Sales page combines summary cards, product and customer breakdowns, a store comparison, and a monthly trend. The KPI page groups sales amount, margin, and cost by calendar year and product category.

| Property | Value |
|---|---|
| Source | `Beispielprojekt_sales.Report/` |
| Semantic model | [Beispielprojekt_sales](./beispielprojekt_sales.semantic-model.md) |
| Pages | 2 |

## Report Flow

The report opens on **Sales**, the overview page. Users can slice the calendar and inspect summary metrics and breakdowns. The **KPI** page provides a year-by-year and category comparison of sales amount, margin, and cost. The Sales page is configured as a drillthrough page on Calendar Year, with single selection required for that drillthrough parameter.

**Screenshot capture limitation:** The `powerbi-desktop` rendering CLI and a report-rendering interface were unavailable in this environment. Screenshots could not be captured or visually validated. The page descriptions below are based on the checked-in PBIR definitions; no screenshots are supplied.

## Pages

### Sales

**Screenshot unavailable:** rendering was not possible in this environment; see the capture limitation above.

The landing page, titled “Northwind Retail Group - Sales Analysis,” presents summary performance and several complementary ways to break it down:

#### Main Metrics

- **Sales Amount**: net price multiplied by quantity across sales lines.
- **Sales Amount Avg per Day**: average sales amount across dates in the current calendar context.
- **Customers with Sales**: distinct customers found on the filtered sales lines.
- **Margin**: quantity multiplied by the difference between net price and unit cost.
- An area chart compares **Sales Amount** with **Sales Amount (LY)** over Year-Month and adds a visual-level 12-period moving average. The moving average is a native visual calculation, not a semantic-model measure.

#### Analysis Breakdowns

- **Product category**: clustered bar chart sorted by Sales Amount descending, with category, subcategory, and product levels.
- **Brand and gender**: bar chart compares sales amount by brand and splits series by customer gender; product is an additional category level.
- **Store and month**: scatter chart titled “Sales Amount vs # Customers” uses sales amount on the vertical axis, month name on the horizontal axis, distinct customers for bubble size, and store as series.
- **Monthly trend**: area chart supports a chronological comparison of current-period and prior-year sales.
- Visual interactions are configured to filter other visuals (`drillFilterOtherVisuals`); the report enables cross-highlighting.

#### Available Filters

| Scope | Filter or slicer | Behavior / default |
|---|---|---|
| Page | Calendar Year | Categorical page filter; configured to require a single selection for the drillthrough parameter. The selected/default value is not specified in the page metadata. |
| Page | Product Category | Categorical filter; no explicit selection is recorded. |
| Page | Product Subcategory | Categorical filter; no explicit selection is recorded. |
| Page | Store | Categorical filter; no explicit selection is recorded. |
| Visual | Calendar Year on the brand/gender chart | Categorical visual filter; no explicit selection is recorded. |
| Visual | Calendar Date slicer | Ascending date field; the stored metadata does not specify a selected range or a user-facing slicer mode. |

#### Interactions and Navigation

The page is bound as a drillthrough page by Calendar Year, with a required single value for the drillthrough parameter. Visual definitions enable filtering other visuals. The checked-in definition contains no documented buttons, bookmarks, or explicit page-navigation controls.

### KPI

**Screenshot unavailable:** rendering was not possible in this environment; see the capture limitation above.

The page titled “Northwind Retail Group - KPI” contains a single KPI table. It provides a compact comparison across time and product categories.

#### Main Metrics

- **Sales Amount**: sales-line quantity multiplied by net price.
- **Margin**: quantity multiplied by net price less unit cost.
- **Cost**: quantity multiplied by unit cost.

#### Analysis Breakdowns

- **Columns**: calendar Year.
- **Rows**: product Category.
- The report definition does not declare additional row/column drill levels or extra measures on this table.

#### Available Filters

| Scope | Filter or slicer | Behavior / default |
|---|---|---|
| Page | None declared | No page-level filters are present in the page definition. |
| Visual | None declared | No visual-level filter is present on the KPI table. |

#### Interactions and Navigation

The table is configured to filter other visuals, but the page has no other data visuals. No explicit buttons, bookmarks, or navigation controls are defined in the checked-in page metadata.

## Global Filters and Navigation

The report definition contains no report-level filters. The Sales page is the landing page and includes its own date slicer and page filters. The report uses the Fluent 2 base theme and a registered Copilot default theme. No report-level navigation buttons or bookmarks were found in the inspected definitions.
