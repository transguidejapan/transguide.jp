# transguide.jp

We're building a transgender-friendly resources database for people living in Japan.

This repository owns the Hugo site, theme, build, and GitHub Pages deployment. Editable site content lives in the [`transguidejapan/content`](https://github.com/transguidejapan/content) repository, mounted locally in `content/` during the build.

## Local Setup

First, make sure you have the following dependencies installed:

- node
- npm
- hugo

Then clone the repo. For local development, either clone the content repo into `content/` or symlink `content/` to your checkout.

```
git clone https://github.com/transguidejapan/content.git content
```

Next, install needed packages and build the site.

```
npm ci
hugo --gc --minify
```

If you want to run a preview server, run the following:

```
hugo serve -D
```

## Deployment

GitHub Pages deploys from `.github/workflows/pages.yml`. The workflow also listens for `repository_dispatch` events from `content` after approved content changes land on `content/live`.
