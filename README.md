# Slack Post GitHub Action

GitHub Action that posts a message to a Slack channel

## Inputs

### `token`

**Required** The Slack auth token

### `channel`

**Required** The channel name to post to (example: `#general`)

### `text`

**Required** The message text to post

## Example usage

```
- name: Post Slack message
  uses: ynab/slack-post-action@v1
  with:
    token: ${{ secrets.SLACK_API_TOKEN }}
    channel: "#general"
    text: ":tada: This is a test from the ${{env.GITHUB_ACTION}} workflow! <https://github.com/ynab/slack-post-action|Action Documentation>"
```