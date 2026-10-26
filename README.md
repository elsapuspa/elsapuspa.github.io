# Personal academic website

A minimal, responsive academic profile using plain HTML and CSS. No build tools, dependencies, tracking, or JavaScript are required.

## Files

- `index.html`: all six sections and personal content
- `assets/style.css`: layout, typography, colors, and responsive styles
- `assets/cv.pdf`: clearly labeled placeholder PDF; replace before publishing
- `.github/workflows/pages.yml`: GitHub Pages deployment
- `.nojekyll`: serves the site without Jekyll

## Edit

Search `index.html` for square brackets to find missing personal information. Replace the name, dates, introduction, contact details, and publication/project entries. Only the research interests and thesis context supplied by the owner are included as facts.

Replace the GitHub and LinkedIn homepage URLs with your profile URLs. Add an email link using `mailto:YOUR_EMAIL` once you provide an address.

Replace `assets/cv.pdf` with your real CV, change the button text to “Download CV”, set its `download` filename to `cv.pdf`, and remove the placeholder notices. The bundled PDF is not a real CV.

For design changes, edit the CSS variables at the top of `assets/style.css`. System fonts keep the site fast and independent of external font services.

## Preview

Open `index.html` directly, or run from this folder:

```sh
python3 -m http.server 8000
```

Visit `http://localhost:8000`. Check narrow/mobile and desktop widths and replace all placeholders before sharing.

## Create a public repository and deploy

With the GitHub CLI installed and authenticated, run from this folder:

```sh
git init -b main
git add .
git commit -m "Create academic website"
gh repo create academic-website --public --source=. --remote=origin --push
```

Alternatively, create an empty public repository at GitHub, then initialize and commit as above and run:

```sh
git remote add origin https://github.com/YOUR_USERNAME/academic-website.git
git push -u origin main
```

In the repository, open **Settings → Pages → Build and deployment → Source → GitHub Actions**. Run “Deploy to GitHub Pages” from the Actions tab if necessary. Future pushes to `main` deploy automatically. The workflow publishes only `index.html`, `.nojekyll`, and `assets/`.

A project repository is hosted at `https://YOUR_USERNAME.github.io/academic-website/`. For a root personal site, name the repository `YOUR_USERNAME.github.io`. Relative asset paths support either option.

Repository creation and publication require GitHub access; local files alone do not create a live website.
