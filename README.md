# Publora for Hermes Agent

Publora publishes and schedules social media posts. With this plugin Hermes can check which accounts you have connected, save a draft, schedule a post, or publish it on LinkedIn, X, Instagram, Threads, TikTok, YouTube, Facebook, Bluesky, Mastodon and Telegram.

## What you need

A Publora account with at least one connected social account. You can [register for free](https://publora.com/register) and connect accounts in the [dashboard](https://app.publora.com/dashboard).

The free Starter plan includes 3 social accounts, 15 posts a month, 3 scheduled posts at a time and scheduling up to 7 days ahead. It covers every network except X, which needs a paid plan. See [pricing](https://publora.com/pricing).

## Setup

Install and enable the plugin:

```bash
hermes plugins install publora-team/hermes-publora --no-enable
hermes plugins enable publora
```

Sign in with OAuth. You don't need an API key:

```bash
hermes mcp add publora --url https://mcp.publora.com/mcp --auth oauth
```

Finish signing in to Publora in your browser and answer the prompt about enabling tools. To have Hermes ask before every write, add `trust: untrusted` under `mcp_servers.publora` in your Hermes `config.yaml`. The native server entry takes precedence over the plugin's own setting.

Then start a new Hermes session.

## What this plugin does

- It connects to the hosted Publora MCP server at `https://mcp.publora.com/mcp`. Your requests and post content go to Publora, and from there to the networks you choose.
- It adds nine skills with each network's rules: `linkedin-post`, `linkedin-analytics`, `x-post`, `instagram-post`, `threads-post`, `tiktok-post`, `bluesky-post`, `telegram-post` and `social-post` for YouTube, Facebook Pages and Mastodon.
- Hermes stores and refreshes the sign-in. The plugin has no local executable code and stores no credentials.
- Publishing is a write action: a published post goes out to your audience.

## Try it

- Show which social accounts are connected to my Publora workspace
- Write a LinkedIn post about the latest change in this repo and save it as a draft

## Help

- Troubleshooting: [docs.publora.com/mcp/troubleshooting](https://docs.publora.com/mcp/troubleshooting)
- Support: [support@publora.com](mailto:support@publora.com)
- [Privacy policy](https://publora.com/privacy) and [terms](https://publora.com/terms)

MIT licensed.
