# lauramascarell.com

Personal academic site for Laura Mascarell — postdoctoral researcher at GIST.

## Layout

```
.
├── index.html        Single-page site, editorial / serif-led, dusty rose accent
├── styles.css        All styling — CSS custom properties drive the palette
├── assets/
│   └── profile.jpg   Hero portrait (replace with your real photo)
└── .nojekyll         Disables Jekyll on GitHub Pages — site is served as static HTML
```

No build step, no dependencies — just static files served by GitHub Pages.

## Local preview

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy

Commit and push to the `main` branch of `lmascarell/lmascarell.github.io`. GitHub
Pages serves it at `https://lauramascarell.com` automatically.

The `.nojekyll` file prevents GitHub from running Jekyll on the repo, which
matters because the previous version of the site was Jekyll-based; we now ship
plain static HTML/CSS and want it served as-is.

## Replacing the portrait

Drop your photo in at `assets/profile.jpg`. Square images at ~400×400 work best,
but any aspect ratio is fine — the CSS uses `object-fit: cover` to crop into the
hero frame. You can swap between portrait styles (square / circle / large /
duotone) by changing `data-portrait="…"` on the `<body>` element in
`index.html`.

## Other body data-attributes you can tweak

- `data-motif="grain"` — also: `dots` | `grid` | `rail` | `none`
- `data-portrait="square"` — also: `circle` | `large` | `duotone`
- `data-bg="white"` — informational; the actual background color is driven by
  `--bg` in `styles.css`

## Editing publications, talks, contact

Plain HTML — search for `<li class="pub">` and `<li class="talk">` in
`index.html` and add/remove entries. Older publications use `data-extra` so
they're collapsed behind the "Show earlier publications" button.
