# Pipeline-dart

pipeline for Affinidi dart projects

## How to use

1. add file to `.github/workflows/check.yaml` to add mr pipeline checks

```yaml
name: checks

on: 
  pull_request:
     
jobs:
  dart-pipeline:
    uses: affinidi/pipeline-dart/.github/workflows/check.yaml@main
    secrets: inherit
```

2. add file to `.github/workflows/release.yaml` to add semantic releases

```yaml
name: "release"

on:
  push:
    branches:
      - main

jobs:
  dart-pipeline:
    uses: affinidi/pipeline-dart/.github/workflows/release.yaml@main
    secrets: inherit
```

3. add file to `.github/workflow/publish.yaml` to add publishing to pub.dev

```yaml
name: "publish"

on:
  push:
    tags:
      - '**v[0-9]+.[0-9]+.[0-9]+*'
  workflow_dispatch:

jobs:
  dart-pipeline:
    uses: affinidi/pipeline-dart/.github/workflows/publish.yaml@main
    secrets: inherit
```
