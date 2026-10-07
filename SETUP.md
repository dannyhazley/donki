# New repository setup

Use this checklist after creating a repository from the `base-repo` template.

## GitHub repository

- [ ] Create the repository as **private**. Make it public only when ready.
- [ ] Keep `main` as the default branch.
- [ ] Allow **squash merging**; disable merge commits and rebase merging.
- [ ] Enable the `main` branch ruleset described below.
- [ ] Enable Dependabot security updates. Do not enable routine version update PRs by default.
- [ ] Add a stack-specific CI workflow for code repositories, covering formatting, lint, tests, and build.
- [ ] If the project publishes releases, follow `RELEASING.md` and enable the opt-in release workflow.
- [ ] Before making a repository public, choose and add its license, review the README for private details, and check that no secrets or credentials are tracked.

## `main` ruleset

GitHub provides branch protection and rulesets for private repositories on Pro and higher plans. On Free, these protections are available for public repositories. GitHub's Student Developer Pack includes Pro for verified students while that benefit is active; see [GitHub Education plan benefits](https://docs.github.com/en/get-started/learning-about-github/faq-about-changes-to-githubs-plans). Check [current ruleset availability](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets) before relying on a private repository's ruleset.

Create an active ruleset targeting the default branch:

- Require a pull request before merging.
- Require **zero** approvals; these are solo repositories.
- Require the `PR title and branch`, `Markdown lint`, and `Link check` status checks. For code repositories, also require the stack-specific CI check.
- Block force-pushes and branch deletion.
- Allow the repository owner to bypass the ruleset for emergencies.
- If using release automation, allow GitHub Actions to create pull requests in the repository’s Actions settings.

GitHub repository rulesets are configured in repository settings and are not part of the template files. The workflows validate branch names and PR titles; the ruleset makes the relevant checks a merge gate.

## Project-specific setup

- [ ] Replace the README placeholders and keep the purpose, setup, usage, configuration, tests, and license sections.
- [ ] Add stack-specific `.gitignore` entries without removing the shared baseline unless they conflict.
- [ ] Add `.env.example` with placeholder values if the project needs environment variables.
- [ ] Add local format, lint, test, and build commands to the README and matching CI workflow.
- [ ] If the project publishes releases, configure release automation to follow the SemVer mapping in `CONTRIBUTING.md`.
