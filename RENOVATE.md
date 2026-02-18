# Renovate

## Quick start

Add this file to the root of your repository `renovate.json`:

```json
{
    "$schema": "https://docs.renovatebot.com/renovate-schema.json",
    "extends": ["github>swissgeo/.github:renovate-preset"],
    "reviewers": ["keetraxx"],
    "baseBranchPatterns": ["master"]
}
```

- **`reviewers`**: List of GitHub usernames that will be assigned as reviewers on Renovate pull requests. It is also possible to set reviewers from a [CODEOWNERS](#CODEOWNERS) file.
- **`baseBranchPatterns`**: Branch patterns that Renovate will target for pull requests (e.g. `master`, `main`, `develop`, ...). If you don't set this, it will take the **default branch** of the repository. You can also use regex patterns (`develop-*`).

  Usually you only want to setup one branch for pull requests.

## Additional interesting parameters

- **`lockFileMaintenance`**: Keeps lock files (e.g. `package-lock.json`, `yarn.lock`) up-to-date by periodically regenerating them, even when no dependency versions have changed. See [docs](https://docs.renovatebot.com/configuration-options/#lockfilemaintenance).
- **`automerge`**: Automatically merges Renovate pull requests when all checks pass, reducing manual effort for low-risk updates. See [docs](https://docs.renovatebot.com/configuration-options/#automerge).
- **`rangeStrategy`**: Controls how Renovate updates version ranges in your manifest files (e.g. whether to widen, pin, or replace ranges), useful for ignoring or constraining specific packages. See [docs](https://docs.renovatebot.com/configuration-options/#rangestrategy).

## CODEOWNERS

Instead of manually listing reviewers in `renovate.json`, you can use GitHub's [CODEOWNERS](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners) file to automatically assign reviewers based on file ownership. By enabling [`assigneesFromCodeOwners`](https://docs.renovatebot.com/configuration-options/#assigneesfromcodeowners) in your Renovate configuration, Renovate will look up the matching code owners for the files changed in each pull request and assign them as reviewers. This keeps reviewer assignments consistent with your repository's ownership model and avoids having to maintain a separate list of reviewers in `renovate.json`.

Example `CODEOWNERS` file (place it in `.github/CODEOWNERS`):

```txt
# Assign reviewers by file extension — using individual users
*.ts       @smith @johndoe
*.py       @janedoe

# Assign reviewers by folder — using organization teams
/docs/     @swissgeo/docs-team
/infra/    @swissgeo/devops-team
```

You can use individual GitHub usernames (`@smith`) and/or organization teams (`@swissgeo/devops-team`). Organization teams are managed in your GitHub organization under **Settings > Teams**.

