# Handover: Acts In Action website

Read this file before making any changes. It records the decisions the owner has already made, so you don't undo them or ask about them again.

## Briefing

**The client.** Acts In Action Events & Entertainment provides entertainment for events: DJs, live bands and vocalists, dancers, MCs and hosts, children's entertainment (magicians, face painting, balloon art, costume characters) and specialty acts (fire and LED performers, stilt walkers, photo booths). Their clients book them for weddings, corporate events, birthdays, festivals, cultural celebrations, school events and private parties. The logo's tagline is "Get your entertainment on".

**The domain.** actsinactionentertainments.com currently shows only a "Coming soon" page. This repository is the site that will replace it. Apart from the logo, the owner hasn't provided any real company information yet, so all content is placeholder copy written to be realistic.

**The site.** A single static page with no build step and no framework:

| File | Purpose |
|---|---|
| `index.html` | The whole site: HTML, CSS in a `<style>` block, JS in a `<script>` block |
| `logo.png` | Owner-supplied logo, 150×150, white artwork on a black square |
| `README.md` | Short guide for humans |
| `HANDOVER.md` | This file |

Page sections in order: header → hero (headline and numbered list of services) → scrolling white ticker of event types → Services (6 cards) → Events (8 cards on a light background) → Portfolio (filterable grid with a detail popup) → Why Us and How It Works → red call-to-action banner → Contact (details and enquiry form) → footer.

## Rules you must follow

### Branches and Git
1. **`main` is the live website. Never commit to `main` directly.** Do all work on `develop`, or on a feature branch created from `develop`.
2. Merge `develop` into `main` **only when the owner explicitly says the changes are ready to go live.**
3. Ask before pushing, force-pushing, rewriting history or deleting branches.
4. Remote: `https://github.com/Keensly11/acts-in-action-website`.

### Design (decided by the owner, so don't change it without asking)
5. **Colours:** black (`#000000`), white and greys, with **red** (`#d7262f`, hover `#b51d25`) as the only accent. A blue accent was tried and rejected. The accent lives in the CSS variable `--accent-color`, so use the variable rather than hard-coding colours.
6. **No emojis anywhere.** The owner wants it to look professional. Use simple inline SVG line icons, or numbers like 01 and 02, instead.
7. **Fonts:** Archivo (headings, uppercase, weight 800) and Inter (body), loaded from Google Fonts.
8. **Style:** sharp corners (no rounded cards), thin 1px dividers, bold uppercase headings, and red used sparingly for one key word in each heading, buttons and small details.
9. **Logo:** use `logo.png` as supplied in the header and footer. The owner has accepted its low resolution. **Don't use it as a large background watermark.** That was tried and looked bad. The red banner uses a pure-CSS texture instead (spotlight beams plus faint stripes).
10. Keep the page background pure black so the logo's black square blends in.

### Content
11. **Don't invent real-looking facts:** no fake reviews or testimonials, client names, phone numbers, addresses or awards. Clearly mark placeholders. Real details come from the owner only.
12. Placeholder contact details are marked with `TODO` comments in `index.html`.
13. Portfolio projects are data in the `PORTFOLIO` array near the bottom of the script. A project with `images: []` shows a grey placeholder. Add real projects by editing that array, not the HTML.

### Quality checks before every hand-off
14. Check desktop and phone width (375px). **There must be no sideways scrolling on a phone.** Earlier bugs: hidden form checkboxes positioned relative to the page, and a headline sized with `vw` units that widened the layout. Absolutely positioned children need a positioned parent.
15. Check that the mobile menu, portfolio filters, project popup (open, thumbnails, close) and enquiry form still work.
16. Respect `prefers-reduced-motion`. Scroll-reveal elements use the `.reveal` class, but only for elements present when the page loads. Cards created by JavaScript, like the portfolio, must not use `.reveal`.

### Previewing
17. Serve the folder locally, for example `python -m http.server 5173`, and open http://localhost:5173. No build step is needed.

## To-do (next steps)

**Waiting on the owner:**
- [ ] Real contact details: phone or WhatsApp, email, Instagram handle and service area (city or region).
- [ ] Real numbers for the hero stats (currently 500+ events, 50+ performers, 10+ years, all made up).
- [ ] Social links for Instagram, Facebook and TikTok. They currently point to the platforms' home pages.
- [ ] Portfolio content: title, category, venue, city, date, guest count, acts provided, description and photos for each event. Put the photos in an `images/` folder.
- [ ] Confirm the services and event types match what the company actually offers. They were assumed.
- [ ] Optional: a higher-resolution logo (large PNG with a transparent background, or SVG).

**Technical work before launch:**
- [ ] Connect the enquiry form to a real form service (Formspree, Netlify Forms, etc.). It currently opens the visitor's email app using `BOOKING_EMAIL` in the script.
- [ ] Choose hosting (GitHub Pages, Netlify or Vercel), deploy from `main` and point actsinactionentertainments.com at it.
- [ ] Optimise portfolio photos for the web (resize to about 1600px wide and compress, or use WebP).
- [ ] SEO and sharing: Open Graph and Twitter meta tags with a share image, a proper favicon set, `robots.txt` and `sitemap.xml`.
- [ ] Optional ideas, only if the owner asks: real event photos in the hero, a testimonials section (with real reviews only), a privacy policy page.

## History of decisions
- **v1:** a colourful gradient design with emojis. The owner rejected it as not professional.
- **v2:** black and white with a red accent and no emojis. Accepted.
- Blue accent tried, then switched back to red.
- The owner's logo replaced the placeholder "AIA" mark. The logo watermark in the red banner was replaced with a CSS spotlight texture.
- Portfolio section added with placeholder projects, waiting for real content.
- Repository created with `main` (live) and `develop` (work in progress).
