# FBnP Wiki on GitHub Pages

The public wiki is built from `data/articles.json`, `data/timeline.json`, `data/galleries.json`, and the images in `public/images/`. GitHub Pages serves the generated `dist/` files.

## Edit the wiki

Only repository collaborators with write access can change articles. Edit the relevant object in `data/articles.json`, commit it to `main`, and the Pages workflow rebuilds the site. GitHub's commit history records the editor, timestamp, summary, and prior content. Use **Revert** on a commit to restore a prior revision. Images go in `public/images/`, with a matching entry in `data/galleries.json`.

For a local preview, run `npm run build` and serve `dist/` from the configured base path. The default project path is `/fbnp-wiki/`. Set `PAGES_BASE=/` before building for a user site or custom domain.

## Hosting

Create a public `fbnp-wiki` repository under `gms-scanner`, add these files, and select **GitHub Actions** in **Settings → Pages → Build and deployment**. The workflow deploys every push to `main` to `https://gms-scanner.github.io/fbnp-wiki/`.

GitHub Pages has no server process or database. Editing is controlled by repository permissions; search runs in the visitor's browser from the generated article index. Public readers cannot edit the wiki through the site.
