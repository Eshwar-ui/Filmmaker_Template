# Customization Guide

## 1) Replace Demo Identity
Search and replace `Marcus Holloway` across all HTML files.

## 2) Update Navigation
Default menu structure:
- Home (dropdown)
  - Home 1
  - Home 2
- About
- Services
- Contact

## 3) Update Colors and Typography
Edit CSS variables in `assets/css/style.css` under `:root`.

## 4) Replace Media
- Replace demo image URLs with your own images.
- Prefer WebP for production.
- Keep alt text descriptive.

## 5) Contact Form Integration
Use a Formspree endpoint in `pages/contact.html`:
```html
<form id="contact-form" action="https://formspree.io/f/YOUR_ID" method="POST">
```

## 6) Newsletter Integration
Replace newsletter form handlers with Mailchimp/ConvertKit embed or API logic.

## 7) Map Integration
Replace the Google Maps iframe source in `pages/contact.html`.

## 8) Video Integration
Replace demo `data-lightbox` and iframe YouTube IDs with project-specific IDs.

## 9) SEO Checklist
For every page:
- Unique `<title>`
- Unique meta description
- Correct canonical URL
- Open Graph meta tags
- JSON-LD structured data

## 10) Accessibility Checklist
- Keyboard reachable controls
- Visible focus states
- Valid heading structure
- Sufficient color contrast
- Form labels and error text
