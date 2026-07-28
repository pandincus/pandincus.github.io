# My Gaming Journal

Live at: https://pandincus.github.io/

A Hugo site using the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme,
deployed automatically to GitHub Pages via GitHub Actions on every push to `main`.
Comments are handled by [giscus](https://giscus.app) (backed by GitHub Discussions).

## Writing a new post

1. Open this folder in VS Code, then open the integrated terminal (`` Ctrl+` ``).

2. Create a new post:
   ```bash
   hugo new content posts/some-post-name/index.md
   ```
   This creates a **page bundle** — a folder containing `index.md` plus whatever
   images/GIFs belong with that post. New posts start as drafts (`draft = true` in
   the front matter), so they won't appear on the live site until you publish them.

3. Write the post in `content/posts/some-post-name/index.md`. Drop screenshots or
   GIFs into that same folder (drag into VS Code's file explorer, or copy via
   Windows Explorer), then reference them in the Markdown like:
   ```
   {{< figure src="screenshot.png" alt="..." caption="..." >}}
   ```

4. Preview it for real (not just VS Code's generic Markdown preview) by running,
   in the integrated terminal:
   ```bash
   hugo server -D
   ```
   Then open http://localhost:1313/ — it live-reloads as you save, rendering with
   the actual theme. The `-D` flag includes drafts. Leave this running in one
   terminal tab while you write.

5. When it's ready to go live, remove `draft = true` (or set it to `false`) in the
   front matter, then publish:
   ```bash
   git add -A
   git commit -m "New post: whatever it's about"
   git push
   ```
   (Or use VS Code's Source Control panel — stage, commit, push with buttons,
   same effect.) GitHub Actions builds and deploys automatically; the live site
   updates within about a minute.

## Project structure

- `content/posts/` — blog posts, one folder per post (page bundles)
- `content/archives.md` — the /archives/ listing page
- `hugo.toml` — site config: title, description, menus, giscus IDs, etc.
- `layouts/partials/comments.html` — the giscus embed (overrides the theme's default)
- `themes/PaperMod/` — the theme, added as a git submodule
- `.github/workflows/hugo.yml` — builds and deploys to Pages on every push to `main`

## Comments

Already fully wired up — giscus is configured in `hugo.toml` under `[params.giscus]`
and mapped to the "Announcements" Discussions category on this repo. Nothing to do
here for new posts; comments just work.

## One-time setup (already done, for reference)

- Repo: `pandincus/pandincus.github.io` (public — required for both Pages on the
  free plan and for giscus to authenticate commenters)
- Pages source: Settings → Pages → Build and deployment → GitHub Actions
- Discussions: enabled under Settings → General → Features
- giscus app installed: https://github.com/apps/giscus
