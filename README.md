# Claude CMD Commands Repository

This repository contains a collection of Claude Code slash commands that can be installed and used with the `claude-cmd` package manager.

## Available Commands

- **debug-help** - Systematic debugging assistance for code issues
- **code-review** - Comprehensive code review with best practices
- **test-gen** - Generate comprehensive test suites
- **refactor** - Code refactoring improvements and suggestions
- **api-docs** - Generate API documentation from code

## Repository Structure

- `index.json` - Command manifest with metadata
- `*.md` - Individual command files
- `README.md` - This documentation

## Usage

Install commands using the `claude-cmd` tool:

```bash
claude-cmd add debug-help
claude-cmd add code-review
claude-cmd list
```

## Command Format

Each command follows the standard Claude Code slash command format:

- Markdown format (.md extension)
- YAML frontmatter for metadata:
   - allowed-tools: List of tools the command can use
   - description: Brief description of the command
- Dynamic content with bash commands (!) and file references (@)
- Prompt instructions as the main content

