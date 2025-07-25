## 2025-07-25 17:20:32Z

<!-- Claude Code Session 445712b7-8557-46d6-be74-5b0b442a5ff7 (2025-07-25_17-20-32Z) -->

_**User**_

You are a helpful assistant that creates well-structured tasks for a software development project. Generate a single new task based on the user's description, adhering strictly to the provided JSON schema. Pay special attention to dependencies between tasks, ensuring the new task correctly references any tasks it depends on.

When determining dependencies for a new task, follow these principles:
1. Select dependencies based on logical requirements - what must be completed before this task can begin.
2. Prioritize task dependencies that are semantically related to the functionality being built.
3. Consider both direct dependencies (immediately prerequisite) and indirect dependencies.
4. Avoid adding unnecessary dependencies - only include tasks that are genuinely prerequisite.
5. Consider the current status of tasks - prefer completed tasks as dependencies when possible.
6. Pay special attention to foundation tasks (1-5) but don't automatically include them without reason.
7. Recent tasks (higher ID numbers) may be more relevant for newer functionality.

The dependencies array should contain task IDs (numbers) of prerequisite tasks. 

 Always respond in English.

Human: You are generating the details for Task #22. Based on the user's request: "Create project setup task: Initialize development environment with Obsidian plugin structure, set up TypeScript configuration, configure build tools (Vite/ESBuild), establish coding standards, and create base plugin architecture. This is the foundation task that all other development depends on.", create a comprehensive new task for a software development project.
      
      
      
      Based on the information about existing tasks provided above, include appropriate dependencies in the "dependencies" array. Only include task IDs that this new task directly depends on.
      
      Return your answer as a single JSON object matching the schema precisely:
      
      {
        "title": "Task title goes here",
        "description": "A concise one or two sentence description of what the task involves",
    "details": "Detailed implementation steps, considerations, code examples, or technical approach",
    "testStrategy": "Specific steps to verify correct implementation and functionality",
    "dependencies": [1, 3] // Example: IDs of tasks that must be completed before this task
  }
      
      Make sure the details and test strategy are comprehensive and specific. DO NOT include the task ID in the title.
      

CRITICAL INSTRUCTION: You MUST respond with ONLY valid JSON. Follow these rules EXACTLY:
1. Start your response with an opening brace {
2. End your response with a closing brace }
3. Do NOT include any text before the opening brace
4. Do NOT include any text after the closing brace
5. Do NOT use markdown code blocks or backticks
6. Do NOT include explanations or commentary
7. The ENTIRE response must be valid JSON that can be parsed with JSON.parse()

Begin your response with { and end with }

---

_**Agent (<synthetic>)**_

Invalid API key · Fix external API key

