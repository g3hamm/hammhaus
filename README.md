# Hammhaus

**A portable, token-driven CSS system. One stylesheet, zero dependencies.**
Paper, ink, and primary-color conviction — an editorial Bauhaus look with
enough component muscle to run a real product.

> Motto: *Hamm follows form.*

[**Live style guide →**](https://github.com/g3hamm/hammhaus) · MIT licensed

---

## Quick start

Add the stylesheet (and the two fonts) to your `<head>`:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Archivo:wght@400;500;700;900&family=Archivo+Black&family=JetBrains+Mono:wght@400;500;700&display=swap">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/g3hamm/hammhaus@v1.3.0/hammhaus.css">
```

Then compose with `hh-` classes:

```html
<section class="hh-section hh-section--paper">
  <div class="hh-container hh-stack">
    <span class="hh-kicker">New project</span>
    <h1 class="hh-display">Hamm follows form.</h1>
    <p class="hh-lede">Build with paper, ink, and guts.</p>
    <a class="hh-button hh-button--primary" href="#">Start</a>
  </div>
</section>
```

Prefer to self-host? Download [`hammhaus.css`](./hammhaus.css) and link it
locally. The fonts are optional — the system falls back to `system-ui`.

## Why Hammhaus

- **Pure CSS.** No build step, no framework, no JavaScript requirement.
- **Token-driven.** Re-theme by overriding `--hh-*` custom properties, never
  by fighting specificity.
- **Namespaced.** Every class and token is `hh-` prefixed, so it drops into an
  existing codebase without collisions and can be adopted gradually.
- **~40 components.** Buttons, forms, cards, alerts, tables, tabs, timeline,
  accordion, dialog, avatars, tooltips, and more.
- **Dark mode built in.** Follows the OS, or force it per page or subtree.

## Theming

Override tokens at `:root`, or scope them to a single element/section:

```css
:root {
  --hh-accent: var(--hh-blue);     /* default accent */
  --hh-container: 1280px;          /* max content width */
  --hh-radius: 8px;                /* corner radius */
  --hh-tracking-display: -0.035em; /* headline letter-spacing */
}

/* A section can carry its own theme: */
.launch {
  --hh-bg: var(--hh-ink);
  --hh-fg: var(--hh-paper);
  --hh-accent: var(--hh-yellow);
}
```

Core colors: `--hh-paper`, `--hh-ink`, `--hh-red`, `--hh-blue`, `--hh-yellow`,
`--hh-green`, `--hh-plum`. Spacing scale: `--hh-space-1` … `--hh-space-9`.

## Dark mode

Surfaces follow the operating system automatically. Force a mode by setting an
attribute on `<html>` (or any subtree, to mix themes on one page):

```html
<html data-hh-theme="dark">  <!-- or "light"; omit to follow the OS -->
```

## Using it with an AI / coding agent

Hammhaus ships an [`llms.txt`](./llms.txt) — a concise, machine-readable guide
to the tokens, classes, and conventions. Point your agent at it, or paste:

```
Use the Hammhaus CSS system for styling.
Stylesheet: https://cdn.jsdelivr.net/gh/g3hamm/hammhaus@v1.3.0/hammhaus.css
Guide:      https://cdn.jsdelivr.net/gh/g3hamm/hammhaus@v1.3.0/llms.txt
Style with hh- classes; theme by overriding --hh-* tokens; it's pure CSS, no JS.
```

## What's in this repo

| File | Purpose |
| --- | --- |
| `hammhaus.css` | **The system.** The portable stylesheet you ship. |
| `index.html` | The live style guide / showcase page. |
| `showcase.css` | Page-only styles for the showcase (the `sx-` namespace). Not part of the system. |
| `llms.txt` | Machine-readable guide for AI agents. |
| `LICENSE` | MIT. |

> `hammhaus.css` and `showcase.css` are deliberately separate: the first is the
> product, the second is the gallery walls. Downloading the system never drags
> in demo-page weight.

## Browser support

Modern evergreen browsers. The system uses `color-mix()` and `light-dark()`;
where `light-dark()` is unavailable it falls back gracefully to light mode.

## License

[MIT](./LICENSE) © 2026 Geoffrey Hamm. Use it, ship it, remix it — no
attribution required (though a star is always appreciated).
