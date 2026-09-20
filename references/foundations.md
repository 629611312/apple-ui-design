# Foundations

Use this reference to decide what the interface should communicate before styling it.

## Design priorities

Apply these in order:

1. **Purpose:** Optimize the view for the user's main job, not for a visual motif.
2. **Content:** Let real content establish size, rhythm, and emphasis. Remove chrome that competes with it.
3. **Hierarchy:** Make location, current state, primary information, and primary action apparent at a glance.
4. **Coherence:** Match the target platform, product vocabulary, and existing interaction patterns.
5. **Agency:** Keep state changes understandable, reversible where practical, and under user control.
6. **Feedback:** Acknowledge input promptly and expose progress, results, and errors near their cause.
7. **Restraint:** Add decoration only when it clarifies grouping, depth, state, or brand.

Apple-inspired means adopting these decision habits. It does not mean copying an Apple screen, logo, product name, trade dress, or every current visual effect.

## Establish the content model

Before arranging components, write down:

- the view's one-sentence purpose;
- the primary object or dataset;
- the top one or two user actions;
- the hierarchy of destinations;
- what is persistent, contextual, transient, or destructive;
- what changes with permissions, device width, or data state.

If a visual element cannot be tied to one of these needs, remove it.

## Layering model

Use a small number of meaningful layers:

- **Base:** page or window background.
- **Content:** lists, tables, forms, media, and reading surfaces.
- **Navigation:** sidebar, tab bar, toolbar, or top navigation.
- **Elevated:** popovers, menus, sheets, dialogs, and transient controls.

Do not turn every group into a floating card. First try whitespace, alignment, a section heading, or a subtle separator. Elevate only interactive or independently movable content.

## Interaction principles

- Make the whole visible control target interactive; don't hide essential actions behind hover.
- Keep a stable location for frequent actions. Put rare commands in overflow menus.
- Use progressive disclosure for advanced options, not for information people need to make the current decision.
- Preserve context when opening details. On roomy layouts, consider split views; on compact layouts, navigate to a focused detail view.
- Favor direct manipulation when it is discoverable and reversible. Also provide a keyboard or explicit-control alternative.
- Confirm destructive actions when the consequence is difficult to reverse. Prefer undo for lightweight reversible actions.

## Accessibility baseline

- Use semantic structure and native controls first; add ARIA only where native semantics are insufficient.
- Keep a logical reading and tab order. Focus must be visible against every surface and restored after closing a transient layer.
- Use text or shape in addition to color for status and chart distinctions.
- Test contrast in light, dark, selected, disabled, and translucent states. Treat WCAG AA as a floor for web content.
- Support text resizing without clipping or overlapping. Avoid light font weights for small text.
- Aim for 44 x 44 CSS px touch targets on touch-first web layouts; compact pointer-first controls still need adequate spacing and an accessible hit area.
- Respect `prefers-reduced-motion`, `prefers-contrast`, and `forced-colors` where supported.
- Announce asynchronous results and validation errors without unexpectedly moving focus.

## Anti-pattern gate

Reject or revise a design when it relies on:

- a purple/blue gradient, star field, glow, or floating orb merely to signal “AI”;
- glass on every surface, stacked transparency, blurred body text, or contrast that changes with wallpaper;
- a card for every heading, row, filter, and metric;
- oversized corner radii on nested elements, or pill shapes for ordinary rectangular controls;
- a crowded Bootstrap-admin composition with boxed widgets, heavy borders, tiny type, and toolbars full of equal-weight buttons;
- huge marketing headings inside operational software;
- icon-only controls with ambiguous meaning and no accessible label;
- hidden navigation or critical actions that appear only on hover;
- hard-coded light colors, grayscale inversion for dark mode, or color as the sole status signal;
- motion that delays work, loops without purpose, or ignores reduced-motion settings;
- fake macOS traffic lights, fake device frames, or Apple logos used as generic decoration.

## Review questions

- Can a first-time user identify where they are and what to do next in five seconds?
- Does removing a shadow, border, card, blur, or animation make the meaning worse? If not, remove it.
- Does every prominent color encode brand, action, selection, status, or data? If not, neutralize it.
- Is the design still coherent with transparency disabled, motion reduced, text enlarged, and data empty?
- Is the interface recognizably the user's product rather than a replica of an Apple product?

## Official guidance

- [Apple HIG: Design principles](https://developer.apple.com/design/human-interface-guidelines/design-principles)
- [Apple HIG: Accessibility](https://developer.apple.com/design/human-interface-guidelines/accessibility)
- [Apple HIG: Foundations](https://developer.apple.com/design/human-interface-guidelines/foundations)
