# app-support — Agent Instructions

## Project Overview

Public support and privacy pages for the iPhone and Apple Watch apps, served by GitHub Pages at <https://evanherve.github.io/app-support/> from the `main` branch root. Each app's App Store Connect Support URL is `https://evanherve.github.io/app-support/<app>/` and its Privacy Policy URL is `https://evanherve.github.io/app-support/<app>/privacy/`. The GitHub repo is `evanherve/app-support` (public).

## Tech Stack

- Static HTML and one shared stylesheet (`assets/style.css`), no build step, no JavaScript
- GitHub Pages (`.nojekyll`, served as-is)

## Package Manager

None.

## Commands

| Purpose | Command |
|---|---|
| Preview locally | `python3 -m http.server 8000` then open http://localhost:8000/ |
| Check the published site | `curl -sI https://evanherve.github.io/app-support/<app>/privacy/` |

## Coding Conventions

- **Layout:** one folder per app, `<app>/index.html` (support) and `<app>/privacy/index.html` (privacy policy); every app is listed in `index.html`
- **Languages:** English first, French in a `<section id="fr" lang="fr">` on the same page; French wording reuses the app's own French UI labels
- **Comments:** No comments in generated code

## Behavioral Rules

- A privacy policy states only what the app's code actually does: read the app's network calls and storage before writing or changing one, and update its effective date on every change.
- These URLs are registered in App Store Connect: never rename or move an app's folder.
- The pages are public: no secrets, tokens, or private addresses.

## Quality Gates

All changes must pass the following before completion:

1. Every page opens in the local preview with working relative links (`../`, `../../assets/style.css`).
2. After pushing, the changed pages return HTTP 200 on GitHub Pages.
