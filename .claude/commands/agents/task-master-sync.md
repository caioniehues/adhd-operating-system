# Sync Task Master agents with current task state

Synchronize Task Master sub agents with the current project's task state for context-aware assistance.

## Steps

1. Get current task state from Task Master:
   ```bash
   task-master list --status=in-progress
   task-master next
   ```

2. Analyze project complexity:
   ```bash
   task-master complexity-report
   ```

3. Update agent context awareness by:
   - Identifying high-complexity tasks needing expansion
   - Finding blocked or dependent tasks
   - Noting current sprint/milestone focus

4. Provide recommendations for agent usage:
   - If complex tasks exist → Recommend task-analyzer
   - If ready tasks available → Recommend task-implementer
   - If navigation needed → Recommend task-navigator

5. Create agent invocation suggestions based on current state

## Sync Output Format

```
📊 Task Master Agent Sync Report
================================

Current State:
- Active Tasks: X in-progress
- Next Available: Task #Y
- Blocked Tasks: Z tasks

Recommended Agent Workflow:
1. Use task-analyzer for tasks: [list high complexity]
2. Use task-implementer for: [next available task]
3. Use task-navigator when: [switching contexts]

Quick Commands:
- Start next task: Use the task-implementer sub agent for task Y
- Analyze blockers: Use the task-analyzer sub agent for dependency check
- Review progress: Use the task-navigator sub agent for status overview
```

## Auto-Sync Triggers

Consider syncing when:
- Starting a new work session
- After completing multiple tasks
- When feeling lost or overwhelmed
- Before sprint planning
- After major milestone completion

This sync ensures agents provide contextually relevant assistance!