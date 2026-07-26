# AGENTS.md

Guidance for future coding agents working on the Wang Lab website.

## Project Shape

This is a Jekyll site on the `source` branch.

- Site config, identity, and navigation live in `_config.yml`.
- Page content lives in `_pages/`.
- Layout shells live in `_layouts/`.
- Shared head/header/footer markup lives in `_includes/`.
- Sass partials live in `_sass/`; the entry point is `assets/main.scss`.
- Generated output lives in `_site/` and should normally be produced by Jekyll, not edited directly.
- JavaScript source is `assets/js/site.js`; the bundled output is `assets/js/site.min.js`.

## Local Preview And Build

Use:

```bash
npm run build
bundle exec jekyll build
bundle exec jekyll serve --host 127.0.0.1 --port 4000
```

The local preview URL is `http://127.0.0.1:4000/`.

If the sandbox blocks binding to the local port, request escalation for `bundle exec jekyll serve`. Do not start multiple Jekyll servers on the same port.

## Editing Rules

- Do not edit `_site/` by hand. Change source files and rebuild.
- Keep changes scoped. Avoid broad restyling unless requested.
- Preserve the existing academic/editorial visual style.
- Use existing Sass partials rather than inline styles where possible.
- If changing shared components, check how they affect multiple pages.
- Rebuild after Sass, Markdown, layout, favicon, or JavaScript changes.
- Run `npm run build` when `assets/js/site.js` changes.

## Current Design System

The site uses a restrained academic/editorial style inspired by Benjamin Noble's website. Preserve this direction unless explicitly asked to redesign.

### Sitewide Tokens

- Layout width is controlled by `--container-max: 1100px` in `_sass/base/_variables.scss`.
- Main content and page headers should generally use `max-width: var(--container-max)` and centered margins.
- The current font stack is declared in `_sass/base/_variables.scss` and imported in `_includes/head.html`:
  - `--font-sans: 'Inter Tight', Helvetica, Arial, sans-serif`
  - `--font-serif: 'Newsreader', Georgia, 'Times New Roman', serif`
  - `--font-mono: 'IBM Plex Mono', ui-monospace, SFMono-Regular, Menlo, monospace`
- Most visible UI and page text should use `var(--font-sans)`. Use `var(--font-serif)` sparingly for long-form quote/editorial accents only.
- Light mode uses warm off-white backgrounds; dark mode uses black/dark gray with `--accent: #cadb2b`.
- Avoid one-note decorative palettes, gradient blobs, rounded decorative cards, and oversized marketing sections.

### Shared Editorial Page Pattern

For most internal tabs, use this structure:

```html
<header class="editorial-page-header" markdown="0">
<h1>Page Title</h1>
<p class="editorial-page-lede">One concise sentence describing the page.</p>
</header>

<section class="editorial-section">
<h2 class="editorial-section-heading">§ Section</h2>
<div class="editorial-panel">
...
</div>
</section>
```

- Shared editorial classes live primarily in `_sass/components/_publication.scss`.
- `.editorial-page-header`, `.editorial-section`, `.editorial-panel`, `.editorial-page-lede`, `.editorial-section-heading`, and `.editorial-list` define the cross-page look.
- Section headings use the `§` prefix and a single horizontal rule from the heading `::after`. Do not add a second divider directly below the heading.
- `.editorial-panel` is intentionally unboxed: transparent background, no border, no shadow, square corners, and content padding only.
- `.editorial-list` intentionally has no lines between items for focus-area style lists.
- Main text should be allowed to use the full 1100px content width; avoid narrow `max-width` constraints on regular paragraphs unless a specific layout needs them.

### Card And Surface Rules

- Main content surfaces should not look like cards. Avoid boxed backgrounds, shadows, rounded panels, or nested cards on About, Team, Fun, Resource, News, Contact, Publications, CV, and Home content sections.
- Square corners are the default for any remaining framed component (`border-radius: 0`).
- `.section-card`, `.editorial-panel`, `.profile-card`, `.team-card`, and contact map/info surfaces have been flattened to match the editorial style.
- Research cards are the exception: `/research/` keeps image-driven interactive `.research-card` blocks with hover/focus behavior.
- Research cards currently have no visible border.
- Favicon assets are generated from `images/logo_png.png` and declared in `_includes/head.html`.

## Page And Tab Design Notes

### Home (`/`)

- Files: `_pages/home.md`, `_layouts/homelay.html`, `_sass/layouts/_home.scss`, `assets/js/site.js`, `assets/js/site.min.js`.
- Keep the hero image section intact unless explicitly asked to change it.
- The hero title is `Wang Lab <span class="home-hero-affiliation">@ CHOP CVI</span>`.
- Only `.home-hero-affiliation` should be smaller than `Wang Lab`; do not reduce the parent `h1` size just to resize the affiliation.
- `assets/js/site.js` can overwrite hero slide text. If changing hero text, update both `_layouts/homelay.html` and the first `heroData` entry in `assets/js/site.js`, then run `npm run build`.
- Home content below the hero follows the editorial header/content style and avoids boxed cards.

### About (`/about/`)

- File: `_pages/about.md`; shared style in `_sass/components/_publication.scss`; profile/logo style in `_sass/components/_profile.scss`.
- Uses `.editorial-page-header`, `.editorial-note`, `.editorial-section`, `.editorial-section-heading`, and `.editorial-panel`.
- The lab logo in `.about-lab-logo` should not have a visible border.
- Focus areas should be a clean list with no separator lines between individual areas.
- Sponsor logos are displayed in `.sponsor-logos` without card borders.

### Research (`/research/`)

- Files: `_pages/research.md`, `_sass/layouts/_research.scss`.
- Only the top title/header adopts the shared editorial page-title style.
- Keep `.research-card` behavior unless explicitly asked otherwise:
  - image fills the card
  - title remains visible over the image
  - description slides up on hover/focus
  - non-hovered cards fade when another card is hovered
  - cards have no visible border
- The word cloud belongs below the research card grid and uses the title/sans font style.
- Do not convert research cards into the flat editorial panel style unless the user explicitly asks.

#### Research Project Detail Pages

- Project-specific research pages currently live in `_pages/project-*.md` and use `layout: gridlay` with permalinks under `/research/.../`.
- The research cards in `_pages/research.md` link to:
  - `/research/postnatal-heart-development/`
  - `/research/direct-cardiac-reprogramming/`
  - `/research/congenital-heart-disease-genetics/`
- Project detail pages use the shared editorial section pattern plus project-specific styles in `_sass/layouts/_research.scss`.
- Project subsection headings are intentionally larger than generic editorial headings on project pages only, via `.project-page-header ~ .editorial-section .editorial-section-heading`.
- The first paragraph in each project subsection uses a project-page-only drop cap. Keep this scoped to project pages unless a sitewide editorial change is requested.
- Project figures use:
  - `.project-hero` for the top project visual
  - `.project-hero-lightbox` with `.project-hero-lightbox-frame` when a dark-mode page needs a white backing behind the image but not behind the caption
  - `.project-animation` and `.project-animation-inline` for inline animated atlas GIFs
  - `.project-scheme` for workflow/schematic figures
  - `.project-scheme-narrow` for a small left-floated schematic with nearby text wrapping around it
- Use `<figure>` and `<figcaption>` for project visuals. Captions should be short, factual, and styled through `_sass/layouts/_research.scss`.
- Project figure captions are intentionally a little larger than before (`0.875rem`) and should stay consistent across `.project-hero`, `.project-animation`, and `.project-scheme`.
- Prefer browser-safe image formats in `images/research/`. Convert TIFF source files to PNG before embedding.
- GIFs used on project pages should be cropped and downsampled enough to avoid unnecessary black space and large page weight, while preserving the scientific signal.
- Current postnatal project media:
  - `images/research/ncl_z_stack_gfp_positive.gif` is the top hero GIF.
  - `images/research/postnatal_atlas.gif` is the inline spatial/temporal atlas GIF.
  - `images/research/pip_seq_scheme.png` is the in vivo Perturb-seq workflow scheme.
- Current direct cardiac reprogramming media:
  - `images/research/am_profile.png` is the top hero image and matches the `/research/` card image.
  - `images/research/am_scheme.jpg` appears in the minimal-cocktail section as a left-floated `.project-scheme project-scheme-narrow` figure with a citation caption.
- Current congenital heart disease genetics media:
  - `images/research/alpha_genome_chd.png` is the top hero image.
  - The CHD hero uses `.project-hero-lightbox`; keep the white background confined to `.project-hero-lightbox-frame` so the caption stays on the normal page background.

### Publications (`/publications/`)

- Files: `_pages/publications.md`, `_sass/components/_publication.scss`.
- Uses `.publication-index` rather than the generic page header.
- Page title is `Publications` with a one-sentence `.publication-lede` directly below it.
- Publications are grouped by year using `.publication-section-heading` headings such as `§ 2026`.
- Each publication row uses `.publication`; the left metadata column should show publication type (`Article`, `Preprint`, `Review`, `Protocol`, `Preview`) rather than year.
- Publication entries should remain row-based and editorial, not card-based.

### Team (`/team/`)

- Files: `_pages/team.md`, `_sass/layouts/_team.scss`.
- Uses the shared editorial header and section structure.
- `.team-card` has been flattened: transparent background, no shadow, square corners.
- Team photos may keep their own image treatment, but avoid adding boxed card containers around each person.

### Fun (`/fun/`)

- File: `_pages/fun.md`; shared style in `_sass/components/_publication.scss`.
- Uses the shared editorial page header and flat `.editorial-panel` sections.
- Keep content informal but visually consistent with the rest of the academic/editorial site.

### Resource (`/resource/`)

- File: `_pages/resource.md`; shared style in `_sass/components/_publication.scss`.
- Uses the shared editorial page header and flat `.editorial-panel` sections.
- Keep resource lists/link groups unboxed unless a functional table or repeated item list clearly needs framing.

### News (`/allnews.html`, `/blogs/`)

- Files: `_pages/allnews.md`, `_pages/blogs.md`; shared card/news style in `_sass/components/_card.scss` and `_sass/components/_publication.scss`.
- `/allnews.html` uses the shared editorial header and flattened panel style.
- `/blogs/` may still contain older `.section-card` markup, but `.section-card` is styled flat. Do not reintroduce card shadows or rounded card backgrounds.

### Contact (`/contact/`)

- Files: `_pages/contact.md`, `_sass/layouts/_contact.scss`.
- Uses the shared editorial page header.
- Contact map/info surfaces are intentionally unboxed: no border, no shadow, transparent background.
- Keep the contact grid constrained to the 1100px content width.

### CV (`/haofei-wang/`)

- Files: `_pages/haofei-wang.md`, CV styles in `_sass/components/_publication.scss`.
- Uses `.cv-index`, `.cv-profile-row`, `.cv-list-row`, and `.cv-row-meta`.
- CV layout should resemble the publication page: structured rows, left metadata column, content on the right.
- Training and appointments use year ranges in the left column, currently in this sequence: `2027-`, `2023-2026`, `2019-2023`, `2018-2019`, `2013-2018`, `2009-2013`.
- CV section title and row content sizes are intentionally swapped from the original hierarchy: section headings are larger; row content headings are smaller uppercase text.

## Git Notes

- The main working branch is `source`, tracking `origin/source`.
- Push with `git push origin source`.
- Do not include unrelated untracked files. At the time this file was created, `images/team-hero.jpg` was untracked and should be left alone unless explicitly requested.
- Avoid reverting user changes. If the worktree is dirty, inspect the diff and stage only files related to the task.

## Common Files For Website Updates

- Navbar: `_includes/header.html`, `_sass/components/_navbar.scss`
- Design tokens and fonts: `_sass/base/_variables.scss`, `_sass/base/_typography.scss`, `_includes/head.html`
- Shared editorial page style: `_sass/components/_publication.scss`
- Flattened card/surface defaults: `_sass/components/_card.scss`, `_sass/components/_profile.scss`
- Home page: `_pages/home.md`, `_layouts/homelay.html`, `_sass/layouts/_home.scss`, `assets/js/site.js`
- About page: `_pages/about.md`, `_sass/components/_publication.scss`, `_sass/components/_profile.scss`
- Research page: `_pages/research.md`, `_sass/layouts/_research.scss`, `_includes/word-cloud.html`
- Publications page: `_pages/publications.md`, `_sass/components/_publication.scss`
- Team page: `_pages/team.md`, `_sass/layouts/_team.scss`
- Fun page: `_pages/fun.md`, `_sass/components/_publication.scss`
- Resource page: `_pages/resource.md`, `_sass/components/_publication.scss`
- News pages: `_pages/allnews.md`, `_pages/blogs.md`, `_sass/components/_card.scss`
- Contact page: `_pages/contact.md`, `_sass/layouts/_contact.scss`
- CV page: `_pages/haofei-wang.md`, `_sass/components/_publication.scss`
- Favicon: `_includes/head.html`, `favicon.ico`, `favicon.svg`, `images/favicon-*.png`, `images/apple-touch-icon.png`
