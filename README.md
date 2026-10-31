# FBnP Wiki

**Preserving the History of Anarchy**

This repository contains the public [FBnP Wiki](https://gms-scanner.github.io/fbnp-wiki/), an archive of First Bots, Now Players and the Player2 SMP world that came before it. The wiki covers players, factions, bases, conflicts, server events, and surviving images. It has the familiar feel of an older Minecraft wiki: straightforward articles, categories, a timeline, galleries, and search.

## How the site works

The wiki is a static site hosted on GitHub Pages. Its pages are generated from JSON files by a small Node script, so there is no database or server to maintain. Visitors can read and search the site; only people with write access to this repository can change its contents.

| Location | What it contains |
| --- | --- |
| `data/articles.json` | Article titles, text, infoboxes, and categories |
| `data/timeline.json` | Entries on the historical timeline |
| `data/galleries.json` | Image descriptions and gallery entries |
| `data/gallery-names.json` | Gallery names |
| `data/categories.json` | Category names |
| `public/images/` | Images used throughout the wiki |
| `public/style.css` | Layout and visual style |
| `public/site.js` | Browser search and navigation behavior |
| `scripts/build.mjs` | Generator for the finished pages |
| `.github/workflows/pages.yml` | GitHub Pages deployment workflow |

The generator writes the finished site to `dist/`. That directory is build output; the files in `data/`, `public/`, and `scripts/` are the source to edit.

## Editing an article

Find the article in `data/articles.json` by its `slug` and update its title, introduction, body, infobox, or categories. Internal article links use the form `[[Player2 SMP]]`. For a new article, give it a unique slug, add its content and categories, then build the site to catch broken links.

To add an image, put the file in `public/images/` and add its caption and gallery entry to `data/galleries.json`. Keep original images and descriptions together so future editors can tell what each picture shows.

Historical claims should be written clearly and checked against the available records. If a date or attribution changes, update the relevant article and timeline entry in the same commit.

## Build locally

You need Node.js. From the repository root, run:

```sh
npm run build
```

This generates the site in `dist/`. To view it locally at its GitHub Pages path, run a static file server from the repository root and open `/fbnp-wiki/` under the served `dist` directory. The build defaults to the project path `/fbnp-wiki/`; set `PAGES_BASE=/` when building for a root domain.

## Publishing and revisions

Every push to `main` runs the [Pages workflow](.github/workflows/pages.yml), builds the wiki, and publishes it to [gms-scanner.github.io/fbnp-wiki](https://gms-scanner.github.io/fbnp-wiki/). Git history records changes to the articles and assets, and an earlier version can be restored with a revert commit. Public readers do not need a GitHub account to browse the wiki.

This is a community history project. Minecraft usernames identify players within the documented server history; they are not invitations to contact or harass anyone.
