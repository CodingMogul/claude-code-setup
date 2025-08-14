Apply the Claude Code custom configuration from this repository to your current project.

This command will:
1. Copy all Claude configuration files to your project
2. Set up custom agents and commands
3. Configure MCP servers
4. Verify the installation

Usage: /setup

The setup will copy:
- .claude/ directory with all agents, commands, and hooks
- .mcp.json for MCP server configurations
- Apply proper permissions to executable scripts

Prerequisites:
- Python 3.8+ installed
- uv package manager installed
- Node.js for MCP servers

After setup, you'll have access to:
- /task_hard - Advanced problem-solving workflow
- /task_easy - Simplified task workflow  
- /commit - Intelligent commit workflow
- /code-review - Review uncommitted changes
- /generate-tests - Generate tests for uncommitted code
- /security-audit - Security audit for uncommitted code