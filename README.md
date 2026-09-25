# HivemindOS for Cursor and Grok Bot

Official [Cursor](https://cursor.com) and Grok Bot plugin for [HivemindOS](https://hivemindos.app/superagent-api/).

Give your agent research reports, image and video generation, hundreds of models, memory that keeps what it learns, managed databases, websites, wallets and more, through one key and one credit balance.

This is a thin connector. It points at the hosted HivemindOS MCP server at `https://api.hivemindos.app/mcp` and ships one skill that tells the agent how to use its tools. It runs no local code, has no hooks and stores no keys.

## Install

1. Create an API key at [hivemindos.app/superagent-api/console](https://hivemindos.app/superagent-api/console/#keys). Give it only the services this agent needs.
2. In Cursor: Marketplace → search **HivemindOS** → Add. In Grok Bot: Settings → Plugins → search **HivemindOS** → Add.
3. Under Plugins → Configure, set `HIVEMINDOS_API_KEY` to your key.

## What it connects to

- Network: `https://api.hivemindos.app/mcp` only.
- Credential: `HIVEMINDOS_API_KEY`, sent as `Authorization: Bearer <key>`. The key is yours to limit, rotate or revoke in the console.

## Tools

- `hive_services_list`: services the key can use.
- `hive_actions_search`: find the exact action for a task.
- `hive_read`: run a read-only action.
- `hive_write`: run an action that changes something. Actions that spend, trade, transfer, sign, delete or publish ask you first.

## Privacy tiers

For work that must stay private, point the server at `https://api.hivemindos.app/v1/private/mcp` (only models and services that keep nothing you send) or `https://api.hivemindos.app/v1/confidential/mcp` (private, on attested hardware).

## Local test

```bash
cp -R . ~/.cursor/plugins/local/hivemindos
```

Reload the window, set `HIVEMINDOS_API_KEY`, and connect the `hivemindos` MCP server.

## Terms and support

- [HivemindOS Terms](https://hivemindos.app/terms/)
- [HivemindOS Privacy](https://hivemindos.app/privacy/)
- [API docs](https://hivemindos.app/superagent-api/llms.txt)
- [Cursor Marketplace Publisher Terms](https://cursor.com/marketplace-publisher-terms)

## License

MIT. See [LICENSE](LICENSE).
