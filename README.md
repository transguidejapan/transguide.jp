# transguide.jp

We're building a transgender-friendly resources database for people living in Japan.

This repository owns the Hugo site, theme, build, and GitHub Pages deployment. Editable site content lives in the [`transguidejapan/site-content`](https://github.com/transguidejapan/site-content) repository, mounted here as `submodules/site-content`.

## Local Setup

First, make sure you have the following dependencies installed:

- node
- npm
- hugo

Then clone the repo. You will also need to ensure that the content submodule is pulled and up-to-date.

```
git submodule update --init --recursive
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

GitHub Pages deploys from `.github/workflows/pages.yml`. The workflow also listens for `repository_dispatch` events from `site-content` after approved content changes land on `site-content/main`.
