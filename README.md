# ayeshabulehyeh.github.io

Source for my academic homepage: <https://ayeshabulehyeh.github.io>

It is a single static page written in plain HTML and CSS. There is no framework, no build step, and no
JavaScript. GitHub Pages serves the `main` branch as it is.

## Credit

The layout follows the well-known academic homepage by [Jon Barron](https://jonbarron.info/)
([source](https://github.com/jonbarron/jonbarron.github.io)): one centered column, a short bio with a photo,
and a publication list with teaser images. If you want a starting point for your own page, his repository is
the original and the best place to begin.

## Using this as a template

You are welcome to reuse the HTML and CSS in this repository for your own page.

1. Fork or copy the repository into one named `<your-username>.github.io`.
2. Edit `index.html`: replace the name, bio, links, news, and publications with your own.
3. Replace `assets/img/profile.jpg` with a square photo, and the images in `assets/img/teasers/` with one
   figure per paper (about 560px wide).
4. Replace the PDF in `assets/pdf/` with your CV and update the link in the header.
5. Change the accent color by editing `--accent` at the top of `style.css`.
6. Remove the `google-site-verification` tag and the `projects/`, `publications/`, `news/`, and `cv/`
   folders. They only exist to redirect old links to my previous site.
7. In your repository settings, open Pages and set the source to "Deploy from a branch", branch `main`,
   folder `/ (root)`.

Please do not reuse the text, photo, CV, or paper figures. Those are mine or belong to the papers they come
from.

## Structure

| Path | Purpose |
| --- | --- |
| `index.html` | The whole page |
| `style.css` | All styling |
| `assets/img/` | Profile photo and paper teaser images |
| `assets/pdf/` | CV |
| `404.html` | Not found page |
| `.nojekyll` | Tells GitHub Pages to serve the files without Jekyll |

## Preview locally

```
python3 -m http.server 8000
```

Then open <http://localhost:8000>.
