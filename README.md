# lwc — Lewis William Christie

Personal portfolio site for Lewis William Christie, a Pega Certified Senior System Architect (CSSA) with a passion for UI and UX.

## Features

- Light / dark theme toggle (remembered between visits)
- English / German language toggle
- Scroll-aware side navigation
- Animated "lwc" logo that expands to the full name on hover
- Responsive layout for mobile

## Structure

```
index.html   # page markup, translations and scripts
main.css     # styles and theme variables
assets/      # images (portrait, project thumbnails)
```

## Running locally

It's a static site with no build step. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

then visit http://localhost:8000.

## Deploying

Enable **GitHub Pages** in the repo settings (Settings → Pages → Deploy from branch → `main` / root) and the site will be served at `https://vanilla487.github.io/portfolio/`.
