# Ensō — a new tab page for Zen Browser

A quiet, glass-panelled new tab page built to sit *inside* Zen Browser's own transparency rather than fight it — designed alongside the [Zen Internet](https://github.com/frostybiscuit/transparent-zen) extension and Zen's native Mica/Acrylic window transparency.

<p align="center">
  <img src="preview.png" alt="Preview of the Ensō new tab page" width="720">
</p>

*(Drop a screenshot named `preview.png` next to this README to make the image above show up.)*

## Features

- **Transparent by default** — the page background is left empty so Zen's own blur/tint (Mica, Acrylic, or Zen Internet) shows straight through. A one-tap "Soft gradient" fallback is built in for setups without OS-level transparency.
- **Ensō mark** — three concentric hand-drawn rings, echoing Zen's own ringed logo, draw themselves in on load.
- **Elegant search bar** — glass pill with Google / DuckDuckGo / Bing / Startpage / Kagi, typing a bare domain navigates directly instead of searching.
- **Duck AI pill** — a separate sparkle button next to the search bar that always routes your query to [Duck AI](https://duck.ai), independent of whichever engine is selected for Enter.
- **Editable greeting** — click it to add your name; combines with a time-of-day greeting.
- **Widgets** — Quick Links, Notes, and a rotating daily line — each toggleable, all persisted.
- **Light & dark themes** ("Washi" / "Ink"), keyboard shortcut `/` to focus search, respects `prefers-reduced-motion`.

All personalization (greeting, links, notes, theme, engine, widget visibility) is saved in browser cookies on the page's own origin — nothing is sent anywhere.

## Hosting on GitHub Pages

1. Push `zen-newtab.html` (rename it to `index.html` if you want it at the root of your Pages site) to a repo.
2. In the repo, go to **Settings → Pages**, set the source branch (usually `main`) and folder (`/root` or `/docs`).
3. GitHub will publish it at `https://<your-username>.github.io/<repo-name>/`.
4. Wait a minute or two for the first deploy, then visit the URL to confirm it loads.

> Cookies are scoped per-origin, so your saved links/notes/greeting will persist for that `github.io` URL specifically.

## Using it as your Zen Browser new tab page

Zen normally uses the URL bar itself instead of a dedicated new tab page, so to point new tabs at this page you'll need a small extension that overrides the new tab URL — for example **New Tab Override** (available on the Firefox Add-ons store, which Zen supports since it's Firefox-based):

1. Install the **New Tab Override** extension.
2. In its settings, choose "Custom URL" and paste your GitHub Pages link (e.g. `https://<your-username>.github.io/<repo-name>/`).
3. Open a new tab to confirm it loads.

If you're also running the **Zen Internet** extension or have Mica/Acrylic enabled in `about:config`, leave the background setting on this page as **Transparent** (the default) so the two layer together correctly. If colors look flat or you're not using either, switch to **Soft gradient** in the page's own settings (gear icon, top right).

## Customizing

Everything lives in one file, so it's easy to tweak:

- **Colors / type** — CSS custom properties at the top of the `<style>` block (`--accent`, `--panel`, fonts, etc.) for both the `dark` and `light` themes.
- **Search engines** — the `engines` object in the script, add or remove entries as needed.
- **Daily lines** — the `lines` array near the bottom of the script.
- **Default widgets** — the `widgetPrefs` fallback object controls what's shown before a visitor changes anything.

## License

Use it, fork it, reshape it for your own setup. But whatever you do, DON'T FORK IT, CHANGE IT A TINY BIT, AND MAKE MONEY OFF OF IT! Forks CANNOT CONTAIN ADS! Forks must not be used for commercial purposes. Ur welcome! 
