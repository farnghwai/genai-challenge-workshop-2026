# Generative AI Challenge Workshop (Bengkel Cabaran AI Generatif)

A static, bilingual (Bahasa Melayu / English) web kit of prompt-building tools for a student workshop on generative AI. Each tool is a self-contained HTML page: fill in a few fields, the page assembles a finished prompt, and the student copies it into [Gemini](https://gemini.google.com/) to run it.

There is no build step, server, or framework — open `index.html` directly in a browser, or serve the folder with any static file server.

**Live site:** published via GitHub Pages.

## Pages

| File | Module | What it does |
|---|---|---|
| [index.html](index.html) | Landing page | Links out to all modules and the bonus tool; has the BM/EN language toggle. |
| [module-1.html](module-1.html) | 1 · AI That Talks | Prompt Builder — assembles a prompt from Context, Role, Task, Format. |
| [module-2.html](module-2.html) | 2 · AI That Does | Agent Task Designer — sets Goal, Completion Criteria, Tools, Return to direct an AI agent. |
| [module-3.html](module-3.html) | 3 · From User to Builder | Build & Refine — generates a first-build prompt, then a refinement prompt, for use in Gemini Canvas. |
| [module-4.html](module-4.html) | 4 · AI With Senses | Multimodal — writes prompts for photo, voice, and sketch input. |
| [bonus-video.html](bonus-video.html) | Bonus · AI That Creates | AI Video Director — generates a 10-second cinematic video prompt with a live storyboard preview, that spells out a chosen word. |

## Shared structure

- [styles.css](styles.css) — single shared stylesheet (design tokens, layout, buttons, the `.panel` / `.slate` / `.row-actions` components used on every tool page).
- Each module page is self-contained: inline `<script>` holds an `I18N` dictionary (`ms` and `en`) plus the logic that builds the output prompt and wires up the copy button. There's no shared JS module — logic is duplicated per page by design, since each tool's prompt-assembly logic differs.
- Language preference is persisted per-browser via `localStorage` (`workshop-lang`).
- Every tool's output panel has a **Copy prompt** button and an **Open Gemini** link (→ https://gemini.google.com/) so students can paste the generated prompt straight into Gemini.

## Publishing (GitHub Pages)

The site is plain static files at the repo root, so no build is needed:

1. Push to GitHub.
2. **Settings → Pages → Build and deployment**, set **Source: Deploy from a branch**.
3. Choose the `main` branch and `/ (root)` folder, then **Save**.

`index.html` at the root is served as the landing page.

## License

Released under the [MIT License](LICENSE).
