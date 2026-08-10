# starter-agent-plugins

Simple [Agent Plugins](https://agent-plugins.org) starter. This format uses a root `plugin.json` and can package skills and MCP servers that load in any spec-compatible client, including Cursor.

```text
starter-agent-plugins/
├── plugin.json
├── skills/
│   └── code-reviewer/
│       └── SKILL.md
└── mcp.json
```

## Included

- `plugin.json`: Agent Plugins 1.0.0 manifest (`$schema` is required)
- `skills/code-reviewer/`: one example [Agent Skill](https://agentskills.io/specification)
- `mcp.json`: one example remote MCP server (`type` is required)

## Not included

Agent Plugins 1.0.0 does not define rules, agents, commands, hooks, logos, or marketplace fields. For those Cursor-specific components, use `starter-simple` or `starter-advanced`.

Client-owned extras belong under `extensions` or a reverse-domain directory. See the [client extensions guide](https://agent-plugins.org/plugin-authors/client-extensions).
