# Golden Cafe Website

A 4-page static site (Home, Menu, About, Contact) built with plain HTML/CSS — no build tools, no frameworks. Ready to push straight to GitHub Pages.

## Files

```
hearth-and-rye/
├── index.html      Home page
├── menu.html        Menu page
├── about.html        About / story page
├── contact.html       Contact page + map + form
├── styles.css         Shared design system
└── README.md
```

## 1. Customize the content

Everything is placeholder text using a fictional bakery, **Hearth & Rye**, at 214 Miller Street. Before publishing, search-and-replace in every `.html` file:

- Business name: `Golden Cafe`
- Address / phone / email in `contact.html`
- Hours (appear on `index.html`, `contact.html`)
- Menu items and prices in `menu.html`
- Story and timeline in `about.html`

In `contact.html`, the embedded map currently searches for "Riverside District." Replace the `src` on the `<iframe>` with your real address, e.g.:
```
https://www.google.com/maps?q=YOUR+ADDRESS+HERE&output=embed
```

To add real photos, drop image files into an `images/` folder and swap the inline SVG illustrations (in `index.html`) for `<img>` tags — the CSS already handles responsive images.

## 2. Put it on GitHub

```bash
cd hearth-and-rye
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git push -u origin main
```

## 3. Turn on GitHub Pages

1. On GitHub, open your repo → **Settings** → **Pages**.
2. Under "Build and deployment," set **Source** to "Deploy from a branch."
3. Set **Branch** to `main` and folder to `/ (root)`, then **Save**.
4. GitHub gives you a live URL after a minute or two, usually:
   `https://YOUR-USERNAME.github.io/YOUR-REPO/`

If you want the site at the root of `YOUR-USERNAME.github.io` (no repo name in the URL), name the repository exactly `YOUR-USERNAME.github.io`.

## 4. The contact form

The form in `contact.html` is front-end only right now — it doesn't send anywhere. GitHub Pages can't run server code, so to actually receive messages, connect it to a free form backend such as:

- [Formspree](https://formspree.io) — add `action="https://formspree.io/f/YOUR_FORM_ID"` and `method="POST"` to the `<form>` tag, remove the `onsubmit` handler.
- [Netlify Forms](https://docs.netlify.com/forms/setup/) — if you host on Netlify instead of GitHub Pages, add `data-netlify="true"` to the form.

## Notes

- Fonts (Fraunces, Karla, Caveat) load from Google Fonts via `<link>` tags — no local font files needed.
- The whole site is responsive down to small phones; no JavaScript is required except the placeholder form handler.
- Colors, type, and spacing all live in `styles.css` under `:root` at the top of the file if you want to adjust the palette.
