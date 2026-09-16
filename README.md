# sambox-test-assets

Test fixture files (PDFs, fonts, images) used by [sambox](https://github.com/torakiki/sambox)'s test suite.

These were originally downloaded on demand from Apache PDFBox JIRA attachments and other
sources during CI, via the `download-maven-plugin` in sambox's `pom.xml`. That caused
intermittent CI timeouts, likely from JIRA throttling repeated automated downloads from
shared GitHub Actions IP ranges.

This repo mirrors those same files so sambox's build can fetch them from GitHub instead.
sambox's `pom.xml` references files here by pinned commit SHA (not branch), and each
download is still checksum-verified (sha512) against the value recorded in `pom.xml`.

## Layout

- `pdfs/` — test PDF documents
- `fonts/` — test font files (ttf, otf, pfb, and font zip archives)
- `imgs/` — test images

## Adding a new file

Add it under the matching directory, commit, push, then update the corresponding URL and
sha512 in sambox's `pom.xml` to the new commit SHA.
