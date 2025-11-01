# STEMFest Robotics Expo — Single Page Website

This repository contains a single-file, responsive event website for the **STEMFest Robotics Expo 2025**. It's built with HTML5, Tailwind CSS (CDN), the Poppins font, and vanilla JavaScript. The site is designed to match an existing suite of portfolio/studio sites and follows a clean, modern aesthetic.

Key features
- Mobile-first, responsive layout
- Poppins font (weights 400, 600, 700)
- Global styling: deep-blue primary (#1E3A8A), accent blue (#3B82F6), background #F9FAFB, text #111827
- Rounded cards (`rounded-2xl`), soft shadows, hover lift effects, smooth transitions
- Sticky blurred navbar that collapses to a hamburger on mobile
- Hero with Unsplash robotics background and countdown timer (JS)
- Sections: About, Schedule, Teams, Sponsors, Registration, Contact (Formspree), Footer
- Smooth scroll behavior for internal links

File
- `index.html` — the complete site. Open directly in a browser or serve with a simple static server.

Design & style contract
- Font: Poppins (Google Fonts) — weights 400, 600, 700
- Max width and layout: `max-w-6xl mx-auto` with `py-20 px-6` section spacing
- Buttons: rounded-full with gradient from `#1E3A8A` to `#3B82F6`, hover scale + glow

Quick preview (local)
You can preview the page by opening `index.html` in your browser or by running a local static server. From the project root (macOS / zsh):

```bash
# start a simple Python HTTP server and open http://localhost:8000
python3 -m http.server 8000
```

Open `http://localhost:8000` in your browser.

Customization guide

- Update the event date (countdown):
  - Edit the JavaScript near the bottom of `index.html` and set the `eventDate` variable to your event date/time in ISO format or `YYYY-MM-DDTHH:MM:SS`.
  - Example:
    ```js
    // Set your event date/time here:
    const eventDate = new Date('2025-11-15T09:00:00'); // <-- update event date/time here
    ```

- Replace Formspree ID (contact form):
  - In the Contact form element, replace `https://formspree.io/f/your-form-id` with your Formspree endpoint.
  - Example:
    ```html
    <form action="https://formspree.io/f/abcd1234" method="POST">
    ```
  - Note: The form in this project uses a simple POST to Formspree. Ensure your account/form is configured per Formspree docs.

- Replace Registration link (Google Form):
  - In the Registration section update the anchor: `href="https://forms.gle/placeholder"` → your Google Form link.

- Images and logos:
  - Hero, about, and team images use Unsplash placeholders. Replace the `src` attributes with your own image URLs or local assets.
  - For improved performance, optimize images (WebP/AVIF, max-widths) before uploading.

Accessibility & semantics
- Semantic elements (header, main, section, article, footer) are used.
- Form controls include labels (screen-reader-only) and focus styles.
- Add ARIA attributes if you want richer semantics for the hamburger menu or custom components.

Deployment to Netlify

1. Commit and push your repo to GitHub (if not already).
2. On Netlify, choose "New site from Git" and connect your GitHub repository.
3. Branch: `main` (or your default branch).
4. Build settings: none required (static single-file site). Leave the build command blank.
5. Publish directory: `/` (repo root).
6. Deploy — Netlify will host the static HTML immediately.

CI / Production Tailwind (optional)

For a production-optimized build that uses a compiled Tailwind CSS file (smaller final CSS):

1. Initialize Node project and install Tailwind locally.
2. Create a minimal `tailwind.config.js` and a CSS entry that imports Tailwind base/components/utilities.
3. Run a production build that purges unused CSS.

If you'd like, I can add a `package.json`, Tailwind config, and an optimized `dist/` folder.

Troubleshooting & tips
- Countdown shows zeros:
  - Make sure `eventDate` is set to a future date. Check the date format and your timezone.
- Contact form doesn't submit:
  - Replace the Formspree action with your valid Formspree form endpoint.
  - Check the browser console or network tab for errors and CORS issues.
- Styles not appearing:
  - The site uses the Tailwind CDN — ensure your network allows CDN access. For production, compile Tailwind locally to avoid runtime dependencies.

Next steps I can help with
- Replace placeholders with your brand assets and images.
- Add a small build step for Tailwind to generate production CSS (and remove the CDN dependency).
- Wire registration to a real Google Form or integrate a simple backend to collect registrations.
- Add analytics, SEO meta tags, and social sharing cards.

If you'd like any of the above, tell me which one and I will implement it next.

---
Site generated for quick deployment and to match your existing design system. If you want a zipped artifact, production Tailwind, or Netlify config files, I can add them next.
