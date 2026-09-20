# Materials, vibrancy, and depth

Materials communicate layering and preserve context. They are not a theme to apply everywhere.

## Choose by meaning

Use the least decorative treatment that explains the layer:

- **Opaque surface:** reading, forms, tables, charts, and long-lived content.
- **Subtle fill or separator:** grouping within a surface.
- **Standard translucent material:** sidebar, toolbar, navigation, or overlay where seeing the underlying context helps orientation.
- **Clearer glass-like material:** rare floating controls over imagery or media, only when legibility remains stable.

Current Apple platforms include Liquid Glass, but Apple-inspired web work should translate its purpose—not mimic every refraction, highlight, and animation. A still, readable approximation is usually enough.

## Web implementation

Use transparency as progressive enhancement with an opaque fallback:

```css
.material {
  background: color-mix(in srgb, var(--surface) 88%, transparent);
  border: 1px solid var(--separator);
}

@supports (backdrop-filter: blur(1px)) {
  .material {
    backdrop-filter: saturate(140%) blur(18px);
  }
}

@media (prefers-reduced-transparency: reduce) {
  .material {
    background: var(--surface);
    backdrop-filter: none;
  }
}
```

`prefers-reduced-transparency` is not universal. Also provide an application setting or a solid fallback whenever translucency is prominent.

## Vibrancy

Treat vibrancy as foreground contrast behavior on a material, not as glow.

- Use semantic foreground colors whose contrast is tested against the material.
- Keep body text and dense data on stable opaque or strongly controlled backgrounds.
- Do not derive foreground color from a sampled background at runtime unless the product already has a robust contrast system.
- Test materials over the brightest, darkest, and busiest allowed content.

## Borders, shadows, and radii

- Prefer a subtle separator for adjacent surfaces and a restrained shadow for floating layers; don't use both heavily.
- Use elevation consistently: a menu, popover, and dialog may rise; a table row normally does not.
- Keep radius proportional to component size. Nested radii should step down rather than repeat one oversized value.
- Pills are for tags, compact filters, segmented choices, and intrinsically capsule-like controls—not every button or field.

## Performance and robustness

- Limit live blur to a few bounded regions. Large fixed blur layers can be costly during scrolling.
- Avoid animating `backdrop-filter`, large shadows, or full-screen blur. Animate opacity and transform where possible.
- Don't place multiple translucent layers over one another.
- Preserve legibility when the browser disables blur, printing removes backgrounds, or high-contrast mode overrides colors.

## Anti-patterns

- frosted cards covering the entire page;
- glass nested inside glass;
- colored edge glow or chromatic blur presented as “premium”;
- low-contrast gray text on translucent surfaces;
- wallpaper chosen only to make blur visible;
- 24–32 px radii on every nested component;
- shadows used to replace clear grouping and alignment.

## Official guidance

- [Apple HIG: Materials](https://developer.apple.com/design/human-interface-guidelines/materials)
- [Apple HIG: Dark Mode](https://developer.apple.com/design/human-interface-guidelines/dark-mode)
