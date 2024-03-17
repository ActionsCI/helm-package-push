# Helm Package and Push Action

This GitHub Action builds a Helm chart's dependencies, packages the chart, and pushes it to a specified Helm repository.

## Inputs

- `chart_dir`: The directory containing the Helm chart to package.
- `version`: Version of the chart to package.
- `registry_url`: Helm registry URL to push the package.
- `token`: Token for authenticating against the Helm registry.

## Usage

To use this action in your workflow, add a step that references your action:

```yaml
steps:
- uses: actions/checkout@vv
- name: Package and Push Helm Chart
  uses: your-github-username/helm-package-push@v1
  with:
    chart_dir: path/to/your/chart
    version: 1.0.0
    registry_url: your-registry-url
    token: ${{ secrets.HELM_REGISTRY_TOKEN }}
```
Replace your-github-username with your GitHub username, path/to/your/chart with the path to your Helm chart, 1.0.0 with your chart version, your-registry-url with your Helm registry URL, and ensure you have HELM_REGISTRY_TOKEN || (custom name) secret set in your repository for authentication.

Additional Information
This action requires Helm can be installed and configured in the runner environment where the action is executed.