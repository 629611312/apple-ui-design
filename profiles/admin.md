# Admin profile

Use for configuration, moderation, inventory, account management, support, permissions, and other operational workflows. Also read [../references/dashboard.md](../references/dashboard.md).

## Primary objective

Optimize for repeated accurate work. Apple-inspired restraint should reduce noise, not reduce information or hide operational controls.

## Information architecture

- Organize destinations by workflow and domain, not technical service boundaries.
- Keep frequent destinations visible in a sidebar; group rare system/configuration areas separately.
- Use list → detail and list → edit flows consistently.
- Put record identity, status, ownership, and risky actions in stable locations.
- Separate reporting/overview from transactional work when each would otherwise compete.

## Density

- Default to compact for pointer-and-keyboard workflows while maintaining readable type and hit areas.
- Reduce vertical padding before shrinking text.
- Offer comfortable density only when users plausibly need it; avoid arbitrary three- or four-level density systems.
- Keep forms comfortable even when tables are compact.

## Tables and bulk work

- Tables are the default for comparable records; don't replace them with cards.
- Lead with identity and decision-driving columns. Move secondary metadata to detail or optional columns.
- Keep row selection, focus, hover, and status visually distinct.
- Reveal bulk actions only after selection, next to the selected count, without shifting the table unexpectedly.
- Make pagination, total count, scope, and export semantics explicit.
- Support saved views only for recurring complex setups.

## Filters and search

- Search handles identity or free text; structured filters handle status, owner, date, type, and other bounded fields.
- Keep active filter summaries visible and removable.
- Preserve filter, sort, page, and selected view in navigable state where practical.
- Use an Apply button for expensive compound filters; otherwise update immediately.

## Forms and editing

- Use focused pages or sheets for multi-field edits; popovers are for short contextual choices.
- Group fields by user decision, not database schema.
- Keep primary save action stable and expose unsaved changes before navigation.
- Preserve input on validation and server errors.
- Use inline editing only for low-risk independent fields with immediate validation and clear commit/cancel behavior.
- Explain disabled permissions and inherited values.

## Destructive and privileged actions

- Visually separate destructive actions from routine actions and keep them out of accidental paths.
- State the exact target and consequence in confirmations.
- Prefer undo or soft deletion when the system already supports it.
- Require reauthentication or stronger confirmation only when the product's risk model calls for it.
- Show partial failure clearly for bulk operations; never imply all items succeeded when they did not.

## Metrics and charts

- Use summary metrics only when they help prioritize operational work.
- Place actionable queues and exceptions before broad vanity metrics.
- Charts should lead to the filtered records behind them when possible.
- Keep statuses, freshness, and time ranges explicit.

## Avoid

- giant titles and low-density landing-page spacing;
- boxed widgets around every filter and field;
- a permanent toolbar of equal-weight buttons;
- icon-only destructive actions;
- hidden bulk-action scope;
- color-only status badges;
- multi-step modals stacked over the record list.
