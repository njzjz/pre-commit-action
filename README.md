# Run pre-commit action with autofix

Run pre-commit on the head reference. If it is triggered by a PR, apply and commit the autofix.

> [!NOTE]
> GitHub Actions runs will [not be triggered](https://github.com/orgs/community/discussions/25702) with the autofix commit. In this case, one can close and reopen the PR to manually trigger the GitHub Actions runs.

`contents: write` permission is required to push autofix commits.

## Usage

```yaml
name: Pre-commit
on:
  push:
  pull_request:
  merge_group:
jobs:
  pre_commit:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    steps:
      - name: Run pre-commit
        uses: njzjz/pre-commit-action@master
```
