# Power BI Artifact Catalog

## Overview

This Power BI project supports Northwind Retail Group sales analysis. Its semantic model brings together sales line items, products, customers, stores, and calendar attributes, and its report presents a sales overview and a KPI breakdown. The report is bound to the model in the same PBIP project.

## Artifacts

| Artifact | Type | Source | Connected artifact(s) | Purpose | Documentation |
|---|---|---|---|---|---|
| Beispielprojekt_sales | Semantic model | `Beispielprojekt_sales.SemanticModel/` | Beispielprojekt_sales report | Provides imported sales, product, customer, store, and calendar data with sales and KPI measures. | [Open](beispielprojekt_sales.semantic-model.md) |
| Beispielprojekt_sales | Report | `Beispielprojekt_sales.Report/` | Beispielprojekt_sales semantic model | Presents sales analysis and a year/category KPI table. | [Open](beispielprojekt_sales.report.md) |

The PBIP entry point is [`Beispielprojekt_sales.pbip`](../Beispielprojekt_sales.pbip). Report-to-model binding is declared in the report definition.
