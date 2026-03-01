# RAPS CI/CD Actions

Official CI/CD integrations for [RAPS](https://github.com/dmytro-yemelianov/raps) — the Rust Autodesk Platform Services CLI.

## GitHub Actions

| Action | Description |
|--------|-------------|
| [setup](setup/) | Install RAPS and configure APS authentication |
| [upload](upload/) | Upload files to Autodesk OSS |
| [translate](translate/) | Translate models via Model Derivative API |
| [pipeline](pipeline/) | Run a RAPS pipeline file |

### Quick Start

```yaml
- uses: dmytro-yemelianov/raps-actions/setup@v1
  with:
    client-id: ${{ secrets.APS_CLIENT_ID }}
    client-secret: ${{ secrets.APS_CLIENT_SECRET }}
```

See each action's directory for full input/output documentation.

## GitLab CI Templates

Reusable [include templates](https://docs.gitlab.com/ee/ci/yaml/includes.html) for GitLab CI/CD.

| Template | Hidden Job | Description |
|----------|-----------|-------------|
| [setup.yml](gitlab/setup.yml) | `.raps-setup` | Install RAPS and configure APS authentication |
| [upload.yml](gitlab/upload.yml) | `.raps-upload` | Upload files to Autodesk OSS |
| [translate.yml](gitlab/translate.yml) | `.raps-translate` | Translate models via Model Derivative API |
| [pipeline.yml](gitlab/pipeline.yml) | `.raps-pipeline` | Run a RAPS pipeline file |

### Quick Start

```yaml
include:
  - remote: 'https://raw.githubusercontent.com/dmytro-yemelianov/raps-actions/v1/gitlab/setup.yml'

my-job:
  extends: .raps-setup
  script:
    - raps bucket list
```

**Required CI/CD variables** (Settings > CI/CD > Variables):
- `APS_CLIENT_ID` — APS OAuth Client ID
- `APS_CLIENT_SECRET` — APS OAuth Client Secret

**Optional variable:**
- `RAPS_VERSION` — Version to install (default: `latest`)

See [gitlab/example.gitlab-ci.yml](gitlab/example.gitlab-ci.yml) for a complete example using all 4 templates.
