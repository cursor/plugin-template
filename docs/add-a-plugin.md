# Add a plugin

Add a new plugin under `plugins/` and register it in `.cursor-plugin/marketplace.json`.

Choose a format first:

- **Cursor Plugin**: `.cursor-plugin/plugin.json`, plus any of rules, skills, agents, commands, hooks, and MCP
- **Agent Plugin**: root `plugin.json` with the Agent Plugins `$schema`, plus optional `skills/` and `mcp.json`

## 1. Create plugin directory

Create a new folder:

```text
plugins/my-new-plugin/
```

### Cursor Plugin manifest

```text
plugins/my-new-plugin/.cursor-plugin/plugin.json
```

Example manifest:

```json
{
  "name": "my-new-plugin",
  "displayName": "My New Plugin",
  "version": "0.1.0",
  "description": "Describe what this plugin does",
  "author": {
    "name": "Your Org"
  },
  "logo": "assets/logo.svg"
}
```

### Agent Plugin manifest

```text
plugins/my-new-plugin/plugin.json
```

Example manifest:

```json
{
  "$schema": "https://agent-plugins.org/schemas/1.0.0/plugin.schema.json",
  "name": "my-new-plugin",
  "version": "1.0.0",
  "description": "Describe what this plugin does",
  "author": {
    "name": "Your Org"
  }
}
```

The Agent Plugins schema is closed. Do not add `displayName`, `logo`, `hooks`, `rules`, or other Cursor-only fields at the top level.

## 2. Add plugin components

Add only the components you need.

### Cursor Plugin components

- `rules/` with `.mdc` files (YAML frontmatter required)
- `skills/<skill-name>/SKILL.md` (YAML frontmatter required)
- `agents/*.md` (YAML frontmatter required)
- `commands/*.(md|mdc|markdown|txt)` (frontmatter recommended)
- `hooks/hooks.json` and `scripts/*` for automation hooks
- `mcp.json` for MCP server definitions
- `assets/logo.svg` for marketplace display

### Agent Plugin components

- `skills/<skill-name>/SKILL.md` (YAML frontmatter required)
- `mcp.json` for MCP server definitions

`mcp.json` must include `$schema`, and each server must declare `type` (`stdio`, `streamable-http`, or `sse`). Agent Plugins do not include rules, agents, commands, hooks, or logos.

## 3. Register in marketplace manifest

Edit `.cursor-plugin/marketplace.json` and append a new entry:

```json
{
  "name": "my-new-plugin",
  "source": "./plugins/my-new-plugin",
  "description": "Describe your plugin"
}
```

`source` is the relative path from the repository root to the plugin folder.

## 4. Validate

```bash
node scripts/validate-template.mjs
```

Fix all reported errors before committing.

## 5. Common pitfalls

- Plugin `name` not kebab-case.
- `source` path in marketplace manifest does not match folder name.
- Missing `.cursor-plugin/plugin.json` for a Cursor Plugin, or missing root `plugin.json` `$schema` for an Agent Plugin.
- Adding Cursor-only fields (`displayName`, `logo`, `rules`) to an Agent Plugin `plugin.json`.
- Agent Plugin `mcp.json` missing `$schema` or server `type`.
- Missing frontmatter keys (`name`, `description`) in skills, agents, or commands.
- Rule files missing frontmatter `description`.
- Using a filename other than `mcp.json` for MCP server definitions.
- Broken relative paths for `logo`, `hooks`, or `mcpServers` in manifest files.

## 6. More resources

- [Cursor Plugins documentation](https://cursor.com/docs/plugins)
- [Agent Plugins](https://agent-plugins.org/)
