# transguide.jp

We're building a transgender-friendly resources database for people living in Japan.

This repository owns the Hugo site, build, and GitHub Pages deployment. It now
uses the Hextra Hugo module, with editable site content living in the
[`transguidejapan/content`](https://github.com/transguidejapan/content)
repository and mounted locally in `content/` during the build.

## Local Setup

First, make sure you have the following dependencies installed:

- node
- npm
- hugo

Then clone the repo. For local development, either clone the content repo into
`content/` or symlink `content/` to your checkout.

```
git clone https://github.com/transguidejapan/content.git content
```

Next, install needed packages and build the site.

```
npm ci
hugo mod get github.com/imfing/hextra@v0.12.0
hugo --gc --minify
```

If you want to run a preview server, run the following:

```
hugo serve -D
```

## Deployment

GitHub Pages deploys from `.github/workflows/pages.yml`. The workflow also listens for `repository_dispatch` events from `content` after approved content changes land on `content/live`.
