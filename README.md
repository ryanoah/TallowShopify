# Tallow Basics — starter Shopify theme

A minimal Shopify theme (Online Store 2.0 / Liquid) for a handmade tallow balm
shop. It's built to plug straight into Shopify once the store/subscription is
set up — nothing here needs to be rewritten, just connected and filled in.

## What's included

- **Home page** (`templates/index.json`) — hero banner + "Our Story" section
  for background/bio content.
- **Shop page** (`templates/collection.json`) — automatically lists every
  product in a Shopify collection, with image, title, short description,
  price, and an Add to cart / Choose options button.
- **Product page** (`templates/product.json`) — full product detail with
  image gallery, variant picker (e.g. sizes/scents), quantity, and buy button.
- **Cart page** (`templates/cart.json`) — line items, quantity updates, and
  checkout button (checkout itself is handled entirely by Shopify).
- Header with logo + nav + cart icon, footer with socials/contact.
- `config/settings_schema.json` — lets you change colors, fonts, and the
  favicon from the Theme Customizer without touching code.

Nothing here is a mockup — once connected to a real Shopify store, the shop
and product pages pull live data (products, prices, inventory) straight from
Shopify admin.

## Where to upload pictures

All images are added through the Shopify **Theme Customizer** (no code
required) or the **product admin**. Until a photo is uploaded, each spot
shows a dashed placeholder so it's obvious what's missing:

| Image | Where to upload it |
|---|---|
| Logo | Customizer → Header section → Logo image |
| Hero photo (top of home page) | Customizer → Home page → Hero banner → Hero image |
| Story/bio photo | Customizer → Home page → Our Story → Photo |
| Favicon | Customizer → Theme settings → Logo & Favicon |
| Product photos | Shopify admin → Products → (each product) → Media |

## Getting it into Shopify

Once the store exists:

**Option A — zip upload (no install needed)**
1. Zip the contents of this folder (the zip should contain `layout/`,
   `sections/`, `templates/`, etc. at the top level — not a nested folder).
2. In Shopify admin: **Online Store → Themes → Add theme → Upload zip file**.
3. Publish it, or preview it first from the theme's "..." menu.

**Option B — Shopify CLI (better for ongoing edits)**
1. Install the CLI: `npm install -g @shopify/cli @shopify/theme`
2. From this folder: `shopify theme dev --store your-store.myshopify.com`
   (live-reloads locally against the real store — needs a store/dev store
   to connect to, doesn't require the paid subscription to be finalized if
   using a Shopify Partners development store).
3. When ready: `shopify theme push` to upload it as a theme in the store.

## Setting up products & the Shop page

1. Shopify admin → **Products → Add product** for each item (title,
   description, price, photos, variants like size/scent if any).
2. Shopify admin → **Products → Collections → Create collection** (e.g.
   "All Products"), add the products to it.
3. Point the "Shop" nav link (Online Store → Navigation → main menu) at that
   collection's URL — the products page will then show them automatically.

## Adding her story

Edit directly in the Theme Customizer (Home page → Our Story) — the body
text field currently holds a placeholder paragraph marked
`[Replace this with her story...]`. No code editing needed for text changes.

## Notes / next steps

- This is intentionally minimal: one home page, one shop page, one product
  page, one cart. Extra sections (testimonials, ingredient breakdowns, an
  FAQ, etc.) are easy to add later as new theme sections once the content
  exists.
- Mobile checkout, taxes, shipping rates, and payment methods are all
  configured in Shopify admin, not in this theme.
- Theme not yet tested inside an actual Shopify store (Liquid can't render
  outside Shopify) — do a first pass through Customizer once connected to
  confirm everything looks right before publishing live.
