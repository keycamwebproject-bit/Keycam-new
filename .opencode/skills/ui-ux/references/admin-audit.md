# Admin UI audit — KeyCam

Snapshot of the admin surfaces as they exist today. Update this file when a
redesign lands.

## Apps

| File | Tabs | Notes |
| --- | --- | --- |
| `admin-catalog.html` | Overview, Products, Inventory, Add Product, Resin | Main catalog admin. Links `shared/admin.css`; no inline `<style>` block. Redesigned 2026-11-18. |
| `deskmat/admin.html` | Overview, Editing, Add Products, Import Stock | Deskmat admin. Still on its own inline styles + `deskmat/styles.css`. Not migrated yet. |
| `shared/admin.css` | — | Single admin design system, live on `admin-catalog.html` only. Tokens, shell, topbar, KPI cards, forms, tables, badges, disclosures, uploads, modals, responsive and reduced-motion rules. |

## Shared behaviour to preserve

- Auth gate: `#loginView` → `#adminView` via `style.display` toggles, idle timer.
- Tab switching driven by `data-tab` on `.admin-tab-btn` and `#tab-*` panels.
  `#adminPageTitle` is kept in sync by `TAB_TITLES` inside `switchTab`.
- Orders: search, status filter, pending-orders block, pagination, invoice modal,
  thermal receipt, create-order modal.
- Triggers shared with `shared/admin-create-order.js`, `shared/invoice.js`,
  `shared/thermal-receipt.js`.
- Supabase client is global (`supabase-client.js`); all writes are direct table
  calls, so no UI change may reorder or rename the data attributes those calls
  read.
- Product row actions live in one "Manage ▾" popover per row (`toggleRowMenu`).
  The popover is `position:fixed` while open so the table's horizontal scroller
  cannot clip it; it flips up or clamps when near the viewport edge.
- Product rows become `is-dirty` on the first `input`/`change`, which is what
  lights up the row's Save button; saving clears the class.

## Current state (post-redesign)

Resolved:

1. ~~Two near-duplicate designs~~ — the catalog admin now uses `shared/admin.css`.
   Deskmat adoption remains.
2. ~~Conflicting `shared/admin.css` visual language~~ — it is now the only source
   of visual truth for the catalog admin.
3. ~~Overview starts with a long discount form~~ — KPIs first, then orders, and
   the festival discount sits in a `<details>` disclosure.
4. ~~Row action clutter~~ — eight inline buttons collapsed into Save + Manage.
5. ~~Mixed iconography~~ — text labels, no decorative glyph soup.
6. Mobile: sidebar becomes a top strip, side foot hidden ≤900px, Deskmat link
   moves to the topbar, "View store" hidden ≤700px.
7. Tables scroll inside their card between 701px and 1180px instead of forcing
   the page wide; products table is fixed-layout (`min-width:900px`).
8. Accessibility: Lighthouse 1.00 across accessibility / best practices / SEO.
   `scope="col"` on headers, `.sr-only` names for empty image/action columns,
   `aria-label` on every live table input, labelled login fields, `role="main"`.

Still open:

1. `deskmat/admin.html` has not adopted `shared/admin.css`; styles are still
   duplicated and will drift.
2. No skeleton state; lists still show "Loading…" text.
3. Dense inline styles remain in some legacy markup (older panels, pickers).
4. Tables below 700px rely on horizontal scroll; no sticky first column.
5. Product/order/inventory lists are unpaginated where datasets grow (products
   paginate; inventory and resin render every row).

## Suggested next steps

1. Migrate `deskmat/admin.html` onto `shared/admin.css`, keeping its IDs and
   `data-*` hooks, then delete the duplicated rules.
2. Add skeleton rows to Orders, Products, Inventory and Resin.
3. Optional: sticky first column for tables below 700px.
4. Optional: server-side pagination for inventory and resin designs.
