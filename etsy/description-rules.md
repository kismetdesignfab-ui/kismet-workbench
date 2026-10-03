# Listing description rules

House style for listing descriptions. Every rewrite follows these.

## Source of truth
- Sizes, kerf and file types come only from the listing's own photos: the round mockup, the
  Illustrator size panel, and the folder screenshot. Treat them like the SKU; they never change.
- The folder screenshot is the best source for files. List what it shows, nothing more.
  Common set: `DXF and DWG (2004 + 2018), SVG (outline + filled), PNG, JPG`.
  Some folders add R14 versions, a nested sheet of all pieces, or fillable AI/EPS/PDF templates.
  Some have no DWG or no PNG/JPG. Write what's there.
- Describe only what the photos show. Never infer a design from a filename (e.g. "H2" was a
  redone H, not a second H). If something can't be read from the photos, leave it out and flag it.
- Count pieces from the folder (Note 1–7 means seven) when the old text disagrees.

## Voice
- Never describe the photos ("The photos show…", "The first photo is…"). Buyers can see them.
  Describe the design itself.
- First person, "I / me". Plain, factual, fabricator to fabricator.
- No sales talk: no "perfect for", "sells well", "makes a great gift", lists of who it's for,
  "beautifully", "cuts cleanly".
- No lectures about machine setup, kerf, lead-ins or checking details at size.
- No requests like "please don't". State terms as specs.

## Layout (Shopify HTML)
1. One or two sentences on what's in the design.
2. Spec block, one per line with `<br>`:
   Size (or one line per piece) · Kerf · Files ·
   `License: commercial use of finished pieces allowed; no sharing or resale of files` ·
   `Instant download. Nothing ships.`
3. `Also in:` links to bundles that contain it (Shopify only).
   Bundles not on Etsy get `Only on cutreadydxf.com. Bundles and sets aren't sold on Etsy.` after
   the intro, and a "cutreadydxf.com exclusive" pill on the preview graphic.
4. `More: Halloween designs` collection link on Halloween items with no bundle (Shopify only).
5. `One free personalization per file when the design has room for it. Message me after you order.`
6. `SKU 0000`

## Etsy
- `etsy/descriptions.json` uses the workbench Load batch shape: `sku`, `title`, `description`, `flags`.
- Plain text: `<br>` → newline, paragraphs → blank line, links → their text.
- Drop Shopify-only collection links and the "Also in" bundle line. Bundles are only sold on
  cutreadydxf.com, and Etsy doesn't allow pointing buyers to another store.
- Start with one line built from the Files line, for Etsy and Google search (both weight the first
  160 characters): `DXF, DWG and SVG cut file for CNC plasma and laser.` Use "cut files" for sets,
  packs and bundles. Fonts: `OTF and TTF font plus DXF and SVG cut files for CNC plasma and laser.`
- Never mention cutreadydxf.com or any other website in Etsy text.

## Process
- Batches of 5. Write → push to Shopify → read back and verify → append to the Etsy JSON → commit.
  A batch is finished before the next one starts.
