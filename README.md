[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
![Workflow Status](https://github.com/simongravelle/simongravelle.github.io/actions/workflows/gh-pages.yml/badge.svg)

# Academic template

## Credit

This original template was originally taken from [wowchemy](https://wowchemy.com/), with
some custom CSS adapted from [nickballousite](https://github.com/nballou) webpage. The changed template was adapted from [this site](https://simongravelle.github.io/).
version

## How to build locally

To build locally on your computer, type:

```bash
hugo server
```

## How to modify

After cloning this repository:

- add your own content in the [content](content/) folder,
- modify the custom css script in [assets/scss/custom.scss](assets/scss/custom.scss),
- enter your publications in [content/publication/](content/publication/).
- replace Stella Huang by your name in [layouts/partials/widgets/about.html](layouts/partials/widgets/about.html).

## How to deploy

In Settings, Pages, select:

- Deploy from a branch as Source
- gh-pages, `/(root)` as Branch
