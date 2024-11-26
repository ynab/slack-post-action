# Slack Post GitHub Action

GitHub Action that posts a message to a Slack channel

## Inputs

### `token`

**Optional** The Slack auth token.  This is only required if environment variable `SLACK_BOT_TOKEN` is not set.

### `channel`

**Required** The channel name to post to (example: `#general`)

### `thread_ts`

**Optional** The timestamp ID of the parent message to reply to (e.g., the `ts` output from a previous Slack message call)

### `text`

**Required** The message text to post. See [Slack's documentation on formatting](https://api.slack.com/reference/surfaces/formatting#basic-formatting). Note that single quotes in your message *must* be escaped as `\'` due to how this input is consumed by bash.

### `unfurl_links`

**Optional** Whether links in the message should be unfurled (default: `true`)

## Outputs

### `ts`

The timestamp ID of the message (can be used to make subsequent Slack messages a threaded reply)

## Example usage

```yaml
- name: Post Slack message
  uses: ynab/slack-post-message-action@v1.3
  with:
    token: ${{ secrets.SLACK_API_TOKEN }}
    channel: "#general"
    text: ":tada: This is a test from the $GITHUB_ACTION workflow! <https://github.com/ynab/slack-post-message-action|Action Documentation>"
```
