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

## Publishing cheat sheet

Live at https://www.philliplicause.com — GitHub (baewater/personal-website) → Netlify
auto-deploys `main` on every push. Push = upload to GitHub. Pull = download from GitHub.

Every session starts with:

    cd "C:\Users\pmlic\Claude\Claude Code\Personal Website"

**Everyday updates (push straight to main):**

    git switch main          # make sure you're on main
    git pull                 # sync down anything new (usually "Already up to date")
    ...make edits...
    git status               # see what changed
    git add .                # stage it
    git commit -m "What and why"
    git push                 # publish — live on Netlify in ~1 minute

**Bigger changes (pull request route):**

    git switch -c my-change-name        # new branch
    ...edit, git add ., git commit...
    git push -u origin my-change-name   # upload branch
    # open the printed URL, create the PR, merge it on GitHub, then:
    git switch main
    git pull                            # bring the merge back down

**If something looks weird:** `git status` first — it shows your branch and changes.
"not a git repository" means you're in the wrong folder. Site not updating? Check the
Deploys tab in Netlify.
