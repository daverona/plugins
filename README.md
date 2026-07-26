# plugins

daverona's [Claude Code](https://claude.com/claude-code) plugin marketplace.

## Installation

Add the marketplace to Claude Code:

```
/plugin marketplace add daverona/plugins
```

Then install a plugin from it:

```
/plugin install tracker@daverona
```

## Plugins

| Plugin | Description | Source |
|--------|-------------|--------|
| tracker | Issue and task workflows for GitHub, GitLab, and ClickUp | [github.com/daverona/tracker](https://github.com/daverona/tracker) |

## Structure

```
.claude-plugin/
└── marketplace.json   # marketplace manifest: name, owner, plugin catalog
```

The manifest follows the [Claude Code marketplace schema](https://json.schemastore.org/claude-code-marketplace.json). Each entry in `plugins` points to an external repository where the plugin itself lives; this repository only catalogs them.

## Adding a plugin

1. Add an entry to the `plugins` array in `.claude-plugin/marketplace.json` with a unique `name`, a `source` (GitHub repo or URL), a `description`, and a `version`.
2. Commit and push — clients pick up the new catalog on `/plugin marketplace update daverona`.
