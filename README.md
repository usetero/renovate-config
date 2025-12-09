# renovate-config

Shared Renovate configuration preset for Tero repositories.

## Usage

Add this to your repository's `.github/renovate.json5`:

```json5
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>usetero/renovate-config"]
}
```

## What's Included

| Ecosystem | Minor/Patch | Major |
|-----------|-------------|-------|
| Go | Automerge, grouped | Grouped, manual review |
| npm | 7-day wait, grouped, manual review | Grouped, manual review |
| Docker | Automerge, grouped | Grouped, manual review |
| Terraform | Grouped, manual review | Grouped, manual review |
| GitHub Actions | Automerge, grouped | Grouped |
| Hermit | Automerge, grouped | Automerge, grouped |

### Schedule

- Runs nights (10pm-6am) and weekends only
- Lock file maintenance: Monday mornings
- Security alerts: Immediate (no delay)

### Safety

- 3-day minimum release age (7 days for npm)
- Security/vulnerability alerts bypass all delays
- PR limits: 5 concurrent, 4 per hour

## Docs

- [Renovate Config Presets](https://docs.renovatebot.com/config-presets/)
- [Configuration Options](https://docs.renovatebot.com/configuration-options/)
