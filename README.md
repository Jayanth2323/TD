# TinDog Project

TinDog is a small Bootstrap-based demo site that showcases a landing page and pricing cards for a fictional dog dating app.

## Quick status
- Images are included in this repo but may not appear on the page when opened directly in a browser unless paths or a local server are configured correctly. See "Fixing missing images" below for debugging steps.

## How to view the project locally
1. Clone the repo:
   ```bash
   git clone https://github.com/Jayanth2323/TD.git
   cd TD
   ```
2. Open `index.html` in your browser, or run a simple local server (recommended):
   - Python 3: `python -m http.server 8000` then open `http://localhost:8000`
   - VS Code: use the Live Server extension.

## Fixing missing images (common causes & solutions)
If images are not visible on the page, try the following checks in order:

1. Check file paths
   - Use correct relative paths. If images are in an `images/` folder next to `index.html`, use `<img src="images/photo.jpg" alt="...">` (not `/images/photo.jpg` unless you serve from the repo root).
   - For nested folders, adjust the path accordingly, e.g. `assets/images/photo.jpg` or `../images/photo.jpg`.

2. Case sensitivity
   - Git and many web servers are case-sensitive. Ensure the filename and extension match exactly (e.g., `Dog.JPG` is different from `dog.jpg`).

3. Ensure images are tracked by Git
   - Run `git status` to confirm the image files are committed. If not, add and commit them:
     ```bash
     git add images/*
     git commit -m "Add image assets"
     git push
     ```

4. Browser console & network tab
   - Open DevTools (F12) → Console/Network to see 404 errors or path issues when the browser tries to load image files.

5. Serving via a local server
   - Some browsers block file:// requests for certain resources. Use a local server (see "How to view the project locally").

6. CSS background-image paths
   - If images are referenced from CSS, paths are relative to the CSS file location. Example in `styles/main.css`:
     ```css
     .hero { background-image: url("../images/hero.jpg"); }
     ```

7. GitHub Pages (if using)
   - If you use GitHub Pages, make sure paths match the published site root or use absolute paths based on the repo name.

8. File permissions
   - Rare, but ensure the files aren’t corrupted and have readable permissions.

## Example file structure (recommended)

TD/
├─ index.html
├─ README.md
├─ css/
│  └─ styles.css
├─ images/
│  └─ example.jpg
└─ js/
   └─ script.js

## SVGs
- Inline SVGs work well (they're already in the repo). If you move them to separate files, reference them with `<img src="images/icon.svg" alt="icon">` or inline the SVG markup in the HTML.

## Features
- Bootstrap-based responsive layout
- Pricing cards
- Inline SVG icons

## Contributing
Contributions welcome — open a PR or issue describing what you want to change.

## License
If you want to add a license, include a LICENSE file (e.g., MIT).

---

If you want, I can:
- update this README in the repository now,
- or inspect your repo to find the image path mismatches and suggest specific fixes. Which would you prefer?