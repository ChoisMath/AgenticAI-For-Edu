# Repository Guidelines

## Project Structure & Module Organization

This repository is a documentation and Claude Skill resource collection for Agentic AI in education. The root contains `README.md`, `LICENSE`, repository config, and `.github/workflows/release.yml`.

- `chapters/README.md` lists the chapter roadmap.
- `chapters/<n>장/README.md` describes each chapter.
- `chapters/4장/` contains project instructions and prompt templates as Markdown files.
- `chapters/5장/claude-project-instructions.md` contains chapter-level Claude Project instructions.
- `chapters/5장/skills/<skill-name>/` contains distributable Claude Skills. Each skill should include `SKILL.md`; supporting files belong in `resources/` and reviewer prompts in `subagents/`.

## Build, Test, and Development Commands

There is no application build or package manager setup. Most work is Markdown editing and skill packaging.

- `git status` checks changed files before committing.
- `git diff --check` catches trailing whitespace and formatting issues.
- `git log -5 --pretty=format:"%s"` reviews recent commit style.
- GitHub Actions builds release ZIPs from tags matching `v*` or from manual workflow runs. The workflow packages each `chapters/*/skills/*` directory into `dist/chNN-<skill-name>.zip`.

## Coding Style & Naming Conventions

Use Markdown for repository content. Keep headings descriptive, sections short, and examples practical. Preserve existing Korean filenames and chapter folder names such as `chapters/5장/`.

Use LF line endings; `.gitattributes` normalizes text files with `* text=auto eol=lf`. Skill folder names should be ASCII, lowercase, and hyphenated, for example `reading-material` or `case-based-problem`, because release ZIP names are generated from folder names.

## Testing Guidelines

No automated test suite is currently defined. Before opening a PR, manually review Markdown rendering, links, and folder references. For skill changes, verify that each skill directory has a valid `SKILL.md` and that referenced `resources/` or `subagents/` files exist.

## Commit & Pull Request Guidelines

Recent commits use imperative, sentence-style subjects, for example `Update root README folder tree and ASCII ZIP example`. Follow that pattern: start with a verb, keep the subject specific, and avoid vague messages like `Update files`.

Pull requests should summarize the changed chapter or skill, list any new files, and note whether release packaging is affected. Include screenshots only when visual rendered output is relevant. Link issues when applicable.

## Security & Configuration Tips

Do not commit local notes, archives, or generated release bundles. `.gitignore` excludes `*.zip`, backup files, IDE folders, and local memo files such as `TODO.local.md` and `NOTES.local.md`.
