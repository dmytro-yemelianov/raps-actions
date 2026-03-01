# RAPS GitHub Actions

Official GitHub Actions for [RAPS](https://github.com/dmytro-yemelianov/raps) — the Rust Autodesk Platform Services CLI.

## Actions

| Action | Description |
|--------|-------------|
| [setup](setup/) | Install RAPS and configure APS authentication |
| [upload](upload/) | Upload files to Autodesk OSS |
| [translate](translate/) | Translate models via Model Derivative API |
| [pipeline](pipeline/) | Run a RAPS pipeline file |

## Quick Start

```yaml
- uses: dmytro-yemelianov/raps-actions/setup@v1
  with:
    client-id: ${{ secrets.APS_CLIENT_ID }}
    client-secret: ${{ secrets.APS_CLIENT_SECRET }}
```

See each action's directory for full input/output documentation.
