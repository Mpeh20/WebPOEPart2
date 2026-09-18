## Project Details

| Field | Value |
|-------|-------|
| **Subject Name** | Web Design & Development |
| **Subject Code** | WEDE5020 |
| **Student Name** | Vuyolwethu Ngwalangwala |
| **Student Number** | [Ngwalangwala] |
| **Group** | 1 |
| **Submission Date** | 18 September 2026 |
| **Assignment** | Part 1 — Project Initiation and Planning · Part 2 — CSS Styling & Responsive Design |

---

## Repository Structure
/ctars-website
│
├── index.html # Homepage — hero, mission/vision, featured pets, CTA
├── about.html # About CTARS — history, mission, team, values
├── services.html # Services + filterable adoptable pet gallery
├── enquiry.html # Volunteer / Foster / Adopt / Sponsor enquiry form
├── contact.html # Two locations (with Google Maps) + contact form
│
├── css/
│ └── style.css # External stylesheet (Part 2)
│
├── js/
│ └── script.js # Pet filter + form helpers
│
├── images/ # Responsive images (srcset/sizes variants)
│
├── documents/
│ └── CTARS_Website_Project.pdf # Full Part 1 report
│
└── README.md # This document

text

---

## Sitemap
Homepage (index.html)
├── About (about.html)
│ ├── Mission & Vision
│ ├── History
│ └── Team
├── Services (services.html)
│ ├── Rescue & Rehabilitation
│ ├── Adoption & Rehoming
│ ├── Foster Care Programme
│ ├── Community Education
│ └── Adoptable Pets Gallery (filter by type)
├── Enquiry (enquiry.html)
│ ├── Volunteer
│ ├── Foster
│ ├── Adopt
│ └── Sponsor
└── Contact (contact.html)
├── Main Adoption Centre (Map 1)
├── Weekend Market Stall (Map 2)
└── Contact Form

text

---

## Changelog

All edits made following lecturer feedback from Part 1 are recorded here, as
required by the Part 2 brief. Each entry includes the specific feedback
received, the exact change made, and the files affected.

### [Part 2] – 18 September 2026

**1. Visual hierarchy on homepage**
- **Feedback addressed:** Weak visual hierarchy on the homepage and inconsistent spacing across cards.
- **Change made:** Introduced CSS custom properties (`--space-*`, `--fs-*`) for a consistent spacing and typography scale. Applied across all components including hero, cards, sections and footer.
- **Files affected:** `css/style.css`, all HTML pages

**2. Navigation active state**
- **Feedback addressed:** Navigation lacked a clear active/current-page indicator.
- **Change made:** Added a `.nav-list a.active` rule in the stylesheet and applied `aria-current="page"` on the current page link in each HTML file for accessibility.
- **Files affected:** `css/style.css`, all HTML pages

**3. Responsive layout on small screens**
- **Feedback addressed:** Pages did not adapt well to small screens.
- **Change made:** Added mobile-first media queries at 600px, 900px and 1200px. Grids (pet grid, mission strip, footer) collapse to a single column on mobile; navigation wraps gracefully; typography scales down.
- **Files affected:** `css/style.css`

**4. Oversized images on mobile**
- **Feedback addressed:** Images loaded at full resolution on small screens, slowing page load.
- **Change made:** Added `srcset`, `sizes` and `<picture>` elements for hero and pet images; added `loading="lazy"` and `decoding="async"` attributes.
- **Files affected:** All HTML pages, `images/`

**5. Form accessibility and validation**
- **Feedback addressed:** Form fields lacked accessible labels and validation hints.
- **Change made:** Added `required`, `novalidate`, clear `<label for>` pairs, consent checkboxes, and helpful placeholder guidance on both forms.
- **Files affected:** `enquiry.html`, `contact.html`

**6. Button and link interaction states**
- **Feedback addressed:** Interactive elements lacked hover/focus feedback.
- **Change made:** Added `:hover`, `:focus-visible` and `:active` states for all buttons, nav links, footer links and social icons.
- **Files affected:** `css/style.css`

**7. Pet filter functionality**
- **Feedback addressed:** Adopt page needed a way to filter pets by type.
- **Change made:** Added filter buttons and JavaScript that toggles pet cards based on `data-type` attribute (dog/cat/all).
- **Files affected:** `services.html`, `js/script.js`, `css/style.css`

### [Part 1] – 27 August 2025
- Initial project proposal and sitemap completed.
- Part 1 proposal document submitted for approval.

---

## Design System (Part 2)

### Colour Palette

| Variable | Colour | Hex | Usage |
|----------|--------|-----|-------|
| `--clr-primary` | Forest green | `#4A7C59` | Header, links, brand |
| `--clr-primary-dark` | Deep green | `#2D5A3B` | Headings |
| `--clr-primary-light` | Pale green | `#EEF5EA` | Section backgrounds |
| `--clr-accent` | Orange | `#F28C38` | CTAs, buttons, active states |
| `--clr-accent-dark` | Deep orange | `#D97A2E` | Button hover |
| `--clr-bg` | Warm cream | `#FBF8F2` | Page background |
| `--clr-surface` | White | `#FFFFFF` | Cards, forms |
| `--clr-text` | Charcoal | `#2D2A24` | Body text |
| `--clr-text-muted` | Muted grey | `#5A5A4E` | Secondary text |
| `--clr-border` | Light grey | `#E2DCD2` | Card borders |
| `--clr-footer` | Dark green | `#1E2E24` | Footer background |

### Typography

- **Headings:** *Playfair Display* (serif) — elegant, warm, trustworthy.
- **Body:** *Open Sans* (sans-serif) — clean, highly readable.
- **Scale:** Major Third (1.250) implemented with `--fs-*` custom properties:

| Variable | Size | Usage |
|----------|------|-------|
| `--fs-xs` | 0.8rem | Small labels |
| `--fs-sm` | 0.9rem | Nav links, meta text |
| `--fs-base` | 1rem | Body text |
| `--fs-md` | 1.125rem | Lead paragraphs |
| `--fs-lg` | 1.5rem | Card headings |
| `--fs-xl` | 2rem | Section headings |
| `--fs-2xl` | 2.5rem | Page titles |
| `--fs-3xl` | 3.2rem | Hero heading |

### Spacing Scale

| Variable | Size | Usage |
|----------|------|-------|
| `--space-xs` | 0.5rem | Tight gaps |
| `--space-sm` | 1rem | Default padding |
| `--space-md` | 1.5rem | Card padding |
| `--space-lg` | 2.5rem | Section spacing |
| `--space-xl` | 4rem | Page section breaks |

### Layout Techniques

- **CSS Grid** for page-level structure: pet grid, mission strip, footer, contact grid.
- **CSS Flexbox** for component-level layout: navigation, buttons, hero buttons, form rows.
- **Mobile-first** approach with three breakpoints.
- Properties used: `display`, `flex-direction`, `justify-content`, `align-items`, `grid-template-columns`, `gap`.

### Responsive Breakpoints

| Breakpoint | Target Device | Behaviour |
|------------|---------------|-----------|
| Base (< 600px) | Mobile | Single-column layout, smaller typography, stacked footer |
| `@media (min-width: 600px)` | Large phone / small tablet | 2-column pet grid, 2-column footer |
| `@media (min-width: 900px)` | Tablet / small desktop | 3-column pet grid, 4-column footer, 2-column mission strip |
| `@media (min-width: 1200px)` | Desktop | Wider container, expanded hero padding |

### Relative Units Used

- `rem` — font sizes, spacing, border radius (scalable with root font size).
- `%` and `vw` — widths and full-bleed images.
- Unitless `line-height` — scalable text rhythm (e.g., `1.7`).

### Responsive Images

All images use `srcset`, `sizes` and `<picture>` elements so the browser
downloads the smallest suitable file for the current screen. Example:

```html
<picture>
  <source
    srcset="images/max-large.webp 1200w,
            images/max-medium.webp 800w,
            images/max-small.webp 400w"
    sizes="(min-width: 900px) 33vw,
           (min-width: 600px) 50vw,
           100vw"
    type="image/webp" />

  <source
    srcset="images/max-large.jpg 1200w,
            images/max-medium.jpg 800w,
            images/max-small.jpg 400w"
    sizes="(min-width: 900px) 33vw,
           (min-width: 600px) 50vw,
           100vw"
    type="image/jpeg" />

  <img
    src="images/max-medium.jpg"
    alt="Max, a two-year-old lab mix waiting for adoption at CTARS"
    width="800"
    height="600"
    loading="lazy"
    decoding="async" />
</picture>
Visual Styles Applied
color and background-color — brand palette across components.

border and border-radius — soft card edges and pill buttons.

box-shadow — layered depth on cards, buttons and hero.

Pseudo-classes: :hover, :focus-visible, :active for interactive elements.

Accessibility
Semantic HTML5 landmarks: <header>, <nav>, <main>, <section>, <article>, <footer>.

aria-current="page" on the active navigation link.

aria-label on icon-only social links.

alt text on all meaningful images; aria-hidden="true" on decorative icons.

Sufficient colour contrast (WCAG AA compliant).

Keyboard-navigable interactive elements with visible focus states (:focus-visible).

Form labels paired with inputs via for/id.

Browser Developer Tools Usage
During development, Chrome DevTools (F12) was used to:

Inspect elements and verify applied CSS rules (Styles pane).

Toggle the device toolbar (Ctrl + Shift + M) to test responsive breakpoints live.

Check computed values for colours, font sizes, and spacing.

Diagnose layout issues with the Grid and Flexbox overlays.

Run Lighthouse audits for accessibility, performance and SEO.

Test colour contrast using the built-in accessibility checker.

Final CSS changes were always copied back into style.css; live edits were never relied upon for submission.

References
Part 2 References
MDN Web Docs. (2026). CSS: Cascading Style Sheets. Mozilla.
https://developer.mozilla.org/en-US/docs/Web/CSS

MDN Web Docs. (2026). Responsive images — srcset and sizes.
https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images

MDN Web Docs. (2026). Using CSS custom properties (variables).
https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties

MDN Web Docs. (2026). CSS Grid Layout.
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout

MDN Web Docs. (2026). Flexbox.
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout

W3C. (2026). Web Content Accessibility Guidelines (WCAG) 2.2.
https://www.w3.org/WAI/standards-guidelines/wcag/

W3C. (2026). CSS Grid Layout Module Level 2.
https://www.w3.org/TR/css-grid-2/

CSS-Tricks. (2026). A Complete Guide to Flexbox.
https://css-tricks.com/snippets/css/a-guide-to-flexbox/

CSS-Tricks. (2026). A Complete Guide to Grid.
https://css-tricks.com/snippets/css/complete-guide-grid/

Google. (2026). Web.dev — Learn Responsive Design.
https://web.dev/learn/design/

Google. (2026). Lighthouse: Automated auditing for web apps.
https://developer.chrome.com/docs/lighthouse/overview/

Chrome DevTools. (2026). Inspect and edit CSS.
https://developer.chrome.com/docs/devtools/css/

Can I Use. (2026). Browser support tables for modern web technologies.
https://caniuse.com/
