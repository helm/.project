# Helm `.project`

`.project` (dot-project) is a CNCF initiative to centralize and automate metadata management for all CNCF projects.
This repository holds the canonical metadata for [Helm](https://helm.sh/) and its website, and is maintained by the CNCF automation tooling.
The `helm` GitHub organization hosts more than one project, so the repository uses the
[multi-project layout](https://github.com/cncf/automation/blob/main/utilities/dot-project/SCHEMA.md#repository-layouts):
each project lives in its own directory and `org.yaml` indexes them.

## What's in this repo

| File | Purpose |
|------|---------|
| `org.yaml` | Index of the projects in this repository (`helm`, `helm-www`) |
| `helm/project.yaml`, `helm-www/project.yaml` | Canonical project metadata (name, maturity, repositories, governance links, …) |
| `helm/maintainers.yaml`, `helm-www/maintainers.yaml` | Maintainer and reviewer roster used for drift detection and mailing-list sync |
| `CODEOWNERS` | Ensures PRs to this repo require maintainer approval |
| `.github/workflows/validate.yaml` | CI — validates every project's `project.yaml` and `maintainers.yaml` on every PR |
| `.github/workflows/update-landscape.yml` | Automatically proposes landscape updates when a `project.yaml` changes |

## Keeping metadata up to date

Open a pull request against this repository to update any metadata field.
The validate workflow will check schema correctness and block merge if validation fails.

> **Note:** This repository was bootstrapped automatically from public sources (CNCF landscape, CLOMonitor, GitHub governance files).
> Some fields are best-effort guesses marked with `# TODO: AUTO-DETECTED — please verify` in the YAML files and should be confirmed by the project maintainers.

## Resources

- [`.project` documentation](https://github.com/cncf/automation/tree/main/utilities/dot-project)
- [Schema reference](https://github.com/cncf/automation/blob/main/utilities/dot-project/SCHEMA.md)
- [CNCF Automation repository](https://github.com/cncf/automation)
