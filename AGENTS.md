## Cursor Cloud specific instructions

This is a static HTML/CSS website (no build tools, no package managers, no tests). It serves as a Git commands reference in Portuguese, hosted on GitHub Pages.

### Running locally

Serve files with any static HTTP server from the repo root:

```
python3 -m http.server 8000
```

Then open `http://localhost:8000/` in a browser.

### Linting

There are no project-defined lint or test scripts. HTML can be validated with `tidy -q -e index.html`.

### CI

The GitHub Actions workflow (`.github/workflows/jekyll-docker.yml`) runs a Jekyll build in a Docker container, but the site itself is served as raw static files on GitHub Pages.
