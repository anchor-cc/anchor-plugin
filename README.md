# Anchor plugin

**The productivity toolkit for every AI agent.**

[Anchor](https://anchor.cc) is a shared drive for you and your agents. This plugin connects your AI agent to it, so the agent can securely create, host, and share apps, interactive presentations, and documents that run on live data, along with SQL tables, HTML, Markdown, SVG, and other files.

- What Anchor is and what you can build with it: [anchor.cc](https://anchor.cc)
- How it works, file types, tables, sharing, and permissions: [anchor.cc/docs](https://anchor.cc/docs)
- The MCP server and its tools: [anchor.cc/mcp](https://anchor.cc/mcp)

## Install

The plugin adds one MCP server, `anchor`, at `https://mcp.anchor.cc/mcp`. It works with any agent that supports MCP; setup guides for every supported agent are at [anchor.cc/supported-agents](https://anchor.cc/supported-agents).

- **Cursor:** install **Anchor** from the [Cursor Marketplace](https://cursor.com/marketplace). Manual setup: [anchor.cc/supported-agents/cursor](https://anchor.cc/supported-agents/cursor).
- **Claude Code:** run `/plugin marketplace add anchor-cc/anchor-plugin`, then `/plugin install anchor@anchor`. Manual setup: [anchor.cc/supported-agents/claude-code](https://anchor.cc/supported-agents/claude-code).
- **Any other agent:** add the server URL above to its MCP configuration, as described at [anchor.cc/supported-agents/other](https://anchor.cc/supported-agents/other).

## Configuration

There is nothing to configure: no API keys, no environment variables. The first time your agent uses Anchor, it opens the Anchor login page in a browser. Sign in once, and the agent only ever touches what you can access.

## Try it

- "Build a sales dashboard app on Anchor connected to our CRM table, where managers approve big discounts."
- "Write our sprint retro as an Anchor Markdown doc and give me the link."
- "Organize my Anchor files into one folder per client."

## Repository layout

```
.cursor-plugin/marketplace.json   Cursor marketplace manifest (lets Cursor import this repository)
.claude-plugin/marketplace.json   Claude Code marketplace manifest
plugins/anchor/
  .cursor-plugin/plugin.json      Cursor plugin manifest
  .claude-plugin/plugin.json      Claude Code plugin manifest
  mcp.json                        MCP server definition, shared by both manifests
  assets/logo.svg                 Marketplace logo
```

## Support

[anchor.cc/support](https://anchor.cc/support) · [Privacy](https://anchor.cc/privacy) · [Terms](https://anchor.cc/terms)

## License

The plugin packaging in this repository is released under the [MIT License](LICENSE). The Anchor service is governed by the [Anchor terms](https://anchor.cc/terms).
