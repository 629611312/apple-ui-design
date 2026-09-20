# Color

Use color semantically. The interface should keep its meaning when the appearance changes, contrast increases, or color perception differs.

## Token model

Name tokens by purpose, not hue:

- background: canvas, surface, elevated surface;
- foreground: primary, secondary, tertiary, inverse;
- structure: separator, opaque separator, fill, selected fill;
- interaction: accent, accent hover, focus ring, link;
- state: success, warning, danger, info;
- data: categorical series and sequential scale.

Components consume semantic tokens; they must not invent local grays or duplicate light/dark values.

## Web starting palette

This palette is Apple-inspired, not an exact system-color contract. Tune it to the product brand and verify contrast in context.

```css
:root {
  color-scheme: light dark;
  --canvas: #f5f5f7;
  --surface: #ffffff;
  --surface-elevated: #ffffff;
  --text-primary: #1d1d1f;
  --text-secondary: #6e6e73;
  --text-tertiary: #86868b;
  --separator: rgb(60 60 67 / 18%);
  --fill: rgb(120 120 128 / 12%);
  --fill-selected: rgb(0 113 227 / 12%);
  --accent: #0071e3;
  --focus-ring: #0071e3;
  --success: #248a3d;
  --warning: #a05a00;
  --danger: #d70015;
}

@media (prefers-color-scheme: dark) {
  :root {
    --canvas: #000000;
    --surface: #1c1c1e;
    --surface-elevated: #2c2c2e;
    --text-primary: #f5f5f7;
    --text-secondary: #aeaeb2;
    --text-tertiary: #8e8e93;
    --separator: rgb(84 84 88 / 65%);
    --fill: rgb(120 120 128 / 24%);
    --fill-selected: rgb(10 132 255 / 20%);
    --accent: #0a84ff;
    --focus-ring: #64d2ff;
    --success: #30d158;
    --warning: #ffd60a;
    --danger: #ff453a;
  }
}
```

If the product offers an explicit appearance setting, apply tokens through a `data-theme` or equivalent attribute and let “system” follow `prefers-color-scheme`.

## Light and dark appearances

- Dark mode is not a negative image. Rebuild surface elevation, contrast, shadows, images, and status colors for the dark context.
- In dark interfaces, a foreground overlay can be lighter than the base surface to convey elevation.
- Avoid pure white for large text blocks when a slightly softened foreground reduces glare without hurting contrast.
- Audit logos, charts, screenshots, illustrations, and empty-state art independently in each appearance.
- Do not use transparency as the only adaptation mechanism; content behind it is unpredictable.

## Accent and state

- Use one dominant interactive accent. Brand colors can coexist, but not every control should compete for attention.
- Keep destructive actions visually distinct and positionally deliberate. Do not make routine cancel actions look destructive.
- Never assign the same color to both an interaction and an unrelated status in the same region.
- Pair state color with an icon, label, pattern, or position. Localize semantic interpretation where red/green meaning differs.
- Disabled controls need reduced prominence but must remain identifiable; don't rely on extreme low contrast.

## Chart color

- Use position, direct labels, line styles, markers, or patterns before expanding the palette.
- Reserve success/warning/danger colors for those meanings; don't reuse them as arbitrary series colors.
- Keep the most important series strongest and comparison series quieter.
- Verify series against both the plot background and one another in light, dark, and color-vision simulations.
- Provide exact values outside color alone through labels, a table, or accessible descriptions.

## Contrast

- Check actual rendered combinations, including hover, selected, disabled, translucent, and chart states.
- For web text, meet WCAG AA at minimum; aim higher for small or critical content.
- Give focus indicators enough contrast against both the control and its surroundings.
- Under `forced-colors`, allow system colors and preserve borders/outlines needed to identify controls.

## Official guidance

- [Apple HIG: Color](https://developer.apple.com/design/human-interface-guidelines/color)
- [Apple HIG: Dark Mode](https://developer.apple.com/design/human-interface-guidelines/dark-mode)
- [Apple HIG: Accessibility](https://developer.apple.com/design/human-interface-guidelines/accessibility)
