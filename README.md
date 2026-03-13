# Gemini Website Tutorial

This repository contains a small static website that teaches a workflow for building websites and interactive demos with Gemini. The main entry point is a slide-based presentation, with several standalone example pages included under `site/`.

## What is included

- `site/index.html`: the main presentation, "Building Websites with Gemini"
- `site/resume1.html`, `site/resume2.html`, `site/resume3.html`: portfolio/resume examples
- `site/business.html`: business website redesign example
- `site/game.html`: 2D "Cricket Rancher" game example
- `site/3dgame.html`: 3D "Dolphin Dash" game example
- `site/project-planning-text.md`: prompt transcript for the project planner example
- `site/lesson-plan-text.md`: prompt transcript for the lesson plan generator example
- `site/meta/`: screenshots used by the presentation for generated app examples

## Tech stack

This repo is intentionally simple:

- Static HTML files
- Tailwind CSS via CDN
- React via CDN on some pages
- A few pages use additional browser-loaded libraries such as Three.js, HTM, Font Awesome, Lucide, or Babel

There is no build step and no package manager configuration in this repository.

## Running locally

Because the site uses multiple HTML files and relative assets, serve the `site/` directory with a local web server instead of opening files directly.

Example with Python:

```bash
cd site
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Project structure

```text
site/
  index.html                  Main tutorial / presentation
  business.html               Business site demo
  game.html                   2D game demo
  3dgame.html                 3D game demo
  resume1.html                Resume demo
  resume2.html                Resume variant
  resume3.html                3D resume variant
  lesson-plan-text.md         Lesson planner prompt text
  project-planning-text.md    Project planner prompt text
  meta/                       Screenshot galleries used in the presentation
```

## Notes

- The presentation embeds several demo pages with `iframe`s, so keeping the files together under `site/` matters.
- Many pages depend on external CDNs, so an internet connection is required when viewing them.
- The presentation stores some UI state in browser `localStorage`.

## Deployment

This repository is suitable for any static hosting provider. To deploy, publish the contents of `site/` as the site root.
# gemini-canvas-no-code-tutorial
