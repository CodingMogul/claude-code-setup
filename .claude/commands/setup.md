Apply the Claude Code enhanced configuration from CodingMogul's repository to your current project.

## Instructions for Claude:

1. **Clone the configuration repository**:
   ```bash
   git clone https://github.com/CodingMogul/claude-code-setup.git /tmp/claude-code-setup-temp
   ```

2. **Copy configuration files to current project**:
   ```bash
   # Copy .claude directory with all configurations
   cp -r /tmp/claude-code-setup-temp/.claude .
   
   # Copy MCP server configuration
   cp /tmp/claude-code-setup-temp/.mcp.json .
   ```

3. **Set proper permissions**:
   ```bash
   chmod +x .claude/hooks/task_hard_prep_hook.py
   ```

4. **Verify installation**:
   - Check that .claude/commands/ contains all command files
   - Check that .claude/agents/ contains all agent files
   - Confirm .mcp.json exists in project root

5. **Clean up temporary files**:
   ```bash
   rm -rf /tmp/claude-code-setup-temp
   ```

6. **Report success** and list available commands:
   - /task_hard - Advanced problem-solving workflow
   - /task_easy - Simplified task workflow  
   - /commit - Intelligent commit workflow
   - /code-review - Review uncommitted changes
   - /generate-tests - Generate tests for uncommitted code
   - /security-audit - Security audit for uncommitted code

## Prerequisites:
- Git installed
- Python 3.8+ installed
- uv package manager installed
- Node.js for MCP servers

## What this setup includes:
- **6 Specialized AI Agents**: investigator, planner, code-flow-mapper, code-reviewer, qa-test-engineer, security-audit-specialist
- **7 Custom Commands**: All the commands listed above
- **MCP Servers**: Context7, Puppeteer, Sequential Thinking, DeepWiki
- **Automated Hooks**: Task directory management and workflow triggers