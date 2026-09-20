# macOS profile

Use for native Mac work or when the user explicitly wants a desktop application informed by macOS. Prefer AppKit/SwiftUI system behavior over drawing a replica.

## Window and information architecture

- Treat the window as a resizable work surface. Define useful minimum size and graceful behavior at large sizes.
- Use a sidebar for persistent sources or destinations and a split view for list/detail workflows.
- Use the toolbar for frequent view-level actions, search, view controls, and primary creation; move rare commands to menus.
- Use the menu bar and standard commands for app-wide actions. Keep command names, shortcuts, and enabled state consistent with visible controls.
- Preserve selection, scroll, column configuration, and window state when appropriate.

## Desktop interaction

- Design for pointer precision and keyboard efficiency without making targets cryptic or tiny.
- Provide conventional shortcuts for frequent commands and expose them in menus.
- Use hover for discovery, not as the only route to essential actions.
- Support multi-selection, contextual menus, drag and drop, and inline rename only when the domain benefits.
- Keep right-click commands available through menus or visible controls too.

## Density

- Use compact, aligned lists and tables for repeated work; keep reading and forms more spacious.
- Let the content area expand instead of centering a narrow mobile column in a large window.
- Use an inspector for properties that need persistent contextual editing; use a popover for a brief anchored choice.
- Keep toolbar and sidebar visually quieter than the active content.

## Presentation

- Use a window-modal sheet for a focused action tied to one window.
- Use an alert for a short consequential decision.
- Use a popover for lightweight anchored content and a menu for commands.
- Avoid modal presentation for browsing, help, or ordinary confirmation.

## Type, color, materials, and symbols

- Use system text styles, semantic colors, control sizes, and standard materials.
- Materials may separate sidebar, toolbar, and overlays; dense content should remain stable and legible.
- Use SF Symbols where available and semantically appropriate; check OS support and licensing.
- Test light, dark, increased contrast, reduced transparency, accent-color changes, and full keyboard access.

## Web adaptation boundary

For a macOS-inspired web app, borrow the persistent sidebar, compact toolbar, strong selection, keyboard support, split views, and restrained materials. Do not draw fake traffic-light window controls, Finder clones, system menus, or permission dialogs.

## Official guidance

- [Apple HIG: Designing for macOS](https://developer.apple.com/design/human-interface-guidelines/designing-for-macos)
- [Apple HIG: Sidebars](https://developer.apple.com/design/human-interface-guidelines/sidebars)
- [Apple HIG: Toolbars](https://developer.apple.com/design/human-interface-guidelines/toolbars)
