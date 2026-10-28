# Acts In Action Events & Entertainment

Website for [actsinactionentertainments.com](https://actsinactionentertainments.com/).

A static site: `index.html` plus `logo.png`. No build step is needed, so it can be hosted on GitHub Pages, Netlify, Vercel or any web host.

## Branches

- `main`: the live website. Only merge into it when changes are ready to go public.
- `develop`: work in progress. Make and preview changes here, then merge into `main`.

## Editing content

- **Portfolio:** edit the `PORTFOLIO` array near the bottom of `index.html`. Put photos in an `images/` folder and list their paths in `images: [...]`. The first photo is the cover.
- **Contact details:** search `index.html` for `TODO` to find the placeholders (phone, email, Instagram, service area, stats).
- **Enquiry form:** it currently opens the visitor's email app. Connect it to a form service (Formspree, Netlify Forms, etc.) before launch.

## Preview locally

```bash
python -m http.server 5173
```

Then open http://localhost:5173.
