# iOS and iPadOS profile

Use for native iPhone/iPad work or when the user explicitly wants an iOS interaction model. Prefer SwiftUI/UIKit system components and current platform APIs over visual imitation.

## Navigation

- Use a navigation stack for hierarchical drill-down.
- Use a tab bar for a small number of peer top-level destinations; keep labels clear and destinations stable.
- On iPad, adapt broad navigation to a sidebar or split view when space permits.
- Preserve state as the interface moves between compact and regular widths.
- Put view actions in navigation or toolbar placements users expect; keep the primary action recognizable.

## Presentation

- Use a sheet for a focused subordinate task and choose detents based on content, not visual novelty.
- Use a popover for lightweight anchored content on iPad; allow the system to adapt it on iPhone.
- Use alerts for short important decisions, not forms or routine success.
- Avoid stacked sheets and alerts. Dismissal must not lose meaningful work without warning.

## Controls and content

- Use standard lists, forms, search, menus, pickers, toolbars, and swipe/context actions where their behavior fits.
- Keep destructive swipe or menu actions explicit and recoverable where possible.
- Use SF Symbols when permitted and available; match text style and provide OS-version fallbacks.
- Respect safe areas, keyboard avoidance, orientation, multitasking, and pointer/keyboard input on iPad.
- Use at least comfortable touch targets; never shrink interaction areas to match a screenshot.

## Type, color, and materials

- Use Dynamic Type text styles and test accessibility sizes.
- Use semantic system colors and assets with light/dark variants.
- Let standard components provide current platform materials. Custom blur should be rare and semantic.
- Keep important text and data off unpredictable translucent backgrounds.

## Accessibility

- Preserve VoiceOver reading order, names, values, traits, and rotor behavior.
- Support Reduce Motion, Increase Contrast, Bold Text, Button Shapes, and Reduce Transparency where relevant.
- Don't encode meaning only through haptics, color, or animation.
- Ensure custom gestures have visible, accessible alternatives.

## Web imitation boundary

If applying this profile to a web experience, borrow the compact hierarchy, touch sizing, sheet adaptation, and directness. Do not fake the iOS status bar, home indicator, native permission prompts, or system-owned controls.

## Official guidance

- [Apple HIG: Designing for iOS](https://developer.apple.com/design/human-interface-guidelines/designing-for-ios)
- [Apple HIG: Navigation and search](https://developer.apple.com/design/human-interface-guidelines/navigation-and-search)
- [Apple HIG: Modality](https://developer.apple.com/design/human-interface-guidelines/modality)
