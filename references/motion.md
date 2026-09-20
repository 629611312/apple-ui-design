# Motion

Motion should explain change, preserve spatial context, or provide feedback. If it only advertises polish, remove it.

## Purposes

Use motion to:

- connect a trigger to a menu, popover, sheet, or detail view;
- show insertion, removal, reordering, or progress;
- clarify navigation direction or hierarchy;
- confirm direct manipulation and selection;
- soften an unavoidable layout change without delaying work.

Do not animate routine data refreshes, every card on page load, or continuous decorative backgrounds.

## Timing and easing

Practical web starting ranges:

- state feedback: 100–160 ms;
- small control or popover transition: 160–240 ms;
- page, sheet, or larger spatial transition: 240–400 ms.

Use decelerating motion for elements entering or responding, and accelerating motion for elements leaving. Avoid spring overshoot on destructive, precise, or frequently repeated actions.

```css
:root {
  --motion-fast: 140ms;
  --motion-standard: 220ms;
  --motion-slow: 360ms;
  --ease-out: cubic-bezier(.2, .8, .2, 1);
}

.popover {
  transition: opacity var(--motion-fast) ease-out,
              transform var(--motion-fast) var(--ease-out);
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    scroll-behavior: auto !important;
    animation-duration: 1ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 1ms !important;
  }
}
```

Keep reduced-motion behavior functional rather than removing status feedback. Replace spatial travel with a near-instant opacity change where feedback still matters.

## Interaction feedback

- Hover can adjust fill or tint subtly; it must not move layout.
- Pressed state should feel immediate and remain visible while activation is held.
- Selection persists after activation and must differ from hover.
- Loading indicators should appear only when latency is perceptible. Preserve layout and show determinate progress when available.
- Charts should animate only when the transition helps compare old and new values; initial flourishes are usually noise.
- Don't animate number counters when users need to read exact values quickly.

## Technical limits

- Prefer `transform` and `opacity` for smooth animation.
- Avoid large animated blur, shadow, filter, and layout properties.
- Make interruption safe: rapid repeated input must not queue long animations or leave stale state.
- Pause nonessential motion when offscreen or when the document is hidden.
- Never delay keyboard focus until an animation ends.

## Verification

Test with reduced motion, keyboard-only input, rapid repeated activation, slow devices, and content that changes size during transition.

## Official guidance

- [Apple HIG: Motion](https://developer.apple.com/design/human-interface-guidelines/motion)
- [Apple HIG: Accessibility](https://developer.apple.com/design/human-interface-guidelines/accessibility)
