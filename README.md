# ePortfolio

A personal portfolio built with [Quarto](https://quarto.org/), styled with custom Sass, and deployed via GitHub Pages.

## Structure

```
.
├── _quarto.yml           # site config
├── .nojekyll             # required for GitHub Pages
├── .gitignore
├── index.qmd             # landing page (About template)
├── about.qmd             # background, skills, goals
├── reflection.qmd        # what I learned
├── contact.qmd           # contact & references
├── styles.scss           # custom theme
├── images/               # profile pic, favicon, logo
├── cv/                   # CV as PDF
├── projects/
│   ├── index.qmd         # project listing page
│   └── list/
│       ├── penguins.qmd
│       └── gapminder.qmd
└── docs/                 # rendered output (served by GitHub Pages)
```

## Setup

Install [Quarto](https://quarto.org/docs/get-started/) and Python with:

```bash
pip install plotly pandas statsmodels
quarto add quarto-ext/fontawesome
```

## Build

```bash
quarto preview   # local dev server with hot reload
quarto render    # produce final site in docs/
```

## Deploy

1. Push to GitHub.
2. In the repo: **Settings → Pages → Source: main branch, /docs folder**.
3. Site goes live at `https://cordova-lilian.github.io/eportfolio`.

## Attribution

- Palmer Penguins data via the [seaborn-data](https://github.com/mwaskom/seaborn-data) repository (originally Horst, Hill, & Gorman, 2020).
- Gapminder data via `plotly.express.data.gapminder()`.
- Theme built on [Bootswatch Flatly](https://bootswatch.com/flatly/) with custom Sass.
