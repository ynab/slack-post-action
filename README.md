# Slack Post GitHub Action

GitHub Action that posts a message to a Slack channel

## Inputs

### `token`

**Optional** The Slack auth token.  This is only required if environment variable `SLACK_BOT_TOKEN` is not set.

### `channel`

**Required** The channel name to post to (example: `#general`)

#### `thread_ts`

**Optional** The timestamp ID of the parent message to reply to (e.g., the `ts` output from a previous Slack message call)

### `text`

**Required** The message text to post

## Outputs

### `ts`

The timestamp ID of the message (can be used to make subsequent Slack messages a threaded reply)

## Example usage

```yaml
- name: Post Slack message
  uses: ynab/slack-post-message-action@v1.2
  with:
    token: ${{ secrets.SLACK_API_TOKEN }}
    channel: "#general"
    text: ":tada: This is a test from the $GITHUB_ACTION workflow! <https://github.com/ynab/slack-post-message-action|Action Documentation>"
```
