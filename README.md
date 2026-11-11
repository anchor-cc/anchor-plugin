# Anchor plugin

**The productivity toolkit for every AI agent.** You don't need a new AI. You need a home to store and share what it creates.

This plugin connects your AI to [Anchor](https://anchor.cc). Then just ask:

- **Apps, presentations, and documents** that run on live data and stay in sync with it.
- **Files** in HTML, Markdown, JSON, CSV, and more, hosted privately and shared with exactly the people you pick.
- **Tables** with typed columns that your AI can design and query with SQL.
- **Folders** to organize, navigate, and share with a structure you are familiar with.

Anchor handles storage, permissions, and versioning. Sign in once, with no API keys and no setup, and your AI only ever touches what you can access.

The plugin works with any agent that supports MCP plugins. It ships manifests for Cursor and Claude Code, and the same server can be added by hand to any other MCP client.

## What you get

One MCP server, `anchor`, at `https://mcp.anchor.cc/mcp` (Streamable HTTP, OAuth sign-in). Its tools cover:

| Area | Tools |
|------|-------|
| Browse and organize | `ls`, `mkdir`, `mv`, `cp`, `rm_file` |
| Files | `read_file`, `write_file`, `upload_file_presigned_url`, `download_file_presigned_url` |
| Tables | `create_table`, `describe_table`, `query_table`, `add_table_column`, `delete_table_column` |
| Apps, documents, presentations | `get_authoring_rules`, `unpack_file`, `build_app`, `commit_document`, `commit_presentation`, `list_mcp_servers` |

The server is the source of truth for the tool list; the table above reflects version 1.0.0 of this plugin.

## Install

### Cursor

Install **Anchor** from the [Cursor Marketplace](https://cursor.com/marketplace), then open **Cursor Settings → Tools & MCP** and sign in to Anchor when prompted.

### Claude Code

Clone this repository and load it as a plugin:

```
git clone https://github.com/anchor-cc/anchor-plugin.git
claude --plugin-dir ./anchor-plugin
```

Then run `/mcp` and sign in to Anchor.

### Any other MCP client

Add the server to your client's MCP configuration:

```json
{
  "mcpServers": {
    "anchor": {
      "url": "https://mcp.anchor.cc/mcp"
    }
  }
}
```

Step-by-step guides for each client are at [anchor.cc/mcp](https://anchor.cc/mcp).

## Configuration

There is nothing to configure: no API keys, no environment variables. The first time your AI uses Anchor, your client opens the Anchor login page in a browser (OAuth 2.0 with PKCE). You need an Anchor account; you can create one on that page.

## Try it

- "Write our sprint retro as an Anchor Markdown doc: wins, blockers, next sprint's bets. Give me the link."
- "Build an Anchor table for our CRM: company, contact, stage, ARR, last touch. Then show me Stage 3+ leads not touched in 14 days."
- "Build a sales dashboard app on Anchor connected to our CRM table, where managers approve big discounts."
- "Turn `docs/architecture.md` into a polished Anchor HTML page I can share with the team."
- "Organize my Anchor files into one folder per client."

## Repository layout

```
.cursor-plugin/plugin.json   Cursor manifest
.claude-plugin/plugin.json   Claude Code manifest
mcp.json                     MCP server definition, shared by both manifests
assets/logo.svg              Marketplace logo
```

## Support

- Documentation: [anchor.cc/mcp](https://anchor.cc/mcp)
- Support: support@anchor.cc
- Privacy policy: [anchor.cc/privacy](https://anchor.cc/privacy)

## License

The plugin packaging in this repository is released under the [MIT License](LICENSE). The Anchor service is governed by the [Anchor terms](https://anchor.cc/terms).
