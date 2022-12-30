---
title: "Github Pages and Github actions"
date: 2022-12-30T17:46:48-05:00
draft: false
author: "Kenneth Quiggins"
---

I ran into a problem with GitHub actions not building my site. I was getting the following error:
```
Error: Error building site: TOCSS: failed to transform "scss/main.scss" (text/x-scss). Check your Hugo installation; you need the extended version to build SCSS/SASS with transpiler set to 'libsass'.: this feature is not available in your current Hugo version, see https://goo.gl/YMrWcn for more information
```
So I did some research on this error and looked at the Hugo documentation. It turns out that I needed to set the `HUGO_VERSION` environment variable to `latest` in my GitHub actions workflow file. I also needed to set the `HUGO_EXTENDED` environment variable to `true`. Because I am using a Hugo theme that uses a git submodule I also added in a line that will update the theme automatically before building the site.
Here is my updated workflow file:

```
name: Build and Deploy Site

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build-and-deploy-site:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v2
        with:
          submodules: true
          fetch-depth: 0

      - name: Update theme
        run: git submodule update --init --recursive

      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: 'latest'
          extended: true

      - name: Build site with Hugo
        run: hugo --minify

      - name: Check HTML
        uses: chabad360/htmlproofer@master
        with:
          directory: "./public"
          arguments: --only-4xx --check-favicon --check-html --assume-extension
        continue-on-error: true

      - name: Deploy to Github Pages
        if: github.event_name == 'push' && github.ref == 'refs/heads/main'
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public

```

