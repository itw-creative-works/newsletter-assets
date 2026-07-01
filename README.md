# newsletter-assets

Public archive of newsletter assets rendered by [backend-manager](https://github.com/itw-creative-works/backend-manager)'s newsletter generator.

## Architecture

Each brand gets its own branch. The `main` branch is a viewer hub — no newsletter content.

```
main branch (GitHub Pages)
  └── index.html        ← viewer: ?path=...&branch=... renders newsletter in iframe

somiibo branch (only somiibo's newsletters)
  └── somiibo/{campaignId}/
        ├── section-1.png
        ├── section-2.png
        ├── ...
        ├── newsletter.html
        ├── newsletter.md
        └── summary.md

optiic branch (only optiic's newsletters)
  └── optiic/{campaignId}/...

(one branch per brand — zero cross-brand contention on uploads)
```

## Preview

Open the viewer on GitHub Pages with a path and branch:

```
https://itw-creative-works.github.io/newsletter-assets/?path={brandId}/{campaignId}/newsletter.html&branch={brandId}
```

## URLs

Images and files are served via `raw.githubusercontent.com` from the brand's branch:

```
https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/{brandId}/{brandId}/{campaignId}/section-1.png
https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/{brandId}/{brandId}/{campaignId}/newsletter.html
https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/{brandId}/{brandId}/{campaignId}/newsletter.md
https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/{brandId}/{brandId}/{campaignId}/summary.md
```

## What gets committed

- Per-section PNG illustrations
- `newsletter.html` — final rendered HTML (download + paste into a provider, or permanent archive)
- `newsletter.md` — markdown view, split into one `## heading` block per section for block-based editors
- `summary.md` — 2-3 sentence editorial recap

**Nothing else.** No source data, no subscriber data, no metadata, no API keys. The upload module ([image-host.js](https://github.com/itw-creative-works/backend-manager/blob/main/src/manager/libraries/email/generators/lib/image-host.js) in `backend-manager`) validates each file before commit (PNG magic-byte check, strict path regex).

## Public-safety policy

Everything in this repo is **permanently public**. Never commit subscriber data, API keys, source content, or anything from `.env`. The upload module enforces this with hardcoded allowlist regexes per file kind.

## Cleanup

Old assets can be pruned by deleting the `{brandId}/{campaignId}/` folder on the brand's branch.
