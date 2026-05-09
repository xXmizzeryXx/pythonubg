# pythonubg
### Eclipse Suite

A minimal, dark-themed browser interface built for the Eclipse Suite. Python provides a proxied browsing experience through a custom Cloudflare Worker backend (Flux), a games library, and a clean settings system — all from a single HTML file.

---

## Features

- **Proxied browsing** — every URL is routed through the Flux Worker, rewriting HTML, JS, CSS, and cookies on the fly so sites load correctly inside the iframe
- **In-page browser modal** — navigate without leaving the tab; the browser panel has a chrome bar, back/forward/refresh, address bar, loading indicator, and a status bar
- **SPA navigation tracking** — the injected runtime fires `postMessage` events on `pushState` / `replaceState` so the address bar stays in sync during single-page app navigations
- **Title sync** — the proxied page's `document.title` is reflected in the browser status bar in real time
- **Games panel** — powered by [Lumin SDK](https://github.com/luminsdk/script), loads a full game library in a searchable grid
- **Settings panel** — toggles for glassmorphism, grid overlay, animations, safe search, and sound effects; persisted to `localStorage`
- **Sound effects** — subtle Web Audio API tones on open/close/toggle (opt-in)
- **Keyboard shortcuts** — `Escape` closes the active modal or browser panel

---

## Project Structure

```
python/
├── index.html        # The entire front-end — page, browser modal, panels, logic
└── worker/
    └── index.js      # Flux Cloudflare Worker — proxy, HTML/JS/CSS rewriter, WS handler
```


---

## Configuration

Settings are stored in `localStorage` under the key `eclipse-settings`:

| Key | Default | Description |
|---|---|---|
| `glassmorphism` | `true` | Heavy backdrop blur on panels |
| `grid` | `true` | Subtle grid overlay on background |
| `animations` | `true` | Entrance and hover animations |
| `safesearch` | `true` | Appends `&safe=active` to Google searches |
| `sounds` | `false` | Web Audio UI tones |

---

## Credits

Built by [Mizzery](https://github.com/xXmizzeryXx/) · Eclipse Suite  
Games powered by [Lumin SDK](https://github.com/luminsdk/script)
