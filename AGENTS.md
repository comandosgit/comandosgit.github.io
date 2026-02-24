## Cursor Cloud specific instructions

This is a Jekyll-powered static website hosted on GitHub Pages (main branch). It serves as a Git commands reference in Portuguese.

### Project structure

- `_config.yml` — Jekyll configuration (site metadata, excludes)
- `_layouts/default.html` — Base HTML layout (head, body wrapper, scripts)
- `_includes/` — Reusable partials: `head.html`, `header.html`, `nav.html`, `footer.html`, `scripts.html`
- `_includes/sections/` — One file per content section (13 files)
- `_data/navigation.yml` — Sidebar navigation data (drives `_includes/nav.html`)
- `index.html` — Main page (front matter + section includes)
- `Gemfile` — Ruby dependencies (Jekyll 4.x, jekyll-seo-tag)

### Running locally

```
bundle install --path vendor/bundle
bundle exec jekyll serve
```

The dev server runs at `http://localhost:4000/` with live-reload on file changes.

### Building

```
bundle exec jekyll build
```

Output goes to `_site/`.

### Linting

No project-defined lint scripts. HTML can be validated with `tidy -q -e _site/index.html` after building.

### CI

The GitHub Actions workflow (`.github/workflows/jekyll-docker.yml`) runs a Jekyll build in a Docker container on pushes/PRs to master.

### Gotchas

- `vendor/` must be in both `.gitignore` and `_config.yml` `exclude:` list, otherwise Jekyll tries to process bundled gems.
- The `_data/navigation.yml` file drives the sidebar navigation; add new sections there and create a matching `_includes/sections/*.html` file.
- Site metadata (title, description, author, GTM ID) is centralized in `_config.yml` and referenced via Liquid variables in includes.
