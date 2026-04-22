# pi-agent-picker

> **Pi Coding Agent Extension** — Switch between agent profiles with subfolder support

A [Pi](https://github.com/mariozechner/pi) extension that provides a fuzzy-search picker UI to switch between agent profiles mid-session. Supports agents stored in nested folders (e.g., `Research/deep-research`, `Write/konzept`).

## Features

- **Fuzzy Search** — Filter agents by name or description
- **Subfolder Support** — Agents in nested directories display their folder path
- **Status Bar** — Shows current agent with folder path (e.g., `AGENT: Research/deep-research`)
- **Tool Presets** — Switch active tools when activating an agent
- **Session Persistence** — Remembers the active agent across restarts
- **Project-Level Override** — Project-specific agents in `.pi/agents/` take priority

## Installation

```bash
cd ~/.pi/agent/extensions
git clone https://github.com/alephtex/pi-agent-picker.git agent-picker
```

Then add to your `~/.pi/agent/extensions/package.json`:

```json
{
  "dependencies": {
    "@mariozechner/pi-agent-picker": "file:./agent-picker"
  }
}
```

## Usage

```
/agent              # Open picker UI
/agent <name>       # Switch directly to named agent
/agents             # List all available agents
```

## Agent Directory Structure

```
~/.pi/agent/agents/
├── Research/
│   ├── deep-research.md
│   └── fast-research.md
├── Write/
│   ├── konzept.md
│   └── transcript.md
└── general-agent.md
```

Agents in subfolders display as `Folder/agent-name` in the picker and status bar.

## Agent Definition Format

```markdown
---
name: my-agent
description: Description of what this agent does
tools: [read, write, grep]
model: anthropic/claude-3-5-sonnet
---

Your system prompt here...
```

## License

MIT
