# renovate-config

Shared Renovate configuration for Tero repositories.

## Usage

Add this to your repository's `.github/renovate.json5`:

```json5
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>usetero/renovate-config"]
}
```

See `default.json` for the actual policies.

## Development

```bash
. bin/activate-hermit  # Get node and task
task validate          # Validate config locally
```
