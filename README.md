# Font Project Burndown Chart Generator GitHub Action

This repository is a GitHub action for [burndown-chart-generator](https://github.com/googlefonts/font-burndown-chart-generator)

## Usage

Example usage:

```yml
name: "Generate burndown chart"
on:
  # Only run manually
  workflow_dispatch:

jobs:
  burndown-chart:
    runs-on: ubuntu-latest
    steps:
      - name: "Checkout repo"
        uses: actions/checkout@v3
        with:
          # This does a full checkout of the repositry, making all
          # commits/branches/tags available, which is needed for generating
          # burndown chart, as we traverse Git history
          fetch-depth: 0
      - name: "Generate burndown chart"
        uses: daltonmaag/action-burndown@v0.1
```

Specifying the path to the config file:

```yml
steps:
  # -- snip --
  - name: "Generate burndown chart"
    uses: daltonmaag/action-burndown@v0.1
    with:
      config-path: "./path/to/burndown.toml"
```

## Versioning

This project adheres to [semantic versioning](https://semver.org/)

This GitHub action is versioned independent of the `burndown-chart-generator`.
A major new version of it does require a new major version of this GitHub Action, however minor version increments do not necessitate any version change of the GitHub Action: the GitHub action is pinned to the latest semver-compatible version of the `burndown-chart-generator` major release.
That is to say, if v0.1 of this GitHub Action is pinned to v0.1 of the `burndown-chart-generator`, then the Action will always use the latest v0.1.x version available on [PyPI](https://pypi.org/project/burndown-chart-generator/)
