# Layout

Use layout to express hierarchy and adaptability before adding borders, shadows, or materials.

## Compose from regions

Most product interfaces need only a few stable regions:

- navigation;
- contextual toolbar or title area;
- primary content;
- optional inspector or detail area;
- transient overlays.

Keep the reading or work surface dominant. Navigation should occupy only the space needed to preserve orientation.

## Spacing and alignment

- Use a 4-point base with an 8-point working rhythm. Common steps: `4, 8, 12, 16, 24, 32, 48, 64`.
- Choose a compact subset for the product and map it to semantic tokens such as `--space-control`, `--space-section`, and `--space-page`.
- Align headings, controls, table columns, and content edges. One strong alignment line is worth more than several containers.
- Use whitespace to separate major sections; use separators when adjacency or scrolling makes whitespace ambiguous.
- Avoid nesting padded containers. A child should normally inherit the parent's alignment grid.

These are starting points, not fixed Apple measurements. Adjust for content, platform, input method, and the existing system.

## Width and measure

- Reading content: target roughly 45–75 characters per line.
- Forms: keep labels and fields close enough to scan; don't stretch short inputs across a wide page.
- Data tables and media can use the full work area.
- Marketing and general web pages may use a centered max-width shell; application shells should use available space with stable navigation and sensible gutters.
- Use `clamp()` for page padding and display type where it removes abrupt breakpoint jumps.

## Adaptive behavior

Choose breakpoints where the content stops working, not from named device presets.

- **Wide:** persistent sidebar, optional inspector, full toolbar labels, multi-column content where relationships benefit.
- **Medium:** narrower or collapsible sidebar, fewer simultaneous panes, compact toolbar, wrapping filter row.
- **Compact:** one primary column, destination navigation adapted to a drawer or tab bar, detail views pushed onto the navigation stack, full-width sheets where appropriate.

Never solve a narrow layout by scaling the desktop UI down. Recompose it.

## Sidebar and split view

- Use a sidebar for several peer destinations, sources, or collections that benefit from persistent visibility.
- Group items sparingly and use disclosure only for real hierarchy.
- Keep labels visible by default; icons support recognition but don't replace unfamiliar names.
- Allow collapse or hide when content benefits, and remember the user's choice when the product supports preferences.
- For deep information hierarchies, use sidebar → list → detail on wide layouts and a navigation stack on compact layouts.

## Toolbar and title area

- Put view-level actions near the view title or content they affect.
- Keep the primary action distinct; place infrequent commands in an overflow menu.
- Don't duplicate global navigation in the toolbar.
- Maintain stable positions for refresh, create, search, view options, and overflow actions.
- Collapse labels only when the icon remains unambiguous and has an accessible name.

## Responsive details

- Respect safe-area insets on installed web apps and native mobile interfaces.
- Don't place essential controls under fixed browser or OS chrome.
- Preserve scroll position and selection when panes collapse or reopen.
- Keep overlays within the viewport and anchor them to their trigger where possible.
- Let tables scroll horizontally only after prioritizing columns, offering column controls, or switching to a list summary on compact screens.
- Avoid layout shifts when loading. Reserve space for media, charts, and known asynchronous regions.

## CSS direction

Prefer modern native layout:

```css
.page {
  width: min(100% - 2 * clamp(16px, 3vw, 40px), 1440px);
  margin-inline: auto;
}

.cluster {
  display: flex;
  flex-wrap: wrap;
  gap: var(--space-control, 12px);
  align-items: center;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 18rem), 1fr));
  gap: var(--space-section, 24px);
}
```

Use container queries when a component's own width, rather than viewport width, determines its composition.

## Official guidance

- [Apple HIG: Layout](https://developer.apple.com/design/human-interface-guidelines/layout)
- [Apple HIG: Sidebars](https://developer.apple.com/design/human-interface-guidelines/sidebars)
- [Apple HIG: Toolbars](https://developer.apple.com/design/human-interface-guidelines/toolbars)
