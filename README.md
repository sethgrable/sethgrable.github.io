# Personal website — Seth Grable

Static HTML and CSS. No build step, no dependencies, no JavaScript.

## Files

| File | What it is |
|---|---|
| `index.html` | About page — positioning statement, research areas, education, contact |
| `research.html` | The four research threads, written out |
| `publications.html` | Papers, preprints, thesis, talks |
| `teaching.html` | Courses, lecture series, mentoring, awards |
| `style.css` | All styling. Light and dark themes via `prefers-color-scheme` |
| `favicon.svg` | Browser tab icon |
| `cv.pdf` | Your CV, linked from the nav bar |

## Preview locally

    cd site
    python3 -m http.server 8000

Then open <http://localhost:8000>.

## Publish on GitHub Pages


1. Create a public repository named exactly `<your-github-username>.github.io`.
2. Copy the contents of this folder into it (the files themselves, not the `site/` folder).
3. Commit and push to the `main` branch.
4. In the repo, go to **Settings → Pages** and set *Source* to "Deploy from a branch",
   branch `main`, folder `/ (root)`.
5. The site goes live at `https://<your-github-username>.github.io` within a minute or two.

For a custom domain (e.g. `sethgrable.com`): add a file named `CNAME` containing just the
domain, point a CNAME DNS record at `<username>.github.io`, and set the domain under
Settings → Pages.

## Editing

Everything is plain HTML. To add a publication, copy an existing `<li>` block in
`publications.html` and change the text — the `<span class="tag">` element renders the small
coloured label ("Under review", "Invited") and can be deleted if not needed.

To change the accent colour, edit `--accent` (and `--accent-soft`) at the top of `style.css`;
the dark-theme values are in the `@media (prefers-color-scheme: dark)` block below it.

## Deliberate omissions

- **Phone number.** Your CV lists one; it is left off the public site, since a published page
  is scraped widely. Add it to `index.html` under Contact if you want it there.
- **Photo.** No headshot is included. To add one, drop `photo.jpg` in this folder and insert
  `<img src="photo.jpg" alt="Seth Grable" width="150">` inside the `.identity` block in each page
  header, or near the top of the About page.
- **ORCID / INSPIRE-HEP.** Not in the CV, so not linked. Both are worth adding for a hep-th
  profile — INSPIRE in particular, since that is where people in the field will look you up.
