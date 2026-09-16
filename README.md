# sambox-test-assets

Test fixture files (PDFs, fonts, images) used by [SAMBox](https://github.com/torakiki/sambox)'s
test suite. This repo asserts no ownership over any of the assets.

## Why this repo exists

SAMBox's `pom.xml` used to download these files on every CI build directly from their
original locations (PDFBox JIRA or other sources) via `download-maven-plugin`, this caused intermittent build timeouts.

This repo mirrors the same files so CI fetches them from GitHub instead. SAMBox's
`pom.xml` references files here by a pinned git commit SHA (never a branch) and every
download is still checksum-verified (sha512) against the value recorded in SAMBox's
`pom.xml`.

## Provenance and licensing

These files were copied as-is from their original locations. None of them were authored
for this repo and none of the original licensing terms are re-asserted, changed or
verified here.

## Layout

- `pdfs/` — test PDF documents
- `fonts/` — test font files (ttf, otf, pfb, and font zip archives)
- `imgs/` — test images

