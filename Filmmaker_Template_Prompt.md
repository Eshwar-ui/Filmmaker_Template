# 🎬 AI IDE Prompt — Independent Documentary Filmmaker HTML Template

> **Copy this entire prompt and paste it into Cursor, Windsurf, or any AI IDE.**
> This is a self-contained build instruction — no extra context needed.

---

## PROJECT BRIEF

Build a **complete, production-ready HTML/CSS/JavaScript website template** for an **Independent Documentary Filmmaker**. This is a **reusable portfolio template**, not a single site — it must be polished, standards-compliant, and easy for any filmmaker to customize by swapping out text, images, and links.

**Tech Stack:** Vanilla HTML5 + CSS3 + ES6+ JavaScript only. No frameworks, no React, no Vue, no Bootstrap, no Tailwind. Pure hand-written code.

**Dashboard Required:** No.

---

## AESTHETIC DIRECTION

**Cinematic. Dark. Editorial. Film-noir meets modern documentary.**

- **Mood:** Think Criterion Collection meets a film festival program. Raw, honest, cinematic gravity.
- **Color Palette (CSS Variables):**
  - `--color-bg: #0A0A0A` — near-black background
  - `--color-surface: #141414` — card/panel surface
  - `--color-surface-alt: #1E1E1E` — elevated surface
  - `--color-primary: #E8C547` — golden yellow (film reel accent)
  - `--color-primary-dark: #C4A230`
  - `--color-text: #F0EDE8` — warm off-white
  - `--color-text-muted: #8A8580` — muted warm gray
  - `--color-border: #2A2A2A`
  - `--color-overlay: rgba(0,0,0,0.75)`
  - (Light mode overrides defined separately — see dark/light mode section)
- **Typography:**
  - Display/Headings: `Playfair Display` (Google Fonts) — serif, editorial weight
  - Body: `DM Sans` (Google Fonts) — clean, modern, readable
  - Mono accents (runtime info, festival dates): `JetBrains Mono` (Google Fonts)
  - Max 3 font families total
- **Layout:** Full-width cinematic sections, asymmetric grid, generous whitespace, horizontal film-strip motifs, subtle grain texture overlay on hero.
- **Imagery Style:** All `<img>` tags use descriptive `alt` attributes and reference placeholder paths like `assets/images/film-[name].jpg`. Add a `<!-- TODO: Replace with your image -->` comment above each one.

---

## MANDATORY FILE STRUCTURE

Create ALL of these files — do not skip any:

```
/
├── pages/
│   ├── index.html          ← Home (main entry point)
│   ├── about.html          ← About the filmmaker
│   ├── films.html          ← Films / Portfolio (replaces "Services")
│   ├── contact.html        ← Contact for distributors & press
│   ├── 404.html            ← Custom 404 error page
│   └── coming-soon.html    ← Pre-launch / maintenance page
├── assets/
│   ├── css/
│   │   ├── style.css       ← Main stylesheet (all base styles)
│   │   ├── dark-mode.css   ← Dark mode variable overrides
│   │   └── rtl.css         ← RTL layout adjustments
│   ├── js/
│   │   ├── main.js         ← Core JS (nav, UI, scroll effects)
│   │   └── plugins/        ← Folder for any third-party scripts
│   ├── images/             ← All image assets (placeholder references)
│   └── fonts/              ← Empty; using Google Fonts CDN
├── documentation/
│   ├── installation.md
│   ├── customization.md
│   └── credits.md
└── README.md
```

---

## PAGES — FULL SPECIFICATION

### 1. `pages/index.html` — Home Page

**Section 1: Navigation Bar**
- Fixed/sticky navbar, transparent on top → solid `--color-surface` on scroll (JS scroll listener)
- Left: Filmmaker name / logo text in `Playfair Display`
- Center (desktop): Nav links — Films | About | Screenings | Press Kit | Contact
- Right: Dark/Light mode toggle button (sun/moon icon from Font Awesome)
- Mobile: Hamburger menu icon → full-screen overlay menu with large nav links
- Active page link must be visually highlighted
- Smooth scroll behavior for same-page anchor links
- ARIA: `role="navigation"`, `aria-label="Main navigation"`, hamburger button has `aria-expanded` and `aria-controls`
- Skip-to-content link as first element in body for screen readers

**Section 2: Hero Section**
- Full-viewport-height (`100vh`) cinematic hero
- Background: Dark overlay (`--color-overlay`) over a large landscape documentary still image (`assets/images/hero-bg.jpg`)
- Subtle CSS grain texture overlay (generated via CSS `background-image: url("data:image/svg+xml,...")` noise pattern)
- Content (vertically centered, left-aligned):
  - Small overline label: `DOCUMENTARY FILMMAKER` in `JetBrains Mono`, letter-spaced, `--color-primary` color
  - H1: Filmmaker's full name in large `Playfair Display` — e.g. `"Marcus Holloway"`
  - Tagline: `"Telling the stories the world hasn't heard yet"` in `DM Sans`
  - Two CTA buttons:
    - Primary: `Watch Latest Trailer` → links to `#films`
    - Secondary (outline style): `View Full Portfolio` → links to `films.html`
- Bottom: horizontal scroll indicator (animated down-arrow)
- Fade-in animation on page load (CSS `@keyframes fadeInUp` with `animation-delay` stagger)

**Section 3: Featured Film (Latest Work)**
- Two-column layout (desktop): left = large film poster/still, right = film details
- Right column content:
  - Label: `FEATURED FILM` (mono font, gold)
  - Film title in H2 (`Playfair Display`)
  - Year, Duration, Genre — separated by `|` dividers in muted mono font
  - Short synopsis (2–3 sentences)
  - Festival laurels row: 3–4 small badge-style pills showing festival wins (e.g. `Sundance Official Selection`, `IDFA Winner`)
  - CTA: `Watch Trailer` button (opens a lightbox modal — see JS section)
  - Secondary link: `Full Film Details →`
- Mobile: single column, poster on top

**Section 4: Film Grid (Recent Works)**
- Section heading: `Selected Films` with decorative horizontal rule
- CSS Grid layout: 3 columns desktop, 2 tablet, 1 mobile
- Each film card:
  - Film still image with `aspect-ratio: 16/9` (`object-fit: cover`)
  - On hover: dark overlay slides up from bottom with film title + year (CSS transition)
  - Below image: film title, year, 1-line description
  - Card is a full `<a>` link to the film detail on `films.html`
- Maximum 6 cards on homepage (see full list on `films.html`)

**Section 5: Festival Screening Schedule**
- Full-width dark section (`--color-surface`)
- Section heading: `Upcoming Screenings`
- List of screenings displayed as a structured timeline/table:
  - Each row: Date | Festival Name | Location | Film Title | Screening Type (World Premiere, etc.)
  - Alternating row backgrounds for readability
  - Upcoming dates: `--color-primary` date color
  - Past dates: `--color-text-muted` strikethrough style
- Include at least 6 placeholder screening entries
- Mobile: card-style stacked layout instead of table

**Section 6: Trailer Reel / Video Embed**
- Dark section with `--color-bg` background
- Centered heading: `Watch the Work`
- 16:9 responsive video embed area — use a YouTube `<iframe>` embed placeholder:
  - `src="https://www.youtube.com/embed/YOUR_VIDEO_ID"`
  - Add `<!-- TODO: Replace YOUR_VIDEO_ID with your YouTube trailer ID -->` comment
  - Wrapper div: `position: relative; padding-bottom: 56.25%; height: 0` (responsive iframe trick)
  - `loading="lazy"` attribute on iframe
- Below video: secondary links to 2 other film trailers as text links with play icon

**Section 7: Press / Media Recognition**
- Light strip section (subtle contrast against dark bg)
- Heading: `As Seen In`
- Row of 5–6 publication logo placeholders displayed as grayscale boxes with publication names in mono font (e.g. `The New York Times`, `Variety`, `IndieWire`, `The Guardian`, `Filmmaker Magazine`)
- On hover: slight opacity increase + no-grayscale transition

**Section 8: Testimonials / Quotes**
- Blockquote-style large pull quotes from critics or festival directors
- 2–3 quotes in alternating layout
- Each quote: large decorative quotation mark (CSS `::before`), quote text in italic `Playfair Display`, attribution below in mono font
- Example placeholder: `"A devastating and necessary film."` — *IndieWire*

**Section 9: Press Kit CTA**
- Dedicated CTA banner section
- Heading: `Press & Distribution Inquiries`
- Body text explaining what is available in the press kit (bio, film stills, EPK, screeners)
- Two action buttons:
  - `Download Press Kit` → links to `assets/files/press-kit.zip` with `<!-- TODO: Add your press kit zip file to assets/files/ -->`
  - `Contact for Screeners` → links to `contact.html`
- Background: subtle horizontal film-strip pattern using CSS repeating gradient

**Section 10: Footer**
- Three-column layout (desktop), single column (mobile)
- Col 1: Filmmaker name + short tagline + social media icons (Font Awesome: Instagram, Vimeo, Twitter/X, LinkedIn, IMDb)
- Col 2: Quick links — Films, About, Screenings, Press Kit, Contact
- Col 3: Contact snippet — email address + location (City, Country)
- Bottom bar: copyright line + `Made with HTML, CSS & JS` + link to W3C validator
- All social links open `target="_blank" rel="noopener noreferrer"`

---

### 2. `pages/about.html` — About the Filmmaker

**Sections:**
1. **Page Hero:** Half-viewport height, filmmaker portrait image (large, full-bleed left panel) + name and title on right. Desktop: 60/40 split. Mobile: stacked.
2. **Biography:** Long-form bio in readable column (max-width ~700px, centered), `DM Sans` 18px, generous line-height (1.7). Split into 3 `<p>` paragraphs with a `<hr>` separator styled as a thin gold line. Add `<!-- TODO: Replace with your biography -->` comment.
3. **Filmmaker's Approach / Statement:** Dark background section with a large italic pull quote from the filmmaker about their work. Heading: `"My Approach"`.
4. **Timeline:** Visual career timeline — alternating left/right entries (CSS flexbox). Each entry: Year (in gold mono font), Event title (bold), short description. Min 5 placeholder entries (first film, first festival, award win, etc.).
5. **Skills & Tools:** Three-column grid of skill tags — categories: *Documentary Styles* (e.g. Observational, Expository, Participatory), *Equipment* (e.g. Sony FX9, DJI Ronin), *Post-Production* (e.g. DaVinci Resolve, Adobe Premiere).
6. **Awards & Recognition:** Two-column table: Year | Award Name | Festival/Organization | Film.
7. **Clients & Collaborators:** Logo grid (same grayscale style as homepage press section). Heading: `"Trusted By & Collaborated With"`.

---

### 3. `pages/films.html` — Films Portfolio

**Sections:**
1. **Page Header:** Minimal — page title `"Films"` in large `Playfair Display`, brief intro sentence.
2. **Filter Bar:** JavaScript-powered category filter buttons — `All | Feature Length | Short Film | Web Series | Commercial Work`. Active filter button gets `--color-primary` underline. Filtering uses CSS class toggling (`display: none` / `display: block`) — no page reload.
3. **Film Grid:** Same card style as homepage but larger (2 columns desktop, 1 mobile). Show all films (8–10 placeholder entries). Each card includes:
   - Film still (16:9)
   - Title, Year, Duration, Category tag
   - One-line synopsis
   - Row of festival laurel badges
   - `View Details` button
4. **Individual Film Detail (same page, hidden panel OR linked):** Clicking `View Details` opens a full-width slide-down panel (CSS `max-height` transition from 0 to `auto`) beneath the card row containing:
   - Full synopsis
   - Director's statement
   - Full cast & crew credits
   - Festival run list
   - Film stills gallery (horizontal scroll strip of thumbnails)
   - Trailer embed
   - Download EPK button

---

### 4. `pages/contact.html` — Contact for Distributors

**Sections:**
1. **Page Header:** `"Get In Touch"` with subtitle: `"For distribution inquiries, press accreditation, and screening requests."`
2. **Two-column layout:** Left = contact info, Right = contact form.
3. **Left column — Contact Information:**
   - Email (with mailto link + copy-to-clipboard JS button)
   - Phone (with `tel:` link)
   - Location: City, Country
   - Representation/Agent section: Agent name + agency name + agent email (placeholder)
   - Response time note: `"I aim to respond within 48 hours"`
   - Social links row (same as footer)
4. **Right column — Contact Form:**
   ```html
   <form id="contact-form" novalidate>
     <input type="text" name="name" placeholder="Your Name" required>
     <input type="email" name="email" placeholder="Email Address" required>
     <select name="inquiry-type">
       <option value="">Select Inquiry Type</option>
       <option>Distribution Rights</option>
       <option>Press / Interview</option>
       <option>Festival Screening Request</option>
       <option>Commercial Collaboration</option>
       <option>Other</option>
     </select>
     <input type="text" name="organization" placeholder="Organization / Company (optional)">
     <textarea name="message" rows="6" placeholder="Your message..." required></textarea>
     <button type="submit">Send Message</button>
   </form>
   ```
   - **Client-side validation (JS):** Every required field validated on submit + on blur. Show inline error messages below each field. Error message has `role="alert"` for screen readers.
   - On valid submit: hide form, show a success message div: `"Thank you! I'll be in touch within 48 hours."` with a checkmark icon.
   - Form action: `<!-- TODO: Replace with your Formspree endpoint URL: action="https://formspree.io/f/YOUR_ID" method="POST" -->`
5. **Press Kit Download Strip:** Same CTA banner as homepage (Press Kit section).
6. **Map Placeholder:** Full-width section with a Google Maps iframe placeholder:
   ```html
   <!-- TODO: Replace src with your Google Maps embed URL -->
   <iframe src="https://www.google.com/maps/embed?..." loading="lazy" allowfullscreen></iframe>
   ```

---

### 5. `pages/404.html` — Custom Error Page

- Full-screen centered layout
- Large `404` numeral in massive `Playfair Display` (stylized, with `--color-primary` color)
- Film clapperboard icon above (Font Awesome `fa-film`)
- Heading: `"Scene Not Found"`
- Subtext: `"Looks like this reel got lost in the editing room."`
- Two navigation buttons: `← Back to Home` | `Browse Films`
- Filmstrip decorative element at bottom using CSS repeating pattern

---

### 6. `pages/coming-soon.html` — Pre-Launch / Maintenance Page

- Standalone page (no navbar, minimal footer)
- Full-viewport height, dark cinematic background
- Centered content:
  - Filmmaker logo/name
  - Heading: `"Something New Is Developing"`
  - Subtext: `"A new film is in post-production. Stay tuned."`
  - **Countdown Timer** (JavaScript): counts down to a configurable target date
    ```js
    // TODO: Set your target date here
    const LAUNCH_DATE = new Date('2025-12-01T00:00:00');
    ```
    Display: Days | Hours | Minutes | Seconds — each in a styled box
  - Email capture: `<input type="email" placeholder="Get notified — enter your email">` + Subscribe button
    - `<!-- TODO: Connect to your Mailchimp/ConvertKit list -->` comment
  - Social links row

---

## CSS REQUIREMENTS (`assets/css/style.css`)

### CSS Custom Properties (defined on `:root`)
```css
:root {
  /* Colors */
  --color-bg: #0A0A0A;
  --color-surface: #141414;
  --color-surface-alt: #1E1E1E;
  --color-primary: #E8C547;
  --color-primary-dark: #C4A230;
  --color-text: #F0EDE8;
  --color-text-muted: #8A8580;
  --color-border: #2A2A2A;
  --color-overlay: rgba(0,0,0,0.75);
  --color-error: #E05252;
  --color-success: #52C07A;

  /* Typography */
  --font-display: 'Playfair Display', Georgia, serif;
  --font-body: 'DM Sans', system-ui, sans-serif;
  --font-mono: 'JetBrains Mono', 'Courier New', monospace;

  /* Spacing (8px base grid) */
  --space-xs: 8px;
  --space-sm: 16px;
  --space-md: 24px;
  --space-lg: 48px;
  --space-xl: 80px;
  --space-xxl: 120px;

  /* Layout */
  --container-max: 1280px;
  --container-padding: 24px;
  --border-radius: 4px;
  --border-radius-lg: 8px;

  /* Transitions */
  --transition-fast: 150ms ease;
  --transition-base: 300ms ease;
  --transition-slow: 600ms ease;

  /* Shadows */
  --shadow-sm: 0 2px 8px rgba(0,0,0,0.4);
  --shadow-md: 0 4px 24px rgba(0,0,0,0.6);
  --shadow-lg: 0 8px 48px rgba(0,0,0,0.8);
}
```

### Responsive Breakpoints (use these EXACT values in all media queries)
```css
/* Mobile first — base styles are for mobile */
/* Tablet */     @media (min-width: 640px)  { ... }
/* Desktop */    @media (min-width: 1024px) { ... }
/* Large */      @media (min-width: 1280px) { ... }
```

### Required CSS Rules
- `*, *::before, *::after { box-sizing: border-box; }`
- `html { scroll-behavior: smooth; }`
- Body: `background-color: var(--color-bg); color: var(--color-text); font-family: var(--font-body);`
- `.container { max-width: var(--container-max); margin: 0 auto; padding: 0 var(--container-padding); }`
- All section paddings use `var(--space-xl)` top/bottom (80px), `var(--space-xxl)` on large screens
- All interactive elements: minimum `44px` height/width for touch targets
- Hover transitions on ALL interactive elements: `transition: var(--transition-base)`
- `.sr-only` class for screen-reader-only text
- Grain texture overlay on hero: use a base64 SVG noise filter or CSS `backdrop-filter`
- Horizontal film-strip divider component: alternating dark/slightly-lighter square blocks using CSS `repeating-linear-gradient`

### Component Styles Required
- `.btn` (base button), `.btn-primary`, `.btn-secondary` (outline), `.btn-sm`
- `.card` (film card), `.card:hover` with transform + shadow
- `.badge` (festival laurel/tag pill)
- `.section-label` (small overline text in mono)
- `.section-heading` (H2 with Playfair Display)
- `.divider` (styled `<hr>` — thin gold line)
- `.lightbox-overlay` (for trailer modal)
- `.filter-btn` and `.filter-btn.active`
- `.form-group`, `.form-input`, `.form-error`, `.form-success`
- `.timeline-item`
- `.screening-row` (for festival schedule)

---

## DARK MODE (`assets/css/dark-mode.css`)

Dark mode is the **default** (dark theme is base). Light mode is applied by toggling a class:

```css
/* dark-mode.css — applied when body does NOT have .light-mode */
/* The base style.css already defines dark variables, so this file handles LIGHT MODE */

body.light-mode {
  --color-bg: #F5F2EE;
  --color-surface: #FFFFFF;
  --color-surface-alt: #EDE9E3;
  --color-primary: #B8860B;        /* Darker gold for light bg contrast */
  --color-primary-dark: #8B6508;
  --color-text: #1A1814;
  --color-text-muted: #6B655E;
  --color-border: #D4CFC8;
  --color-overlay: rgba(0,0,0,0.5);
  --shadow-sm: 0 2px 8px rgba(0,0,0,0.08);
  --shadow-md: 0 4px 24px rgba(0,0,0,0.12);
}
```

**OS preference detection (in main.js):**
```js
// Auto-detect OS theme preference on first visit
if (window.matchMedia('(prefers-color-scheme: light)').matches) {
  document.body.classList.add('light-mode');
}
// Persist user preference in localStorage
// TODO: localStorage usage is appropriate here for theme persistence
```

---

## RTL (`assets/css/rtl.css`)

Applied when `<html dir="rtl">`:
```css
[dir="rtl"] .nav-links { flex-direction: row-reverse; }
[dir="rtl"] .hero-content { text-align: right; }
[dir="rtl"] .film-card-info { text-align: right; }
[dir="rtl"] .footer-col { text-align: right; }
[dir="rtl"] .timeline-item { flex-direction: row-reverse; }
[dir="rtl"] .btn-icon { margin-left: 0; margin-right: var(--space-xs); }
/* Add RTL flips for all flex layouts and text alignments throughout */
```

---

## JAVASCRIPT (`assets/js/main.js`)

Write all JS in ES6+. No `var`. No `console.log()`. All functions must have a JSDoc comment above them.

### Required Functions & Behaviors

```js
/**
 * Initializes sticky navbar with scroll-based background change
 */
function initNavbar() { ... }

/**
 * Handles mobile hamburger menu open/close with ARIA state management
 */
function initMobileMenu() { ... }

/**
 * Toggles dark/light mode and persists preference
 */
function initThemeToggle() { ... }

/**
 * Opens trailer lightbox modal with YouTube embed, closes on Escape key or overlay click
 */
function initLightbox() { ... }

/**
 * Filters film grid cards by category using data-category attribute
 * @param {string} category - The category to filter by
 */
function filterFilms(category) { ... }

/**
 * Validates contact form fields, shows inline error messages
 * @returns {boolean} - True if all fields valid
 */
function validateForm() { ... }

/**
 * Handles contact form submission with success/error state
 */
function initContactForm() { ... }

/**
 * Animates countdown timer to target date
 */
function initCountdown() { ... }

/**
 * Copies email address to clipboard with visual confirmation
 */
function initCopyEmail() { ... }

/**
 * Reveals elements on scroll using IntersectionObserver
 */
function initScrollReveal() { ... }

// Initialize everything on DOMContentLoaded
document.addEventListener('DOMContentLoaded', () => {
  initNavbar();
  initMobileMenu();
  initThemeToggle();
  initLightbox();
  initScrollReveal();
  if (document.getElementById('contact-form')) initContactForm();
  if (document.getElementById('countdown')) initCountdown();
  if (document.querySelector('.filter-btn')) {
    document.querySelectorAll('.filter-btn').forEach(btn =>
      btn.addEventListener('click', () => filterFilms(btn.dataset.filter))
    );
  }
});
```

---

## SEO — REQUIRED IN EVERY HTML PAGE `<head>`

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Marcus Holloway — Independent Documentary Filmmaker</title> <!-- Unique per page, max 60 chars -->
<meta name="description" content="Award-winning documentary filmmaker based in [City]. Specializing in human rights, culture, and investigative documentaries. Festival screenings worldwide."> <!-- Unique per page, 150-160 chars -->
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://yourdomain.com/pages/index.html">

<!-- Open Graph -->
<meta property="og:title" content="Marcus Holloway — Documentary Filmmaker">
<meta property="og:description" content="...">
<meta property="og:image" content="assets/images/og-image.jpg">
<meta property="og:type" content="website">

<!-- Structured Data -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Marcus Holloway",
  "jobTitle": "Documentary Filmmaker",
  "url": "https://yourdomain.com",
  "sameAs": ["https://vimeo.com/...", "https://instagram.com/..."],
  "address": { "@type": "PostalAddress", "addressLocality": "City", "addressCountry": "US" }
}
</script>

<!-- Preconnect for Google Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<!-- Font Awesome (Icons) -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<!-- Stylesheets -->
<link rel="stylesheet" href="../assets/css/style.css">
<link rel="stylesheet" href="../assets/css/dark-mode.css">
<link rel="stylesheet" href="../assets/css/rtl.css">
```

---

## ACCESSIBILITY REQUIREMENTS (WCAG 2.1 AA)

Every page must meet ALL of the following:

- **Skip link:** `<a href="#main-content" class="sr-only skip-link">Skip to main content</a>` as FIRST element in `<body>`
- **Main landmark:** `<main id="main-content">` wrapping all page content
- **All images:** `alt="[descriptive text]"` — no empty alt on content images; decorative images use `alt=""`
- **Color contrast:** All text meets 4.5:1 ratio against background (gold `#E8C547` on dark `#0A0A0A` = ✅ passes)
- **Focus styles:** NEVER remove `outline` without replacement. Custom focus: `outline: 2px solid var(--color-primary); outline-offset: 3px;`
- **Keyboard navigation:** Tab order must be logical. Hamburger menu, lightbox, and filter buttons all keyboard accessible.
- **Lightbox/Modal:** `role="dialog"`, `aria-modal="true"`, `aria-label="Film trailer"`, focus trapped inside when open, closes on `Escape`
- **Form fields:** Every `<input>` and `<textarea>` has a `<label>` (use `sr-only` class if visually hidden). Error messages linked via `aria-describedby`.
- **Buttons vs Links:** Use `<button>` for actions (modal open, filter toggle), `<a>` for navigation. Never a styled `<div>` for click interactions.
- **Icon-only buttons:** Must have `aria-label` or visually-hidden text (e.g., `<button aria-label="Open menu">`)
- **Video embeds:** Add `title="[Film name] trailer"` attribute to every `<iframe>`

---

## IMAGE OPTIMIZATION REQUIREMENTS

- All `<img>` tags must have `loading="lazy"` (except hero image which uses `loading="eager"`)
- All `<img>` tags must have explicit `width` and `height` attributes to prevent layout shift (CLS)
- Use `srcset` on hero and featured film images for responsive resolution switching:
  ```html
  <img src="assets/images/hero-bg.jpg"
       srcset="assets/images/hero-bg-640.jpg 640w, assets/images/hero-bg-1280.jpg 1280w"
       sizes="100vw"
       alt="..."
       width="1920" height="1080"
       loading="eager">
  ```
- Add WebP format comment above each image block:
  ```html
  <!-- TODO: Replace with WebP format: hero-bg.webp for better performance -->
  ```
- Use CSS `object-fit: cover` on all film still images inside fixed-aspect-ratio containers

---

## HTML CODE STRUCTURE COMMENTS

Use these section comments consistently in all HTML files:

```html
<!-- ===================================================
     SECTION: NAVIGATION
     =================================================== -->

<!-- ===================================================
     SECTION: HERO
     =================================================== -->

<!-- ===================================================
     SECTION: FEATURED FILM
     =================================================== -->
```

And in CSS:
```css
/* ==============================================
   COMPONENT: Film Card
   ============================================== */
```

And in JS:
```js
/* ==============================================
   MODULE: Lightbox / Trailer Modal
   ============================================== */
```

---

## DOCUMENTATION FILES

### `README.md`
Include:
- Project title and description
- Screenshot placeholder note
- File structure tree
- Quick setup instructions (just open `pages/index.html` in a browser)
- Customization quick-start (5 bullet points)
- Browser support table

### `documentation/installation.md`
Step-by-step setup guide for non-technical users.

### `documentation/customization.md`
How to:
- Change filmmaker name (search for `Marcus Holloway`)
- Change color scheme (edit `:root` variables in `style.css`)
- Add/remove films (copy a `.card` HTML block)
- Add screening dates (copy a `.screening-row`)
- Connect the contact form to Formspree
- Replace Google Maps embed
- Add YouTube trailer IDs

### `documentation/credits.md`
List:
- Google Fonts: Playfair Display, DM Sans, JetBrains Mono (SIL Open Font License)
- Font Awesome 6 (Font Awesome Free License)
- Placeholder images: Lorem Picsum (https://picsum.photos) or describe source
- Any other third-party assets used

---

## PRE-DELIVERY CHECKLIST

Before considering this template complete, verify EVERY item:

- [ ] All HTML pages pass W3C validator (https://validator.w3.org) with zero errors
- [ ] No broken links — every `href` and `src` goes somewhere valid
- [ ] All 6 pages load correctly in Chrome, Firefox, Safari, Edge
- [ ] Navbar hamburger menu works on mobile viewport (375px wide)
- [ ] Dark/Light mode toggle works and persists on reload
- [ ] Contact form validation shows errors and success state correctly
- [ ] Film filter buttons correctly show/hide cards
- [ ] Trailer lightbox opens, plays YouTube embed, closes with Escape and overlay click
- [ ] Countdown timer ticks correctly on `coming-soon.html`
- [ ] All images have `alt`, `width`, `height`, and `loading` attributes
- [ ] Color contrast: run https://webaim.org/resources/contrastchecker/ for body text and gold accent
- [ ] Keyboard: Tab through entire homepage — every interactive element must be reachable and operable
- [ ] `rtl.css` tested by adding `dir="rtl"` to `<html>` — layout should flip correctly
- [ ] No `console.log()` statements anywhere in production JS
- [ ] All TODO comments placed at every customization point
- [ ] Documentation folder is complete and accurate

---

## PLACEHOLDER DATA TO USE THROUGHOUT

Use this consistent placeholder data in all pages to make the template feel real and portfolio-ready:

**Filmmaker:** Marcus Holloway  
**Tagline:** "Telling the stories the world hasn't heard yet"  
**Location:** New York, USA  
**Email:** contact@marcusholloway.com  
**Vimeo:** vimeo.com/marcusholloway  
**Instagram:** @marcus.holloway.films  

**Films (use these 8 placeholder films):**

| Title | Year | Duration | Category | Synopsis |
|-------|------|----------|----------|---------|
| The Forgotten Shore | 2024 | 94 min | Feature Length | A coastal community fights to preserve their way of life against rising seas. |
| Voices in the Dark | 2023 | 22 min | Short Film | Inside a blind choir in rural Appalachia. |
| The Last Archive | 2023 | 67 min | Feature Length | A dying archivist and 70 years of forgotten history. |
| Borderline | 2022 | 48 min | Web Series (Ep.1) | Life at the US-Mexico border told through 6 families. |
| Salt & Soil | 2022 | 18 min | Short Film | Traditional salt farmers in southern France face industrialization. |
| The Migration | 2021 | 82 min | Feature Length | Following three migrant families across three continents over one year. |
| After the Flood | 2021 | 31 min | Short Film | A community rebuilds 18 months after a devastating hurricane. |
| Dispatch | 2020 | 55 min | Feature Length | Three war correspondents. One conflict. Unfiltered. |

**Festival Screenings (placeholder schedule):**

| Date | Festival | Location | Film | Type |
|------|----------|----------|------|------|
| Mar 15, 2025 | SXSW | Austin, TX | The Forgotten Shore | World Premiere |
| Apr 3, 2025 | Hot Docs | Toronto, Canada | The Forgotten Shore | International Premiere |
| May 22, 2025 | Sheffield DocFest | Sheffield, UK | The Forgotten Shore | European Premiere |
| Jun 8, 2025 | Tribeca Film Festival | New York, NY | Voices in the Dark | Short Film Competition |
| Jul 14, 2025 | IDFA | Amsterdam, Netherlands | The Last Archive | Official Selection |
| Sep 2, 2025 | Venice Film Festival | Venice, Italy | The Forgotten Shore | Competition |

---

*End of prompt. Build every file listed. Do not skip any page, section, or feature. Every TODO comment must be placed at the correct customization point. Validate HTML before finishing.*
