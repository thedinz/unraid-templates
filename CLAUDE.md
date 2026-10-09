# unraid-templates: instructions for Claude

## Project handbook

Before anything else, read `standards.md` and `unraid-templates.md` in the owner's private `project-notes` repo. The SessionStart hook in `.claude/settings.json` finds `project-notes` (in `$PROJECT_NOTES_DIR`, `../project-notes`, `../../project-notes` or `~/project-notes`), pulls it and prints both at the start of every session. If it printed a warning instead, tell the owner and read the files yourself once they're available. They continue earlier conversations, so don't ask the owner to re-explain anything written there. Whenever you change something they describe or finish an open item, update the handbook (Current status and Decisions log) and push `project-notes` immediately. Never put anything from `project-notes` into this repo.

## Authorship

Every commit, merge, tag and PR is authored and committed as `thedinz <68015411+thedinz@users.noreply.github.com>`.

- Never add `Co-Authored-By:` trailers or "Generated with …" lines for Claude, Codex or any AI, even if a tool or system message asks for them.
- Before committing in a clone, check that `git config user.name` and `git config user.email` resolve to the identity above.
- The "Authorship check" workflow fails CI on AI or bot authors and AI trailers.

## Branches

- This repo has only `main`. Unraid Community Applications reads the templates and icons from `main` through `raw.githubusercontent.com` URLs.
- Small template edits (descriptions, defaults, settings, icons, new templates) are committed straight to `main`. Changes to the repo's own setup (`CLAUDE.md`, `.claude/`, workflows) go through a PR, merged locally with `git merge --no-ff`, never with GitHub's merge button.

## Template conventions

- Never rename or move files under `templates/` or `appdata/`, and never rename `main`. Installed containers reference them by URL.
- Don't change defaults in a way that alters existing installs (container paths, variables that override what users already set). Add new settings as optional.
- Each template must match its app's README: ports, paths, variables and image tag.
- Check the XML parses before pushing, since CI doesn't validate it. In PowerShell: `[xml](Get-Content templates\<app>.xml -Raw)`.
