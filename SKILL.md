---
name: apple-ui-design
description: Design or refine Apple-inspired web, dashboard, admin, iOS, iPadOS, and macOS interfaces using content-first hierarchy, semantic styling, adaptive layouts, restrained materials, accessible interaction states, and platform-appropriate navigation. Use for UI creation, implementation, review, or redesign; do not use to imitate Apple branding or unrelated visual styles.
---

# Apple UI Design

Create calm, legible, content-first interfaces that borrow Apple platform design logic without copying Apple products or reducing the style to rounded cards and blur.

## Start with the real product

1. Inspect the existing stack, information architecture, user tasks, components, and constraints before changing visuals.
2. Preserve business logic, data contracts, routes, and established product identity unless the user explicitly asks to change them.
3. Reuse the codebase's components and tokens before adding new ones. Prefer semantic HTML, native controls, CSS, and existing dependencies.
4. Identify the primary task, the content that supports it, and the single strongest action on each view. Let those determine hierarchy.

## Choose one profile

Read the closest profile before designing:

- General product or marketing site: [profiles/web.md](profiles/web.md)
- Analytics or monitoring product: [profiles/dashboard.md](profiles/dashboard.md)
- Operational back office: [profiles/admin.md](profiles/admin.md)
- Native iPhone or iPad product, or an explicitly requested iOS adaptation: [profiles/ios.md](profiles/ios.md)
- Native Mac product, or an explicitly requested macOS adaptation: [profiles/macos.md](profiles/macos.md)

For a web app with data, `dashboard` or `admin` takes precedence over `web`. Use `ios` or `macos` only when the target platform or requested interaction model warrants it; don't add fake operating-system chrome to ordinary websites.

## Load only the guidance the task needs

- Always read [references/foundations.md](references/foundations.md) for design priorities and anti-patterns.
- Read [references/layout.md](references/layout.md), [references/typography.md](references/typography.md), and [references/color.md](references/color.md) when establishing or changing the visual system.
- Read [references/components.md](references/components.md) when selecting navigation, controls, search, tables, lists, forms, or overlays.
- Read [references/materials.md](references/materials.md) before using translucency, vibrancy, blur, elevation, or glass effects.
- Read [references/motion.md](references/motion.md) for animated transitions or interactive feedback.
- Read [references/dashboard.md](references/dashboard.md) for metrics, charts, filters, tables, and dense data views.

## Make the design

- Build hierarchy with placement, type, spacing, and disclosure before decoration.
- Use semantic tokens for text, fills, surfaces, separators, accents, status, focus, and chart series. Define both light and dark appearances; don't mechanically invert colors.
- Choose navigation by information architecture: tabs for a few peer destinations, a sidebar for broad persistent hierarchy, a toolbar for contextual actions, and breadcrumbs only when they clarify location.
- Keep content surfaces mostly opaque. Reserve material effects for navigation, toolbars, floating controls, and transient layers where background context matters.
- Choose overlays by task: menu for compact commands, popover for lightweight contextual choices, sheet for a focused subordinate flow, dialog for a brief decision that truly blocks progress.
- Provide hover, focus-visible, pressed, selected, disabled, loading, empty, error, and success behavior wherever each state can occur.
- Keep keyboard access, visible focus, readable contrast, scalable text, touch target size, reduced motion, and screen-reader meaning intact.
- Treat SF Symbols as a native-platform resource with license and availability constraints. On the web, use an already-approved icon set or simple custom icons unless the product is entitled to use SF Symbols there. Never use a symbol as a logo.

## Check before finishing

Verify the implemented result, not just the source:

- Primary content and action are obvious without decorative explanation.
- Light and dark modes both preserve hierarchy and contrast.
- Narrow, medium, and wide layouts reflow without clipped controls or hidden actions.
- Keyboard order, focus, labels, errors, and reduced-motion behavior work.
- Tables, charts, filters, forms, and overlays cover empty, loading, error, and long-content cases.
- Blur is optional enhancement with an opaque fallback; no important content depends on transparency.
- The result has no purple AI gradient, gratuitous glow, card grid for every section, excessive pill shapes, ornamental glass, or generic Bootstrap-admin density.

When Apple-inspired aesthetics conflict with usability, accessibility, the product's brand, or the target platform's conventions, keep the latter and use Apple influence only in hierarchy, restraint, and interaction quality.

## v0.1 scope

The first public release is intentionally strongest for Web App, Dashboard, and Admin Panel work. The iOS and macOS profiles are guidance for native projects or deliberate platform adaptations; they are not permission to fake operating-system chrome in a normal website.

When evolving this skill, prefer a small rule that changes an agent's decision over a longer style manifesto. Add a rule only when it prevents a demonstrated failure, and keep platform-specific detail in the relevant reference or profile.
