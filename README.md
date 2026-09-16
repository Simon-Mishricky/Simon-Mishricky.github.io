# simon-mishricky.github.io

Personal academic website. Static HTML and one stylesheet, no build step.

```
index.html        About / landing page
research.html     Working papers, software, research assistance
teaching.html     Teaching record and evaluations
cv.html           Education and supervisors, plus the CV PDF download
assets/styles.css Single stylesheet
assets/favicon.svg
Simon-Mishricky-CV.pdf
.nojekyll         Tells GitHub Pages to serve the files as-is
```

## Viewing it without a web server

Opening `index.html` straight from the folder (double-click) works, including the
cross-fade between pages. Only the hover prefetching needs a real http(s) address,
and that is invisible either way.

## Preview locally

```sh
cd website
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy to GitHub Pages

The CV already points papers at `https://simon-mishricky.github.io/...`, so the site
belongs in the **user site** repository named `simon-mishricky.github.io`, served
from the repository root.

```sh
# from this website/ folder
git init
git add -A
git commit -m "Personal academic website"
git branch -M main
git remote add origin git@github.com:simon-mishricky/simon-mishricky.github.io.git
git push -u origin main
```

Then in the repository, go to **Settings → Pages** and set the source to
`Deploy from a branch`, branch `main`, folder `/ (root)`. The site appears at
`https://simon-mishricky.github.io/` within a minute or two.

If instead you want it at `https://simon-mishricky.github.io/website/`, push this
folder into any repository and adjust the paper links accordingly.

## Things to update before going live

- The job market paper links to `https://simon-mishricky.github.io/APD_Paper.pdf`,
  which is already live. Keep that file at the repository root so the link holds.
- `Simon-Mishricky-CV.pdf` here is a copy of `Version 15`. Re-copy it whenever the
  LaTeX CV changes:
  `cp "../Version 15/Simon-Mishricky-CV.pdf" Simon-Mishricky-CV.pdf`
- Drafts for the two non-JMP papers are currently "available on request" and link to
  a mailto. Swap those for direct PDF links once the drafts are public.
- Optional: add an `og-image.png` (1200x630) and reference it from the `og:image`
  meta tag on each page for nicer link previews.
