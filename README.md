# ftcm-topics

Public topic pages for **Follow the Clucking Money (FTCM)**, a civic finance
group covering Petaluma municipal finance. This site is the published,
sourced version of topics the group researches — plain static HTML, hosted
on GitHub Pages, editable by anyone in the group without needing to run a
build.

Live site: `https://<owner>.github.io/ftcm-topics/` (or a custom domain,
once one is configured — see below).

## How it's organized

Each topic gets its own folder with a single page:

```
<topic>/
└── index.html   # the whole topic — key numbers, explanation, sources
```

One page per topic, self-contained (data, explanation, and a numbered
sources list at the bottom), rather than split across a short and a
detailed version.

The root `index.html` lists every published topic and links to each one's
page. `roads/` is the first topic and the reference implementation of this
pattern.

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

1. Copy `roads/index.html` to `<new-topic>/index.html`.
2. Update the `<title>`, headings, and content for the new topic, including
   the numbered sources list at the bottom.
3. Add a `.topic-card` entry linking to the new topic's page on the root
   `index.html`.
4. Leave `[SOURCE: ...]` placeholders for any figure without a citation yet.

## Styling

The root `index.html` uses the shared `assets/style.css` — plain CSS, no
framework, no build step, with a light theme and automatic dark mode (via
`prefers-color-scheme`).

Topic pages (e.g. `roads/index.html`) are self-contained instead: each
carries its own inline `<style>` block rather than linking the shared
stylesheet, so a topic can be copied, edited, and shared as a single file.
Any group member can open one directly and adjust a color or spacing value
without touching anything else on the site.

Chart images or generated SVGs go in `assets/charts/`.

## Custom domain

No custom domain is configured yet. To add one later: create a `CNAME`
file at the repo root containing just the domain, set it under
**Settings → Pages → Custom domain**, and point the domain's DNS at GitHub
Pages per [GitHub's docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).
