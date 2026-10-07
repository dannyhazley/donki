# Releases

Release automation is opt-in. Use it only for repositories that publish versioned releases.

## Version policy

Release Please reads Conventional Commit titles and opens a release PR with a version bump and generated release notes:

- `feat` → minor
- `fix` → patch
- a breaking change (`!` in the title or a `BREAKING CHANGE:` footer) → major
- other types → no version bump

Review the release notes and version in the generated PR, then squash merge it to publish the GitHub release.

## Enable the workflow

1. Copy `.github/workflows/release-please.yml.example` to `.github/workflows/release-please.yml`.
2. Add the Release Please config and manifest for the project’s actual release type and initial version. See the [Release Please manifest guide](https://github.com/googleapis/release-please/blob/main/docs/manifest-releaser.md).
3. In GitHub Actions settings, allow GitHub Actions to create pull requests.
4. When Release Please opens a release PR, manually run `Repository quality` and the project’s stack-specific CI against that PR branch. GitHub does not automatically start workflows for PRs created with the default `GITHUB_TOKEN`.
5. Merge the release PR only after its checks pass.

The template intentionally does not include a release config or manifest: those depend on the project’s package type and starting version.

