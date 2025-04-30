# Publish GitBook Docs

Check the commit message for proper Signed-off-by and Contributed-under tags.
If the commit message is good, then publish the GitBook document in HTML,
PDF, and ePub formats.

## Example Workflow

```
name: 'Publish GitBook Docs'
on:
  pull_request_target:
    types:
      - opened
      - edited
      - reopened
      - synchronize
  push:
    branches:
      - main
      - release/*
  workflow_dispatch:

jobs:
  publish-gitbook-docs:
    name: Publish GitBook Docs
    runs-on: ubuntu-latest
    steps:
      - name: Publish GitBook Docs
        uses: tianocore-docs/publish-gitbook-docs
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
```

## License

This project is released under the terms of the [BSD-2-Clause Plus Patent License](License.txt)
