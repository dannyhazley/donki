# Contributing

All changes go through a pull request into `main`, including changes made by the repository owner.

## Branch names

Use `type/short-description`, for example:

- `feat/export-csv`
- `fix/empty-input`
- `docs/setup-guide`

The CI workflow checks this pattern.

Release Please branches named `release-please--branches--main` are the only automated exception.

## Pull request titles

Use a Conventional Commit title with a lowercase type, an optional scope, and a short description:

- `feat: add export`
- `fix(parser): handle empty input`
- `feat(api)!: remove legacy endpoint`

Allowed types: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, and `revert`.

## Reviews and merging

- A second-person approval is not required for solo repositories.
- Squash merge pull requests.
- Keep `main` protected; owner bypass is reserved for emergencies.
- Required CI checks must pass before merging.

## Checks

For code changes, CI must run the available formatter, linter, tests, and build. Add the project’s stack-specific workflow and make its check required in the `main` ruleset. Documentation-only repositories still run the repository policy and documentation checks.

## Releases

For projects that publish releases, use automated Semantic Versioning from Conventional Commit titles: `feat` is a minor release, `fix` is a patch release, and a breaking-change marker (`!` or a `BREAKING CHANGE:` footer) is a major release. Other types do not trigger a version bump.

Release automation opens a release PR for review. Because it uses the default GitHub Actions token, CI does not start automatically on that generated PR. Run the quality workflow and the project’s stack-specific CI manually against the release PR branch, confirm they pass, and then squash merge it.
