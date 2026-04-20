# Quick Start — Read Me First

This is everything you need to go from zero to a deployed site today.

## Step 1: Install prerequisites (10 min)

```bash
# Install Quarto from https://quarto.org/docs/get-started/

# Install Python packages for the projects
pip install plotly pandas statsmodels

# Install FontAwesome extension (from inside the project folder)
quarto add quarto-ext/fontawesome
```

## Step 2: Find-and-replace placeholders (15 min)

Search across all files for these strings and replace them. Use your editor's project-wide search (VS Code: Ctrl+Shift+F).

| Placeholder | Replace with |
|-------------|--------------|
| `Lilian Elizabeth Cordova Hernandez` | Your actual name |
| `cordova-lilian` | Your GitHub username |
| `eportfolio` | Your repository name |
| `linkedin.com/in/lilian-cordova-hernandez-916a37232` | Your LinkedIn username (the part after `/in/`) |
| `lilian-cordova-hernandez-916a37232` | Your email |
| `[your field, ...]` etc. | Write your actual content — all bracketed placeholders |

## Step 3: Add your assets (10 min)

Drop these files into the `images/` and `cv/` folders:

- `images/profile.jpg` — a professional headshot (roughly square, 500x500+ recommended)
- `images/favicon.ico` — generate one at [favicon.io](https://favicon.io/)
- `images/logo.png` — a small logo for the navbar (~200x50)
- `cv/cv.pdf` — your CV as a PDF
- `projects/list/thumbnail.jpg` — a cover image for each project (copy the same file twice if you need to, or screenshot the rendered chart later)

## Step 4: First local render (5 min)

```bash
quarto preview
```

This starts a local server. If everything works, you'll see your site at `http://localhost:port`. Fix any errors now before pushing.

## Step 5: Git init and first commit (5 min)

```bash
git init
git add .gitignore .nojekyll README.md _quarto.yml styles.scss
git commit -m "Initial project scaffold: Quarto config, gitignore, styles"

git add index.qmd about.qmd
git commit -m "Add landing page with jolla About template and about page"

git add projects/
git commit -m "Add projects listing and two Python project pages (penguins, gapminder)"

git add reflection.qmd contact.qmd
git commit -m "Add reflection page and contact/references page"

git add images/ cv/
git commit -m "Add profile image, favicon, logo, and CV PDF"
```

## Step 6: Render and push (5 min)

```bash
quarto render

git add docs/
git commit -m "Render site output"

# Connect to GitHub (create the repo on github.com first, empty)
git remote add origin https://github.com/cordova-lilian/eportfolio.git
git branch -M main
git push -u origin main
```

## Step 7: Enable GitHub Pages (2 min)

On GitHub:
1. Go to your repo → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: **main**, Folder: **/docs**
4. Save. Wait 1–2 minutes.
5. Your site is live at `https://cordova-lilian.github.io/eportfolio/`

## Commit checklist for good git history

The rubric rewards incremental commits. As you customise, commit after every meaningful change:

- [ ] "Customise About page with personal background"
- [ ] "Add real CV PDF and update link"
- [ ] "Tune SCSS colour palette to match personal branding"
- [ ] "Expand Reflection with specific debugging story"
- [ ] "Update project descriptions and add thumbnails"
- [ ] "Add third project on [topic]" (if time)
- [ ] "Fix navbar logo sizing"
- [ ] "Proofread and fix typos across all pages"

**Do not squash these into one giant commit at the end.** The rubric explicitly checks for incremental history.

## Rubric quick-check

Before submitting, verify:

- [ ] Live site URL loads without errors
- [ ] All navbar links work
- [ ] CV link opens in a new tab
- [ ] Both Python projects render with charts visible
- [ ] At least 5 commits with descriptive messages
- [ ] `.gitignore` is present and committed
- [ ] `.nojekyll` is present at the repo root
- [ ] Favicon shows in browser tab
- [ ] No broken images or 404s
- [ ] Spell-checked everything

## Common failures and fixes

| Symptom | Fix |
|---------|-----|
| Site 404s after deploy | Check `.nojekyll` exists, Pages source set to `/docs` |
| Python chunks show error | `pip install plotly pandas statsmodels` |
| FontAwesome icons not showing | `quarto add quarto-ext/fontawesome` from project root |
| Logo/favicon missing | Check filenames match exactly (case-sensitive) |
| SCSS not applying | Ensure `- styles.scss` is listed under theme in `_quarto.yml` |
| Listing page empty | Project `.qmd` files must be in `projects/list/` subfolder |
