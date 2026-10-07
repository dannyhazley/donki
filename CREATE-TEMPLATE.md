# Publish `base-repo` as a GitHub template

This is a one-time setup for the reusable template itself.

1. In GitHub, create a new repository named `base-repo` and keep it **private**. Do not initialize it with extra files.
2. Open this local folder in GitHub Desktop, create the initial commit on `main`, and publish it to the private `base-repo` repository.
3. On GitHub, open **Settings → General** and enable **Template repository**.
4. Keep the template private. When creating a project, choose **Use this template** and create the new repository as private.
5. In each generated project, follow `SETUP.md` to configure `main` protection and add the project’s stack-specific CI.

The template copies its files and branch structure. GitHub repository settings such as branch protection must be configured on each new repository. See [GitHub's template repository guide](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-template-repository).

