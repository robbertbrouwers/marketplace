# rbro Marketplace

A personal marketplace of Claude Code plugins — skills, agents, and MCP servers — installable directly from GitHub via Claude's `/plugin` command.

## Using this marketplace

In Claude Code, run:

```
/plugin marketplace add rbro/marketplace
```

(replace `rbro` with your actual GitHub username/org once published)

Then browse and install plugins:

```
/plugin install example-plugin@rbro-marketplace
```

## Structure

```
.claude-plugin/
  marketplace.json      # marketplace manifest listing all plugins
plugins/
  example-plugin/
    .claude-plugin/
      plugin.json        # plugin manifest
    skills/
      hello/
        SKILL.md          # a skill
    .mcp.json             # optional MCP server definitions bundled with the plugin
```

## Adding a new plugin

1. Create a new folder under `plugins/<your-plugin-name>/`.
2. Add `plugins/<your-plugin-name>/.claude-plugin/plugin.json` with `name`, `version`, `description`, `author`.
3. Add any `skills/<skill-name>/SKILL.md`, `agents/`, `commands/`, or `.mcp.json` content.
4. Register the plugin in the root `.claude-plugin/marketplace.json` under `"plugins"`.
5. Commit and push.

## Publishing

```
git init
git add .
git commit -m "Initial marketplace scaffold"
git branch -M main
git remote add origin https://github.com/<you>/marketplace.git
git push -u origin main
```
