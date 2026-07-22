# TaryagNotes — portfolio site

Source for the public-facing portfolio page for **TaryagNotes**, a local-first desktop workspace for learning the
613 mitzvos: a mitzvah browser routed into the primary sources, a structured reader, and a source-linked notes
system (ha'aros) with a plain spaced-repetition review pass. Built with .NET + Avalonia, backed by a local SQLite
notebook — no account, no cloud sync required.

**Live site:** https://menachem-d.github.io/Portfolio/ *(GitHub Pages, served from this repo)*

## What's in here

This is a static site — plain HTML/CSS, no build step, no framework:

```
index.html          the portfolio page itself
css/style.css        styling — palette and type pulled directly from the app's own design tokens
mockup/               live HTML/CSS reconstructions of three real app screens, filled with placeholder data
  today.html          the Today dashboard
  learn.html          the mitzvah browser + notes panel, showing the quote+source note convention
  reader.html         the Reader screen and its parchment reading surface
  mockup.css          shared styling for the three mockup screens
assets/               favicon and resume PDF
```

The `mockup/` pages are embedded live in `index.html` via `<iframe>` (not screenshots) so they stay crisp at any
zoom level and don't require a screenshot tool to keep up to date — if the app's design tokens change, these are
quick to update by hand since they're just CSS variables, not a raster image.

## Adding the workflow GIF

`index.html` currently has a placeholder card in the "Workflow" section (`#workflow`) instead of a real GIF. To
add one:

1. Record: **Today** → pick a mitzvah in **Learn** → open it in the **Reader** → write a note using the
   `"quote" (source)` convention → show it land in the **Review** queue.
2. Use a free screen-recorder-to-GIF tool — [ScreenToGif](https://www.screentogif.com/) (Windows) or
   [ShareX](https://getsharex.com/) both work well and are free.
3. Aim for roughly 960px wide, keep the file under ~8MB so it renders smoothly on GitHub Pages, and trim dead time
   at the start/end.
4. Drop the file at `assets/img/workflow.gif` and replace the placeholder `<div class="gif-placeholder">…</div>`
   block in `index.html`'s `#workflow` section with an `<img>` pointing at it.

## Local preview

No build step — just open `index.html` directly in a browser, or serve the folder with any static file server
(e.g. `npx serve .`) if you want the `<iframe>` mockups to load under `http://` instead of `file://`.
