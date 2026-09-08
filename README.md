# ftcm-topics

Public topic pages for **Follow the Clucking Money (FTCM)**, a civic finance
group covering Petaluma municipal finance. This site is the published,
sourced version of topics the group researches — plain static HTML, hosted
on GitHub Pages, editable by anyone in the group without needing to run a
build.

Live site: `https://<owner>.github.io/ftcm-topics/` (or a custom domain,
once one is configured — see below).

## How it's organized

Each topic gets its own folder with three pages:

```
<topic>/
├── index.html          # topic overview / table of contents
├── start-simple.html   # short, workshop-slide-style version
└── advanced.html       # full version — data, methodology, citations
```

- **Start simple** is the five-minute version: the key numbers, the core
  question, the takeaway. No jargon, minimal setup.
- **Advanced** covers the same material in the same section order, but with
  full data tables, methodology notes, and a citation for every figure.

Both versions link to each other (the toggle near the top of each page), so
a reader can start wherever fits the time they have.

The root `index.html` lists every published topic and links to each one's
start-simple and advanced pages. `roads/` is the first topic and the
reference implementation of this pattern.

## Sourcing rules

Every factual claim needs a named, checkable source — a city budget
document, an MTC publication, council meeting minutes/transcript, etc.
Where a page is scaffolded but the real citation isn't in hand yet, it's
marked inline as:

```html
[SOURCE: ]
```

Don't remove a `[SOURCE: ...]` placeholder without replacing it with an
actual citation. Don't fabricate a citation to fill one in.

Tone is informative, not persuasive: state what the sources say, flag
estimates as estimates, and keep any disputed or discretionary claim
(e.g. "who gets prioritized and why") plainly attributed rather than
implied.

## Adding a new topic

1. Copy the `roads/` folder to `<new-topic>/`. The filenames inside stay the
   same (`index.html`, `start-simple.html`, `advanced.html`).
2. Update the `<title>`, headings, and content for the new topic. Keep the
   section-header HTML comments as a scaffold while drafting — they mark
   where each piece of content goes.
3. Add a `.topic-card` entry linking to the new topic on the root
   `index.html`.
4. Leave `[SOURCE: ...]` placeholders for any figure without a citation yet.

## Styling

All pages share `assets/style.css` — plain CSS, no framework, no build
step. It's intentionally minimal: system fonts, a light theme with an
automatic dark mode (via `prefers-color-scheme`), and a handful of reusable
patterns (stat callouts, Q&A "challenge" blocks, data tables) used across
topics. Any group member can open the file directly and adjust a color or
spacing value without tooling.

Chart images or generated SVGs go in `assets/charts/`.

## Custom domain

No custom domain is configured yet. To add one later: create a `CNAME`
file at the repo root containing just the domain, set it under
**Settings → Pages → Custom domain**, and point the domain's DNS at GitHub
Pages per [GitHub's docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).
