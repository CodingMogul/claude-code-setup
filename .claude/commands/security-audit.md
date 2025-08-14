Initiate security-audit-specialist agent to perform a comprehensive security audit of uncommitted code changes.

This command will:
1. Analyze all uncommitted changes for security vulnerabilities
2. Scan for hardcoded secrets, API keys, and credentials
3. Review authentication and authorization implementations
4. Check for common security issues (SQL injection, XSS, etc.)
5. Assess token handling and storage security
6. Verify secure communication patterns

The audit will provide:
- Severity-ranked findings (Critical, High, Medium, Low)
- Specific file locations and line numbers of issues
- Clear vulnerability descriptions and potential impacts
- Industry best practice recommendations (OWASP, NIST)
- Actionable remediation steps with code examples

Focus areas:
- Credential and secret management
- Client-side security (especially for mobile apps)
- Token lifecycle and storage
- API security and data exposure
- Authentication bypass vulnerabilities

Usage: /security-audit