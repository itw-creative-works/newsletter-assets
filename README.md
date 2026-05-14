# newsletter-assets

Public archive of newsletter assets rendered by [backend-manager](https://github.com/itw-creative-works/backend-manager)'s newsletter generator.

Each newsletter campaign uploads its rendered files here so they can be referenced by `https://raw.githubusercontent.com/...` URLs (from the email HTML), pasted into provider editors, or browsed as an issue archive.

## Layout

```
{brandId}/
  {campaignId}/
    section-1.png       — per-section illustration
    section-2.png
    section-3.png
    ...
    newsletter.html     — final rendered email-safe HTML
    newsletter.md       — programmatic markdown view (per-section blocks)
    summary.md          — short editorial recap (2-3 sentences)
```

- `brandId` — the brand slug (e.g. `somiibo`)
- `campaignId` — the corresponding `marketing-campaigns/{id}` Firestore document ID

URLs resolve as:

```
https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/main/{brandId}/{campaignId}/section-1.png
https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/main/{brandId}/{campaignId}/newsletter.html
https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/main/{brandId}/{campaignId}/newsletter.md
https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/main/{brandId}/{campaignId}/summary.md
```

## What gets committed here

- Per-section PNG illustrations
- `newsletter.html` — final rendered HTML (download + paste into a provider, or use as a permanent archive)
- `newsletter.md` — markdown view, split into one `## heading` block per section so it can be pasted into block-based editors (e.g. Beehiiv) with ad blocks inserted between
- `summary.md` — 2-3 sentence editorial recap (separate from the inbox preheader)
- This README

**Nothing else.** No source data, no subscriber data, no metadata, no API keys, no SVGs. The upload module ([src/manager/libraries/email/generators/lib/image-host.js](https://github.com/itw-creative-works/backend-manager/blob/main/src/manager/libraries/email/generators/lib/image-host.js) in `backend-manager`) only accepts allowlisted file kinds and validates each before commit (PNG magic-byte check on images, strict path regex on every file).

## Public-safety policy

Anything in this repo is **permanently public on the open internet**, indexed by GitHub search, and cached by archive services. Treat every commit as irreversible.

**Never commit:**

- Subscriber data (emails, names, segments) — PII / GDPR liability
- Source publication names or article content — copyright / scraping liability
- API keys, tokens, service account JSON — credential leak
- Internal Firestore content (other than the campaign ID used as a folder name)
- Anything from `.env`

The upload module enforces this with hardcoded allowlist regexes — one per file kind:

```
^[a-z0-9-]+/[A-Za-z0-9_-]+/section-\d+\.png$
^[a-z0-9-]+/[A-Za-z0-9_-]+/newsletter\.html$
^[a-z0-9-]+/[A-Za-z0-9_-]+/newsletter\.md$
^[a-z0-9-]+/[A-Za-z0-9_-]+/summary\.md$
```

Anything outside these patterns is rejected before the commit even reaches GitHub.

## Cleanup

Old assets can be pruned by deleting the corresponding `{brandId}/{campaignId}/` folder. URLs in already-sent newsletters will 404 after that, which is expected — those emails are immutable in subscribers' inboxes by the time we'd consider pruning.
