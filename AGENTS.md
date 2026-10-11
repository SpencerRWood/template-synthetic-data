# Repository Guidance

## Purpose and boundaries
- Maintain a reusable typed synthetic-data generation baseline.
- Leave real datasets, schemas, and deployment decisions to projects created from it.

## Development
- Keep generators in `src/`, scenario tests in `tests/`, and output paths configurable.
- Preserve deterministic seeds and repeatable fixture behavior when changing generation code.

## Validation
- Run `uv sync --frozen --group dev`, `uv run ruff check .`, `uv run ruff format --check .`, `uv run mypy`, `uv run pytest`, and `uv run pre-commit run --all-files`.
- Run `uv build` when package metadata changes.

## Architecture constraints
- Keep the package and documentation rename-ready.
- Do not tie template data generation to a particular database or deployment target.

## Safety
- Use generated or placeholder examples only; avoid real user data and secrets.

## Branching strategy

- This repository uses **trunk-based development**. Create short-lived change branches from current `main` and target PRs to `main`.
- Follow the [canonical branching and delivery policy](https://github.com/SpencerRWood/codex-config/blob/main/docs/branching-policy.md), available through the installed codex-config source path. Verify the strategy, release association, fetched base and PR target before implementation and record them in Story evidence. Story completion does not authorize publication or deployment; retain existing review, CI, security and rollback requirements.
- This classification applies to maintenance of the template repository. Replace it with the new repository's classification during project creation; applications must use release-branch integration before Story development begins.
