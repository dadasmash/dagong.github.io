---
name: update-website-from-cv
description: Update Da Gong's academic website from a supplied LaTeX or PDF CV while preserving the website's established layouts and formatting. Use for CV synchronization, adding or reclassifying research, updating talks and conferences, teaching, advising, grants, service, biography, contact details, rebuilding the local preview, or committing and pushing validated website updates to GitHub.
---

# Update Website from CV

Treat the supplied CV as the content source of truth and the existing website as the design source of truth.

## Non-negotiable rules

1. Preserve every page's original layout.
   - Do not rewrite a page wholesale or replace its HTML with generic Markdown.
   - Preserve existing headings, anchors, classes, inline styles, dividers, columns, cards, images, links, abstracts, and section order.
   - Add or edit entries by copying the surrounding page's markup pattern.
2. Use the CV's wording and abbreviations exactly.
   - Do not expand conference abbreviations.
   - Examples include `MEA 90th`, `MPSA 83rd`, `BMP at Duke`, `MapleMeth at McMaster`, `SICSS at University of Rochester`, `EPOVB at WashU`, `VIM and Polmeth at Michigan State`, `EIP`, and `APSA 122nd (scheduled)`.
   - Preserve course codes and semester abbreviations such as `DANL 202`, `F24`, `S25`, and `F26`.
3. Do not invent content.
   - Do not write new abstracts, summaries, links, images, awards, dates, affiliations, or expanded event names unless they are present in the CV or the user supplies them.
4. Require user-supplied files and images.
   - When an update refers to a file or image that is missing from its corresponding project folder, remind the user to attach or add it.
   - State the expected folder and filename when they can be determined from the request or existing markup.
   - Do not generate, recreate, substitute, or fabricate a missing file or image unless the user explicitly instructs you to do so.
   - Pause only the affected item; continue other unambiguous updates when possible.
5. Ask before making an uncertain change.
   - Ask when classification, removal, replacement, ordering, authorship, dates, links, images, or abstracts are unclear.
   - In particular, ask before deleting an existing website entry that is absent from the new CV.
6. Make only content changes required by the CV. Do not redesign or modernize the website unless the user separately requests it.

## Page mapping

- `_pages/about.md`: appointment, affiliation, education, research interests, and short biography.
- `_pages/research.html`: Publications, Working Papers, Other Publications & Technical Reports, and Work in Progress.
- `_pages/talks.html`: Talks and Presentations, Grants & Awards, Referee Service, Professional Service, and University Service.
- `_pages/teaching.html`: teaching assignments and advising.
- `_pages/cv.md`: CV download page.
- `_config.yml`: public biography, email, affiliation, and related profile metadata.
- `files/DaGong_Academic_CV.pdf`: downloadable current CV.

## Workflow

1. Read the complete supplied CV.
2. Inspect the current website pages and compare them with their committed versions when useful.
3. Prepare a page-by-page change list:
   - additions;
   - factual updates;
   - reclassifications such as Working Paper to Publication;
   - required files or images that are missing from their corresponding folders;
   - possible removals requiring confirmation.
4. Remind the user about any missing required files or images; do not generate replacements without explicit instructions.
5. If any decision is uncertain, ask the user before editing.
6. Patch entries into the existing markup patterns. Avoid full-file rewrites.
7. Check that:
   - titles, coauthors, journals, years, course codes, semesters, amounts, and abbreviations match the CV;
   - existing page structure and visual patterns remain intact;
   - no item appears in two sections after a reclassification.
8. Run `git diff --check` and inspect the diff to confirm it contains targeted insertions and factual edits rather than a layout replacement.
9. Compile from the local repository root:
   - source: `C:\Users\Da\Dropbox\Personal_Website`
   - output: `C:\Users\Da\Dropbox\Personal_Website\_site`
   - include `_config.dev.yml` after `_config.yml` so preview navigation remains on localhost.
10. Verify the local Research, Experience, and Teaching URLs return the updated content.

## Local preview requirements

- Use `http://127.0.0.1:4000/` for the preview.
- Confirm generated navigation links resolve to localhost, not the published GitHub Pages URL.
- Never claim the user is viewing updated pages until Research, Experience, and Teaching have each been checked in the generated `_site` output.
- Publishing or pushing is separate and requires an explicit user request.

## GitHub push requirements

1. Push only when the user explicitly requests it.
2. Before committing:
   - confirm the remote is exactly `https://github.com/dadasmash/dagong.github.io.git`;
   - confirm the publishing branch is `master`;
   - fetch `origin` and incorporate remote changes without overwriting local work;
   - stop and ask the user if a conflict or uncertain remote change affects a locally edited file.
3. Rebuild and verify the website, run `git diff --check`, and inspect the staged diff before pushing.
4. Stage only explicitly intended source files. Never use broad staging such as `git add .`.
5. Never commit local or generated artifacts such as `.runtime/`, `.sass-cache/`, `_site/`, temporary build folders, credentials, or tokens.
6. Check the staged files for secrets and unintended large files.
7. Commit with a descriptive message, push to `origin master`, and confirm the remote branch SHA matches the local `HEAD`.
8. If authentication fails, ask the user to sign in with Git Credential Manager. Never ask the user to paste a token into chat or embed a token in the remote URL.
