# Repository Guidelines

## Project Structure & Module Organization

Source artifacts live directly in the repository root. `resume.md`, `gn.md`, and `yzrh.md` contain the canonical narratives; `resume.pdf`, `cv.docx`, and similar binaries are generated exports. Always edit the Markdown sources, regenerate the binary artifacts from them, and keep filenames short, lowercase, and descriptive (for example, `projectX.md` for a new engagement write-up). Avoid creating nested directories unless a document truly needs its own asset bundle.

## Build, Test, and Development Commands

- `npx markdownlint-cli "**/*.md"` — validates headings, link targets, and table formatting across every Markdown file before sharing changes.
- `npx md-to-pdf resume.md` — regenerates a polished PDF from the Japanese résumé; swap the input file to export other narratives, and use `-o cv.docx` when a Word document is needed.
- `rg -n "TODO" *.md` — quick sweep to ensure no drafting placeholders remain in published documents.

## Coding Style & Naming Conventions

Use `#` for document titles, increment heading levels without skipping, and keep paragraphs short for easy translation. Indent lists with two spaces, align Markdown tables, and prefer backticks for inline English technical terms. Preserve Japanese typography (full-width punctuation, era names, etc.) present in the existing files, and mirror the concise filename pattern already used at the repository root.

## Testing Guidelines

Treat every export as a review artifact: rerun `pandoc` after edits, visually inspect the resulting PDF/DOCX, and verify line wrapping for long Japanese sentences. Run `npx markdownlint-cli` locally and block merges until it passes. When documenting quantitative results, double-check figures against the source system and annotate verification notes inline using italicized callouts.

## Commit & Pull Request Guidelines

Recent history favors compact imperative messages (`add`, `fix`, `fixed`). Follow the same lower-case verb style, mention the primary document (`fix resume.md bullet order`), and keep unrelated changes in separate commits. Pull requests should summarize the narrative change, link to any relevant issue or interview request, and attach regenerated exports (PDF/DOCX) plus before/after screenshots when the visual layout changes.

## Localization & Confidentiality

The repository stores personally identifiable career data. Keep edits in Japanese unless explicitly tasked with translation, redact client-sensitive names when unsure, and scrub temporary files before pushing. Avoid storing secrets or proprietary metrics; use placeholders such as `<client>` until approval is granted to reveal details.
