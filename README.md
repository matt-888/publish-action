# publish-action

automated container image publishing for multiple architectures

## Usage

1. Add this workflow:

```yaml
name: Publish

env:
    REGISTRY: ghcr.io

on:
  release:
    types: [created]

permissions:
  contents: read
  packages: write

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:

      - uses: matt-888/publish-action@main
        with:
            registry: ${{ env.REGISTRY }}
```
