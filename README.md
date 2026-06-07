# Thien Blog

This repository now contains the Hugo source for `https://thiennguyen56.github.io`.

New builds are generated from `hugo.yaml`, `content/`, and the PaperMod theme submodule.

## Local Development

Install Hugo Extended, initialize the theme submodule, then run the server:

```bash
git submodule update --init --recursive
hugo server
```

## Add Content

Create posts under `content/posts/`. Use language suffixes for translations:

```bash
hugo new posts/my-new-post.en.md
hugo new posts/my-new-post.vi.md
```

English is served at `/`; Vietnamese is served at `/vi/`.

## Comments, Sharing, And Likes

Comments are enabled with Disqus through `disqusShortname` in `hugo.yaml` and `layouts/partials/comments.html`.

Post sharing buttons are enabled with PaperMod's `ShowShareButtons` setting.

Post likes need a backing service because Hugo generates static files. Good options are:

- Use Giscus comments with GitHub Discussions reactions.
- Add a small backend or serverless endpoint for like counts.
- Use a third-party reaction widget.

## Deploy

The GitHub Actions workflow in `.github/workflows/hugo.yml` builds the site with Hugo `0.162.1` and deploys `public/` to GitHub Pages.

In the repository settings, set GitHub Pages to deploy from GitHub Actions.
