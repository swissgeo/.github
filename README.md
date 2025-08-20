# .github

This is the special organization main repository

## Github Workflows Templates and Reusable Workflow

This repository contains the Swissgeo workflows templates and reusable workflows used for the organization's projects.

### Reusable workflows

Reusable workflow are in the [.github/workflows](.github/workflows/), they are managed by PP-BGDI.

:warning: ***WARNING: Changing reusable workflows affect all production PP-BGDI repositories :exclamation:*** :warning:

For more information on Reusable Workflow see [Reusing workflows](https://docs.github.com/en/actions/learn-github-actions/reusing-workflows).

:memo: *NOTE: Although in theory reusable workflows can be located in any repository, those ones needs be in the special `.github` repository because of the configuration of the Release Drafter action. This action can only read its configuration from the current repository (repository using the reusable workflow) or from the special `.github` repository (see [Probot Oktokit plugin config](https://github.com/probot/octokit-plugin-config#octokit-plugin-config)).*

## Testing the workflow

Before merging any changes in the reusable worklows main branch, they must be tested with [swissgeo/test-semver-workflow](https://github.com/swissgeo/test-semver-workflow). This repository is configured to use the reusable workflows based on the `develop` branch, not that the productive repository refer to the `main` branch.
