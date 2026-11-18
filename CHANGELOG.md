# Changelog

## 2026-11-18 — Naruto series rebuilt from the exact reference sheets

The previous two-design attempt was rejected. The Naruto series is now built
from the user's exact references:

| Designs | Reference | Motif |
|---|---|---|
| `naruto-village-01` … `naruto-village-15` | Dreamstime "Collection of tattoo stickers … all naruto village symbols" | The **15 village emblems** traced from the high-res 5×3 sheet, each redrawn as a bold white mark with a black keyline so it reads on a dark keycap tile. |
| `naruto-akatsuki-cloud` | Pinterest red-cloud reference | The plain **Akatsuki red cloud** (Wikimedia Commons vector, black outline). |
| `naruto-akatsuki-crossed` | Shutterstock "Akatsuki symbol crossed ninja village logos" + attached image | Red cloud carrying crossed-out village emblems, matching the attached reference. |

The collection stays named **Anime** with internal ID `sharingan`. It now has
**57 designs** (40 dojutsu discs + 17 Naruto designs). The two rejected WebPs
and catalog entries are removed; the 40 eye designs are unchanged.

| File | Status | Notes |
|---|---|---|
| `resin/logos.js` | modified | Naruto series replaced with 15 village emblems + 2 Akatsuki designs (57 total). |
| `resin/logos/*.webp` | replaced | 17 new 256px transparent WebPs (~110 KB total); 2 rejected WebPs deleted. |
| `CHANGELOG.md` | modified | This entry. |

### Notes
- Final pass removed sticker-sheet rule lines from the traced masks and fixed
  alpha compositing so only the emblem shape is opaque.
- Full-colour artwork still needs a printed/UV transfer route, not the current
  single-colour white-ink resin process.

## 2026-11-18 — Naruto series rebuilt from the two reference images

The six original Naruto symbol emblems were rejected, so they are removed and
replaced by **two** designs built directly from the user's references:

| Design | Reference | Motif |
|---|---|---|
| `naruto-village` | Dreamstime "All naruto village symbols" tattoo sticker sheet | Authentic Konoha leaf-village spiral from Wikimedia Commons `Konohagakure.svg`, redrawn as a bold red mark with a black outline. |
| `naruto-akatsuki-slash` | Wallpaper Alchemy "Akatsuki Symbols Minimalist Dark" | Red Akatsuki cloud (`Akatsuki nuage.svg`) above a denim forehead protector whose engraved leaf plate is crossed out with a red slash. |

The collection stays named **Anime** with internal ID `sharingan`. It now has
**42 designs** (40 dojutsu discs + 2 Naruto symbols). The six rejected WebPs are
deleted and their catalog entries removed; names/IDs of all 40 eye designs are
unchanged.

| File | Status | Notes |
|---|---|---|
| `resin/logos.js` | modified | Naruto series reduced from 6 to 2 reference-based designs (42 total). |
| `resin/logos/*.webp` | replaced | 2 new 256px WebPs (17.9 KB total); 6 rejected WebPs deleted. |
| `CHANGELOG.md` | modified | This entry. |

### Notes
- Full-colour artwork still needs a printed/UV transfer route, not the current
  single-colour white-ink resin process.

## 2026-11-18 — Anime collection: Naruto symbol series (6 designs)

The single anime collection is now named **Anime** on the hub and collection
page. Its internal ID stays `sharingan`, so existing links, image URLs and
Supabase rows keep working — no migration needed.

First franchise series is **Naruto**: six signature symbols, drawn as original
bold vector emblems with black outlines and a limited full-colour palette. They
sit after the 40 dojutsu discs and are named with a `Naruto ·` prefix so the
series groups together in the dense grid.

| Design | Motif |
|---|---|
| `naruto-leaf` | Leaf Village spiral with leaf tip |
| `naruto-akatsuki` | Akatsuki cloud |
| `naruto-rasengan` | Blue spinning Rasengan |
| `naruto-kurama` | Nine-tailed fox face and tails |
| `naruto-headband` | Forehead protector with engraved leaf |
| `naruto-kunai` | Ninja kunai with red-wrapped handle |

| File | Status | Notes |
|---|---|---|
| `resin/logos.js` | modified | Collection renamed to Anime; 6 new dark-tile designs appended (46 total). |
| `resin/logos/*.webp` | new | 6 full-colour 256px WebPs, transparent, 1px border, q92 (37.8 KB total). |
| `CHANGELOG.md` | modified | This entry. |

### Notes
- Franchise series will be appended to this same collection (no extra hub
  cards). Next candidates: One Piece, Demon Slayer, Attack on Titan.
- Full-colour artwork still needs a printed/UV transfer route, not the current
  single-colour white-ink resin process.

## 2026-11-18 — Sharingan artwork rebuilt from Commons SVGs

Replaces the 40 full-colour almond-eye icons shipped earlier in the `sharingan`
collection (the entry below describes that superseded set). Every image is now a
**square, circular dojutsu disc** with a dark radial-gradient iris, black outlines
and black tomoe/blade paths, so it fills the keycap the way the reference does.
No white sclera remains anywhere in the set.

Artwork comes from the Wikimedia Commons `Category:Sharingan` SVG family — the
same style as `Mangekyou Sharingan Sasuke (Eternal).svg`: a 300×300 radial
gradient (`#660000` → `#c30000` → `#a00000`) inside a black stroke, with the
character-specific black pattern on top. Per-character files are used wherever
Commons has one (Indra, Madara + Eternal, Izuna, Itachi, Shisui, Kakashi, Sasuke
+ Eternal, Sarada, Shin, base 1/2/3-tomoe, Rinne-Sharingan, Kaguya). Characters
without a dedicated file use the base 3-tomoe or Kamui pattern. Only gradient
colours were changed: Sharingan stay red, Rinnegan are violet, and the black
linework is untouched. The 4-tomoe and violet Ripple/Rinnegan marks are built
from the same Commons tomoe and gradient geometry.

All 40 design IDs and names are unchanged, so `resin/logos.js`, the Supabase rows
and the image URLs stay the same. Only the WebP files were swapped.

| File | Status | Notes |
|---|---|---|
| `resin/logos/*.webp` | replaced | 40 circular discs, 256×256, transparent, 1px border, q92 (6.0–12.5 KB each, 350 KB total). |
| `resin/logos.js` | unchanged | Same 40 IDs, names, dark tiles and ordering. |
| `CHANGELOG.md` | modified | This entry. |

### Notes
- Verified locally and live: 40 designs, dense grid, no role chips, no QWER bar,
  red/violet pixels present, **zero white pixels** in all 40 assets.
- Still a production caveat: full-colour artwork needs a printed/UV transfer,
  not the current single-colour white-ink resin process.

## 2026-11-18 — Catalog admin redesign

`admin-catalog.html` now runs on one shared stylesheet instead of a page-level
`<style>` block. Same dark PCB/datasheet look, tightened: fixed sidebar plus a
sticky topbar whose title follows the active tab, KPIs before orders on
Overview, and the festival discount demoted into a disclosure card.

Products table rows dropped from ~120px to 53px: eight per-row buttons became
**Save** plus a single **Manage ▾** popover, and Save stays muted until the row
is edited. Row menus use fixed positioning so they escape the table scroller,
flipping up or clamping near the viewport edge. Tables scroll inside their card
between 701–1180px; below 700px the sidebar becomes a top strip.

Accessibility went from 0.85 to 1.00 (Lighthouse accessibility, best practices
and SEO all 1.00): column `scope`, screen-reader names for empty columns, labels
on every live table input, labelled login fields, a `main` landmark and a meta
description.

| File | Status | Notes |
|---|---|---|
| `shared/admin.css` | rewritten | Admin design system: tokens, shell, topbar, KPIs, forms, tables, badges, disclosures, uploads, modals, responsive and reduced-motion rules. |
| `admin-catalog.html` | modified | Links `shared/admin.css`, new shell markup, tab titles in `switchTab`, merged Manage menu, dirty-row state, a11y fixes. |
| `.opencode/skills/ui-ux/SKILL.md` | new | Reusable UI/UX workflow and repo constraints. |
| `.opencode/skills/ui-ux/references/admin-audit.md` | new | Admin inventory, preserved behaviour and remaining debt. |

### Notes
- All element IDs, `data-tab` values, JS hooks and Supabase calls are unchanged.
- `deskmat/admin.html` still uses its old inline styles; adopting the shared
  sheet there is the next step.

## 2026-11-18 — Sharingan & Rinnegan (40 designs)

First entry of the Anime group. New collection `sharingan` ("Sharingan &
Rinnegan") — 40 full-colour dojutsu marks, with the Sharingan family kept in
canonical red and the Rinnegan family in violet. It sits between Tech & dev marks
and Your own logo on the hub and uses the dense auto-fill grid, with no role
chips and no QWER set bar. Every tile is `dark` so the coloured irises stay vivid.

| Group | Marks |
|---|---|
| Base states (7) | 1-, 2-, 3- and 4-tomoe Sharingan, Mangekyo, Rinnegan, Rinne-Sharingan |
| Uchiha & early users (11) | Indra, Madara (+ Mangekyo, Eternal Mangekyo, Rinnegan), Izuna, Fugaku, Mikoto, Itachi (+ Mangekyo), Shisui (+ Mangekyo) |
| Obito & Kakashi (6) | Obito (+ Kamui, Rinnegan), Kakashi (+ Sharingan, Kamui, Rinnegan) |
| Sasuke (5) | Sasuke (+ Amaterasu, Mangekyo, Eternal Mangekyo, Rinnegan) |
| Later users (5) | Danzo (+ stolen Shisui eye), Sarada, Shin, Uchiha Clan |
| Rinnegan / Otsutsuki (6) | Hagoromo, Nagato / Pain, Kaguya, Momoshiki, Urashiki, plus the base Rinnegan above |

Artwork is original geometric vector work built in this repo (almond eye,
tomoe commas, Mangekyo blades/arms, Rinnegan ripple rings) — no official artwork
was traced or downloaded. Small identifiers such as Kakashi's headband, Obito's
scar and Danzo's extra eyes are part of the vector, not sourced images.

### Files
| File | Status | Notes |
|---|---|---|
| `resin/logos.js` | modified | New `sharingan` collection (40 designs, all `tile: "dark"`) after Tech & dev marks. |
| `resin/logos/*.webp` | new | 40 full-colour WebPs, transparent, trimmed, 1px safe border, 256px longest side, q92 (5.4–9.8 KB each, 259 KB total). |

### Notes
- **Production caveat:** these are the first non-white assets in the catalog.
  The current resin process prints one colour of ink; full-colour eyes need a
  printed/UV transfer or a different production route. Keep them marked as
  full-colour in the product description rather than promising white-ink resin.
- Kaguya, Momoshiki and Urashiki are included as Rinnegan-eyed Ōtsutsuki for
  coverage; their eye patterns are stylised interpretations, not frame-accurate.
- No `role` values, so `store.js` keeps the role filters and QWER builder off.

## 2026-11-17 — Motorsport & car badges (51 designs)

New collection `motorsport` ("Motorsport & car badges") — 51 one-colour racing
and car marques as white glyphs on dark tiles. It sits between Football clubs
and Tech & dev marks on the hub and uses the dense auto-fill grid (same as the
tech marks), with no role chips and no QWER set bar.

| Group | Marks |
|---|---|
| Formula 1 & motorsport (10) | Ferrari, McLaren, Red Bull, Aston Martin, Mercedes-Benz, Audi, Cadillac, Alpine, Haas F1, Formula 1 |
| Europe (18) | BMW, MINI, Porsche, Volkswagen, Lamborghini, Bugatti, Bentley, Rolls-Royce, Maserati, Fiat, Peugeot, Citroen, Renault, Skoda, Opel, Land Rover, Volvo, Polestar |
| America (5) | Tesla, Ford, Chevrolet, Jeep, Chrysler |
| Japan (8) | Toyota, Honda, Nissan, Infiniti, Lexus, Subaru, Mitsubishi, Suzuki |
| Rest of Asia (5) | Hyundai, Kia, MG, Proton, Acura |
| Motorcycles (4) | Ducati, KTM, Yamaha, Husqvarna |
| Motorsport kit (1) | Shell |

Sources: 45 marks from simple-icons (official 24x24 single-path SVGs, same
pipeline as the tech collection) plus 6 from Wikimedia Commons for the brands
simple-icons no longer carries — Mercedes-Benz, Lexus, Land Rover, Yamaha, Haas
and Alpine. The Mercedes star is pulled from the SVG's alpha channel (its
2022 artwork is a gradient, so a luminance threshold only produced the outline),
the Yamaha lockup is rendered from its embedded raster at 1:1, and the Alpine
lockup is cropped just above the tricolour bars.

Left out on purpose: Dacia and SEAT (solid square badges that read as white
blocks at keycap size), Mazda and Lucid (very heavy wordmarks), Mercedes-AMG
(a 9.5:1 wordmark that is illegible on a key), and Williams, Dodge, Aprilia,
Alfa Romeo, Jaguar, Kawasaki and BYD (no usable single-colour source).

### Files
| File | Status | Notes |
|---|---|---|
| `resin/logos.js` | modified | New `motorsport` collection (51 designs, all `tile: "dark"`) after Football, before Tech & dev marks. |
| `resin/logos/*.webp` | new | 51 assets: white on transparent, trimmed, 1px safe border, 256px longest side, WebP q92 (1.2–13.7 KB each, 282 KB total). |

### Notes
- Re-running **Import bundled logos** from `admin-catalog.html` adds the
  collection and its 51 rows to Supabase.
- Brand logos are trademarks of their owners; they are used here as product
  artwork, not as an endorsement.
- No `role` values, so `store.js` keeps the role filters and QWER builder off
  for this collection automatically.

## 2026-11-16 — Tech & dev marks (98 designs)

New collection `tech-marks` ("Tech & dev marks") — 98 one-colour developer
logos as white glyphs on dark tiles, built from the official simple-icons SVG
set (`cdn.simpleicons.org`). It sits between Football clubs and Your own logo on
the hub, and uses the normal dense auto-fill grid (9 across on a 1440px screen),
with no role chips and no QWER set bar.

Coverage, in display order:

| Group | Marks |
|---|---|
| Languages | JavaScript, TypeScript, Python, Rust, Go, PHP, Ruby, Java, Kotlin, Swift, C, C++, .NET, Dart, Elixir, Lua, Zig, Haskell, HTML5, CSS, Sass |
| Frameworks | React, Vue, Angular, Svelte, Next.js, Nuxt, Astro, Remix, Tailwind CSS, Bootstrap, Django, Flask, Laravel, Spring, Ruby on Rails, Express, Flutter, Electron, Three.js, Vite, webpack, npm, Yarn, pnpm, Deno, Bun, Node.js |
| Tools & infra | Git, GitHub, GitLab, Docker, Kubernetes, Terraform, NGINX, Vercel, Netlify, Cloudflare, Supabase, Firebase, MongoDB, PostgreSQL, MySQL, Redis, SQLite, Prisma, GraphQL, Linux, Ubuntu, Debian, Arch Linux, Fedora, Android, Apple |
| Editors & 3D | Vim, Neovim, JetBrains, Figma, Blender, Unity, Godot, Unreal Engine |
| AI | Anthropic, Claude, Hugging Face, Ollama, Gemini |
| Work & gear | Postman, Insomnia, Jira, Notion, Discord, Stack Overflow, GitHub Copilot, Raspberry Pi, Arduino, WordPress, Stripe |

Simple-icons no longer ships OpenAI, Slack, VS Code, C# or CSS3 (removed for
brand-policy reasons), so the closest official marks were used instead: **.NET**
for C#, **CSS** for CSS3, **OpenJDK** for Java, **Nuxt** (slug change) and
**Claude** alongside Anthropic. Everything else is the exact brand glyph.

### Files
| File | Status | Notes |
|---|---|---|
| `resin/logos.js` | modified | New `tech-marks` collection (98 designs, all `tile: "dark"`) after Football, before the custom card. |
| `resin/logos/*.webp` | new | 98 assets rendered from the white simple-icons SVGs at 1200 dpi, trimmed, 1px safe border, 256px longest side, WebP q92 (0.7–10.7 KB each, 421 KB total). |

### Notes
- Re-running **Import bundled logos** from `admin-catalog.html` adds the
  collection and its 98 rows to Supabase.
- simple-icons logos are trademarks of their owners and are published under
  each brand's usage terms; they are used here as product artwork, not as an
  endorsement.
- This collection has no `role` values, so `store.js` leaves the role filters
  and QWER builder off for it automatically.

## 2026-11-16 — QWER ability sets (pick 4, $10 a set)

Agent-ability collections can now be bought as a **4-key loadout** instead of
one key at a time. A "Build a QWER set" bar sits above the grid:

1. Press **Pick 4 abilities** — the grid switches to pick mode (steppers and the
   per-card R1–R4 shortcut step aside).
2. Tap any four abilities — each gets a numbered badge (1–4). Tapping a picked
   card removes it; a fifth tap is ignored.
3. Press **Add 4-key set · $10** — the four keys are staged on **Cherry R2**
   (the letter row that holds Q, W, E and R), then Add to order checks out.

The set is priced by the existing 4+ tier ($2.50 × 4 = $10), so the bar quotes
the same price the cart will charge. Pressing Add a second time never doubles a
key that is already on R2. `Cancel` and `Clear` both leave pick mode.

The bar only appears on collections that have agent roles (the 120 ability
icons); team-logo and football collections are unchanged.

### Files
| File | Status | Notes |
|---|---|---|
| `resin/collection.html` | modified | `#resinSetBar` / `#resinSetStart` / `#resinSetCancel` / `#resinSetCount` / `#resinSetAdd` markup above the toolbar. |
| `resin/resin.css` | modified | `.resin-setbar`, `.resin-pick-order` badge, `.is-selected` card state, `.is-set-mode` grid overrides, mobile bar layout. |
| `resin/resin.js` | modified | `SET_SIZE` / `SET_ROW` / `setMode` / `picks` state, `isAbilityCollection()`, `renderSetBar()`, `paintPick()`, `togglePick()`, `startSet()`, `cancelSet()`, `addQwerSet()`; grid click intercepts picks while in set mode; `clearAll()` resets the picker. |

## 2026-11-16 — Hush added to Valorant Agent Abilities (120 designs)

Hush — the 30th agent, a Duelist released 27 October 2026 — was not on the
uploaded ability sheet, so she was added separately. Her four active abilities
now sit between Harbor and Iso:

| id | Name | Slot |
|---|---|---|
| `hush-flashbulb` | Hush · Flashbulb | Q |
| `hush-displacement` | Hush · Displacement | E |
| `hush-flow` | Hush · Flow | C |
| `hush-suspension` | Hush · Suspension | X |

The passive (Telekinesis) is left out, matching the four-abilities-per-agent
rule used by every other kit in the collection.

Collection counts are now **All abilities 120 · Duelist 36 · Initiator 28 ·
Controller 28 · Sentinel 28**.

### Files
| File | Status | Notes |
|---|---|---|
| `resin/logos.js` | modified | Four `hush-*` designs inserted after Harbor (alphabetical), `tile: "dark"`, `role: "Duelist"`; blurb now 120. |
| `resin/logos/hush-*.webp` | new | Four icons built from the official valorant-api.com glyphs (white on transparent, 128px source), trimmed, 256px on the longest side, WebP q92 (17–28 KB each). |

### Notes
- The glyphs come from the same valorant-api.com icons the sheet was matched
  against, so the art is the official ability set; they are naturally a little
  lighter than the boldest older kits.
- Re-running **Import bundled logos** from `admin-catalog.html` adds the four
  rows to `resin_designs` without touching existing ones.

## 2026-11-16 — Valorant Agent Abilities (116 designs, filter by role)

Added the uploaded Valorant ability sheet as **one collection**, `valorant-abilities`
("Valorant Agent Abilities"). Every design is one agent ability, named
`"Agent · Ability"` with the id `<agent>-<ability>` (e.g. `jett-cloudburst`,
"Jett · Cloudburst") and a dark tile.

The collection page splits the icons by agent role with a chip row —
**All abilities 116 · Duelist 32 · Initiator 28 · Controller 28 · Sentinel 28** —
and the grid is **8 across** on desktop (4 on phones), so each desktop row is
two full agent kits and each phone row is one agent's four abilities.

> The icons first shipped as four separate role collections (`val-duelists`,
> `val-initiators`, `val-controllers`, `val-sentinels`). Those were replaced by
> this single collection; their old links redirect to it.

### Files
| File | Status | Notes |
|---|---|---|
| `resin/logos.js` | modified | One `valorant-abilities` collection after `valorant`; each design carries `role`, all use `tile: "dark"`. |
| `resin/logos/` | modified | 116 new WebP icons, 256px on the longest side, transparent, trimmed (2–15 KB each, 673 KB total). |
| `resin/logos/Valorant-agents-abilities.svg` | new | The upload the icons were cut from (kept as the source sheet). |
| `resin/collection.html` | modified | Role filter row (`#resinRoles` / `#resinRoleChips`). |
| `resin/resin.js` | modified | Role chips, role+search filtering, retired-id redirect, role in the count text. |
| `resin/resin.css` | modified | Ability collections use a fixed 8-across grid (4 at ≤560px); other collections keep the dense auto-fill grid. |
| `resin/store.js` | modified | DB rows have no `role` column, so the role label is copied from the bundled design with the same id. |

### Source and identification
- The upload is one A4 sprite sheet with 29 agent groups × 4 glyphs. Group ids
  are anonymous (`agent-01`…`agent-29`) and the icons are white (`fill="#fff"`),
  which is why every design uses a dark tile.
- Each glyph was matched against the official ability icons from
  valorant-api.com by comparing 64×64 alpha masks, scored as four-icon kits.
  All 29 agents matched (scores 0.938–0.999; the runner-up scored about 0.5)
  with no duplicate slots and no duplicate ids.
- Agents are alphabetical, Astra → Yoru. **Hush is not in the sheet**, so the
  collection covers 29 of the 30 playable agents.
- API names that ship in all caps (Yoru's four, Killjoy's Alarmbot and Turret)
  were title-cased for consistency; ids are unchanged.

### Tested in headless Chrome
- Bundled fallback (local): 116 designs, 8-column grid, 5 role chips with the
  right counts, each role filters to 32/28/28/28 with every agent still a 4-icon
  kit, "killjoy" inside Sentinel returns 4, 390px viewport is 4 across.
- Live site after deploy: same checks against the seeded DB, plus the football
  grid still uses the dense layout and the hub lists 6 collections.

### Notes
- The DB was migrated with **Import bundled logos** and the four role
  collections were deleted; `resin_designs` keeps the 116 ability rows and the
  manual `inter` crest (180 rows total). Re-running the import is still safe.
- Because `resin_designs` has no role column, a design added later through the
  admin (not in `logos.js`) appears under "All abilities" but not in a role
  filter until it is added to the bundled file.

## 2026-11-15 — Football collection: 11 more club crests

Expanded **Football clubs** from 8 to 20 crests using the global-following
ranking (CIES 2026) as the guide. The two clubs missing from the global top 10
were PSG (#4) and Juventus (#6); the rest of the additions are the next tier of
European heavyweights.

### Files
| File | Status | Notes |
|---|---|---|
| `resin/logos.js` | modified | `football` gains 11 designs and `blurb` becomes "20 club crests". |
| `resin/logos/` | modified | 11 new WebP logos, 256px on the longest side, transparent, trimmed (2–26 KB each). |

### Added clubs
Paris Saint-Germain, Juventus, AC Milan, Borussia Dortmund, Atlético Madrid,
Napoli, Ajax, Benfica, FC Porto, Tottenham Hotspur and Newcastle United — in that
order after Bayern Munich.

### Notes
- `tile` follows the same rule as the existing crests (light artwork sits on a
  `light` tile): Napoli and Ajax are the only two new `dark` tiles.
- **Inter Milan is deliberately not in `logos.js`.** The live DB already has a
  manual `inter` design with an uploaded logo, so adding a bundled `inter` would
  either duplicate the crest or null that row's `image_url` on the next import.
  The bundled file therefore lists 19 football designs while the live collection
  shows 20 (19 bundled + the manual `inter`).
- Crests came from the football-data.org crest CDN (200×200 PNG, transparent),
  trimmed and re-encoded with ImageMagick. Wikimedia was rate-limiting (HTTP
  429), so its larger SVGs were not used.
- Re-importing bundled logos from the admin is required before the 11 new
  crests appear on the storefront — the pages prefer the `resin_designs` table
  over `logos.js`.

Verified in headless Chrome against the bundled fallback at 1280px: the football
collection renders 19 tiles with 5 dark tiles, every `logos/<id>.webp` resolves,
and there is no empty state.

## 2026-11-15 — Resin data moves to Supabase (admin-editable prices, collections, designs)

The resin storefront now reads its prices, collections and designs from
Supabase, so the Resin tab in `admin-catalog.html` can change them without a
code deploy. If the tables are missing, empty, offline or slower than 2.5 s, the
pages fall back to the bundled `resin/logos.js` and render exactly as before.

### Files
| File | Status | Notes |
|---|---|---|
| `resin/resin-schema.sql` | new | Creates `resin_collections` + `resin_designs`, adds `store_settings.resin_prices`, and sets public-read / admin-write RLS + grants. Run once in Supabase. |
| `resin/store.js` | new | Loads the tables before render, merges prices over the bundled defaults, and falls back to `logos.js`. Exposes `window.ResinStore.ready()`. |
| `resin/index.html`, `resin/collection.html` | modified | Load `store.js` after `logos.js`; the header/footer still render immediately. |
| `resin/hub.js`, `resin/resin.js` | modified | Async init awaits `ResinStore.ready()`, then resolves the collection and renders. Logos use the DB `image_url` when present. |
| `shared/catalog-cart.js` | modified | `repairResinPricing()` reads the live table (or the price saved on each cart line) instead of only the hardcoded defaults; `ensureStoreSettings()` picks up `resin_prices` on every catalog page. |
| `admin-catalog.html` | modified | New **Resin** tab: prices, collection CRUD, design CRUD, 256px WebP logo upload, and **Import bundled logos** seeding. |

### Admin
- **Prices** — Cherry, SA and Cherry space bar read/write `store_settings.resin_prices` (same singleton row as the other settings). Tier count and 4+ price are editable; space bar stays a fixed price.
- **Collections** — add/edit/delete name, short name, region, group, blurb, sort order, active and the custom-only flag. Deleting a collection cascades to its designs.
- **Designs** — add/edit/delete with collection, tile, sort order, active and an optional logo upload. Uploads are resized to 256px WebP and stored in `keycam-images/resin/logos/`; without an upload the storefront keeps using `resin/logos/<id>.webp`.
- **Import bundled logos** — one click upserts the five collections and 52 designs from `resin/logos.js`, then writes the bundled prices. Existing IDs are overwritten, so it is also the way to reset.
- Before the schema exists the tab still opens, shows the bundled prices, and explains how to fix the missing tables.

### Notes
- The custom-logo collection is stored with `custom_only = true`; its builder keeps the "Your own logo" CTA and still has no designs.
- New designs without an uploaded logo automatically look for `resin/logos/<id>.webp`, matching the existing static files.
- No SQL INSERT list is kept in the repo — seeding reads the same `logos.js` the storefront ships with, so the 52-design list lives in one place.

Verified in headless Chrome at 1280px and 534px: all six resin pages still render from the fallback with 23/17/4/8-design cards, no broken images and no overflow; the Resin admin tab opens, renders the three price rows from the bundled file, and shows the "run `resin/resin-schema.sql`" message while the tables are absent.

The database path was exercised with a stubbed Supabase client: inactive collections and designs were filtered out, an inactive custom collection stayed hidden, DB prices overrode the defaults ($4.25, dropping to $3.75 at 5+), a missing `image_url` fell back to `resin/logos/<id>.webp`, and adding a design wrote a cart line at the DB price. The admin was tested against the same stub: price save payload, collection/design writes, and **Import bundled logos** produced 5 collections and 52 designs. The live database was seeded and verified separately (below).

### Live database
- Ran `resin/resin-schema.sql` once on the project: `resin_collections` and `resin_designs` exist with RLS enabled, and `store_settings.resin_prices` is a `jsonb` column. Seeded from `resin/logos.js` with 5 collections and 52 designs (23 MLBB Cambodia, 17 Valorant, 4 MLBB International, 8 football, custom), default prices $3 / $2.50 at 4+, $5 / $4 at 4+ and the $10 space bar.
- Storefront proof: all five collections render from the database at 1280px and 534px with no broken images. Changing `cherry.single` to `3.33` in SQL changed the hub price card to `$3.33`; restoring it to `3` brought back `$3`.
- Grants: `anon` has SELECT only on `resin_collections`, `resin_designs` and `store_settings`; `authenticated` keeps insert/update/delete on the resin tables and update on `store_settings`. RLS already blocked anon writes, but the unused privileges are revoked too, so an anon PATCH on `store_settings` now returns `401 permission denied` instead of a misleading `204`, and the prices stay unchanged.
- Cart repricing was checked on non-resin pages: a saved cart line keeps its price when the live table is unavailable, and the live table wins when it is present.
- **Signed-in admin path verified against the live project** through the actual page in headless Chrome: submitted the real login form, opened the Resin tab (5 collections, 52 bundled designs), changed Cherry single to `$3.77` with **Save prices** (row persisted, then restored to `$3`), and ran **Import bundled logos** ("Imported 5 collections and 52 designs ✓", prices preserved). The sign-out button returned the login screen, and the console stayed clean.
- A manually added football design (`inter`) with an uploaded logo is also live; the import upserts bundled IDs but does not delete extra rows, so that addition survived and renders correctly.

Cart pricing note: `repairResinPricing()` now prefers the live table, then the price stored on the cart lines, then the hardcoded defaults — so changing a price in the admin can't be silently reverted on pages that don't load the resin data. Re-importing bundled logos also preserves prices that have already been saved.

## 2026-11-15 — Resin collections: Valorant, MLBB International, football

Added three logo collections from the customer-supplied `team logo.ai` and the
esports/football artwork folders. The hub now has five collections: MLBB
Cambodia (23), Valorant (17), MLBB International (4), Football clubs (8) and
Your own logo. The hero collage mixes the first three.

### Files
| File | Status | Notes |
|---|---|---|
| `resin/logos.js` | modified | `valorant`, `mlbb-intl` and `football` collections; coming-soon trimmed to PUBG Mobile, Free Fire, Dota 2, CS2, League of Legends, RoV. |
| `resin/logos/` | modified | 29 new WebP logos, 256px, transparent, trimmed (306 KB total). |
| `resin/index.html` | modified | Hero collage now 2 MLBB + 2 Valorant + 2 football tiles. |
| `resin/resin.css` | modified | The "Your own logo" card spans both columns, so five cards end on a full-width CTA. |

### Collections
- **Valorant · VCT** — 17 designs: Sentinels, Paper Rex, T1, Cloud9, FUT
  Esports, RRQ, MIBR, Fnatic, LOUD, 100 Thieves, NRG, Leviatán, G2 Esports,
  Team Heretics, Team Liquid, Team Vitality and DRX.
- **Mobile Legends: Bang Bang · International** — 4 designs: Blacklist
  International, Red Giants, EGO and Omega Esports. Separate from the Cambodia
  collection, which keeps its original 23.
- **Football clubs · Europe** — 8 crests: Real Madrid, Barcelona, Manchester
  United, Manchester City, Liverpool, Arsenal, Chelsea and Bayern Munich.
- Every new design uses the same Cherry / SA / space-bar variants, rows and
  prices as the existing ones; nothing else in the builder changed.

### Source and exclusions
- Logos came from the 49 images embedded in `team logo.ai`, plus 17 colour
  Valorant PNGs in `Downloads\New folder (3)` and 5 football crest WebPs in its
  `New folder`.
- 13 logos in the `.ai` could not be identified, so they are **not** published
  (per the customer's instruction to skip them): sheet numbers 6, 10, 11, 12,
  13, 17, 18, 19, 21, 23, 24, 31 and 38.
- 7 identified logos duplicated existing Cambodia designs (Pro Esports, See You
  Soon, Galaxy, Flash, Vigor Apex, Rvz, Angkor Warriors) and were not re-added.
- `tile` (light/dark) is derived from ink luminance, calibrated on the original
  23 logos, then checked for contrast against the tile background. The G2 and
  Liverpool crests sit in the overlap and were set to dark by eye-of-data.

### Unconfirmed
- **Chelsea** is a best guess from `.ai` id 1000 (royal blue + gold + red, OCR
  "c*ELSE") — worth a quick look before launch.
- The `mlbb-intl` region label "International" is ours; the four teams are
  simply the non-Cambodian MLBB logos we could name.
- Valorant teams that were not in the supplied artwork (ZETA DIVISION, KRU,
  BBL, EDward Gaming, Xi Lai Gaming) are not in the collection.

Verified in headless Chrome at 1280px and 534px: 5 hub cards with the right
counts, `?c=valorant` 18 tiles, `?c=mlbb-intl` 5, `?c=football` 9, `?c=custom` 1
(builder adds the custom tile to every collection), no broken images and no
horizontal overflow. Functional pass: picking Sentinels, switching to R2,
**Set R1–R4**, then adding two more R3 keys produced 6 Cherry keys at $2.50
with per-row counts R1 ×1 · R2 ×1 · R3 ×3 · R4 ×1.

## 2026-11-13 — Resin collections, rows and Deskmat nav

Split the resin storefront into a collection hub and per-collection builders,
and made Cherry row a real variant. The 23 existing logos are now labelled as
the Mobile Legends: Bang Bang · Cambodia collection, with "Your own logo" as a
second collection and a coming-soon strip for future ones.

### Files
| File | Status | Notes |
|---|---|---|
| `resin/index.html` | rewritten | Hub: hero, collections, coming-soon strip, prices, profiles, how-it's-made, FAQ. Builder moved out. |
| `resin/collection.html` | **new** | Builder shell for `?c=<collection>` — breadcrumb, collection header, profile tabs, row chips, grid, summary. |
| `resin/hub.js` | **new** | Renders collection cards, coming-soon names and price cards; repairs stored resin prices. |
| `resin/resin.js` | rewritten | `?c=` routing, Cherry R1–R4 row state, row-aware cart lines, full-set shortcut, cross-profile summary. |
| `resin/resin.css` | modified | Collection cards, coming-soon strip, breadcrumb, row chips, row guide, set button, other-row badge, compact price bar, CTA. |
| `resin/logos.js` | modified | `RESIN_COLLECTIONS` (`mlbb`, `custom`), `RESIN_COMING_SOON`, price labels unchanged. |
| `deskmat/*.html` (6 public pages) | modified | Resin added to the desktop and mobile topbar so the nav is the same on every page. |
| `keyboard/index.html` | modified | Featured strip now says "Shop collections" and mentions rows. |

### Rows
- Cherry has **R1 · R2 · R3 · R4** chips above the grid. The active row gets the
  quantities; every design keeps a separate count per row.
- SA stays **R1 only**; the space bar has no row and hides the row bar.
- **Set R1–R4** in a card adds one key in each missing Cherry row. A design with
  all four rows already added shows a disabled "R1–R4 set".
- A `+N` badge on a card counts its keys in the other rows, so switching rows
  never hides what is already picked.
- Prices do not change per row: all Cherry rows count together for the 4+ tier.

### Cart
- One line per **design + row**, keyed `resin|profile|row|design`, e.g.
  `resin|cherry|R3|valhalla` / `Resin Keycap · Cherry R3` / `Valhalla`.
- The space bar uses `resin|space|none|navi`.
- `repairResinPricing()` is unchanged: it still groups by profile, so row lines
  re-price together when the order crosses 4.
- Saved phase-1 lines (`resin|profile|design`, no row) are migrated to `R1` on
  load, merged by the new key and re-priced, so an existing drawer does not
  break.

### Pages
- `resin/index.html` → hub. `resin/collection.html?c=mlbb` → the 23 logos.
  `resin/collection.html?c=custom` → only the "Your own logo" tile.
- An unknown `?c=` falls back to the first collection and rewrites the URL.
- The summary bar is static while empty and only sticks to the bottom once a
  key is picked; the per-group breakdown is hidden on phones to keep it short.
- Resin still skips `shared/catalog-client.js`, so the festival banner and
  discount do not appear.

Verified in headless Chrome at 1280px and 534px (headless minimum): hub cards,
`?c=mlbb`, `?c=custom`, row switching, set shortcut, 4+ tier crossing, SA and
space-bar lines, legacy cart migration, and no horizontal overflow. The deskmat
topbar keeps 5 links inside its width at 1280px and 1024px.

Known, pre-existing: `deskmat/app.js` calls an undefined `createThemeToggle()`,
which throws in the console on deskmat pages. It is unrelated to the resin work
and is left untouched for now.

## 2026-11-13 — Resin keycap storefront (phase 1)

New `/resin/index.html` page for custom resin keycaps: 23 ready logo designs
plus the customer's own logo, in Cherry (R1–R4 + space bar) and SA (R1 only).
Page only — the admin tab comes in phase 2, so prices and the design list are
still bundled with the page.

### Files
| File | Status | Notes |
|---|---|---|
| `resin/index.html` | **new** | Hero, price cards, profile drawings, logo builder, how-it's-made, FAQ. |
| `resin/resin.css` | **new** | Page styles; catalog palette + teal `#3ad1c0` / amber `#ffb02e` accents. |
| `resin/resin.js` | **new** | Profile tabs, search, per-design steppers, live tier total, add to order. |
| `resin/logos.js` | **new** | 23 designs with light/dark tile mapping + `window.RESIN_PRICES`. |
| `resin/logos/` | **new** | 23 WebP logos (391 KB total, down from 2.9 MB PNG). |
| `shared/catalog-cart.js` | modified | `repairResinPricing()` + call from `setCatalogOrder()`, resin note in the Telegram message. |
| `shared/layout.js` | modified | "Resin" in desktop nav, mobile menu and footer EXPLORE. |
| `shared/catalog.css` | modified | `.resin-feature` strip styles for the keyboard landing. |
| `keyboard/index.html` | modified | Resin featured strip below the six category tiles. |
| `admin-catalog.html`, `shared/invoice.js`, `shared/thermal-receipt.js`, `deskmat/*` | unchanged | Invoice/receipt already do unit price × qty. |

### Pricing
- Cherry R1–R4: **$3** each, **$2.50** each at 4+ keys.
- SA R1: **$5** each, **$4** each at 4+ keys.
- Cherry space bar: **$10** flat, logo optional.
- Tiers count **per profile** across the whole order (4 Cherry + 4 SA = $10 + $16).
- Resin is not part of the Pchum Ben festival discount, so the page skips
  `shared/catalog-client.js` and the festival banner stays hidden there.

### Cart
- One line per design, e.g. `Resin Keycap · Cherry R1–R4` / `Valhalla`, keyed
  `resin|profile|design`.
- `repairResinPricing()` re-prices every line of a profile whenever its total
  quantity crosses 4 (or drops back below), including edits made in the order
  drawer on other pages. It uses `window.RESIN_PRICES` when present and a
  matching fallback otherwise.
- Custom logos: same price, cart line reads `Custom logo — send file on
  Telegram`, and the Telegram order message asks the customer to attach the
  file (PNG, transparent, 1000px+).
- Orders still save to Supabase through the existing `orders` insert.

### Not in this phase
- Resin admin tab (upload logos, edit prices) — next pass.
- Customer logo uploads: the `keycam-images` bucket is admin-write only, so
  custom files stay on Telegram by design.

Verified in headless Chrome at 1280px and 390px: prices/tiers, tab switching,
search, add-to-order merging, drawer re-pricing in both directions, and no
horizontal overflow.

## 2026-11-12 — Thermal receipt printing for orders

Imported the standalone receipt maker (`invoice-maker (3).html`) into the KeyCam
admin and wired it to the `orders` table, so an order can be printed on a
Bluetooth / USB thermal printer without retyping anything.

### Files
| File | Status | Notes |
|---|---|---|
| `shared/thermal-receipt.js` | **new** | Receipt module (canvas → ESC/POS bitmap), printing, QR, font picker, prefs. |
| `admin-catalog.html` | modified | New script include, **Receipt** row button, **Print receipt** in the invoice modal, `openThermalReceipt()`, `closeInvoicePreview()`, `invoiceOrderId`. |
| `deskmat/admin.html` | modified | Same integration with `../shared/...` paths and QR `assets/ABA_QR.jpg`. |
| `shared/invoice.js` | unchanged | Source of `BUSINESS`, `_pricing()`, `invoiceNumberFor()` (created 2026-10-22). |

### What it does
- **Receipt button on every order row** (pending and all orders) in both admin pages.
- **Print receipt** button inside the existing Invoice Preview modal — closes the PDF preview and opens the receipt for the same order.
- Draws the receipt as a **bitmap, 1 canvas px = 1 printer dot**, so Khmer / Chinese
  product names print correctly on any ESC/POS printer (no printer font needed).
- **Print paths:** Bluetooth (Web Bluetooth), USB cable (WebUSB), System print,
  Save PNG. Bluetooth / USB need Chrome on Android or desktop over HTTPS.
- **Paper:** 58 mm (384 dots, default) and 80 mm (576 dots).
- **ABA KHQR:** uses `deskmat/ABA_QR.jpg` / `assets/ABA_QR.jpg` with
  “Scan to pay (ABA)”; falls back to an offline-generated Telegram QR if missing.
- **Logo upload** (stored as a downscaled PNG), footer message, print darkness,
  slow-Bluetooth mode.

### Pricing (must stay identical to the PDF invoice)
All math is delegated to `window.KeycamInvoice._pricing(order, item)` and
`invoiceNumberFor(order)`, so the receipt matches `shared/invoice.js`:
- line rate / qty / line discount / amount,
- subtotal, item discount, order discount (with % when percent),
- delivery fee,
- stored `orders.total` as the authoritative total (un-itemised differences are
  shown as “Other discount” / “Adjustment”),
- paid and balance.
- Legacy maintenance-mode discount is handled by `invoice.js` as before.
- Invoice number format: `INV-YYYYMMDD-XXXXXX`.

### Persistence (`localStorage`, per browser)
- `keycam_receipt_prefs_v1` → `{ conn, paper, dark, slow, note, font }`
- `keycam_receipt_logo_v1` → logo data URL
- Defaults: Bluetooth, 58 mm, darkness 165, note “Thank you!”, font `system`.

### Font picker (added same day, after first version)
Modal → **Style → Receipt font**:
| Key | Label |
|---|---|
| `system` | System (default) |
| `kantumruy` | Kantumruy Pro — Khmer + English (recommended) |
| `roboto` | Roboto Condensed — narrow, fits more |
| `inter` | Inter — clean and modern |
| `mono` | JetBrains Mono — receipt style |

- Google fonts are loaded on demand (`ensureFont`), with a 6 s timeout so an
  offline phone falls back to the system font instead of blocking.
- The modal opens immediately and redraws when the font is ready; switching
  font shows “Loading font…” and redraws after load.
- Because printing is a bitmap, only the phone/computer needs the font.

### API
```js
window.KeycamReceipt.open(order, { qrPath: 'deskmat/ABA_QR.jpg', qrCaption: 'Scan to pay (ABA)' });
window.KeycamReceipt.close();
window.KeycamReceipt.buildModel(order);   // { business, invoiceNo, date, customer, phone, lines, rows, total, paid, balance }
window.KeycamReceipt.renderCanvas();      // canvas for the current order
window.KeycamReceipt._qrMatrix(text);     // offline QR encoder (byte mode, EC M, v1–10)
window.KeycamReceipt._raster(canvas);     // ESC/POS GS v 0 bytes
```

### QR encoder fix
The imported offline encoder was patched: format-info modules are reserved before
data placement and the format bits + mask are applied per candidate mask, then the
lowest-penalty mask is chosen. Verified with `jsQR` (decodes exactly).

### Tested
- Receipt opens from order rows and from the invoice modal on both pages.
- Real orders reproduce invoice totals (Josua maintenance discount, 4-item Heng order).
- 384 / 576 widths; ESC/POS band headers (GS v 0), init `ESC @`, feed `ESC d 4` valid.
- All five fonts load, change the bitmap, and persist across reload.
- No console errors on either admin page.

### Known limitation (not fixed, deliberately skipped)
- **WebUSB on Windows** often fails with “Could not take control of the USB
  printer…” because the printer is bound to the Windows driver (`usbprint.sys`)
  rather than WinUSB; Chrome cannot claim the interface. Bluetooth works and is
  the chosen path. Options if USB is needed later: use System print, or replace
  the printer driver with WinUSB via Zadig (dedicates the device to the web app),
  or use Android Chrome + USB‑C OTG.

### To deploy
Upload to Netlify:
1. `shared/thermal-receipt.js` (new)
2. `admin-catalog.html`
3. `deskmat/admin.html`

The live site stays on the old code until these are uploaded.
