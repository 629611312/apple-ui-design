# Components and interaction patterns

Select components by information structure and task cost, not by visual novelty.

## Navigation

| Need | Prefer | Avoid |
| --- | --- | --- |
| A few peer destinations | Tab bar or compact top navigation | Deep nested menus |
| Many persistent sections or sources | Sidebar | Icon-only rail with unfamiliar symbols |
| Parent → collection → detail | Split view on wide screens; navigation stack on compact screens | Showing all panes at unusable widths |
| Actions for the current view | Toolbar | Mixing global navigation and object actions |
| Location in a deep web hierarchy | Breadcrumbs | Breadcrumbs for a flat app |

Keep destination navigation distinct from filters and object actions.

## Search

- Use a search field when users know or can infer what to query. Use filters for bounded attributes.
- Scope search clearly when it doesn't cover the whole product.
- Show recent or suggested queries only when they are genuinely useful.
- Keep the query while filters, sorting, or detail views change unless the user clears it.
- Provide clear, submit, and cancel behavior appropriate to platform and input method.
- Announce result counts and no-result states. Don't interpret no results as an error.
- Use debouncing only for network or expensive queries; immediate local filtering needs no artificial delay.

## Lists, tables, and cards

- **List:** items are primarily identified and opened; columns are not needed for comparison.
- **Table:** users compare repeated fields, scan numeric values, sort, select, or perform batch work.
- **Card:** an item is self-contained, heterogeneous, visual, or independently actionable.

Do not convert a dense table to dozens of cards just to appear modern. On compact screens, show a prioritized list summary and open the full record separately.

For tables:

- keep headers visible for long vertical scans;
- align numbers and dates consistently;
- make sorting direction explicit;
- keep row selection distinct from hover and keyboard focus;
- place batch actions near the selection count;
- allow column resizing, pinning, or visibility only when users genuinely need it;
- preserve accessible header-cell associations and expose sort state.

## Forms

- Use visible labels; placeholders are examples, not labels.
- Group related fields and keep optional/required meaning consistent.
- Choose native input types and browser capabilities before custom widgets.
- Validate format as the user works when helpful, but don't show errors before a meaningful attempt.
- Put actionable error text next to the field and summarize multiple submission errors at the top.
- Preserve entered data after validation or server errors.
- Use a form sheet or focused page for substantial creation/editing; don't squeeze long forms into popovers.

## Buttons and controls

- One region normally has one visually primary button.
- Use text labels for unfamiliar or consequential actions. Icon-only buttons need a tooltip and accessible name.
- Use segmented controls for a small set of mutually exclusive views, not for multi-select filters.
- Use switches for immediate persistent on/off settings; use checkboxes for selections that are submitted together.
- Disable only when the reason is evident. Often it is clearer to allow submission and explain what is missing.

## Menus, popovers, sheets, and dialogs

- **Menu:** compact list of commands or single-step choices. No long explanations or complex forms.
- **Popover:** lightweight contextual content anchored to a trigger; dismissing it should be low cost.
- **Sheet:** focused subordinate task that retains the parent context, such as editing or creating an item.
- **Dialog:** short decision or alert requiring attention before work can continue. Use sparingly.

On compact layouts, a popover may adapt to a sheet. Preserve the same task and state across the adaptation.

Transient-layer requirements:

- move focus into the layer and restore it to the trigger on close;
- support Escape where conventional and safe;
- trap focus only for modal content;
- prevent background activation under modal content;
- keep destructive confirmation explicit;
- avoid stacking modal layers.

## State model

Specify applicable states for every interactive component:

- default;
- hover for pointer discovery;
- focus-visible for keyboard orientation;
- pressed/active for immediate feedback;
- selected/current for persistent state;
- disabled and its reason;
- loading/progress;
- validation error and success where appropriate.

Hover, focus, and selection are different concepts and should not share one indistinguishable style. Do not remove the browser outline unless replacing it with a stronger focus indicator.

## SF Symbols and icons

- Prefer SF Symbols in native Apple-platform apps when a symbol matches the concept and the deployment target supports it.
- Match symbol weight and scale to adjacent text. Prefer familiar semantics over decorative consistency.
- Check symbol availability by OS version and provide a fallback where needed.
- Respect rendering modes and localization; directional symbols may need right-to-left adaptation.
- Do not use SF Symbols in logos or trademark-like marks. Confirm Apple's license before shipping symbols outside their permitted context.
- On the web, use an existing approved icon library or a tiny coherent custom SVG set; do not mix unrelated icon families.

## Feedback and data states

- Use skeletons only when they resemble the final stable layout. Otherwise use a compact progress indicator.
- Empty states explain what is absent and offer the next useful action, if any.
- Error states retain context and provide retry or recovery.
- Toasts are for nonblocking confirmation; important errors belong near the affected content.
- Success should not interrupt the next task with a modal.

## Official guidance

- [Apple HIG: Navigation and search](https://developer.apple.com/design/human-interface-guidelines/navigation-and-search)
- [Apple HIG: Search fields](https://developer.apple.com/design/human-interface-guidelines/search-fields)
- [Apple HIG: Sidebars](https://developer.apple.com/design/human-interface-guidelines/sidebars)
- [Apple HIG: Toolbars](https://developer.apple.com/design/human-interface-guidelines/toolbars)
- [Apple HIG: Modality](https://developer.apple.com/design/human-interface-guidelines/modality)
- [Apple HIG: SF Symbols](https://developer.apple.com/design/human-interface-guidelines/sf-symbols)
