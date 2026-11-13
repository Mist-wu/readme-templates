<div align="center">

# readme-templates

*Two README templates, private and public, that make README better.*

[![License](https://img.shields.io/github/license/Mist-wu/readme-templates)](LICENSE)

</div>

## Why readme-templates?

Most READMEs fail in one of two ways: a wall of setup notes nobody reads, or a pile of badges with no clear first sentence. These templates fix the shape so you only fill in content.

- **Two audiences, two templates**: a private one (Chinese, one screen, for future you) and a public one (English, for strangers).
- **README is for humans only**: commands in depth, conventions and don'ts go to `AGENTS.md`.
- **Hints live in `<!-- -->` comments**: they never render, so a half-filled template still looks clean.
- **Optional parts are commented out**, not deleted: banner, nav row, feature table, alerts, screenshots, Cite.

## Quick start

### Copy a template

```sh
# private repo
curl -fsSL https://raw.githubusercontent.com/Mist-wu/readme-templates/main/templates/private/README.md -o README.md

# public repo
curl -fsSL https://raw.githubusercontent.com/Mist-wu/readme-templates/main/templates/public/README.md -o README.md
```

### Fill it in

Replace placeholders, uncomment the optional sections you need, delete the rest. For public repos, search for `OWNER/REPO`.

### Compare with a filled example

| | Template | Filled example |
|---|---|---|
| Private | [templates/private](templates/private/README.md) | [examples/private](examples/private/README.md) |
| Public | [templates/public](templates/public/README.md) | [examples/public](examples/public/README.md) |

## Usage

### Pick a template

| | Private | Public |
|---|---|---|
| Reader | Future you, and agents | A stranger on first visit |
| Language | Chinese | English |
| Length | One screen | As long as Quick start + Usage need |
| Header | Plain `#` title + one line | Centered: optional logo, tagline, up to 3 badges |
| Sections | 状态 · 快速开始 · 目录 · 笔记 | Why · Quick start · Usage · License, plus optional ones |

### Split README and AGENTS.md

| Goes in README.md | Goes in AGENTS.md |
|---|---|
| What it is, why it exists | Exact build / test / lint / deploy commands |
| Shortest path to a working result | Conventions: style, naming, doc language |
| Current status and results | Non-obvious layout: entry points, generated files |
| Screenshots, usage examples | Don'ts, and what to do without asking |

Rule of thumb: if a sentence only matters to whoever edits the code, it belongs in `AGENTS.md`. Keep `AGENTS.md` as the source and symlink `CLAUDE.md` to it:

```sh
ln -s AGENTS.md CLAUDE.md
```

### What makes it look good

- One sentence under the title that says what it is. This matters more than any image.
- A screenshot or GIF of the result right after the first command.
- At most 3 badges, no emoji headings, no Features list that repeats Why.
- Long or secondary content goes into `<details>` or `docs/`.

Header and Quick start style borrow from [GuideLLM](https://github.com/vllm-project/guidellm) and [Parabolic](https://github.com/NickvisionApps/Parabolic).

## License

[MIT](LICENSE)
