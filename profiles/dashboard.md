# Dashboard profile

Use for analytics, usage, monitoring, finance, health, performance, or reporting products where understanding data is the main job. Also read [../references/dashboard.md](../references/dashboard.md).

## Primary objective

Help users answer, in order:

1. What is happening?
2. Is it expected?
3. Why is it happening?
4. What should I inspect or do next?

Every metric, chart, comparison, and filter should support one of these questions.

## Information architecture

- Use Overview for decision-driving summaries, not a dumping ground for every widget.
- Group deeper views by user mental model: usage, cost, reliability, users, resources, or another real domain.
- Keep account/workspace/environment and date range as stable global context.
- Let summary items drill into filtered detail while preserving scope.
- Place definitions, data freshness, aggregation, and timezone near affected values.

## Density and shell

- Default to comfortable or compact desktop density, not oversized marketing spacing.
- Use a persistent sidebar when there are enough destinations to justify it; allow collapse when charts or tables need width.
- Keep a quiet title/toolbar row with range, refresh, export, and primary view actions.
- Use a restrained metric strip followed by the most important trend or breakdown, then supporting detail.
- Reserve cards for summary metrics and independently scoped visualizations. Tables and related charts can share a plain section surface.

## Metrics

- Show three to six top metrics, each with value, unit, comparison basis, and direction.
- Differentiate beneficial and harmful changes semantically; “up” is not inherently good.
- Avoid rolling-number animation and oversized numerals that crowd out context.
- Show exact values where decisions depend on precision; compact formatting may be secondary.

## Charts and tables

- Use chart forms from [../references/dashboard.md](../references/dashboard.md); default to direct labels and a muted grid.
- Highlight one primary series, dim comparisons, and reserve state colors for state.
- Keep tables available for exact inspection and accessible values.
- Allow sorting and column choices only where they support analysis. Keep row actions visually quiet.
- Use split detail or a pushed detail view for records; avoid stacked modals.

## Filters

- Keep date range and domain scope separate from local chart/table filters.
- Show active filters, result impact, and one reset path.
- On compact layouts, move filters into a sheet and keep the active count visible.
- Preserve filter state when moving between overview and detail.

## States

- Loading preserves the eventual layout.
- Empty state distinguishes “no activity,” “not configured,” and “filters exclude all data.”
- Errors state which region failed and allow targeted retry.
- Stale or partial data is labeled; don't silently present it as current.

## Avoid

- a mosaic of equal-weight cards;
- bright gradients under metrics;
- chart rainbow palettes;
- three-dimensional or ornamental charts;
- hiding definitions exclusively in tooltips;
- combining monitoring alerts and administrative CRUD into one visual hierarchy.
