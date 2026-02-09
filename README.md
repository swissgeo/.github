# .github

This is the special organization main repository

- [Github Workflows](#github-workflows)
  - [Reusable workflows](#reusable-workflows)
    - [Amplify PR preview link](#amplify-pr-preview-link)
    - [PR Auto Semver](#pr-auto-semver)
    - [Semver Release](#semver-release)
  - [Testing the workflow](#testing-the-workflow)
- [Renovate](#renovate)

## Github Workflows

This repository contains the Swissgeo workflows templates and reusable workflows used for the organization's projects.

### Reusable workflows

Reusable workflow are in the [.github/workflows](.github/workflows/), they are managed by PP-BGDI.

> [!warning]
> Changing reusable workflows affect all repositories

For more information on Reusable Workflow see [Reusing workflows](https://docs.github.com/en/actions/learn-github-actions/reusing-workflows).

> [!NOTE]
> Although in theory reusable workflows can be located in any repository, those ones needs be in the special `.github` repository because of the configuration of the Release Drafter action. This action can only read its configuration from the current repository (repository using the reusable workflow) or from the special `.github` repository (see [Probot Oktokit plugin config](https://github.com/probot/octokit-plugin-config#octokit-plugin-config)).*

#### Amplify PR preview link

[amplify-pr-preview-link.yml](.github/workflows/amplify-pr-preview-link.yml) workflow can be used with
frontend deployed by AWS Amplify. Amplify automatically creates a PR comment with a preview link, which
uses a default amplify domain. This workflow update this comment with our custom deployment domain.

#### PR Auto Semver

[pr-auto-semver.yml](.github/workflows/pr-auto-semver.yml) workflow to set the PR label based on 
head branch prefix. It also automatically set the PR title for new release PR (develop -> master)

#### Semver Release

[semver-release.yml](.github/workflows/semver-release.yml) workflow to create a new semver tag and 
github release with auto generated release notes.

### Testing the workflow

Before merging any changes in the reusable worklows main branch, they must be tested with [swissgeo/test-semver-workflow](https://github.com/swissgeo/test-semver-workflow). This repository is configured to use the reusable workflows based on the `develop` branch, not that the productive repository refer to the `main` branch.

## Renovate

See [Renovate](README.md)
