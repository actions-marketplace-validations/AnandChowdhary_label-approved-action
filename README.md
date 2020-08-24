# 🏷️🎬 Label Approved Action

GitHub Action to automatically label approved pull requests

[![Build CI](https://github.com/koj-co/label-approved-action/workflows/Build%20CI/badge.svg)](https://github.com/koj-co/label-approved-action/actions?query=workflow%3A%22Build+CI%22)
[![Test CI](https://github.com/koj-co/label-approved-action/workflows/Test%20CI/badge.svg)](https://github.com/koj-co/label-approved-action/actions?query=workflow%3A%22Test+CI%22)
[![Release CI](https://github.com/koj-co/label-approved-action/workflows/Release%20CI/badge.svg)](https://github.com/koj-co/label-approved-action/actions?query=workflow%3A%22Release+CI%22)
[![Node CI](https://github.com/koj-co/label-approved-action/workflows/Node%20CI/badge.svg)](https://github.com/koj-co/label-approved-action/actions?query=workflow%3A%22Node+CI%22)

## ⚙️ Usage

### Inputs

#### `labels`

Comma-separated list of labels to add on the approved pull request, default to `approved`

#### `approvals`

List of labels to add on the approved pull request, default to `1`

### Environment variables

#### `GITHUB_TOKEN` (required)

GitHub token to add labels to pull requests: `GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}`

### Example

```yaml
name: Label PRs
on:
  pull_request_review:
    types:
      - submitted
      - edited
      - dismissed
jobs:
  automerge:
    runs-on: ubuntu-latest
    steps:
      - name: Label approved PRs
        uses: koj-co/label-approved-action@master
        with:
          labels: "approved"
          approvals: 2
        env:
          GITHUB_TOKEN: "${{ secrets.GITHUB_TOKEN }}"
```

## 📄 License

- Code: [MIT](./LICENSE) © [Koj](https://koj.co)
- "GitHub" is a trademark of GitHub, Inc.

<p align="center">
  <a href="https://koj.co">
    <img width="44" alt="Koj" src="https://kojcdn.com/v1598284251/website-v2/koj-github-footer_m089ze.svg">
  </a>
</p>
<p align="center">
  <sub>An open source project by <a href="https://koj.co">Koj</a>. <br> <a href="https://koj.co">Furnish your home in style, for as low as CHF175/month →</a></sub>
</p>
