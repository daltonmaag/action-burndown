# Font Project Burndown Chart Generator GitHub Action

This repository is a GitHub action for [burndown-chart-generator](https://github.com/daltonmaag/font-burndown-chart-generator)

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
