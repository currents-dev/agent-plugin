# agent-plugin

[Open Plugins](https://open-plugins.com/) agent extensions for [Currents](https://currents.dev).

Provides the [Currents MCP Server](https://github.com/currents-dev/currents-mcp) and supporting skills, agents, and rules — packaged as a single installable plugin for Cursor, Claude Code, and other conformant hosts.

## Setup

1. Install the plugin via your tool's plugin mechanism.
2. Set the `CURRENTS_API_KEY` environment variable ([get a key](https://currents.dev/docs/api/api-keys)).

## Structure

```
agent-plugin/
├── .plugin/
│   └── plugin.json        # Manifest
├── skills/
│   └── hello/SKILL.md    # Greeting / onboarding skill
├── commands/
│   └── status.md         # /agent-plugin:status
├── agents/
│   └── reviewer.md       # Code review sub-agent
├── rules/
│   └── prefer-const.mdc  # Coding standard
├── hooks/
│   └── hooks.json        # Post-write lint hook
├── scripts/
│   └── lint.sh           # Hook script
├── .mcp.json             # Currents MCP server
└── .lsp.json             # LSP servers (placeholder)
```

## MCP Server

The plugin installs the `@currents/mcp` server, giving agents access to:

- Test runs, results, and spec-file performance
- Project insights and error explorer
- Actions (quarantine, skip, tag)
- Webhooks management
- CI cancellation and run resets

See the full tool list in the [currents-mcp README](https://github.com/currents-dev/currents-mcp#tools).

## Components

- **MCP** — Currents MCP server (`@currents/mcp`)
- **Skills** — `hello` greets users and offers guidance
- **Commands** — `status` reports loaded components
- **Agents** — `reviewer` performs thorough code reviews
- **Rules** — `prefer-const` enforces `const` over `let`/`var`
- **Hooks** — runs lint after file writes

## License

MIT
