# Cursor plugin template

Build and publish Cursor Marketplace plugins from a single repo.

This template includes both [Cursor Plugins](https://cursor.com/docs/plugins) and an [Agent Plugins](https://agent-plugins.org) starter:

- **starter-simple**: Cursor Plugin with rules and skills only
- **starter-advanced**: Cursor Plugin with rules, skills, agents, commands, hooks, MCP, and scripts
- **starter-agent-plugins**: Agent Plugins format with a root `plugin.json`, skills, and MCP servers

Cursor Plugins use `.cursor-plugin/plugin.json` and can bundle Cursor-specific components. Agent Plugins use a root `plugin.json` with the standard `$schema` and package portable skills and MCP servers.

## Getting started

[Use this template](https://github.com/cursor/plugin-template/generate) to create a new repository, then customize:

1. `.cursor-plugin/marketplace.json`: set marketplace `name`, `owner`, and `metadata`.
2. For a Cursor Plugin, edit `plugins/*/.cursor-plugin/plugin.json`: set `name` (lowercase kebab-case), `displayName`, `author`, `description`, `keywords`, `license`, and `version`.
3. For an Agent Plugin, edit `plugins/*/plugin.json`: keep `$schema` and set `name`, `author`, `description`, `keywords`, `license`, and `version`.
4. Replace placeholder rules, skills, agents, commands, hooks, scripts, MCP servers, and logos.

To add more plugins, see `docs/add-a-plugin.md`.

## Single plugin vs multi-plugin

This template defaults to **multi-plugin** (multiple plugins in one repo).

For a **single plugin**, move your plugin folder contents to the repository root, keep one `.cursor-plugin/plugin.json`, and remove `.cursor-plugin/marketplace.json`.

## Submission checklist

- Each Cursor Plugin has a valid `.cursor-plugin/plugin.json`.
- Each Agent Plugin has a valid root `plugin.json` with `$schema` set to `https://agent-plugins.org/schemas/1.0.0/plugin.schema.json`.
- Plugin names are unique, lowercase, and kebab-case.
- `.cursor-plugin/marketplace.json` entries map to real plugin folders.
- All frontmatter metadata is present in rule, skill, agent, and command files.
- Logos are committed and referenced with relative paths.
- `node scripts/validate-template.mjs` passes.
- Repository link is ready for submission to the Cursor team (Slack or `kniparko@anysphere.com`).
