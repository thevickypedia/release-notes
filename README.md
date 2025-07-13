[![made-with-gha](https://img.shields.io/badge/Made%20with-Github_Actions-black?style=for-the-badge&logo=GitHub)][marketplace]

# update-release-notes

GitHub actions to generate/update release notes using [gitverse]

## Install Guide

#### Add `update-release-notes` action to your build workflow

- In your GitHub repository, select the Actions tab and either add or edit a workflow.
- Navigate to `update-release-notes` in [Marketplace][marketplace].
- Copy and paste the yaml into your workflow.

**[OR]**

Copy & paste the following workflow definition into your project `.github/workflows/update-release-notes.yml`

```yaml
name: Update Release Notes

on:
  workflow_dispatch:
  release:
    types: [ published ]

jobs:
  update-release-notes:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0
      - uses: actions/setup-python@v4
        with:
          python-version: '3.x'
      - uses: thevickypedia/update-release-notes@v1
        env:
          git_token: ${{ secrets.GIT_TOKEN }}
```

### Allowed Inputs

| Parameter       | Description                                    | Default             |
|-----------------|------------------------------------------------|---------------------|
| `source`        | Source for release notes. (`commit`/`release`) | `release`           |
| `commit-branch` | Branch to use for commit-based release notes.  | `$default`          |
| `branch`        | Branch to push release notes to.               | `$default`          |
| `filename`      | Filename for the release notes.                | `release_notes.rst` |
| `title`         | Title for the release notes.                   | `Release Notes`     |
| `reverse`       | Boolean flag to sort in reverse order.         | `true`              |

## License & copyright

&copy; Vignesh Rao

Licensed under the [MIT License][license]

[license]: https://github.com/thevickypedia/update-release-notes/blob/main/LICENSE

[gitverse]: https://github.com/thevickypedia/gitverse

[marketplace]: https://github.com/marketplace/actions/update-release-notes
