# Reference Prototype v2 — Brand Librarian (public)

This directory contains a **reference implementation** of the Brand Librarian
frontstage interaction model. It is published so the public can inspect the
architecture, the synthetic-metadata contract, and the accessibility/keyboard
contract without any private brand-library data.

## What this prototype is

- A 6-folder grid that demonstrates: folder cover, hover image reveal, click
  into a side detail drawer, keyboard navigation, focus management, modal
  semantics, and the synthetic-metadata labelling rule.
- A reusable layout pattern. The look and feel approximate a fashion-archive
  reference; the data is wholly invented.
- Self-contained: HTML + CSS + a small script, plus six inline SVG
  placeholders. No build step, no server, no external API call beyond a
  Google Fonts stylesheet (optional — the page still reads with system fonts
  if the request is blocked).

## What this prototype is **not**

- It is **not** a system of record. It does not hold any real inventory.
- It does **not** contain or reference any private archive, real asset, real
  brand, real product, real filename, real absolute path, or any other
  identifier that could point back to a private collection.
- It does **not** establish facts about any real brand or its catalogue.
- The visual treatment, the synthetic-metadata labels, the focus management,
  and the modal contract are reference patterns only. They are not
  certification that a downstream implementation is correct, secure, or
  compliant with any specific brand's governance.

## How to open

Open `fashion-archive-prototype.html` in any modern browser. The 6 SVG
placeholders under `assets/display/` are loaded relative to the HTML, so the
directory must stay intact.

## Synthetic-metadata contract

Every field in the UI that is not derived from the placeholder image is
labelled as synthetic. The drawer explicitly tags `Visual Note`,
`Asset ID`, and `Observation` with `(synthetic)` and `(synthetic, AI-written)`
in the field labels. The cover stamp is the literal string `DEMO / UNVERIFIED`.
The header reads `Reference Implementation · Synthetic Data`. The shelf meta
reads `6 demo entries · 1 of 1 (synthetic)`.

This labelling is a contract: any consumer of this reference must preserve
the distinction between observation, inference, and confirmation. Inference
must not be promoted to confirmed fact. Visual similarity must not establish
identity, rights, product variant, or fitness for use. Missing evidence
must fail closed rather than trigger silent substitution.

## Interaction contract (carried over from the private spec)

- Folder cover → hover/focus reveals the underlying image; click or Enter
  opens the case file drawer.
- Drawer opens → focus moves to the Close button.
- Drawer closes (Close button, scrim click, Escape) → focus returns to the
  folder that opened the drawer; Close becomes `inert` and not tab-focusable
  while hidden.
- `role="dialog"` on the panel carries `aria-modal="true"` while open and
  `aria-modal="false"` while closed. The outer `<aside>` keeps `aria-hidden`
  for the open/close visual state.
- `prefers-reduced-motion` is respected: hover transitions are disabled and
  the cover drops to 0.2 opacity instead of sliding.

## Source asset rule

No real source asset is referenced. The 6 image placeholders are inline SVG
files of the form `assets/display/placeholder_0N.svg` that contain only
gradient fills, dashed borders, and the literal text "Demo placeholder".
They are part of this repository and may be freely replaced by downstream
implementations that have their own approved placeholder strategy.

## Boundary check

This directory satisfies the public-repository boundary contract in
[`REPO_BOUNDARY.md`](../../REPO_BOUNDARY.md) and
[`CONTRIBUTING.md`](../../CONTRIBUTING.md):

- No NUDE brand references, no real inventory, no real filenames, no real
  archive paths, no real asset IDs, no real content hashes, no real
  provenance, no real product bindings, no secrets, no model traces.
- All 6 entries use generic vocabulary (`Collection Alpha`..`Collection
  Foxtrot`, `Reference frame 1`..`Reference frame 6`, `T-001`..`T-006`).
- The `Source Reference` field uses a governed placeholder
  (`<source-archive>/<year>/<group>/<tab>`) rather than a real on-disk
  path.
- No binary image, video, audio, or document is included. Only inline SVG
  placeholders, which are text and review-friendly.

## Provenance of this reference

This reference is derived from a private prototype that was independently
gated and accepted. The private prototype's bytes are not committed here. The
public version was rewritten to be brand-neutral and content-free while
preserving the same interaction model, accessibility contract, and
synthetic-metadata labelling rule. No private semantic was carried over
beyond the interaction itself.

## License

This reference is part of the Brand Librarian public repository. See the
top-level [`README.md`](../../README.md) and
[`REPO_BOUNDARY.md`](../../REPO_BOUNDARY.md) for the full governance
contract.
