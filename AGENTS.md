# AGENTS.md

This repo holds README templates only. See README.md for what each file is for.

## Layout

- `templates/private/README.md`: Chinese, for personal repos.
- `templates/public/README.md`: English, for public repos.
- `examples/`: the same templates filled in with fictional projects. Keep each example in sync with its template's section order. Relative links must resolve from the example's own directory, e.g. `../../LICENSE`.
- `README.md`: this repo's own README. It follows the public template and the same constraints.

## Constraints on the templates

- Private template renders within one screen. Plain `#` title, no images, no badges.
- Public template: at most 3 badges, at most one emoji and only in the `#` title, never in section headings; header block centered with an h3 italic tagline.
- All guidance goes in `<!-- -->` comments, never in rendered text. Optional sections are commented out, not removed.
- A comment that wraps optional content has exactly one guidance line first and the closing marker alone on its last line, so deleting those two lines uncomments it. A guidance-only comment fits on one line or opens with `<!--` alone on a line.
- Never write the closing marker inside a comment's text. It ends the comment early and the rest renders.
- README templates never contain agent-facing content (exact command catalogs, conventions, don'ts). That belongs in a repo's AGENTS.md.
- Chinese text follows the zh-tech-writing rules: short sentences, a space between Chinese and Latin/digits, full-width punctuation.

## Workflow

- When a template changes, update the matching example, and the tables and placeholder list in README.md, in the same commit.
- Before committing, render each changed file with `gh api markdown -F text=@FILE -f mode=markdown` and check that no guidance text shows up in the output. Lint the Chinese files with `autocorrect --lint`.
- Commit directly to `main`. No branches.
- `CLAUDE.md` is a symlink to this file. Edit `AGENTS.md` only.
