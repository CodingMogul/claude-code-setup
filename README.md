# Claude Code Setup - Enhanced Edition

> A comprehensive configuration framework for Claude Code that enhances your development workflow with intelligent agents, custom commands, automated testing, and security auditing capabilities.

[![Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-blue.svg)](https://claude.ai/code) [![MCP](https://img.shields.io/badge/MCP-Enabled-green.svg)](https://modelcontextprotocol.io/) [![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)

## 🙏 Credits

This enhanced configuration is built upon the excellent foundation created by [AizenvoltPrime](https://github.com/AizenvoltPrime/claude-setup). The original setup provided the core framework for task automation, MCP servers, and workflow management.

### What's New in This Fork
Maintained by [@codingmogul](https://github.com/codingmogul), this fork adds:
- **QA Test Engineer Agent**: Automated test generation for uncommitted code
- **Security Audit Specialist Agent**: Comprehensive security vulnerability detection
- **Enhanced Commands**: `/setup`, `/generate-tests`, `/security-audit`
- **Improved Documentation**: Expanded guides and examples

## Table of Contents

- [Overview](#overview)
- [Quick Start](#quick-start)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Features](#features)
- [Commands](#commands)
- [Configuration](#configuration)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Overview

This project provides a powerful configuration framework for Claude Code that transforms your development workflow with:

- **Intelligent Agents**: Specialized AI agents for code investigation, testing, security auditing, and planning
- **MCP Servers**: Context7, Puppeteer, Sequential Thinking, DeepWiki for enhanced capabilities
- **Custom Commands**: Streamlined workflows for commits, testing, security audits, and complex problem-solving
- **Hook System**: Automated directory management and workflow triggers
- **Quality Assurance**: Automated test generation and comprehensive security auditing
- **Structured Workflows**: Organized task management with detailed reporting and planning

## Quick Start

```bash
# 1. Install dependencies
pip install uv

# 2. Clone this configuration
git clone https://github.com/CodingMogul/claude-code-setup.git
cd claude-code-setup

# 3. Apply configuration to your project
/setup

# 4. Start using enhanced commands
/task_hard implement user authentication
/generate-tests
/security-audit
```

## Prerequisites

Before using this setup, ensure you have:

- **Claude Code**: Installed and configured
- **Python 3.8+**: For hook script execution
- **uv**: Package manager for Python script execution
- **Node.js**: For MCP server functionality (npx)

### Installation

#### 1. Install uv (if not already installed)

```bash
# macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"

# After installation, open a new terminal and verify:
uv --version
```

#### 2. Setup Configuration

```bash
# Copy configuration files to your project
cp -r .claude/ /your/project/
cp .mcp.json /your/project/

# Ensure hook permissions
chmod +x .claude/hooks/task_hard_prep_hook.py
```

## Features

### 🎯 Custom Commands

- **`/setup`**: Apply Claude configuration to your project
- **`/commit`**: Intelligent commit workflow with conventional standards
- **`/code-review`**: Reviews uncommitted changes before committing
- **`/generate-tests`**: Automatically generate comprehensive tests for uncommitted code
- **`/security-audit`**: Perform security audit on uncommitted changes
- **`/task_hard`**: Advanced problem-solving with automated directory management
- **`/task_easy`**: Simplified task workflow for lighter needs

### 🤖 Custom Agents

- **`investigator`**: Expert code investigator that tracks down related code to problems
  - Uses sequential thinking and advanced search tools
  - Generates comprehensive INVESTIGATION_REPORT.md files
  - Integrated with task_hard workflow
- **`code-flow-mapper`**: Expert code flow mapper that traces execution paths and file interconnections
  - Maps code flow and analyzes file relationships
  - Generates FLOW_REPORT.md files
- **`planner`**: Expert planner that takes into account investigation and flow analysis reports
  - Creates detailed plans that solve all problems
  - Generates comprehensive PLAN.md files
- **`code-reviewer`**: Senior code review specialist for quality assurance
  - Reviews changes for quality, security, and maintainability
  - Provides prioritized feedback (critical, warnings, suggestions)
  - Checks for best practices and potential issues
- **`qa-test-engineer`**: Expert QA engineer for comprehensive testing
  - Analyzes code and generates appropriate test cases
  - Creates unit, integration, and e2e tests
  - Ensures comprehensive test coverage
  - Validates application functionality
- **`security-audit-specialist`**: Senior security auditor for vulnerability detection
  - Scans for hardcoded secrets and credentials
  - Reviews authentication and authorization
  - Identifies OWASP Top 10 vulnerabilities
  - Provides remediation recommendations

### 🔌 MCP Servers

- **Context7**: Library documentation and code context
- **Puppeteer**: Browser automation and web scraping
- **Sequential Thinking**: Advanced reasoning and problem-solving
- **DeepWiki**: Repository documentation fetching

### ⚡ Hook System

- **UserPromptSubmit**: Automatic directory creation for task workflows
- **Extensible**: Easy to add custom hooks for workflow automation
- **Documentation**: [Hooks Reference](https://docs.anthropic.com/en/docs/claude-code/hooks) | [Hooks Guide](https://docs.anthropic.com/en/docs/claude-code/hooks-guide)

## Commands

### `/task_hard` - Advanced Problem Solving

Automated workflow for complex problem-solving with structured investigation and planning.

**Usage:**

```bash
/task_hard [problem description]
```

**Features:**

- ✅ Automatic `claude-instance-{id}` directory creation
- ✅ Sequential thinking for complex reasoning
- ✅ Multi-agent workflow with specialized subagents
- ✅ Codebase investigation with INVESTIGATION_REPORT.md generation
- ✅ Code flow mapping with FLOW_REPORT.md analysis
- ✅ Structured planning with PLAN.md output
- ✅ Incremental instance numbering
- ✅ Edge case handling and best practices focus

**Example:**

```bash
/task_hard implement user authentication system
```

**Workflow:**

1. 🔧 Hook detects `/task_hard` prompt
2. 📁 Creates `claude-code-storage/claude-instance-{id}/` directory
3. 🔍 Investigator agent analyzes codebase using sequential thinking
4. 📄 Generates comprehensive INVESTIGATION_REPORT.md with related files
5. 🗺️ Code-flow-mapper agent traces execution paths and file interconnections
6. 📊 Generates detailed FLOW_REPORT.md with code relationships
7. 📋 Planner agent reads both reports and creates comprehensive PLAN.md
8. 👤 User reviews and approves plan

### `/code-review` - Automated Code Review

Initiates code-reviewer agent to analyze uncommitted changes only.

**Usage:**

```bash
/code-review
```

**Features:**

- Focuses exclusively on uncommitted changes
- Reviews modified files for quality, security, and maintainability
- Provides prioritized feedback:
  - 🚨 Critical issues (must fix)
  - ⚠️ Warnings (should fix)
  - 💡 Suggestions (consider improving)
- Includes specific fix examples

**Example:**

```bash
# After making changes
/code-review
# Fix any critical issues
/commit
```

### `/commit` - Intelligent Commits

Streamlined commit workflow following conventional commit standards.

**Features:**

- Diff analysis and change summarization
- Conventional commit message formatting
- Clean, focused commits

**Important:** Run `/code-review` before committing to ensure code quality.

**Example:**

```bash
# Review changes first
/code-review
# After fixing issues
/commit
```

### `/task_easy` - Simplified Tasks

Lightweight task workflow for simpler problem-solving needs.

### `/setup` - Apply Claude Configuration

Apply this Claude configuration framework to your project.

**Usage:**

```bash
/setup
```

**Features:**

- Copies all Claude configuration files to your project
- Sets up custom agents and commands
- Configures MCP servers
- Verifies installation and permissions

### `/generate-tests` - Automated Test Generation

Generates comprehensive test cases for uncommitted code changes.

**Usage:**

```bash
/generate-tests
```

**Features:**

- Analyzes uncommitted changes
- Identifies testing frameworks in use
- Generates appropriate test cases:
  - Unit tests for functions and methods
  - Integration tests for components
  - E2E tests for critical paths
- Covers edge cases and error scenarios
- Ensures proper test coverage

**Example:**

```bash
# After implementing new features
/generate-tests
# Review and run the generated tests
npm test
```

### `/security-audit` - Security Vulnerability Detection

Performs comprehensive security audit on uncommitted changes.

**Usage:**

```bash
/security-audit
```

**Features:**

- Scans for hardcoded secrets and API keys
- Reviews authentication implementations
- Checks for common vulnerabilities:
  - SQL injection
  - XSS attacks
  - CSRF vulnerabilities
  - Insecure data storage
- Provides severity-ranked findings
- Offers remediation recommendations

**Example:**

```bash
# Before committing sensitive changes
/security-audit
# Fix any critical vulnerabilities
/commit
```

## Configuration

### Directory Structure

```
claude-setup/
├── .claude/
│   ├── settings.json          # Permissions and hook configuration
│   ├── agents/
│   │   ├── investigator.md    # Code investigation agent
│   │   ├── code-flow-mapper.md # Code flow mapping agent
│   │   ├── planner.md         # Planning agent
│   │   ├── code-reviewer.md   # Code review specialist
│   │   ├── qa-test-engineer.md # Test generation specialist
│   │   └── security-audit-specialist.md # Security audit expert
│   ├── hooks/
│   │   └── task_hard_prep_hook.py  # Auto directory creation
│   └── commands/
│       ├── setup.md           # Setup configuration command
│       ├── task_hard.md       # Advanced task workflow
│       ├── task_easy.md       # Simple task workflow
│       ├── code-review.md     # Code review workflow
│       ├── commit.md          # Commit workflow
│       ├── generate-tests.md  # Test generation command
│       └── security-audit.md  # Security audit command
├── .mcp.json                  # MCP server configuration
├── claude-code-storage/       # Auto-generated task directories
└── README.md
```

### Settings Configuration

The `.claude/settings.json` file contains:

```json
{
  "permissions": {
    "allow": ["WebFetch(domain:docs.anthropic.com)", ...],
    "deny": [...]
  },
  "hooks": {
    "UserPromptSubmit": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "uv run .claude/hooks/task_hard_prep_hook.py"
          }
        ]
      }
    ]
  },
  "enabledMcpjsonServers": ["context7", "puppeteer", "sequential-thinking", ...]
}
```

### MCP Configuration

The `.mcp.json` file defines server configurations:

```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["@context7/claude-dev", "--minTokens", "1000"]
    },
    "puppeteer": {
      "command": "npx",
      "args": ["@puppeteer/claude-dev"]
    }
  }
}
```

## Troubleshooting

### Common Issues

**Hook not triggering:**

- Ensure `uv` is installed and in PATH
- Check script permissions: `chmod +x .claude/hooks/task_hard_prep_hook.py`
- Verify hook configuration in `.claude/settings.json`

**Directory creation fails:**

- Check file system permissions
- Ensure `claude-code-storage/` parent directory exists
- Review hook script logs for error details

**MCP servers not loading:**

- Verify Node.js and npx are installed
- Check `.mcp.json` configuration syntax
- Ensure MCP packages are available via npx

### Debug Mode

Enable debug mode for detailed logging:

```bash
claude --debug
```

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and test thoroughly
4. Submit a pull request with detailed description

### Adding Custom Hooks

1. Create script in `.claude/hooks/`
2. Make executable: `chmod +x .claude/hooks/your_hook.py`
3. Add configuration to `.claude/settings.json`
4. Test with sample inputs

**Resources:**

- [Hooks Reference Documentation](https://docs.anthropic.com/en/docs/claude-code/hooks)
- [Hooks Implementation Guide](https://docs.anthropic.com/en/docs/claude-code/hooks-guide)

## Acknowledgments

### Original Project
This project is forked from [AizenvoltPrime/claude-setup](https://github.com/AizenvoltPrime/claude-setup), which provided the foundational framework for Claude Code enhancement including:
- Core agent architecture (investigator, planner, code-flow-mapper)
- Task automation system (`/task_hard`, `/task_easy`)
- MCP server integrations
- Hook system for workflow automation

### This Fork's Contributions
Built by [@codingmogul](https://github.com/codingmogul) to add:
- Quality assurance automation
- Security audit capabilities
- Enhanced setup workflow
- Comprehensive testing and security commands

## License

This configuration setup is provided as-is for Claude Code enhancement.

Original work by [AizenvoltPrime](https://github.com/AizenvoltPrime)  
Enhanced by [codingmogul](https://github.com/codingmogul)

---

**Need help?** Check the documentation:

- [Claude Code Main Docs](https://docs.anthropic.com/claude-code)
- [Hooks Reference](https://docs.anthropic.com/en/docs/claude-code/hooks)
- [Hooks Implementation Guide](https://docs.anthropic.com/en/docs/claude-code/hooks-guide)

Or open an issue for project-specific questions.

---

**Repository**: [github.com/CodingMogul/claude-code-setup](https://github.com/CodingMogul/claude-code-setup)  
**Original Project**: [github.com/AizenvoltPrime/claude-setup](https://github.com/AizenvoltPrime/claude-setup)
