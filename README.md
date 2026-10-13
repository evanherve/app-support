# app-support

Public support and privacy pages for the iPhone and Apple Watch apps, served by GitHub Pages at <https://evanherve.github.io/app-support/>. App Store Connect points each app's Support URL and Privacy Policy URL here.

## Layout

| Path | Page |
|---|---|
| `index.html` | List of apps |
| `assets/style.css` | Shared style, light and dark |
| `<app>/index.html` | Support page: contact and FAQ, English then French (`#fr`) |
| `<app>/privacy/index.html` | Privacy policy, English then French (`#fr`) |

## Adding an app

1. Copy `dryway/` to `<app>/` and rewrite both pages for the new app: what it stores, what it sends and to whom.
2. Add the app to the list in `index.html`.
3. Push to `main`. Pages redeploys in about a minute.
4. In App Store Connect, set the Support URL to `https://evanherve.github.io/app-support/<app>/` and the Privacy Policy URL to `https://evanherve.github.io/app-support/<app>/privacy/`.

When a privacy policy changes, update its effective date.
