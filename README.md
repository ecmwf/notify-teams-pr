# Notify Teams - New PR

A GitHub Action that notifies a Microsoft Teams channel when a new Pull Request is opened.

Supports both:
- **Teams Workflows (Power Automate)** webhooks (`AdaptiveCard`)
- **Legacy Office 365 Connector** incoming webhooks (`MessageCard`)

## Usage

Create `.github/workflows/notify-new-pr.yml`:

```yaml
name: Notify new PR

on:
  pull_request:
    types:
      - "opened"

jobs:
  notify:
    runs-on: ubuntu-latest
    steps:
      - name: Notify new PR
        uses: ecmwf/notify-teams-pr@v2
        with:
          incoming_webhook: ${{ secrets.MS_TEAMS_INCOMING_WEBHOOK }}
```
