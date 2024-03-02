# Metadelta GitHub Action

This allows you to compute a diff of your [Hasura](https://hasura.io/)
permissions using [Metadelta](https://invariant.club/).

Usage:

```
jobs:
  compute-diff:
    permissions:
      contents: write
      pull-requests: write
    runs-on: ubuntu-latest
    steps:
      - uses: InvariantClub/metadelta-github-action@v1.1
        with:
          # Repo-relative path to the hasura metadata folder.
          hasura_path: hasura/metadata
```
