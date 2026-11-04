# Long Branch Church website

The site at [longbranchchurch.org](https://www.longbranchchurch.org/) is built with [Hugo](https://gohugo.io/) and published by GitHub Pages. Every push to `main` rebuilds and publishes it automatically (see `.github/workflows/hugo.yml`).

## Making common edits

| To change… | Edit this file |
|---|---|
| Service times, home page headline, "family" cards, home verse | `content/_index.md` (top section) |
| Home page "Who we are" paragraph | `content/_index.md` (below the `---`) |
| Address, phone, email, social and Google Drive links | `config.toml` → `[params]` |
| Top menu | `config.toml` → `[[menu.main]]` |
| Plan a Visit / Kids / Contact / Giving pages | `content/<page>/index.md` |
| Colors, fonts, spacing | `assets/css/site.css` |
| Logos and photos | `static/img/brand/`, `static/img/photos/` |

Handy shortcodes inside page content:

```
{{</* button href="https://..." */>}}Button text{{</* /button */>}}
{{</* verse ref="John 3:16" */>}}Verse text{{</* /verse */>}}
{{</* columns */>}} left side {{</* column */>}} right side {{</* endcolumns */>}}
```

## Branding

Colors and logos follow the 2026 LBC Brand Guidelines. Proxima Nova is the brand font; the site uses the free Google font **Figtree** as a close match. If the church has an Adobe Fonts account, add the Proxima Nova kit link to `layouts/_default/baseof.html` and it will be used automatically.

## Preview locally

1. [Install Hugo](https://gohugo.io/installation/) (extended, v0.124+).
2. From this folder run `hugo server`.
3. Open http://localhost:1313. The page refreshes as you save.
