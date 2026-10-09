# Cursor plugin template

Build and publish Cursor Marketplace plugins from a single repo.

Two starter plugins are included:

- **starter-simple**: rules and skills only
- **starter-advanced**: rules, skills, agents, commands, hooks, MCP, and scripts

## Getting started

[Use this template](https://github.com/cursor/plugin-template/generate) to create a new repository, then customize:

1. `.cursor-plugin/marketplace.json`: set marketplace `name`, `owner`, and `metadata`.
2. `plugins/*/.cursor-plugin/plugin.json`: set `name` (lowercase kebab-case), `displayName`, `author`, `description`, `keywords`, `license`, and `version`.
3. Replace placeholder rules, skills, agents, commands, hooks, scripts, and logos.

To add more plugins, see `docs/add-a-plugin.md`.

## Single plugin vs multi-plugin

This template defaults to **multi-plugin** (multiple plugins in one repo).

For a **single plugin**, move your plugin folder contents to the repository root, keep one `.cursor-plugin/plugin.json`, and remove `.cursor-plugin/marketplace.json`.

## Submission checklist

- Each plugin has a valid `.cursor-plugin/plugin.json`.
- Plugin names are unique, lowercase, and kebab-case.
- `.cursor-plugin/marketplace.json` entries map to real plugin folders.
- All frontmatter metadata is present in rule, skill, agent, and command files.
- Logos are committed and referenced with relative paths.
- `node scripts/validate-template.mjs` passes.
- Repository is public and submitted at [cursor.directory/plugins/new](https://cursor.directory/plugins/new) (community directory). Listings for the curated marketplace on cursor.com go through [cursor.com/marketplace/publish](https://cursor.com/marketplace/publish).
