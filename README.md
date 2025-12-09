# renovate-config

Shared Renovate configuration preset for all Tero repositories. This centralizes our dependency update policies so they're consistent across the organization.

## Using This Preset

Add this to your repository's `.github/renovate.json5`:

```json5
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>usetero/renovate-config"]
}
```

That's it. Your repo will inherit all the policies below.

## Policies

| Ecosystem | Minor/Patch | Major |
|-----------|-------------|-------|
| Go | Automerge, grouped | Grouped, manual review |
| npm | 7-day wait, grouped, manual review | Grouped, manual review |
| Docker | Automerge, grouped | Grouped, manual review |
| Terraform | Grouped, manual review | Grouped, manual review |
| GitHub Actions | Automerge, grouped | Grouped |
| Hermit | Automerge, grouped | Automerge, grouped |

**Schedule:** Nights (10pm-6am) and weekends only. Lock file maintenance runs Monday mornings.

**Safety:** 3-day minimum release age (7 days for npm). Security alerts bypass all delays and run immediately.

**Limits:** 5 concurrent PRs, 4 per hour.

## Development

### Setup

```bash
# Activate Hermit to get node and task
. bin/activate-hermit
```

### Commands

```bash
task validate  # Validate the Renovate config
task do        # Same as validate (fast dev loop)
```

### Making Changes

1. Edit `default.json`
2. Run `task validate` to check syntax
3. Commit and push - CI will validate again

Changes take effect on the next Renovate run for all repos using this preset.

## Docs

- [Renovate Config Presets](https://docs.renovatebot.com/config-presets/)
- [Configuration Options](https://docs.renovatebot.com/configuration-options/)
