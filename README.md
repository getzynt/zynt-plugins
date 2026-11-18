# ZYNT plugin for Claude Code and Codex

[ZYNT](https://getzynt.com) watches the market for news about the companies and people you sell to: funding rounds, hires, expansions, tenders and events. This plugin puts ZYNT in your AI agent's tools.

- **Sign in once.** The agent connects with your ZYNT account in the browser. No API key to copy, and ZYNT stays in your agent's tools for every chat.
- **"Set up ZYNT for me".** Your agent sets ZYNT up from what it already knows about your business, and asks you only what is missing.
- **"Signals for me" or "Any news on my list?"** Your agent reads every ZYNT list you have: the scored signals first, then the other news this week, then this month.

## Install

**Codex:** paste this into a chat:

```
Read https://github.com/getzynt/zynt-plugins/blob/main/INSTALL.md and follow it exactly.
```

**Claude Code:** type:

```
/plugin marketplace add getzynt/zynt-plugins
/plugin install zynt@zynt
```

Then `/mcp`, pick `zynt` and sign in.

**Claude.ai, ChatGPT and other assistants:** add ZYNT as a custom connector with the URL `https://app.getzynt.com/mcp`. See [the docs](https://app.getzynt.com/docs#mcp).

## What is inside

- A connection to ZYNT's remote MCP server (`https://app.getzynt.com/mcp`, Streamable HTTP, OAuth). Nothing runs on your machine.
- Two skills: `zynt-setup` and `zynt-news`. All other ZYNT tools (signals, events, lists, notes, tasks) come with the connection.

## License

MIT
