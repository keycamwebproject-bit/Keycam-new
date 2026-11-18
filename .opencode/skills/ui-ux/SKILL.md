---
name: UI UX
description: Design or redesign screens, layouts, and components for the KeyCam storefront and admin apps. Use for visual polish, dashboard layout, spacing/typography, responsive behavior, accessibility, and UX flow reviews.
---

## Scope

KeyCam is static HTML + plain CSS + vanilla JS, deployed on Netlify, with
Supabase as the backend. No build step and no framework. Every screen must keep
existing element IDs, `data-` hooks, and JS event wiring intact unless the
matching script is updated in the same change.

## Design tokens (from `deskmat/styles.css`)

```
--bg:#090d10   --line:#29343a   --blue:#20c3df   --blue2:#8deeff
admin surfaces  #111a1e (surface)  #172226 (surface-2)  #1c2a2f (surface-3)
admin ink       #edf4f5 (ink)  #89a0a7 (dim)  #5c7178 (faint)
status          --amber:#e0b23c  --green:#3bd1a0  --red:#e05a5a
fonts           DM Sans (UI)  Space Grotesk (display)  JetBrains Mono (numbers)
```

Rules:
- Cyan `--blue` is the single accent. Never add a second brand hue.
- Monospace is reserved for figures the operator scans: prices, stock, totals,
  order counts. Not for prose, labels, or buttons.
- Dark theme only for admin today; keep contrast at or above 4.5:1 for body text
  and 3:1 for large text and UI borders.
- Reuse tokens; do not hardcode new hex values when an existing token fits.

## Process

1. **Read before styling.** Inspect the page's inline `<style>`, the shared
   stylesheets it imports (`deskmat/styles.css`, `shared/admin.css`), and the JS
   that toggles visibility (`display:none` on panels, `style.display`).
2. **Map the screen**: list panels/tabs, primary task per panel, primary action,
   and secondary actions. One primary action per view.
3. **Fix hierarchy first.** Page title, section heading, label, value. Size steps
   should be obvious; if everything is 13px, nothing leads.
4. **Then spacing.** Use a 4px scale (4/8/12/16/24/32/48). Group related fields;
   separate sections with more space than the space inside them.
5. **Then components.** Buttons, inputs, tables, badges, empty states, toasts.
6. **Then responsive.** Check 1440, 1024, 768, 390. Tables may scroll, but never
   the page as a whole horizontally.
7. **Finally verify.** Click every tab, submit a form, check the empty state, and
   confirm derived numbers (totals, counts) still update.

## Component conventions

- Buttons: primary = cyan fill with dark ink; secondary = transparent with
  `--line` border; destructive = red text, red border on hover. Never a red fill
  for a routine action.
- Inputs: visible label above the field, 40px min height, focus ring
  `0 0 0 3px rgba(32,195,223,.14)`. Placeholder is not a label.
- Tables: uppercase mono micro-headers, 11-13px cells, row hover, numeric columns
  right-aligned in mono, sticky header on long lists, and a pagination control
  that shows the current range ("1–20 of 176").
- Status: use text plus color, never color alone. `pending` amber, `confirmed`
  green, `shipped` blue, `cancelled` red.
- Empty state: say what is missing and the next action, not just "No data".
- Destructive confirmations: name the object being deleted.
- Loading: skeleton or "Loading…" text inside the container that will fill, so
  layout does not jump.

## UX checks before finishing

- Every clickable thing looks clickable, and has a hover + focus state.
- Keyboard: tab order follows visual order; Escape closes modals; focus returns
  to the trigger.
- Forms: inline validation next to the field, error text names the fix, success
  feedback appears where the action happened.
- Numbers: prices show 2 decimals and a currency symbol; never rely on the user
  reading a raw float.
- Mobile: primary action reachable with one thumb; no hover-only affordances.
- Nothing important is hidden behind `title` only.

## Hard constraints for this repo

- Do not rename IDs, classes used by JS, or `data-tab` values.
- Do not add a framework, build tool, or CSS preprocessor.
- Do not introduce external JS libraries for layout or styling.
- Keep pages self-contained: inline `<style>` is acceptable here, but shared
  patterns belong in `shared/` and must be linked by all admin pages that use
  them, or removed.
- Preserve Supabase calls, auth flow, and Telegram/order logic exactly.

See `references/admin-audit.md` for the current admin page inventory and known
UI debt.
