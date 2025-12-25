# GitKraken CLI - AI Coding Agent Instructions

## Project Overview

This is the **public documentation repository** for [GitKraken CLI](https://github.com/gitkraken/gk-cli) (`gk`), a premium command-line tool for managing multiple Git repositories with AI-powered features. This repo contains user-facing documentation, issue templates, and examples—not source code.

## What This Repo Does

- **Multi-repo management**: Users work with "Work Items" (features/issues) that can span multiple repos with monorepo-like UX
- **AI features**: Automated commit messages (`gk work commit --ai`) and Pull Request generation (`gk work pr create --ai`)
- **MCP Server**: Provides Model Context Protocol integration for LLM-based tools, wrapping git, GitHub, Jira, and GitKraken APIs
- **Git passthrough**: Users can run any `git` command via `gk` (e.g., `gk status`, `gk remote -v`)

## Key Workflows

### Standard User Workflow
```bash
gk auth login                          # Authenticate with GitKraken
cd /path/to/repo
gk work create "Feature description"   # Create work item, adds current directory
# ...edit files...
gk work commit --ai                    # Generate AI commit message
gk work push                           # Push changes
gk work pr create --ai                 # Generate AI-powered PR
```

### Multi-Repo Work Item
Users add additional repos to active work items:
```bash
gk work add ./path/to/another/repo
```

## Core CLI Commands

Primary command groups (from `gk help`):
- **auth**: Authenticate with GitKraken platform
- **provider**: Add/remove provider tokens
- **graph**: Display commit graph in current repository
- **issue**: Manage issues
- **organization**: Manage GitKraken organizations
- **work**: Interact with work items (primary feature)
- **workspace**: Manage workspaces (alias: `ws`)

## Documentation Structure

- **README.md**: Main user documentation, installation guides (Homebrew, Snap, Winget, manual), troubleshooting, Nerd Fonts support
- **CONTRIBUTING.md**: Contribution guidelines (minimal template, needs expansion)
- **.github/ISSUE_TEMPLATE/**: Bug reports and feature request templates (YAML config)

## Documentation Conventions

- Use bash code blocks for CLI examples
- Reference `gk help [command]` as the primary user documentation source
- Include platform-specific installation instructions (macOS, Unix/Ubuntu, Windows)
- Document common troubleshooting scenarios (e.g., Oh-My-Zsh `gk` alias conflict, Safari/Brave localhost issues)

## MCP Server Context

The CLI provides an MCP (Model Context Protocol) server for AI applications. When documenting features:
- Reference [GitKraken Help Center MCP guide](https://help.gitkraken.com/cli/gk-cli-mcp/)
- Mention integration with GitHub, Jira, and GitLab
- Note this enables LLM tools to interact with Git repos and issue trackers

## Typical Updates

When updating documentation:
1. Reflect new/changed commands in README.md command reference
2. Add installation steps for new package managers (e.g., new Linux distributions)
3. Expand CONTRIBUTING.md with specific guidelines as needed
4. Update issue templates if new information fields become relevant
5. Keep troubleshooting section current with known issues

## External Resources

- **Product Documentation**: https://help.gitkraken.com/cli/gk-cli-mcp/
- **MCP Introduction**: https://www.gitkraken.com/blog/introducing-gitkraken-mcp
- **Releases**: https://github.com/gitkraken/gk-cli/releases
- **Nerd Fonts**: https://www.nerdfonts.com/

## When Making Changes

- Verify command syntax matches actual CLI behavior
- Test links to external resources remain valid
- Ensure examples are copy-paste ready (no invalid syntax)
- Keep installation instructions platform-specific and up-to-date with package managers
