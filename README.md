# Organization GitHub Configuration

This repository contains organization-wide GitHub configuration, reusable workflows, composite actions, and AI assistant integrations for the **epicpast** ecosystem.

## What This Repository Provides

When you create this as `epicpast/.github`, GitHub automatically applies these configurations across all repositories in the organization:

| Component | Purpose | Location |
|-----------|---------|----------|
| **Community Health Files** | Default SECURITY.md, CONTRIBUTING.md for all repos | Root directory |
| **Organization Profile** | Public profile shown on github.com/epicpast | `profile/README.md` |
| **Reusable Workflows** | Callable CI/CD workflows for all repos | `.github/workflows/` |
| **Composite Actions** | Shared action building blocks | `actions/` |
| **Label Definitions** | Standardized issue/PR labels | `labels.yml` |
| **Copilot Skills** | AI-assisted development capabilities | `.github/skills/` |
| **Autonomous Agents** | Multi-step AI workflow automation | `agents/` |

## Repository Structure

```
.github/
├── .github/
│   ├── workflows/               # Reusable workflows
│   │   ├── reusable-ci-python.yml
│   │   ├── reusable-ci-typescript.yml
│   │   ├── reusable-ci-go.yml
│   │   ├── reusable-release.yml
│   │   ├── reusable-security.yml
│   │   └── sync-labels.yml
│   ├── skills/                  # Copilot Skills
│   │   └── (planned)
│   ├── copilot-instructions.md  # Organization-wide Copilot context
│   └── ISSUE_TEMPLATE/          # Issue templates
├── actions/                     # Composite Actions (planned)
├── agents/                      # Autonomous Agents (planned)
├── profile/
│   └── README.md                # Organization profile
├── labels.yml                   # Standard label definitions
├── SECURITY.md                  # Security policy
├── CONTRIBUTING.md              # Contribution guidelines
├── FUNDING.yml                  # Sponsorship configuration
└── README.md                    # This file
```

## Reusable Workflows

Call these workflows from any repository in the organization:

### Python CI

```yaml
jobs:
  ci:
    uses: epicpast/.github/.github/workflows/reusable-ci-python.yml@main
    with:
      python-version: "3.12"
      coverage-threshold: 80
```

### TypeScript CI

```yaml
jobs:
  ci:
    uses: epicpast/.github/.github/workflows/reusable-ci-typescript.yml@main
    with:
      node-version: "22"
      coverage-threshold: 80
```

### Go CI

```yaml
jobs:
  ci:
    uses: epicpast/.github/.github/workflows/reusable-ci-go.yml@main
    with:
      go-version: "1.23"
      coverage-threshold: 80
```

### Security Scanning

```yaml
jobs:
  security:
    uses: epicpast/.github/.github/workflows/reusable-security.yml@main
    with:
      python-audit: true
      node-audit: true
```

### Release Automation

```yaml
jobs:
  release:
    uses: epicpast/.github/.github/workflows/reusable-release.yml@main
    with:
      release-type: auto  # or patch, minor, major
```

## Label Sync

The `sync-labels.yml` workflow maintains consistent labels across repositories.

### Available Labels

| Category | Labels |
|----------|--------|
| **Priority** | `priority: critical`, `priority: high`, `priority: medium`, `priority: low` |
| **Type** | `type: bug`, `type: feature`, `type: enhancement`, `type: documentation`, `type: security`, `type: maintenance`, `type: performance` |
| **Status** | `status: needs-triage`, `status: in-progress`, `status: blocked`, `status: ready-for-review`, `status: approved` |
| **Area** | `area: ci-cd`, `area: dependencies`, `area: testing`, `area: infrastructure` |
| **Effort** | `effort: small`, `effort: medium`, `effort: large` |

### Manual Sync

```bash
# Sync labels to a specific repo
gh workflow run sync-labels.yml -f target_repository=epicpast/my-repo

# Preview changes first (dry run)
gh workflow run sync-labels.yml -f target_repository=epicpast/my-repo -f dry_run=true
```

## Security Policy

The `SECURITY.md` file defines:
- Vulnerability reporting process
- Response timelines
- Security scope
- Safe harbor provisions

## Contributing

See `CONTRIBUTING.md` for:
- Code of conduct
- Pull request process
- Commit message conventions
- Code review requirements

## Customization

### Adding New Workflows

1. Create workflow in `.github/workflows/`
2. Use `workflow_call` trigger for reusability
3. Document inputs and secrets in workflow comments
4. Add usage example to this README

### Modifying Labels

1. Edit `labels.yml`
2. Run sync workflow to apply changes
3. Labels are additive (won't delete existing labels by default)

## Security Best Practices

All workflows in this repository follow security best practices:

- **SHA-Pinned Actions**: All actions use full commit SHA with version comments
- **Input Validation**: All user inputs are validated before use
- **Environment Variables**: Inputs passed via env blocks, not interpolated in commands
- **Minimal Permissions**: Explicit permissions declarations with least privilege
- **No Secret Exposure**: Secrets only in `env:` blocks, never in shell expansions

## License

MIT License - See individual files for specific licensing.
