# newsletter-assets

Public archive of newsletter illustrations rendered by [backend-manager](https://github.com/itw-creative-works/backend-manager)'s newsletter generator.

Each newsletter campaign uploads its per-section PNG illustrations here so they can be referenced by `https://raw.githubusercontent.com/...` URLs in the rendered email HTML.

## Layout

```
{brandId}/
  {campaignId}/
    section-1.png
    section-2.png
    section-3.png
    ...
```

- `brandId` — the brand slug (e.g. `somiibo`)
- `campaignId` — the corresponding `marketing-campaigns/{id}` Firestore document ID

URLs resolve as:

```
https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/main/{brandId}/{campaignId}/section-1.png
```

## What gets committed here

✅ Per-section PNG illustrations
✅ This README

**Nothing else.** No source data, no subscriber data, no metadata, no API keys, no SVGs. The upload module (`src/manager/libraries/email/generators/lib/image-host.js` in `backend-manager`) accepts PNG buffers only and validates them as PNGs before commit.

## Public-safety policy

Anything in this repo is **permanently public on the open internet**, indexed by GitHub search, and cached by archive services. Treat every commit as irreversible.

**Never commit:**

- Subscriber data (emails, names, segments) — PII / GDPR liability
- Source publication names or article content — copyright / scraping liability
- API keys, tokens, service account JSON — credential leak
- Internal Firestore content (other than the campaign ID used as a folder name)
- Anything from `.env`

The upload module enforces this with a hardcoded allowlist — only files matching `^[a-z0-9-]+/[A-Za-z0-9_-]+/section-\d+\.png$` are accepted.

## Cleanup

Old assets can be pruned by deleting the corresponding `{brandId}/{campaignId}/` folder. URLs in already-sent newsletters will 404 after that, which is expected — those emails are immutable in subscribers' inboxes by the time we'd consider pruning.
