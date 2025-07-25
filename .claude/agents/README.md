# 🤖 ADHD-OS Claude Code Sub Agents

This directory contains specialized sub agents for the ADHD Operating System project, enhancing development workflow with Task Master integration and ADHD-specific features.

## 📁 Directory Structure

```
.claude/agents/
├── taskmaster/          # Task Master workflow agents
│   ├── task-navigator.md      # Task discovery and navigation
│   ├── task-implementer.md    # Implementation lifecycle
│   └── task-analyzer.md       # Complexity analysis
├── adhd-os/            # ADHD-OS specific agents
│   ├── adhd-feature-builder.md  # ADHD-friendly feature development
│   └── obsidian-plugin-tester.md # Plugin testing specialist
└── README.md           # This file
```

## 🚀 Quick Start

### Using Sub Agents

1. **Automatic Invocation**: Agents are invoked automatically based on context
2. **Explicit Request**: `Use the [agent-name] sub agent to...`
3. **Interactive Management**: Run `/agents` command

### Task Master Workflow

```bash
# Find next task
Use the task-navigator sub agent to find my next available task

# Implement a task
Use the task-implementer sub agent to implement task 5.2

# Analyze complexity
Use the task-analyzer sub agent to check task dependencies
```

### ADHD-OS Development

```bash
# Build ADHD feature
Use the adhd-feature-builder sub agent to implement focus mode

# Test plugin
Use the obsidian-plugin-tester sub agent to verify compatibility
```

## 🎯 Agent Descriptions

### Task Master Agents

#### task-navigator
- **Purpose**: Efficient task discovery and navigation
- **When to use**: Finding tasks, checking status, understanding dependencies
- **Key features**: Proactive task recommendations, dependency awareness

#### task-implementer
- **Purpose**: Complete task implementation lifecycle
- **When to use**: Implementing any Task Master task
- **Key features**: Progress tracking, quality checks, status management

#### task-analyzer
- **Purpose**: Task complexity and dependency analysis
- **When to use**: Before task expansion, sprint planning, checking blockers
- **Key features**: Complexity scoring, dependency validation, expansion recommendations

### ADHD-OS Agents

#### adhd-feature-builder
- **Purpose**: ADHD-specific feature implementation
- **When to use**: Building any ADHD-OS feature
- **Key features**: Cognitive load reduction, time awareness, emotional safety

#### obsidian-plugin-tester
- **Purpose**: Comprehensive plugin testing
- **When to use**: After code changes, before releases
- **Key features**: ADHD-specific scenarios, performance testing, compatibility checks

## 🔧 Configuration

Each agent uses YAML frontmatter:

```yaml
---
name: agent-name
description: When this agent should be used (include PROACTIVELY or MUST BE USED)
tools: tool1, tool2  # Optional - inherits all if omitted
---
```

## 📋 Management Commands

Access agent management via slash commands:

- `/agents` - Interactive agent management
- `/agents/task-master/setup` - Initialize Task Master agents
- `/agents/task-master/sync` - Sync with current task state
- `/agents/task-master/report` - View usage analytics

## 🔄 Workflow Examples

### Standard Development Flow
```
1. task-navigator → Find next task
2. task-analyzer → Check complexity
3. task-implementer → Build feature
4. adhd-feature-builder → Ensure ADHD-friendly
5. obsidian-plugin-tester → Verify works
6. code-reviewer → Final quality check
```

### Complex Task Flow
```
1. task-analyzer → Identify high complexity
2. task-implementer → Break down task
3. Pattern chain for subtasks
4. task-navigator → Track progress
```

## 📝 Best Practices

1. **Let agents specialize** - Don't make one agent do everything
2. **Provide context** - Agents have separate context windows
3. **Chain for complex workflows** - Combine agent strengths
4. **Use PROACTIVELY in descriptions** - For automatic invocation
5. **Test agent combinations** - Find what works for your workflow

## 🤝 Contributing

To add new agents:

1. Create `.md` file in appropriate directory
2. Add YAML frontmatter with name and description
3. Write clear instructions and examples
4. Test the agent behavior
5. Update this README
6. Commit to version control

## 🐛 Troubleshooting

- **Agent not invoked**: Check description includes trigger words
- **Wrong agent used**: Make descriptions more specific
- **Tool access issues**: Verify tools field or omit for all
- **Performance slow**: Agents gather context on each invocation

## 📚 Related Documentation

- [Claude Code Sub Agents Docs](https://docs.anthropic.com/en/docs/claude-code/sub-agents)
- [Task Master Integration Guide](.taskmaster/CLAUDE.md)
- [ADHD-OS Development Guide](../../CLAUDE.md)

---

Remember: These agents are here to make development smoother, faster, and more enjoyable. Use them liberally!