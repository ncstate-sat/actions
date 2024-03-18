# SAT Actions

Useful and reusable GitHub Composite Actions for your workflows. These actions
are designed for internal use only, but feel free to use them if you find them.

## Usage

```yaml
# .github/workflows/release.yml
name: Docker Login Example
on:
    workflow_dispatch:
jobs:
    release:
        runs-on: sat-hosted # internal runner label
        steps:
            - uses: actions/checkout@v3
              with:
                  repository: SAT/sat-actions
                  path: sat-actions

            - uses: ./sat-actions/docker-login
              with:
                  username: ${{ secrets.DOCKER_USERNAME }}
                  password: ${{ secrets.DOCKER_PASSWORD }}
                  registry-url: ${{ secrets.DOCKER_REGISTRY_URL }}

            ...
```
