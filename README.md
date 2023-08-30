# GitHub Action - Automatically Rebuild Pull Requests
This is a GitHub Action to automatically rebuild pull requests when the pull request target changes.

Review the GitHub action in the marketplace: [GitHub Rebuild PullRequests](https://github.com/marketplace/actions/github-rebuild-pull-requests)

### How does this GitHub action work?
When a branch in your GitHub repository is updated, this GitHub action automatically finds open pull requests that target that branch and forces a rebuild for them.

## Usage
In your GitHub action workflow add the follow step.

```yaml
# Important! This is required: https://docs.github.com/en/rest/actions/workflow-jobs?apiVersion=2022-11-28
permissions:
  contents: read
  actions: write

jobs:
  build:
    steps:
    - uses: actions/checkout@v2
    # Put this action anywhere in your GitHub action workflow
    - uses: rhosys/github-action-rebuild-pull-requests@v1
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
```