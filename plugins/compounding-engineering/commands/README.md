# Commands

This directory contains all slash commands for the compounding-engineering plugin. Each `.md` file defines a command that can be invoked via `claude /command-name`.

## Documentation Management

### `/release-docs`

**Purpose:** Build and update the documentation site with current plugin components.

**Usage:**
```bash
# Full documentation release
claude /release-docs

# Preview changes without writing files
claude /release-docs --dry-run
```

**What it does:**
1. Inventories all current components (agents, commands, skills, MCP servers)
2. Updates `docs/index.html` with accurate stats
3. Regenerates reference pages (`agents.html`, `commands.html`, `skills.html`, `mcp-servers.html`)
4. Updates `changelog.html` with latest version history
5. Ensures counts in `plugin.json` and `marketplace.json` match actual files
6. Validates all JSON files

**When to run:**
- After adding, removing, or modifying any agent
- After adding, removing, or modifying any command
- After adding, removing, or modifying any skill
- After adding, removing, or modifying any MCP server
- Before releasing a new version

## Workflow Commands

### `/plan_review`
Multi-agent plan review running in parallel for thorough analysis.

### `/resolve_parallel`
Resolve TODO comments in the codebase in parallel.

### `/resolve_pr_parallel`
Resolve PR comments in parallel.

### `/resolve_todo_parallel`
Resolve TODO items from a list in parallel.

## Development Commands

### `/changelog`
Create engaging changelogs for recent merges to main branch.

### `/generate_command`
Generate new slash command files from a description.

### `/create-agent-skill`
Create or edit Claude Code skills with best practices.

### `/heal-skill`
Fix skill documentation issues and formatting.

### `/prime`
Prime/setup command for initializing projects.

### `/reproduce-bug`
Reproduce bugs using logs and console output.

### `/report-bug`
Report bugs in the compounding-engineering plugin with structured workflow.

### `/triage`
Triage and prioritize issues.

## Command File Structure

Each command file follows this structure:

```markdown
---
name: command-name
description: Brief description of what the command does
argument-hint: "[optional arguments description]"
---

# Command Title

Instructions for Claude on how to execute this command...
```

## Adding a New Command

1. Create a new `.md` file in this directory
2. Add the frontmatter with `name`, `description`, and optional `argument-hint`
3. Write detailed instructions for Claude
4. Run `/release-docs` to update documentation
5. Test with `claude /your-command-name`

## Best Practices

- Keep command names short and descriptive (use hyphens, not underscores)
- Provide clear step-by-step instructions
- Include examples of expected output
- Document any prerequisites or dependencies
- Use parallel agent invocation when tasks are independent
