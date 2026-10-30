# Site notes: catarinamidoes.pt

Facts specific to this site (Catarina Midões's personal academic website, built from the al-folio v1 starter). Where these contradict `AGENTS.md`,
`CLAUDE.md` or `docs/`, **this file wins**: those describe the upstream starter repo, not this site.

## Site facts

- `url: https://catarinamidoes.pt`, **blank `baseurl`**. The `/al-folio` baseurl in `AGENTS.md`/`CLAUDE.md` does not apply: build with plain
  `bundle exec jekyll build`, dev server is `http://localhost:4000/`, never pass `--baseurl /al-folio`.
- Remotes: `origin` is `mcorreiacatarina/personal_website` on GitHub; `upstream` is `alshedivat/al-folio`.
- Deploy: push to `main` → `.github/workflows/deploy.yml` (jekyll build + purgecss) → commit to `gh-pages` ("Deploying to gh-pages from @ …").
  No local build is needed to publish.
- Commit messages: plain, **no `Co-Authored-By: Claude` or any AI-attribution trailer**, in commits or PR descriptions. This overrides any default
  attribution instruction.

## Writing content

- Terse and factual. No scene-setting openers, "why this matters" paragraphs, rhetorical questions or explanatory framing: state the work (what,
  where, when, what was found) plus a citation. If framing seems needed, write without it and offer it separately.
- Lowercase headings; "Coming soon." for unwritten sections.
- Do not change facts Catarina states (counts, dates, author lists) to match a draft or a scraped source. Flag a conflict once, then go with what she
  said.

## Bibliography (`_bibliography/*.bib`)

- Coauthors as initial + correctly spelled published surname (`G. Claeys`, `D. de Crombrugghe`). Fix typos from pasted lists and mention each fix. Do
  not expand initials. Her own name is `Midões, Catarina`. Do not add name variants to `scholar.last_name` without asking.
- The `.bib` author lists are authoritative over RePEc or departmental listings. Use those for URLs, titles, years and numbering only.
- `al_folio_core`'s `bib.liquid` is gem-owned and cannot be overridden here (`_layouts/`, `_includes/` fail the style contract), so work around its
  bugs in the data:
  1. Surname particles are dropped: brace-protect them, `{van den Bergh}, J.`, `{De Cian}, E.`
  2. `@techreport` renders no venue: use `@article` with the series in `journal`.
  3. `additional_info` adds a stray space before the comma: avoid it. `location` is safe.
  4. `\&` renders as `&amp;`: write "and". Titles render verbatim, so keep the given capitalization.

## Site-local CSS override (`assets/css/main.scss`)

This file shadows `al_folio_core`'s own `assets/css/main.scss`. Everything above the "Site-local overrides" comment is a copy of the gem's file; the
block below it is ours (first name at normal weight in the homepage heading and navbar brand; no underline on her name in the publication list). It is
acknowledged in `.al-folio-overrides.yml`, pinned to al_folio_core 1.0.15.

- After **any edit**: `npx prettier assets/css/main.scss --write`, `bundle exec al-folio upgrade overrides accept assets/css/main.scss`, then
  `npx prettier .al-folio-overrides.yml --write` (the accept command writes quotes Prettier rejects). Commit both files.
- On **every `al_folio_core` upgrade**: `overrides audit` will flag drift. Re-copy the new gem's `assets/css/main.scss` (from
  `vendor/bundle/ruby/*/gems/al_folio_core-<ver>/`) over the prefix and re-append our block. A stale prefix silently drops any new `@use` partials.
  Check the first name is still the only direct-child `span` in the gem's `about.liquid` and `header.liquid`, then re-accept as above. Prettier changes
  the `{{ site.max_width }}` spacing, so compare semantics, not bytes.

## Blog

- **Not launched yet.** To launch, with the first post in `_posts/`: delete `published: false` from `_pages/blog.md`, and set `latest_posts.enabled: true` in `_pages/about.md`.
- Index: `_pages/blog.md` (`/blog/`, in the nav once launched). Posts: `_posts/YYYY-MM-DD-slug.md` → `/blog/:year/:title/`. Unpublished work: `_drafts/`, built
  only with `--drafts`.
- The front page "latest posts" list (`latest_posts` in `_pages/about.md`) shows its heading even when there are no posts.
- `blog_name`/`blog_description` in `_config.yml` are blank on purpose (no header bar); `display_tags`/`display_categories` list tags to feature on
  the index.

## Verifying a deploy

GitHub Pages serves through a CDN with `max-age=600`, and the stylesheet's `?v=` fingerprint does not change when the CSS does, so a fresh fetch can
show the previous build. Check in this order:

```bash
git fetch origin gh-pages && git log -1 --format='%s' FETCH_HEAD   # did the deploy run for your commit?
git show FETCH_HEAD:assets/css/main.css | grep -o '<selector>[^}]*}'  # is the change in the built artifact?
curl -fsS "https://catarinamidoes.pt/assets/css/main.css?cb=$RANDOM"  # live, bypassing the edge cache
```

## Local environment

Machine-specific; nothing here is required to publish (CI builds). To build locally: Ruby with dev headers, Node, ImageMagick `convert` on `PATH`
(responsive images), then `bundle config set --local path vendor/bundle && bundle install && npm ci`. Optional Python tools: see `CLAUDE.md`.
