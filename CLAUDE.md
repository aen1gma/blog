# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based personal blog called "Cloning the Goose" (cloningthegoose.com) focused on supercharging personal productivity with AI tools and workflows. The blog is hosted on GitHub Pages and uses the Beautiful Jekyll theme.

## Repository Structure

- `blog/` - The main Jekyll site directory
  - `_config.yml` - Jekyll configuration file
  - `_posts/` - Blog posts in Markdown format with YYYY-MM-DD-title.md naming
  - `_includes/` - Jekyll template partials
  - `_site/` - Generated site (ignored by git)
  - `assets/` - Static assets (images, CSS, JS)
  - `index.md` - Homepage
  - `about.md` - About page

## Development Commands

All commands should be run from the `blog/` directory.

### Setup
```bash
bundle install
```

### Development Server
```bash
bundle exec jekyll serve
```
This starts a local development server, typically at http://localhost:4000

### Build Site
```bash
bundle exec jekyll build
```

### Important Notes
- Always use `bundle exec` when running Jekyll commands to avoid gem version conflicts
- New blog posts should follow the naming convention: `YYYY-MM-DD-title.md` in `_posts/`
- The site uses the Beautiful Jekyll remote theme (daattali/beautiful-jekyll@6.0.1)
- Front matter is required for all pages and posts