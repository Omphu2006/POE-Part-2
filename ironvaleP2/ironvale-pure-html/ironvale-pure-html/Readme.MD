# Ironvale Plumbing Co. — Website Project

## Project Overview
A five-page website built for Ironvale Plumbing Co., a fictional residential
and commercial plumbing service, as the target organisation for this
Portfolio of Evidence. The site showcases the company's story, services,
and rates, and allows visitors to request a free quote or send a general
enquiry.

## Website Goals and Objectives
- Give the business a professional web presence beyond word-of-mouth.
- Allow visitors to request a quote for residential, commercial, or
  emergency plumbing work.
- Build trust with clear licensing, pricing, and guarantee information
  up front.
- KPIs: quote form submissions, click-throughs on the emergency call
  button, time spent on the services page, growth in unique visitors.

## Key Features and Functionality
- Homepage with a work-order-styled hero, core services overview, and an
  emergency call-to-action.
- About Us page with the company's history, mission/vision, values, and
  team.
- Services page with categorised offerings (Residential, Commercial,
  Emergency) and a rate guide table.
- Get a Quote page with a job-detail enquiry form and an FAQ accordion.
- Contact page with office hours, service area, an embedded map, service
  policies, and a general contact form.

## Part 2 — CSS Styling and Responsive Design
Part 1 shipped as HTML with CSS inlined directly into each page. For
Part 2 the styling has been extracted into a single **external stylesheet**
(`css/style.css`) that all five pages link to, per the brief's requirement
to create one stylesheet and link every page to it.

**2.1–2.2 External stylesheet & base style**
- One shared `css/style.css`, linked from every page's `<head>`.
- A CSS reset at the top of the file (box-sizing, margin/padding zeroing,
  list-style removal, image scaling) so all five pages start from the same
  baseline across browsers.
- Base styles (font family, colour scheme, line-height) set once on `html`/
  `body` and inherited everywhere via the cascade, rather than repeated
  per selector.

**2.3 Typography**
- A typographic scale defined as CSS custom properties (`--fs-body`,
  `--fs-h2`, `--fs-h2-hero`, etc.), all in `rem` so they scale with the
  user's base font size.
- The hero heading uses `clamp()` to scale fluidly between a minimum and
  maximum size across viewport widths, instead of jumping at a fixed
  breakpoint.

**2.4 Layout structure**
- CSS Grid for the homepage hero, service/team/card grids, and the numbered
  "why us" process list (`display: grid`, `grid-template-columns`).
- Flexbox for the header, primary navigation, hero actions, badges, and
  footer (`display: flex`, `justify-content`, `align-items`, `flex-wrap`).
- A spacing scale (`--space-1` … `--space-9`, in `rem`) used for section
  and component spacing so gaps stay consistent and scale with type size.

**2.5 Visual styles & interaction states**
- Colour, background-colour, border, and box-shadow used to differentiate
  cards, badges, and the ticket component.
- `:hover` states on nav links, buttons, cards, and FAQ summaries.
- `:focus-visible` states on links, nav items, buttons, and form summaries
  for keyboard accessibility.
- `:active` states on buttons for tactile press feedback.

## Part 3 — Responsive Design
- **Breakpoints:** two breakpoints defined in `em` (not `px`), so they
  scale with the browser's own font-size/zoom setting rather than only
  physical pixels — `55em` (~880px, desktop → tablet) and `35em` (~560px,
  tablet → mobile). Desktop styles are the default; grids collapse from
  3 columns → 2 columns → 1 column as the viewport narrows.
- **Relative units:** font sizes and spacing throughout use `rem`; the
  hero heading uses `clamp()` with a `vw`-based fluid component; percentage
  widths are used for form fields and grid tracks.
- **Responsive tables:** the rate-guide and hours tables scroll
  horizontally on narrow viewports (`overflow-x: auto`) instead of
  breaking their layout.
- **Responsive embed:** the Contact page map `iframe` uses `aspect-ratio`
  instead of a fixed pixel height, so it resizes proportionally.
- **Testing:** layouts were checked at desktop (~1280px+), tablet
  (~768–880px), and mobile (~375–560px) widths using browser developer
  tools' device toolbar, confirming the grid-to-single-column collapse,
  stacked header/nav on mobile, and horizontally-scrollable tables.
  *(Insert your own device-toolbar screenshots here for submission —
  desktop / tablet / mobile for at least the homepage and one inner page.)*

## Sitemap
```
Home (index.html)
├── About Us (about.html)
├── Services (services.html)
├── Get a Quote (quote.html)
└── Contact (contact.html)
```

## File and Folder Structure
```
ironvale-plumbing/
├── index.html
├── about.html
├── services.html
├── quote.html
├── contact.html
├── css/
│   └── style.css
├── js
└── images/
    ├── team-marcus.jpg
    ├── team-renee.jpg
    ├── team-darius.jpg
    ├── leak-icon.jpg
    ├── water-heater-icon.jpg
    ├── drain-icon..jpg
    ├── services-residential.jpg
    ├── services-commercial.jpg
    ├── services-emergency-placeholder.jpg
```

## Design Notes
- **Palette:** ink navy (#16283A), copper (#BE6E3C), warm paper (#F3EEE4),
  steel grey (#4C5B66), alert red (#B3411F) reserved for emergency calls
  to action.
- **Type:** Zilla Slab (headings), Work Sans (body copy), IBM Plex Mono
  (labels, prices, ticket/table data) — loaded via Google Fonts.
- **Signature element:** the homepage hero is styled as a plumber's work
  order ticket (job number, dispatch details, service badges) rather than
  a generic banner image, tying the visual language back to the trade.
- Semantic HTML throughout (`header`, `nav`, `main`, `footer`, `article`,
  `address`, `details`/`summary`, `dl`, tables with `caption`/`scope`), a
  skip-to-content link, and per-page `aria-current="page"` navigation
  states.

## Changelog

### Part 2 — CSS Styling and Responsive Design
- **Added:** external stylesheet `css/style.css`, linked from all five
  pages, replacing the inline `<style>` block each page previously carried.
- **Added:** CSS reset (box-sizing, margin/padding, list-style, image
  scaling) for consistent cross-browser rendering.
- **Added:** typography scale and spacing scale as CSS custom properties,
  expressed in `rem`.
- **Added:** `:hover`, `:focus-visible`, and `:active` states on
  navigation links, buttons, cards, and FAQ summaries.
- **Added:** two responsive breakpoints (`55em` / `35em`) with `em` units,
  collapsing grid layouts from 3 → 2 → 1 columns and stacking the header
  on mobile.
- **Added:** horizontal scroll on tables and `aspect-ratio` on the
  embedded map for smaller viewports.
- **Changed:** fixed-pixel spacing (section margins, card padding, button
  padding) converted to the `rem`-based spacing scale.
- **Changed:** breakpoints converted from `px` to `em` per responsive
  design best practice.

### Part 1 feedback addressed
- *(List any corrections made to Part 1 here following lecturer feedback,
  e.g. heading hierarchy fixes, alt-text additions, or markup corrections —
  update this entry with the specific feedback received.)*

## References
- Google Fonts (n.d.) Available at: https://fonts.google.com (Accessed: 12 August 2026).
- MDN Web Docs (n.d.) CSS Grid Layout. Available at: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout (Accessed: 11 September 2026).
- MDN Web Docs (n.d.) CSS Flexible Box Layout. Available at: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout (Accessed: 11 September 2026).
- MDN Web Docs (n.d.) Using media queries. Available at: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries (Accessed: 11 September 2026).
- MDN Web Docs (n.d.) HTML elements reference. Available at: https://developer.mozilla.org/en-US/docs/Web/HTML/Element (Accessed: 12 August 2026).
