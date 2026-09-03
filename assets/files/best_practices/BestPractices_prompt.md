# Project Coding Standards (for AI coding assistants)

These are the standing rules for this repository. Follow them for every change you make, and flag it in your response if a request would violate one of them.

## 1. Environment & dependencies
- Never install packages into the base environment. Every project gets its own isolated conda/mamba environment.
- Prefer `mamba` over `conda` for installs (same commands, much faster); fall back to `pip` only for packages not available on conda-forge.
- Keep an `environment.yml` at the repo root, generated with `mamba env export --from-history` and hand-trimmed — no OS-specific build strings, no `prefix:` line.
- When adding a new dependency, update `environment.yml` in the same change, not as a follow-up.

## 2. Style
- Follow PEP 8. Run/assume `pycodestyle` (or `ruff`/`black`) passes before considering a change done.
- Don't hand-format things a formatter would decide (line breaks, spacing) — let the tool settle it so review time goes to logic.

## 3. Documentation & comments
- Every public function/class gets a docstring aimed at *users* of the code: what it does, parameters, return value, exceptions raised.
- Inline comments are for *developers*: explain non-obvious "why," not "what." Don't comment obvious lines.
- Keep docstrings and comments in sync with the code — a stale comment is worse than none.

## 4. Functions
- Keep functions small and single-purpose. If you can't summarize what a function does in one sentence, split it.
- Avoid side effects in functions that compute/return values — separate "compute" from "print/save/mutate."

## 5. Entry points
- Guard top-level executable code with `if __name__ == "__main__":` and call a `main()` function from there.
- Code should be importable without side effects (no work happens just from `import module`).

## 6. CLI design
- Use `argparse` (or a comparable library) for any script that takes inputs — no positional magic, no hardcoded paths. Flags should be named, order-independent, and self-documenting (`--help` should be genuinely useful).

## 7. Error handling
- Catch exceptions deliberately and narrowly — never a bare `except:`.
- Fail with a clear message and a non-zero exit code on error; don't let scripts silently continue on bad input.

## 8. Git workflow
- Never commit directly to `main`. Branch → push → open a pull request → merge → pull latest `main` locally.
- Use descriptive branch names and commit messages (why, not just what).
- Tag meaningful points (releases, milestones) with annotated tags.

## 9. Repository layout
- Standard structure: `src/` (source), `test/` (tests, mirroring `src/` layout), `doc/` (docs/specs), plus `.gitignore`, `LICENSE`, and `README.md` at the root.
- Don't let scratch files, notebooks-as-scripts, or generated output land outside their designated folder.

## 10. README
At minimum, the README must cover, in this order:
1. A short description — the "elevator pitch": scientific field, methods/models used, expected input data.
2. How to use it, with concrete examples — not just the flags `argparse` prints, but example commands and what they produce.
3. How to install it — step-by-step, assuming nothing about the reader's machine; point to `environment.yml` / mamba as the setup path.

---
*Generated from the team's "Best Practices — Software Engineering for Scientists" deck/doc. Keep this file in sync if those source materials change.*
