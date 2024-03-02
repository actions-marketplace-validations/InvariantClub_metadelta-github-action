# Metadelta GitHub Action

This allows you to compute a diff of your [Hasura](https://hasura.io/)
permissions using [Metadelta](https://invariant.club/).

The result will be a link on your pull-request to the [Metadelta
UI](https://metadelta.invariant.club/), that will download the diff as an
artifact from GitHub and allow you to view the permission changes in a
convenient UI.

## Requirements

Note that the GitHub API requires a private access token for accessing
artifacts, which you need to provide to the UI on the settings page: [Metadelta -
Settings](https://metadelta.invariant.club/settings).

Because of this, this Action works for both private and public repos.

## Usage

Add the following workflow:

```yaml
jobs:
  compute-diff:
    permissions:
      # To upload artifacts
      contents: write
      # To write a comment on the PR
      pull-requests: write
    runs-on: ubuntu-latest
    steps:
      - uses: InvariantClub/metadelta-github-action@v1.2
        with:
          # Repo-relative path to the hasura metadata folder.
          hasura_path: hasura/metadata
```
