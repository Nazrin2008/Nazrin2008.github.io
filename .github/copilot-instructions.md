# Copilot / AI Agent Instructions for Nazrin.github.io

This repository is a small Jekyll site (GitHub Pages style). Below are the essential facts, conventions, and concrete examples an AI coding agent needs to be productive immediately.

**Big Picture**
- **Static site**: Source files (Markdown, layouts, assets) in the repo are processed by Jekyll into the `_site/` directory. Do not edit files under `_site/`—they are generated output.
- **Build tool**: Jekyll (Gemfile pins `jekyll ~> 4.4.1`). Theme is `minima` but the project includes a custom `_layouts/default.html` which overrides site markup.
- **Key source dirs/files**: `_layouts/default.html`, `_posts/`, `assets/` (CSS, JS, images), `_config.yml`, pages like `index.markdown`, `projects.md.markdown`.

**Common workflows / commands**
- Install Ruby gems (from repo root):

  ```powershell
  bundle install
  ```

- Serve locally (recommended):

  ```powershell
  bundle exec jekyll serve
  ```

  Notes: use `bundle exec` so the Gemfile Jekyll version is used. On Windows this repo already lists `wdm` for file-watching. If you change `_config.yml`, restart the server—Jekyll will not reload `_config.yml` automatically.

- Build for production / debug errors:

  ```powershell
  bundle exec jekyll build --trace
  ```

**Project-specific conventions & patterns**
- Asset linking uses the `relative_url` filter (example in `_layouts/default.html`):

  ```html
  <link rel="stylesheet" href="{{ '/assets/main.css' | relative_url }}">
  <script src="{{ '/assets/main.js' | relative_url }}"></script>
  ```

- Pages use YAML front matter and `layout: page` or default layouts. Example: `projects.md.markdown` begins with:

  ```yaml
  ---
  layout: page
  title: Projects
  permalink: /projects/
  ---
  ```

- Image and asset paths referenced under `assets/` (e.g. `/assets/images/profile.jpg`). Always use `relative_url` when constructing URLs in templates.

- The repo contains both source and a pre-built site under `_site/`. When editing, modify source files in the root and not files under `_site/`.

**Integration points & external deps**
- `Gemfile` controls Ruby gems and Jekyll version. Key entries discovered:
  - `jekyll ~> 4.4.1`
  - `minima ~> 2.5` (theme)
  - group `:jekyll_plugins` includes `jekyll-feed`
  - `wdm` is included for Windows file watching
- GitHub Pages: `_config.yml` has `url: "https://nazrin2008.github.io"` and `baseurl: ""`. The site is intended to be published at that address.

**Debugging guidance**
- If pages do not update locally, stop and restart `bundle exec jekyll serve`. Changes to `_config.yml` require a server restart.
- For build failures, run `bundle exec jekyll build --trace` to get a stack trace.
- Check the markup in `_layouts/default.html` and the `assets/` console output if CSS/JS appear missing. The `relative_url` filter is used to resolve asset paths—ensure `baseurl` and `url` values in `_config.yml` are correct for absolute links.

**Examples of actionable edits**
- To add a new page: create `about.md.markdown` or a file in the root with YAML front matter and a `permalink:` if you want a custom URL.
- To add a project entry: edit `projects.md.markdown` (front matter shown above), commit images to `assets/images/` and reference them with `{{ '/assets/images/<name>' | relative_url }}`.

**Files to inspect for context**
- `_config.yml` — global site settings and plugins
- `Gemfile` — Jekyll and plugin versions; run `bundle install` after changes
- `_layouts/default.html` — site markup, header/footer, asset linking
- `assets/main.css`, `assets/main.js` — custom styles and scripts
- `_posts/` — blog posts (date-prefixed filenames)

If anything in this file is unclear or you'd like more examples (e.g., a short PR template for content edits, or guidance for CI/deploy rules), tell me which section to expand and I will iterate.
