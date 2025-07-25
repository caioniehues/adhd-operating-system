# Initialize all Task Master sub agents

Initialize and verify all Task Master-specific sub agents for optimal workflow integration.

## Steps

1. Check for existing Task Master agents in `.claude/agents/taskmaster/`
2. List all available Task Master agents:
   - task-navigator - Task discovery and navigation
   - task-implementer - Implementation lifecycle management
   - task-analyzer - Complexity and dependency analysis
3. Verify each agent has proper YAML frontmatter
4. Test agent invocation with a simple task
5. Display agent status and recommendations

## Agent Descriptions

### task-navigator
Expert at finding and tracking tasks. Use for:
- Finding next available task
- Checking task dependencies
- Navigating between task contexts
- Understanding current progress

### task-implementer
Handles complete implementation lifecycle. Use for:
- Implementing Task Master tasks
- Tracking progress with subtask updates
- Ensuring quality before completion
- Managing task status changes

### task-analyzer
Provides deep task insights. Use for:
- Analyzing task complexity
- Validating dependencies
- Planning task expansion
- Sprint planning recommendations

## Usage Examples

```
# Find your next task
Use the task-navigator sub agent to find my next task

# Implement a specific task
Use the task-implementer sub agent to implement task 5.2

# Analyze project complexity
Use the task-analyzer sub agent to analyze task complexity
```

## Verification

After setup, test with:
```bash
# Quick agent test
echo "Use the task-navigator sub agent to show current tasks"
```

All Task Master agents are now ready for use!