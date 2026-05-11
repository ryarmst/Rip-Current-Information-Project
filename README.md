# Rip Current Information Project Website

Static website for the Rip Current Information Project, a Canadian non-profit focused on Great Lakes water safety and rip current awareness.

The site is built with Eleventy, Nunjucks, vanilla CSS, and minimal vanilla JavaScript. It deploys to GitHub Pages through GitHub Actions.

## Local Development

1. Install dependencies.

```bash
npm install
```

2. Start the local development server.

```bash
npm start
```

3. Build the production site.

```bash
npm run build
```

Eleventy outputs the built site to `_site/`.

## Project Structure

- `src/` contains all site pages, templates, data, assets, and posts.
- `src/_includes/` contains reusable Nunjucks layouts and components.
- `src/_data/site.json` controls the site name, description, navigation, social links, email, and donation URL.
- `src/news/` contains Markdown news posts.
- `src/assets/` contains CSS, JavaScript, images, and future downloads.
- `.github/workflows/deploy.yml` builds and deploys the site to GitHub Pages.

## How to Update the Site

### Adding a News Post

Create a new Markdown file in `src/news/` named with this format:

```text
YYYY-MM-DD-post-title.md
```

Add this front matter at the top:

```yaml
---
title: "Post Title"
date: YYYY-MM-DD
author: "Nathan MacIntyre"
excerpt: "One sentence summary."
tags: news
---
```

Write the post body below the front matter using Markdown.

### Editing Page Content

Edit the corresponding `.njk` file in `src/`.

For example:

- Home: `src/index.njk`
- About: `src/about.njk`
- Rip Currents 101: `src/rip-currents-101.njk`
- Resources: `src/resources.njk`
- Contact: `src/contact.njk`

### Adding Downloadable Files

Commit PDFs or other downloadable files to:

```text
src/assets/downloads/
```

Then add or update the matching link entry on `src/resources.njk`.

### Deploying

Push or merge changes to `main`.

GitHub Actions will install dependencies, build the site, and publish `_site/` to the `gh-pages` branch automatically.

### GitHub Pages Setup

This is a one-time repository setting.

In GitHub, go to Settings -> Pages and set the source to:

```text
gh-pages branch, root directory
```

After that, deployments happen automatically on push or merge to `main`.

## Logo Notes

The current header uses `src/assets/images/logo-placeholder.png`.

The logo requires a version with a dark or transparent background suitable for both light and dark contexts. A color variant should be created before launch.

Replace the placeholder image before launch and keep meaningful `alt` text in the header template.
