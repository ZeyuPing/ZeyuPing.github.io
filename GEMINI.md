# GEMINI.md

## Project Overview

**al-folio** is a simple, clean, and responsive Jekyll theme designed specifically for academics. It supports a wide range of features including a blog with Distill-style layouts, automated publication lists from BibTeX, a programmatic CV, and a dark/light mode.

- **Technology Stack:** Jekyll (Ruby), Liquid, SCSS, BibTeX (via `jekyll-scholar`), MathJax, Bootstrap.
- **Key Features:**
  - Automated publications from `_bibliography/papers.bib`.
  - Programmatic CV via `assets/json/resume.json` or `_data/cv.yml`.
  - Collections for news items (`_news/`) and projects (`_projects/`).
  - Support for Jupyter Notebooks, Mermaid diagrams, and TikZ figures.
  - Light/Dark mode with automatic detection.

## Building and Running

### Using Docker (Recommended)

The project provides a Dockerized environment for consistent development.

- **Start the site:**
  ```bash
  docker compose pull
  docker compose up
  ```
- **Slim version:**
  ```bash
  docker compose -f docker-compose-slim.yml up
  ```
- **Access the site:** `http://localhost:8080`

### Local Setup (Ruby)

Ensure you have Ruby and Bundler installed.

- **Install dependencies:**
  ```bash
  bundle install
  ```
- **Run the development server:**
  ```bash
  bundle exec jekyll serve
  ```
- **Access the site:** `http://localhost:4000`

### Optional: Python/Jupyter Support

- **Install Jupyter:**
  ```bash
  pip install jupyter
  ```

## Development Conventions

### Content Management

- **Publications:** Managed in `_bibliography/papers.bib`.
- **CV:** Update `assets/json/resume.json` (JSON Resume standard) or fallback to `_data/cv.yml`.
- **News:** Add Markdown files to `_news/`.
- **Projects:** Add Markdown files to `_projects/`.
- **Blog Posts:** Add Markdown files to `_posts/` using the standard Jekyll naming convention (`YYYY-MM-DD-title.md`).
- **Static Pages:** Main pages are located in `_pages/`.

### Formatting and Quality

- **Code Formatting:** The project uses Prettier with a Liquid plugin.
  ```bash
  npx prettier --write .
  ```
- **Link Checking:** Automated via `lychee` in GitHub Actions.
- **Styling:** Customizations should be made in `_sass/_themes.scss` or `_sass/_variables.scss`. Global theme color is defined in `_sass/_themes.scss`.

### Configuration

- **Main Config:** `_config.yml` contains all site-wide settings, including social links, analytics, and plugin configurations.
- **Socials:** Managed in `_data/socials.yml`.
- **Navigation:** The navigation bar is automatically generated from pages in `_pages/` based on their `nav: true` and `nav_order` front matter.

## Key Directory Structure

- `_bibliography/`: BibTeX files for publications.
- `_data/`: YAML data files (CV, coauthors, venues, etc.).
- `_includes/`: Reusable Liquid components.
- `_layouts/`: Page templates (about, bib, post, etc.).
- `_news/`: News items displayed on the homepage.
- `_pages/`: Main site pages.
- `_posts/`: Blog posts.
- `_projects/`: Project pages.
- `_sass/`: SCSS stylesheets.
- `assets/`: Static assets (images, PDFs, JSON, JS).
- `bin/`: Utility scripts (deployment, scholarship updates).
