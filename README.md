# ayeshabulehyeh.github.io

Personal academic homepage. Plain HTML and one CSS file: no build step, no Jekyll.
GitHub Pages serves the `main` branch root as-is (`.nojekyll`).

## Files

- `index.html`: the whole homepage.
- `style.css`: all styling. The accent color is `--accent` at the top.
- `assets/img/profile.jpg`: header photo (square, 480px).
- `assets/img/teasers/`: one image per paper.
- `assets/pdf/Ayesh_Abu_Lehyeh_CV.pdf`: the CV. Replace the file, keep the name.
- `projects/`, `publications/`, `news/`, `cv/`: redirects for URLs from the old site.

The GeoFlow project page at `/geoflow_page/` lives in its own repository
(`AyeshAbuLehyeh/geoflow_page`). Do not create a `geoflow_page/` folder here.

## Common updates

- **News item:** add a `<dt>Mon YYYY</dt><dd>text</dd>` pair at the top of the News list. Keep 6 to 8 items.
- **Paper:** copy an `<article class="pub">` block in `index.html`, edit it, and give the BibTeX block
  a new `id` that matches the button's `aria-controls`.
- **Teaser image:** about 560px wide, JPEG, under 200KB, saved in `assets/img/teasers/`.
  With ImageMagick: `convert figure.png -background white -flatten -resize 560x -strip -quality 88 name.jpg`
- **New photo:** crop to a square, resize to 480px, and overwrite `assets/img/profile.jpg`.
- Update "Last updated" in the footer.

## Preview locally

    python3 -m http.server 8000

Then open http://localhost:8000.

The previous al-folio site is kept on the `al-folio-backup` branch.
