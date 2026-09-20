# Typography

Typography carries most of the hierarchy. Use size, weight, spacing, and color deliberately; avoid decorative font changes.

## Font strategy

- Native Apple platforms: use the system text styles so Dynamic Type, localization, and platform metrics work automatically.
- Web: prefer the system stack unless the product already has a licensed brand typeface.
- Chinese web content: keep platform fallbacks rather than forcing one operating system's font everywhere.

```css
font-family: ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont,
  "SF Pro Text", "SF Pro Display", "PingFang SC", "Microsoft YaHei",
  "Segoe UI", sans-serif;
```

Do not bundle SF Pro files without the appropriate license. A system font stack can use an installed system face without redistributing it.

## Roles, not arbitrary sizes

Define a short semantic scale:

- **Display:** rare, expressive page or marketing statement.
- **Title:** page/window identity.
- **Section heading:** groups related content.
- **Body:** default reading and task text.
- **Callout:** emphasized value or short supporting statement.
- **Label:** control, metadata, column, or navigation label.
- **Caption:** secondary annotation that remains readable.
- **Data:** numeric values, often with tabular figures.

A practical web starting point:

```css
:root {
  --text-title: clamp(2rem, 1.5rem + 2vw, 3.5rem);
  --text-h1: clamp(1.75rem, 1.5rem + 1vw, 2.5rem);
  --text-h2: 1.375rem;
  --text-body: 1rem;
  --text-label: 0.875rem;
  --text-caption: 0.75rem;
}
```

Dashboard and admin profiles usually use the lower end of this scale; operational titles should not consume working space.

## Hierarchy

- Use no more than three obvious emphasis levels in one region.
- Prefer Regular, Medium, Semibold, or Bold. Avoid very light weights, especially below body size.
- Use color to reinforce hierarchy after size and weight, not instead of them.
- Tighten display headings slightly; keep body line-height generous, generally around 1.45–1.65 on the web.
- Keep labels close to their controls. Helper and error text belong immediately below the relevant field.
- Use sentence case unless the product language requires another convention. Avoid all caps for ordinary navigation and controls.

## Data and numbers

- Use `font-variant-numeric: tabular-nums` for aligned metrics, financial values, timers, and changing counters.
- Align comparable numeric table cells consistently, usually to the end edge.
- Keep unit, currency, sign, and time-zone meaning explicit.
- Don't abbreviate precision that changes the decision. Use compact notation only where users can inspect the exact value.

## Adaptation and localization

- Let text wrap. Reserve truncation for repeated rows where a detail view or tooltip exposes the full value.
- Test long German-like labels, Chinese strings, right-to-left direction, large text, and mixed numbers/symbols.
- Avoid fixed-height text containers.
- Keep icon and text baselines optically aligned; don't compensate with per-icon magic numbers unless verified.

## Official guidance

- [Apple HIG: Typography](https://developer.apple.com/design/human-interface-guidelines/typography)
- [Apple HIG: Writing](https://developer.apple.com/design/human-interface-guidelines/writing)
