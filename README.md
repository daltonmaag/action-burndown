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
      - name: "Generate burndown chart"
        uses: daltonmaag/action-burndown@0.1
```

Specifying the path to the config file:

```yml
steps:
  - name: "Generate burndown chart"
    uses: daltonmaag/action-burndown@0.1
    with:
      config-path: "./path/to/burndown.toml"
```
