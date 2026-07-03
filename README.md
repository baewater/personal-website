# PhillipLicause.com

Not a portfolio. A digital home for a systems thinker. The philosophy is the product.

## Structure (v1)

Three pages, plain HTML + CSS. No framework, no build step, no JavaScript.

- `index.html` — landing: headshot + "I'm Phillip" statement, the AI quote, one CTA
- `how-i-think.html` — who I am and how I operate (my own words)
- `essays/index.html` — essay list; `essays/dishwasher-engineer.html` — the first essay
- `css/style.css` — the entire design system in one file
- `assets/headshot.jpg` — monochrome-treated via CSS, so the source stays color

"Contact" in the nav and the email in the footer both open a Gmail compose draft
(no contact page). The footer LinkedIn icon links to linkedin.com/in/phillip-licause.

## Design rules

- Dark theme: deep blue-black (`#0a1020`), white text, blue accent (`#5b9dff`)
- Reading column ~42rem (56rem on the homepage hero); the writing is the product
- Inter for UI/headings, Newsreader (serif) for long-form prose
- No animations, no effects, nothing that competes with the words

## Adding an essay

1. Copy `essays/dishwasher-engineer.html`, replace the title, meta/OG tags, and the
   paragraphs inside `<div class="prose">`
2. Add a `<li>` to `essays/index.html` — use the essay's opening lines as the excerpt
   (the `essay-excerpt` class fades them out automatically)

## Local preview

`python -m http.server 8720` from this folder (also configured in `.claude/launch.json`),
or just open `index.html` in a browser.

## Deploying

Any static host: GitHub Pages, Netlify, Cloudflare Pages. Upload everything except
`.claude/` and `README.md` (harmless if included). OG tags assume the site lives at
`https://www.philliplicause.com` — update them if the domain differs.
