# Colabo

An open-source framework for orchestrating multiple AI coding agents on a single project.

Colabo provides a ready-to-use folder structure with rules, roles, and templates so that AI agents (Claude Code, GitHub Copilot, Cursor, Anti-Gravity...) can collaborate on your codebase in a coordinated, traceable, and validated way.

## The Problem

When using multiple AI agents on the same project, things get messy fast:
- Agents overwrite each other's work
- No single source of truth for what needs to be done
- Changes are hard to track and review
- No validation process before modifications are applied

Colabo solves this by defining a clear hierarchy: **one planner, multiple executors, full traceability**.

## How It Works

```
You (request) --> Claude Code (analysis + plan) --> Execution Agents (implement) --> Change Log (trace)
                        |                                    |                           |
                  Reads project_context/              Follows the plan strictly    Documents everything
                  Produces detailed plan              No unauthorized changes      Awaits your validation
```

## Quick Start

### 1. Get Colabo

**Option A: Use as a GitHub Template**

1. Click **"Use this template"** on the GitHub repo page
2. Name your new repository
3. Clone it locally

**Option B: Clone directly**

```bash
git clone https://github.com/Kevinmrgt/colabo.git my-project
cd my-project
```

**Option C: Copy into an existing project**

```bash
# From your existing project root
git clone https://github.com/Kevinmrgt/colabo.git /tmp/colabo
cp -r /tmp/colabo/ai_agents_rules ./ai_agents_rules
rm -rf /tmp/colabo
```

### 2. Configure your project

Edit `ai_agents_rules/project_context/project_config.yaml` to point to your project:

```yaml
project_path: "C:\\Users\\Kevin\\Projects\\my-app"
project_name: "My App"
description: "A task management web application"
tech_stack:
  - Next.js
  - TypeScript
  - PostgreSQL
entry_points:
  - src/
  - package.json
exclude:
  - node_modules/
  - .git/
  - dist/
```

Your project can live anywhere on your filesystem. Agents will use this config to locate and analyze it.

## Project Structure

```
your-project/
├── ai_agents_rules/               # Colabo framework
│   ├── README.md                  # Framework documentation
│   ├── project_context/           # Your project description (source of truth)
│   │   ├── ROLE.md
│   │   └── project_config.yaml   # ** Point to your project here **
│   ├── claude_code/               # Planner agent rules
│   │   ├── ROLE.md
│   │   └── plan_template.md
│   ├── execution_agents/          # Executor agents rules
│   │   ├── ROLE.md
│   │   ├── github_copilot.md
│   │   ├── cursor.md
│   │   └── anti_gravity.md
│   └── code_changes_log/          # Modification history
│       ├── ROLE.md
│       └── _template.md
├── src/                           # Your project code
└── ...
```

## Workflow

| Step | Who | What |
|------|-----|------|
| 0 | **You** | Configure `project_config.yaml` with your project path (once) |
| 1 | **You** | Submit a request |
| 2 | **All agents** | Read `project_config.yaml` to locate and understand the project |
| 3 | **Claude Code** | Analyzes the codebase and produces a detailed action plan |
| 4 | **Execution agents** | Implement tasks strictly following the plan |
| 5 | **All agents** | Log every change in `code_changes_log/` |
| 6 | **You** | Validate or request corrections |

## Key Principles

- **No unauthorized changes** - Execution agents only do what the plan says
- **Full traceability** - Every modification is logged with date, agent name, description, and status
- **User validation required** - Nothing is considered done until you approve it
- **Single source of truth** - `project_context/` describes your project, the plan describes the work

## Adding a New Agent

1. Create a new file in `ai_agents_rules/execution_agents/` (e.g. `my_agent.md`)
2. Follow the format of existing agent files
3. The agent must comply with the common rules defined in `execution_agents/ROLE.md`

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

## License

MIT
