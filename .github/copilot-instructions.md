<!--
Purpose: Guidance for AI coding agents working in this repository.
This repo currently contains only GitHub issue templates and their config.
Edit this file when the repository grows with code or workflows.
-->

# Copilot / AI agent instructions (concise)

This repository currently contains only issue templates under `.github/ISSUE_TEMPLATE/` and a small `config.yml` for issue behavior. Use the notes below to make safe, useful edits related to templates and repo metadata.

1. Big picture
- What this repo contains: `.github/ISSUE_TEMPLATE/Bug_Report.yml`, `.github/ISSUE_TEMPLATE/Feature_Request.yml`, and `.github/ISSUE_TEMPLATE/config.yml`.
- There is no application source, build, or test tooling present in the workspace. If you need to modify code or CI, first check for added files or ask the maintainer for context.

2. When editing issue templates
- Preserve top-level fields: `name`, `description`, `labels`, `type`, and `body`.
- `body` is an array of blocks (markdown, input, textarea). Keep the YAML structure and `validations` keys intact.
- Example to add a label:
  - Update the `labels:` array (e.g. `labels: [Issue-Bug, Needs-Triage]`).
- Example to change a required field:
  - Locate the block with `validations:` and set `required: true|false`.

3. Patterns and conventions seen here
- Labels used: `Issue-Bug`, `Needs-Triage`, `Issue-Feature` (see `Bug_Report.yml` and `Feature_Request.yml`).
- `config.yml` controls issue behavior; contains `blank_issues_enabled` and `contact_links` (add new contact entries here if you add external reporting links).

4. How to validate changes (practical, discoverable checks)
- Preview the resulting form in GitHub by opening a branch and using the repository's "New issue" UI — GitHub will render the template form.
- For syntactic safety, keep YAML indentation and the dash/list structure unchanged. If unsure, create a tiny branch and open a draft PR so maintainers can visually verify the rendered template.

5. Editing rules for agents (do this, not that)
- Do: Make minimal, focused changes to templates (fix wording, adjust placeholders, tweak `validations`).
- Do: Reference exact filenames when suggesting changes (e.g. `Bug_Report.yml`).
- Don't: Remove `body` blocks or rename template files without a maintainer note — that can break GitHub's template discovery.
- Don't: Assume there is CI, build, or tests — none were found in the repository root.

6. Integration points & external dependencies
- The templates mention external resources/links (e.g., Feedback Hub). These are simple links stored in `config.yml` under `contact_links` — update only when confident.

7. If you need to add code or CI
- Stop and request more context from the maintainer. This repo currently has no code or build files to infer conventions (no package.json, no workflow files, no source directories).

Files to reference when working here:
- `.github/ISSUE_TEMPLATE/Bug_Report.yml` — bug template, fields and required validations.
- `.github/ISSUE_TEMPLATE/Feature_Request.yml` — feature template.
- `.github/ISSUE_TEMPLATE/config.yml` — blank issue behavior and contact links.

If any of these statements are incomplete or you expect other directories (source code, CI) to exist, tell me where they live or attach them and I will expand these instructions.
