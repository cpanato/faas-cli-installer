# faas-cli-installer GitHub Action

This action enables you to use faas-cli in your GitHub Actions workflows.

For a quick start guide on the usage of `faas-cli`, please refer to https://docs.openfaas.com/.
For available `faas-cli` releases, see https://github.com/openfaas/faas-cli/releases.

## Usage

Add the following entry to your Github workflow YAML file:

```yaml
uses: cpanato/faas-cli-installer@main
with:
  faas-cli-release: '0.14.1' # optional
```

Example using a pinned version:

```yaml
jobs:
  test_cosign_action:
    runs-on: ubuntu-latest

    permissions:
      actions: none
      checks: none
      contents: none
      deployments: none
      issues: none
      packages: none
      pull-requests: none
      repository-projects: none
      security-events: none
      statuses: none

    name: Install Cosign and test presence in path
    steps:
      - name: Install faas-cli
        uses: cpanato/faas-cli-installer@main
        with:
          faas-cli-release: '0.14.1'
      - name: Check install!
        run: faas-cli version
```

### Optional Inputs
The following optional inputs:

| Input | Description |
| --- | --- |
| `faas-cli-release` | `faas-cli` version to use instead of the default. |
