# piyushkp27.github.io

Personal academic website, served by GitHub Pages at https://piyushkp27.github.io

The whole site is one hand-written HTML file. There is no build step, no
framework and nothing to install. Edit the file, push, and the site updates
within about a minute.

## Files

| Path | What it is |
|---|---|
| `index.html` | The entire site: content, styles and scripts in one file |
| `Piyush_Prajapati_CV.pdf` | The CV linked from the top-right "CV" button |
| `assets/mri/anat.png` | Anatomical slice shown in the banner |
| `assets/mri/map.png` | Parametric map revealed under the cursor |
| `README.md` | This file |

## Editing

Open `index.html` in any editor (VS Code is fine). Everything you would
normally change is plain text inside the `<main>` section. Search for the
section heading you want (for example `id="publications"`) and edit in place.

Preview locally by opening the file in a browser:

```
open index.html
```

### Add a publication or abstract

Find `<ol class="pubs" id="pubList">` and add a new `<li>` at the position
you want (the list is shown in page order, five at a time). Copy an existing
entry and change the text. Each entry has three attributes that drive the
filters:

```html
<li data-type="abstract" data-year="2027" data-first="1">
  <span class="venue">ISMRM 2027 · Submitted</span>
  <span class="ptitle">Title of the work</span>
  <span class="authors"><b>P. K. Prajapati</b>, A. Kandpal, A. Singh. City, Country.</span>
  <a class="plink" href="https://doi.org/..." target="_blank" rel="noopener">[DOI]</a>
</li>
```

- `data-type`: `journal`, `conference`, `abstract` or `progress`
  (`progress` is used for "Under Review"; it appears under the "In Progress" filter)
- `data-first`: `1` if you are first author, else `0`
- Leave out the `<a class="plink">` line if there is no link yet
- Use `<span class="venue soft">` for a greyed tag such as "Under Review"

### Add a news item

Find `<ol class="news">` inside the About section and add a line at the top:

```html
<li><span class="d">2027</span><span>What happened.</span></li>
```

### Edit the biography or the banner text

- Biography: the four `<p>` paragraphs inside `<div class="bio">`
- The keyword line under the biography: `<p class="interests-line">`
- Banner: the `<div class="eyebrow">`, `<h1>`, `<p class="role">` and
  `<p class="tagline">` inside `<header class="hero">`
- Links in the banner: `<div class="hero-links">`

### Education, experience, teaching, service

Each item is a `<div class="entry">` with this shape:

```html
<div class="entry">
  <div class="top"><span class="title">Title</span><span class="date">2020 – Present</span></div>
  <div class="sub">One-line detail</div>
  <ul><li>Optional bullet</li></ul>
</div>
```

### Update the CV

Replace `Piyush_Prajapati_CV.pdf` with the new PDF, keeping the same file
name, then push. Remember the PDF is public: anything in it (phone number,
referee emails) is downloadable by anyone.

### Replace the banner images

Both images must be the same size and show the same slice, with the
background filled in the banner colour `#0d1b33` so the edges blend. The
current pair is a brain-masked slice at 900×900 px, with the parametric map
displayed over 0–0.1 min⁻¹ on a jet colour scale. The images contain no
identifying information; keep it that way.

### Colours and fonts

Colours are variables at the top of the `<style>` block (`--bg`, `--navy`,
`--blue`, and so on). The font is the system font (SF Pro on Mac and iPhone,
Helvetica or Arial elsewhere); there are no external font or script requests.

## Publishing

```
git add -A
git commit -m "Describe the change"
git push
```

GitHub Pages rebuilds automatically. If a push fails with
"Internal Server Error", that is GitHub, not you; wait a few seconds and push
again. If `git push` asks for a password, use a GitHub personal access token
limited to this repository, or run `gh auth login` once.

## Notes

- The `._*` files that macOS creates on external drives are ignored via
  `.gitignore`. Do not commit them.
- Nothing on the site shows your email address or phone number except the
  CV PDF itself.
