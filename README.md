# Notify Teams - New PR

A GitHub Action that notifies of a new Pull Request via Microsoft Teams.

See `action.yml` for required inputs.

## Usage

Create a file `.github/workflows/notify_new_pr.yml`

```
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
        uses: ecmwf-actions/notify-teams-pr@v1
        with:
          incoming_webhook: ${{ secrets.MS_TEAMS_INCOMING_WEBHOOK }}
```
