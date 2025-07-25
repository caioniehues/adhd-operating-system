# ADHD-OS GitHub Actions with Claude

This directory contains GitHub Actions workflows that integrate Claude AI to help with development of the ADHD Operating System Obsidian plugin.

## Available Workflows

### 1. Claude PR Assistant (`claude-pr-assistant.yml`)
- **Trigger**: When `@claude` is mentioned in issues or PR comments
- **Purpose**: Helps implement features, fix bugs, and answer questions
- **Usage**: 
  - In an issue: `@claude implement this feature`
  - In a PR: `@claude how should I handle this edge case?`
  - For bugs: `@claude fix the TypeError in daily notes`

### 2. Claude Code Review (`claude-code-review.yml`)
- **Trigger**: Automatically on all PRs that modify TypeScript files
- **Purpose**: Reviews code for ADHD-specific considerations
- **Focus Areas**:
  - Cognitive load and simplicity
  - ADHD-friendly features
  - Accessibility compliance
  - Performance implications
  - Test coverage

### 3. Claude Issue to PR (`claude-issue-to-pr.yml`)
- **Trigger**: When `@claude` is mentioned in issues
- **Purpose**: Converts issues into working pull requests
- **Commands**:
  - `@claude implement this` - Creates PR with implementation
  - `@claude fix this bug` - Debugs and fixes reported issues
  - `@claude create tests` - Generates test cases

### 4. Claude Documentation Generator (`claude-docs-generator.yml`)
- **Trigger**: Manual workflow dispatch or on main branch changes
- **Purpose**: Generates and updates documentation
- **Types**:
  - User guides with ADHD tips
  - API reference documentation
  - Developer setup guides
  - ADHD best practices

## Setup Instructions

### Prerequisites
1. Admin access to the repository
2. Anthropic API key

### Quick Setup
1. Install the Claude GitHub app: https://github.com/apps/claude
2. Add your Anthropic API key as a repository secret:
   - Go to Settings → Secrets and variables → Actions
   - Add new secret: `ANTHROPIC_API_KEY`
3. The workflows are ready to use!

### Testing the Setup
Create a new issue with:
```
@claude can you help me understand how the task management system should work?
```

## Best Practices

### When Creating Issues
- Be specific about what you need
- Include context about ADHD considerations
- Reference existing code if relevant
- Use clear commands (@claude implement, fix, etc.)

### Code Review Guidelines
Claude will automatically review PRs focusing on:
- Simplicity and cognitive load
- Visual clarity and feedback
- Accessibility standards
- ADHD-specific edge cases
- Performance implications

### Documentation Requests
Use the manual workflow dispatch to generate:
- User documentation
- API references
- Developer guides
- ADHD usage tips

## Security Notes
- Never commit API keys directly
- All secrets should use GitHub Secrets
- Review Claude's suggestions before merging
- The workflows have appropriate permission scoping

## Troubleshooting

### Claude Not Responding
1. Check that `@claude` (not `/claude`) is used
2. Verify the GitHub app is installed
3. Confirm API key is set in secrets
4. Check Actions tab for workflow runs

### Review Comments Not Appearing
1. Ensure the PR modifies TypeScript files
2. Check workflow runs in Actions tab
3. Verify permissions are correct

### Implementation Issues
1. Be specific in your requests
2. Break complex features into smaller issues
3. Provide examples when possible
4. Reference the CLAUDE.md file for context

## Cost Considerations
- Each Claude interaction uses API tokens
- Workflows have timeout limits to prevent runaway costs
- Use specific, focused requests to minimize token usage
- Monitor your Anthropic API usage dashboard

## Support
For issues with the workflows, check:
1. GitHub Actions logs
2. Anthropic API status
3. Repository settings and permissions

Remember: These workflows are designed to help create an ADHD-friendly plugin. Always keep the end user's needs in mind!