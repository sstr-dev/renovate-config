# @sstr-dev/renovate-config

📦 **Shared Renovate configuration presets by [sstr-dev](https://github.com/sstr-dev)**

This repository provides reusable Renovate configuration presets to ensure consistent and automated dependency updates across projects – including support for containers, Helm, GitHub Actions, Terraform, Ansible, and more.

---

## ✨ Features

- ✅ Automatically merges trusted updates (e.g., GitHub Actions, Docker digests)
- 🏷️ Automatically adds labels based on update type and datasource
- 🛠️ Custom regex managers for parsing dependencies in YAML and templated files
- 🔖 Semantic commit messages with structured prefixes and scopes
- 🧠 Preconfigured security and quality presets (OpenSSF Scorecard, merge confidence)
- 🧼 Automatic cleanup of obsolete branches

---

## 🔧 Usage

To use this configuration in your project, create or update your `renovate.json` or `.github/renovate.json`:

```json
{
  "extends": ["github>sstr-dev/renovate-config"]
}
```

You can also add your own project-specific settings:

```json
{
  "extends": ["github>sstr-dev/renovate-config"],
  "schedule": ["before 6am on Monday"],
  "automerge": false
}
```

---

## 📚 Preset Overview

| File                    | Purpose                                                                 |
|-------------------------|-------------------------------------------------------------------------|
| `default.json`          | Main preset – extends all other presets                                 |
| `autoMerge.json5`       | Rules for safely auto-merging updates (e.g., GitHub Actions, Docker)    |
| `labels.json5`          | Automatically applies labels (e.g., `type/patch`, `renovate/terraform`) |
| `semanticCommits.json5` | Enables semantic commit messages with scopes and changelogs             |
| `custom-managers.json5` | Custom dependency extraction for YAML files and GitHub URLs             |

---

## 🧪 Example: GitHub Actions Workflow

```yaml
on:
  workflow_dispatch:

jobs:
  renovate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: renovatebot/github-action@v43
        with:
          token: ${{ secrets.RENOVATE_TOKEN }}
```

---

## 📖 Resources

- [Renovate Docs](https://docs.renovatebot.com/)
- [Renovate Schema Reference](https://docs.renovatebot.com/renovate-schema/)
- [Conventional Commits](https://www.conventionalcommits.org/)

---

## 📝 License

This project is licensed under the [MIT License](./LICENSE).

---

## 🤝 Contributing

Contributions, suggestions, and pull requests are welcome! If you want to improve or extend the configuration, feel free to open an issue or submit a PR.
