# Cursor plugin template

Build and publish Cursor Marketplace plugins from a single repo.

Two starter plugins are included:

- **starter-simple**: rules and skills only
- **starter-advanced**: rules, skills, agents, commands, hooks, MCP, and scripts

## Repository layout

```text
.
├── .cursor-plugin/
│   └── marketplace.json
├── plugins/
│   ├── starter-simple/
│   │   ├── .cursor-plugin/plugin.json
│   │   ├── rules/
│   │   ├── skills/
│   │   └── assets/
│   └── starter-advanced/
│       ├── .cursor-plugin/plugin.json
│       ├── rules/
│       ├── skills/
│       ├── agents/
│       ├── commands/
│       ├── hooks/
│       ├── mcp.json
│       ├── scripts/
│       └── assets/
├── docs/add-a-plugin.md
└── scripts/validate-template.mjs
```

## Use this template

1. Click **Use this template** > **Create a new repository** on GitHub.
2. Choose owner, repo name, and visibility.
3. Create the repository. Default branch only is recommended.
4. Clone and customize.

## Quick customization

Update these files first:

1. `.cursor-plugin/marketplace.json`
   - Set marketplace `name`, `owner`, and `metadata`.
   - `metadata.pluginRoot` is optional. Remove it if plugin `source` paths are explicit.
2. `plugins/*/.cursor-plugin/plugin.json`
   - Rename `name` to a unique lowercase kebab-case value.
   - Replace `author`, `description`, `keywords`, `license`, and `version`.
   - Keep logo paths relative (e.g. `assets/logo.svg`).
3. Replace placeholder content:
   - `plugins/*/assets/logo.svg`
   - Rules, skills, agents, commands, hooks, and scripts

## Single plugin vs multi-plugin

Use **multi-plugin** (current setup) when one repository publishes several related plugins.

For a **single plugin**:

1. Move your plugin folder contents to the repository root.
2. Keep one `.cursor-plugin/plugin.json` at the root plugin directory.
3. Remove `.cursor-plugin/marketplace.json`.
4. Update all component paths accordingly.

## Local validation

```bash
node scripts/validate-template.mjs
```

This checks:

- Marketplace and plugin manifest presence
- Plugin naming format (kebab-case)
- Referenced file paths in manifests
- Frontmatter metadata on rules, skills, agents, and commands

## Submission checklist

- Each plugin has a valid `.cursor-plugin/plugin.json`.
- Plugin names are unique, lowercase, and kebab-case.
- `.cursor-plugin/marketplace.json` entries map to real plugin folders.
- All frontmatter metadata is present in rule, skill, agent, and command files.
- Logos are committed and referenced with relative paths.
- `node scripts/validate-template.mjs` passes.
- README and plugin docs describe behavior and required configuration.
- Repository link is ready for submission to the Cursor team (Slack or `kniparko@anysphere.com`).

## Next steps

- Add or remove plugin folders under `plugins/`.
- Follow `docs/add-a-plugin.md` for adding a new plugin entry.

**Create a new repo from this template:** [Use this template](https://github.com/cursor/plugin-template/generate) or click **Use this template** on the repo page.
