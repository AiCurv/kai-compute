# kai-compute

Remote compute engine for Kai9000. Uses GitHub Actions as an on-demand VM.

## How it works
1. Agent sends a `repository_dispatch` event with a base64-encoded script
2. GitHub Actions spins up an Ubuntu VM (~30-60s)
3. Script executes with full apt/pip/npm access
4. Output is captured and returned as a downloadable artifact

## Structure
```
.github/workflows/engine.yml   # The compute engine
scripts/                        # Reusable helper scripts
outputs/                        # Last execution output (auto-updated)
```
