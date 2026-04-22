# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository is a **Claude Code Skill package** — not application code. It defines the `backyard-leisure-brand` skill, which applies Backyard Leisure's official brand colors, typography, voice, and visual design guidelines to any artifact Claude produces (web pages, marketing copy, designs, social posts, etc.).

There are no build, test, or lint steps. Artifacts are plain Markdown plus PNG logo assets; the skill is consumed by Claude at runtime via the `Skill` tool.

## File Layout and Role

- `SKILL.md` — Skill entry point. Frontmatter (`name`, `description`, `allowed-tools`) controls when Claude auto-activates the skill. The `description` field is what the skill-matching engine reads — edits here directly affect activation triggers.
- `colors.md` — Confirmed hex values, usage rules, CSS variable block, WCAG contrast notes, forbidden uses.
- `typography.md` — Font stack (logo fonts are **logo-only**; web uses Montserrat + Open Sans), type scale, CSS implementation.
- `voice.md` — Voice pillars, tone-by-channel matrix, per-product messaging, phrases to use/avoid.
- `products.md` — Product categories, partner brands, service URLs, business details (address, phone, hours).
- `logo.md` — Logo variants, Google Drive links, clear space, minimum sizes, partner co-branding rules.
- `logos/` — PNG renditions: `BL-logo-dark-bg.png`, `BL-logo-white-reversed.png`, `BL-logo-white-reversed-on-dark.png`, `BL-icon-only.png`, `BL-favicon-32.png`, `BL-favicon-64.png`.

## Important Structural Note

`SKILL.md` refers to the reference files as `references/colors.md`, `references/typography.md`, etc., but the files currently live at the **repo root**, not in a `references/` subdirectory. When editing `SKILL.md` or the reference files, keep paths consistent — either move the reference files into `references/` or update `SKILL.md` to point at root. Do not silently introduce a new path scheme.

## Authoring Conventions

When adding or editing content:

- **Confirmed vs. to-confirm.** Values marked `(confirmed)` come from the official "Font & Colours.pdf" brand document (March 2026). Items marked `[TO CONFIRM — ...]` are pending. Do not promote a TO CONFIRM item to confirmed without explicit instruction.
- **Brand palette is fixed.** The four logo colors are `#2F7769` (teal), `#79CBC5` (aqua), `#8FC855` (lime), `#D0EFE9` (mint), plus supporting `#F8F6F2` off-white and `#2C2C2C` charcoal. Never introduce new brand colors in reference files; new hexes need user approval.
- **Logo fonts are off-limits for body use.** Alloy Bold and Moonlight are the logo wordmark only. Web/digital substitutes are Montserrat (headings) and Open Sans (body). Don't change these substitutes without user direction.
- **Voice rules are prescriptive.** The ✅/❌ phrase tables in `voice.md` (e.g. "Backyard sanctuary" ✅, "Dream backyard" ❌; "Get started" ✅, "Click here" ❌) should be respected by any copy produced under this skill.
- **Off-white over white, charcoal over black.** `colors.md` explicitly forbids `#FFFFFF` as the primary page background and `#000000` for body text — apply this when generating CSS or design artifacts.
- **Accessibility guardrails.** Aqua and Lime Green fail AA contrast for body text on white — don't use them for running copy; stick to the background/text pairings in the `colors.md` "Text on Backgrounds" table.

## Skill Activation Model

The skill auto-activates when the user mentions Backyard Leisure branding, asks to make something "on-brand", or works on web/marketing artifacts for the company (see `SKILL.md` frontmatter `description` for the full trigger list). Changes to the `description` field alter activation behavior — edit deliberately.

When the skill is active, the expected loading pattern is: read `SKILL.md` first, then load only the reference file(s) relevant to the task (colors for design, voice for copy, etc.), rather than loading everything.

## Git Workflow

- Branch prefix in use: `claude/...` (e.g. `claude/add-claude-documentation-Rusih`). Development happens on these branches; pushes go to the same branch.
- Commit messages are short, imperative, and content-focused (examples from history: `Add confirmed logo files from Google Drive Logo Package`, `Fix icon-only crop: correct boundary at x=111, droplet only`). Match this style.
