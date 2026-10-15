# Personal website — Alejandra C. Hernández

A hand-designed, single-page academic site. No build step, no framework: one HTML file,
one CSS file, a few lines of JavaScript. Hosted for free on GitHub Pages.

```
website/
├── index.html            all the content (edit this)
├── css/style.css         design: colours, fonts, layout
├── js/main.js            dark-mode toggle, mobile menu, active nav link
└── assets/
    ├── photo.jpg               portrait (from the 2021 CV, replace when you like)
    └── photo-placeholder.svg   fallback, can be deleted
```

## 1. Before publishing — fill in the TODOs

Search `index.html` for `TODO`. Each one is a place where I could not know the right value:

| Item | Where | What to do |
|---|---|---|
| Photo | `assets/photo.jpg` | Currently the portrait from your 2021 CV. Replace with a newer 4:5 photo when you have one |
| Google Scholar URL | hero pills, publications footer, contact card | Replace `href="#"` |
| LinkedIn URL | hero pills, contact card | Replace `href="#"` |
| CV | hero (commented out) | The 2021 CV is outdated and has your home address and phone numbers, so it is **not** linked and `.gitignore` keeps it out of the repository. Make a public-safe PDF, save as `assets/cv.pdf`, and remove the comment markers |
| ICRA 2026 workshop PDF | publications | Put the PDF in `assets/papers/` and link it |
| CVPR 2027 workshop | news + activities | Add the official title and URL once public |
| ECCV 2026 news item | news | Keep, edit or delete |
| Reviewer line | activities | Lists IROS 2019–2020 and ICRA 2020 from the CV; add venues since 2021 |
| Postal address | contact | Verify |

Everything else (bio, background, publications, patents, teaching) was written from your
2021 CV, your public record (OpenAlex, ORCID) and our notes. Read it once and adjust wording you don't like.

## 2. Preview locally

Open `index.html` in a browser (double-click). That's it. Fonts load from Google Fonts,
so you need internet for the exact typefaces; offline you get a fallback.

## 3. Publish on GitHub Pages (about 10 minutes, once)

**Concept.** GitHub Pages serves the files in a repository as a website. If the repository
is named `alejandrachernandez.github.io`, the site appears at `https://alejandrachernandez.github.io/`.
Every later edit is: change the file, push, wait a minute, refresh.

1. Sign in to GitHub as `alejandrachernandez`.
2. Create a new **public** repository named exactly `alejandrachernandez.github.io`.
   Leave it empty (no README, no .gitignore).
3. From this folder, run:

   ```bash
   cd ~/workspace/website
   git init
   git add .
   git commit -m "Personal website"
   git branch -M main
   git remote add origin https://github.com/alejandrachernandez/alejandrachernandez.github.io.git
   git push -u origin main
   ```

   GitHub will ask you to log in. Use a personal access token or the browser login flow.
4. On GitHub: repository → **Settings** → **Pages** → Source: *Deploy from a branch*,
   branch `main`, folder `/ (root)` → Save.
5. Wait one or two minutes, then open `https://alejandrachernandez.github.io/`.

### Updating the site later

```bash
cd ~/workspace/website
# edit index.html
git add . && git commit -m "Add new paper" && git push
```

### Optional: your own domain

If you later buy e.g. `alejandrahernandez.org`, add a file named `CNAME` containing the
domain, and point the domain's DNS at GitHub Pages (Settings → Pages shows the records).

## 4. Editing cheatsheet

* **Add a news item**: copy one `<li>` inside `<ul class="timeline">`, newest first.
* **Add a paper**: copy one `<li class="pub">` block under the right `<h3 class="pub-year">`.
  Your name is bolded with `<b>…</b>`.
* **Change colours**: `css/style.css`, the `:root` block. `--accent` is the teal.
* **Change fonts**: the Google Fonts `<link>` in `<head>` and `--font-display` / `--font-body`.
* **Dark mode** follows the visitor's system setting; the moon button overrides it.

## 5. Why not al-folio / Jekyll like Michele and Nicolas?

al-folio is a good template, but it needs Ruby, Jekyll and a build step; small changes
can break the build, and the result looks like hundreds of other academic pages. This site
is plain HTML you can read and edit with any text editor, loads fast, and is yours to
restyle. If you ever want a blog or many sub-pages, al-folio becomes worth it; for a
profile page it is not.
