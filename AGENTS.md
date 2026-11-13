# AGENTS.md

This repo holds README templates only. See README.md for what each file is for.

## Layout

- `templates/private/README.md`: Chinese, for personal repos.
- `templates/public/README.md`: English, for public repos.
- `examples/`: the same templates filled in with fictional projects. Keep each example in sync with its template's section order.

## Constraints on the templates

- Private template renders within one screen. Plain `#` title, no images, no badges.
- Public template: at most 3 badges, no emoji in headings, header block centered.
- All guidance goes in `<!-- -->` comments, never in rendered text. Optional sections are commented out, not removed.
- README templates never contain agent-facing content (exact command catalogs, conventions, don'ts). That belongs in a repo's AGENTS.md.
- Chinese text follows the zh-tech-writing rules: short sentences, a space between Chinese and Latin/digits, full-width punctuation.

## Workflow

- When a template changes, update the matching example and the tables in README.md in the same commit.
- Commit directly to `main`. No branches.
- `CLAUDE.md` is a symlink to this file. Edit `AGENTS.md` only.
