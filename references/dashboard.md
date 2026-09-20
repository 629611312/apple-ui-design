# Data dashboards and admin surfaces

Use this reference with the dashboard or admin profile. Dashboards explain; admin surfaces enable action. A product may contain both, but each view should have one dominant purpose.

## Information architecture

Organize around decisions and workflows, not around available database tables.

1. Give each destination a clear domain name and one primary purpose.
2. Put overview, investigation, and object management at different levels rather than mixing all three in one screen.
3. Keep global scope—workspace, account, environment, date range—visibly distinct from local filters.
4. Preserve filters, sort, visible columns, density, and time range in the URL or saved view when sharing and returning matters.
5. Put definitions, freshness, timezone, and source near the data they qualify.

## Data density

Choose density from task frequency and input method:

- **Comfortable:** overview, mixed content, occasional use, touch-capable layouts.
- **Compact:** repeated scanning, comparison, pointer/keyboard use, operational work.
- **Dense:** only for expert workflows where more simultaneous rows measurably improves decisions.

Do not shrink type below readability to create density. Reduce padding, decorative containers, duplicated labels, and low-value columns first. If users have materially different needs, offer two density settings, not a continuous control.

## Metric cards

Use a metric card only for a decision-driving summary.

Include, as applicable:

- plain-language label;
- current value with unit;
- comparison period and direction;
- small context such as target, range, or freshness;
- link to the underlying detail.

Limit the first row to the few metrics that change action, usually three to six. Keep cards visually quiet and equal in hierarchy unless one metric truly dominates. Do not use decorative sparklines when they add no decision value.

## Charts

Start with the question:

- trend over time → line or area;
- comparison among categories → sorted bar;
- composition → stacked bar; use a pie only for a few distinct parts;
- distribution → histogram or box plot;
- relationship → scatter;
- exact lookup → table.

Chart rules:

- state the takeaway in the title or annotation when known;
- label axes, units, timezone, aggregation, and date range;
- prefer direct series labels over distant legends;
- begin quantitative axes at zero when bar length encodes value; explain justified exceptions;
- keep grid lines and framing quiet;
- expose exact values through focus/hover and an accessible table or summary;
- don't encode different metrics on dual axes unless the relationship is essential and unmistakable;
- preserve selected range and filters when navigating to detail;
- avoid 3D, gradients used as data ink, smoothed lines that imply false values, and animated counters.

## Filters

- Separate global filters from view-local filters.
- Show active filters and a clear reset path.
- Use chips only for short active-filter summaries, not as the only control for complex filtering.
- Apply simple local filters immediately. For expensive or multi-field queries, use an explicit Apply action and show unapplied changes.
- Support saved views only when users repeat complex filter/sort/column configurations.
- Make date presets explicit and show the resolved range; include timezone when relevant.
- When filters yield no results, keep them visible and offer to clear or adjust them.

## Tables

- Default columns should answer the main operational question. Hide secondary metadata in details or optional columns.
- Freeze only the identity column and headers needed to retain context.
- Use stable sorting and preserve it through refresh.
- Right-align numeric values; use tabular figures; format missing, zero, and not-applicable values differently.
- Keep row actions at a stable trailing position. Use overflow for rare actions.
- Make the selection model explicit and keep bulk actions adjacent to the selection count.
- For server-side data, expose loading, total/estimated count, pagination or virtualized position, and stale-data state honestly.
- Inline editing is appropriate for short, low-risk fields. Use a detail view or sheet for dependent, validated, or destructive changes.
- Keep export faithful to current scope and filters, and state whether it exports the page or full result set.

## Status and freshness

- Use calm neutral states for normal operation; reserve saturated color for attention.
- Distinguish warning, failure, paused, stale, and unknown. “No data” is not automatically healthy.
- Show last updated time and refresh behavior when decisions depend on freshness.
- Keep alert acknowledgement separate from resolution.
- For live data, avoid constant layout shifts and motion. Update in place and let users pause when needed.

## Responsive strategy

- Keep summary metrics and primary alerting visible first.
- Reflow filter bars into a dedicated sheet or panel on compact layouts while showing an active-filter count.
- Replace wide tables with a prioritized record summary plus detail view; don't hide essential fields without a path to them.
- Reduce simultaneously visible charts before shrinking them below legibility.
- Preserve comparison context when drilling into a single metric.

## Accessibility

- Give every chart a concise text summary and access to underlying values.
- Never rely on red/green alone; add symbols, labels, or line patterns.
- Make sortable headers, selected rows, expanded detail, and async updates available to assistive technology.
- Keep keyboard interaction conventional; don't build spreadsheet-like behavior unless the task actually requires it.
- Ensure tooltips are reachable by focus and don't contain the only copy of important information.
