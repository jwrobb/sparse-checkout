# Sparse checkout

Sparse checkout a git repository like [actions/checkout](https://github.com/actions/checkout).

## Usage

```yml
name: 'Checkout mono repository'
on:
  push:

jobs:
  checkout:
    runs-on: ubuntu-20.04
    steps:
      - uses: snow-actions/sparse-checkout@v1.1.0
        with:
          initopts: "--no-cone"
          patterns: |
            .github
```

## Inputs

See [action.yml](action.yml).

|name|required|description|default value|
|---|---|---|---|
|patterns|required|Write a set of patterns to the sparse-checkout file.|-|
|initopts|optional|Pass parameters to the `sparse-checkout init` command.|`--cone`|
|repository|optional|Same as actions/checkout|`${{ github.repository }}`|
|ref|optional|Same as actions/checkout|`''`|
|token|optional|Same as actions/checkout|`${{ github.token }}`|
|path|optional|Same as actions/checkout|`'.'`|

## Support OS
[![Test](https://github.com/snow-actions/sparse-checkout/actions/workflows/test.yml/badge.svg)](https://github.com/snow-actions/sparse-checkout/actions/workflows/test.yml)

* `ubuntu-20.04` (`ubuntu-latest`)
* `ubuntu-18.04`
* `windows-2019` (`windows-latest`)
* `windows-2016`
* `macos-10.15` (`macos-latest`)
