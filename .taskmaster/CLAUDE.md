# Task Master AI - Guia de Integração de Agentes

## Comandos Essenciais

### Comandos de Fluxo de Trabalho Principal

```bash
# Configuração do Projeto
task-master init                                    # Inicializar Task Master no projeto atual
task-master parse-prd .taskmaster/docs/prd.txt      # Gerar tarefas do documento PRD
task-master models --setup                        # Configurar modelos de IA interativamente

# Fluxo de Trabalho de Desenvolvimento Diário
task-master list                                   # Mostrar todas as tarefas com status
task-master next                                   # Obter próxima tarefa disponível para trabalhar
task-master show <id>                             # Ver informações detalhadas da tarefa (ex: task-master show 1.2)
task-master set-status --id=<id> --status=done    # Marcar tarefa como completa

# Gerenciamento de Tarefas
task-master add-task --prompt="descrição" --research        # Adicionar nova tarefa com assistência de IA
task-master expand --id=<id> --research --force              # Dividir tarefa em subtarefas
task-master update-task --id=<id> --prompt="mudanças"         # Atualizar tarefa específica
task-master update --from=<id> --prompt="mudanças"            # Atualizar múltiplas tarefas a partir do ID
task-master update-subtask --id=<id> --prompt="notas"        # Adicionar notas de implementação à subtarefa

# Análise e Planejamento
task-master analyze-complexity --research          # Analisar complexidade da tarefa
task-master complexity-report                      # Ver análise de complexidade
task-master expand --all --research               # Expandir todas as tarefas elegíveis

# Dependências e Organização
task-master add-dependency --id=<id> --depends-on=<id>       # Adicionar dependência de tarefa
task-master move --from=<id> --to=<id>                       # Reorganizar hierarquia de tarefas
task-master validate-dependencies                            # Verificar problemas de dependências
task-master generate                                         # Atualizar arquivos markdown de tarefas (geralmente auto-chamado)
```

## Arquivos Principais e Estrutura do Projeto

### Arquivos Centrais

- `.taskmaster/tasks/tasks.json` - Arquivo principal de dados de tarefas (auto-gerenciado)
- `.taskmaster/config.json` - Configuração de modelos de IA (use `task-master models` para modificar)
- `.taskmaster/docs/prd.txt` - Documento de Requisitos do Produto para análise
- `.taskmaster/tasks/*.txt` - Arquivos individuais de tarefas (auto-gerados do tasks.json)
- `.env` - Chaves de API para uso da CLI

### Arquivos de Integração Claude Code

- `CLAUDE.md` - Contexto carregado automaticamente para Claude Code (este arquivo)
- `.claude/settings.json` - Lista de ferramentas permitidas e preferências do Claude Code
- `.claude/commands/` - Comandos de barra personalizados para fluxos de trabalho repetidos
- `.mcp.json` - Configuração do servidor MCP (específica do projeto)

### Directory Structure

```
project/
├── .taskmaster/
│   ├── tasks/              # Task files directory
│   │   ├── tasks.json      # Main task database
│   │   ├── task-1.md      # Individual task files
│   │   └── task-2.md
│   ├── docs/              # Documentation directory
│   │   ├── prd.txt        # Product requirements
│   ├── reports/           # Analysis reports directory
│   │   └── task-complexity-report.json
│   ├── templates/         # Template files
│   │   └── example_prd.txt  # Example PRD template
│   └── config.json        # AI models & settings
├── .claude/
│   ├── settings.json      # Claude Code configuration
│   └── commands/         # Custom slash commands
├── .env                  # API keys
├── .mcp.json            # MCP configuration
└── CLAUDE.md            # This file - auto-loaded by Claude Code
```

## Integração MCP

O Task Master fornece um servidor MCP ao qual o Claude Code pode se conectar. Configure no `.mcp.json`:

```json
{
  "mcpServers": {
    "task-master-ai": {
      "command": "npx",
      "args": ["-y", "--package=task-master-ai", "task-master-ai"],
      "env": {
        "ANTHROPIC_API_KEY": "your_key_here",
        "PERPLEXITY_API_KEY": "your_key_here",
        "OPENAI_API_KEY": "OPENAI_API_KEY_HERE",
        "GOOGLE_API_KEY": "GOOGLE_API_KEY_HERE",
        "XAI_API_KEY": "XAI_API_KEY_HERE",
        "OPENROUTER_API_KEY": "OPENROUTER_API_KEY_HERE",
        "MISTRAL_API_KEY": "MISTRAL_API_KEY_HERE",
        "AZURE_OPENAI_API_KEY": "AZURE_OPENAI_API_KEY_HERE",
        "OLLAMA_API_KEY": "OLLAMA_API_KEY_HERE"
      }
    }
  }
}
```

### Ferramentas MCP Essenciais

```javascript
help; // = mostra comandos taskmaster disponíveis
// Configuração do projeto
initialize_project; // = task-master init
parse_prd; // = task-master parse-prd

// Fluxo de trabalho diário
get_tasks; // = task-master list
next_task; // = task-master next
get_task; // = task-master show <id>
set_task_status; // = task-master set-status

// Gerenciamento de tarefas
add_task; // = task-master add-task
expand_task; // = task-master expand
update_task; // = task-master update-task
update_subtask; // = task-master update-subtask
update; // = task-master update

// Análise
analyze_project_complexity; // = task-master analyze-complexity
complexity_report; // = task-master complexity-report
```

## Integração do Fluxo de Trabalho Claude Code

### Fluxo de Trabalho de Desenvolvimento Padrão

#### 1. Inicialização do Projeto

```bash
# Inicializar Task Master
task-master init

# Criar ou obter PRD, depois analisá-lo
task-master parse-prd .taskmaster/docs/prd.txt

# Analisar complexidade e expandir tarefas
task-master analyze-complexity --research
task-master expand --all --research
```

Se as tarefas já existem, outro PRD pode ser analisado (apenas com novas informações!) usando parse-prd com a flag --append. Isso adicionará as tarefas geradas à lista existente de tarefas.

#### 2. Loop de Desenvolvimento Diário

```bash
# Começar cada sessão
task-master next                           # Encontrar próxima tarefa disponível
task-master show <id>                     # Revisar detalhes da tarefa

# Durante a implementação, registrar contexto do código nas tarefas e subtarefas
task-master update-subtask --id=<id> --prompt="notas de implementação..."

# Completar tarefas
task-master set-status --id=<id> --status=done
```

#### 3. Multi-Claude Workflows

For complex projects, use multiple Claude Code sessions:

```bash
# Terminal 1: Main implementation
cd project && claude

# Terminal 2: Testing and validation
cd project-test-worktree && claude

# Terminal 3: Documentation updates
cd project-docs-worktree && claude
```

### Custom Slash Commands

Create `.claude/commands/taskmaster-next.md`:

```markdown
Find the next available Task Master task and show its details.

Steps:

1. Run `task-master next` to get the next task
2. If a task is available, run `task-master show <id>` for full details
3. Provide a summary of what needs to be implemented
4. Suggest the first implementation step
```

Create `.claude/commands/taskmaster-complete.md`:

```markdown
Complete a Task Master task: $ARGUMENTS

Steps:

1. Review the current task with `task-master show $ARGUMENTS`
2. Verify all implementation is complete
3. Run any tests related to this task
4. Mark as complete: `task-master set-status --id=$ARGUMENTS --status=done`
5. Show the next available task with `task-master next`
```

## Tool Allowlist Recommendations

Add to `.claude/settings.json`:

```json
{
  "allowedTools": [
    "Edit",
    "Bash(task-master *)",
    "Bash(git commit:*)",
    "Bash(git add:*)",
    "Bash(npm run *)",
    "mcp__task_master_ai__*"
  ]
}
```

## Configuration & Setup

### API Keys Required

At least **one** of these API keys must be configured:

- `ANTHROPIC_API_KEY` (Claude models) - **Recommended**
- `PERPLEXITY_API_KEY` (Research features) - **Highly recommended**
- `OPENAI_API_KEY` (GPT models)
- `GOOGLE_API_KEY` (Gemini models)
- `MISTRAL_API_KEY` (Mistral models)
- `OPENROUTER_API_KEY` (Multiple models)
- `XAI_API_KEY` (Grok models)

An API key is required for any provider used across any of the 3 roles defined in the `models` command.

### Model Configuration

```bash
# Interactive setup (recommended)
task-master models --setup

# Set specific models
task-master models --set-main claude-3-5-sonnet-20241022
task-master models --set-research perplexity-llama-3.1-sonar-large-128k-online
task-master models --set-fallback gpt-4o-mini
```

## Task Structure & IDs

### Task ID Format

- Main tasks: `1`, `2`, `3`, etc.
- Subtasks: `1.1`, `1.2`, `2.1`, etc.
- Sub-subtasks: `1.1.1`, `1.1.2`, etc.

### Task Status Values

- `pending` - Ready to work on
- `in-progress` - Currently being worked on
- `done` - Completed and verified
- `deferred` - Postponed
- `cancelled` - No longer needed
- `blocked` - Waiting on external factors

### Task Fields

```json
{
  "id": "1.2",
  "title": "Implement user authentication",
  "description": "Set up JWT-based auth system",
  "status": "pending",
  "priority": "high",
  "dependencies": ["1.1"],
  "details": "Use bcrypt for hashing, JWT for tokens...",
  "testStrategy": "Unit tests for auth functions, integration tests for login flow",
  "subtasks": []
}
```

## Claude Code Best Practices with Task Master

### Context Management

- Use `/clear` between different tasks to maintain focus
- This CLAUDE.md file is automatically loaded for context
- Use `task-master show <id>` to pull specific task context when needed

### Iterative Implementation

1. `task-master show <subtask-id>` - Understand requirements
2. Explore codebase and plan implementation
3. `task-master update-subtask --id=<id> --prompt="detailed plan"` - Log plan
4. `task-master set-status --id=<id> --status=in-progress` - Start work
5. Implement code following logged plan
6. `task-master update-subtask --id=<id> --prompt="what worked/didn't work"` - Log progress
7. `task-master set-status --id=<id> --status=done` - Complete task

### Complex Workflows with Checklists

For large migrations or multi-step processes:

1. Create a markdown PRD file describing the new changes: `touch task-migration-checklist.md` (prds can be .txt or .md)
2. Use Taskmaster to parse the new prd with `task-master parse-prd --append` (also available in MCP)
3. Use Taskmaster to expand the newly generated tasks into subtasks. Consdier using `analyze-complexity` with the correct --to and --from IDs (the new ids) to identify the ideal subtask amounts for each task. Then expand them.
4. Work through items systematically, checking them off as completed
5. Use `task-master update-subtask` to log progress on each task/subtask and/or updating/researching them before/during implementation if getting stuck

### Git Integration

Task Master works well with `gh` CLI:

```bash
# Create PR for completed task
gh pr create --title "Complete task 1.2: User authentication" --body "Implements JWT auth system as specified in task 1.2"

# Reference task in commits
git commit -m "feat: implement JWT auth (task 1.2)"
```

### Parallel Development with Git Worktrees

```bash
# Create worktrees for parallel task development
git worktree add ../project-auth feature/auth-system
git worktree add ../project-api feature/api-refactor

# Run Claude Code in each worktree
cd ../project-auth && claude    # Terminal 1: Auth work
cd ../project-api && claude     # Terminal 2: API work
```

## Troubleshooting

### AI Commands Failing

```bash
# Check API keys are configured
cat .env                           # For CLI usage

# Verify model configuration
task-master models

# Test with different model
task-master models --set-fallback gpt-4o-mini
```

### MCP Connection Issues

- Check `.mcp.json` configuration
- Verify Node.js installation
- Use `--mcp-debug` flag when starting Claude Code
- Use CLI as fallback if MCP unavailable

### Task File Sync Issues

```bash
# Regenerate task files from tasks.json
task-master generate

# Fix dependency issues
task-master fix-dependencies
```

DO NOT RE-INITIALIZE. That will not do anything beyond re-adding the same Taskmaster core files.

## Important Notes

### AI-Powered Operations

These commands make AI calls and may take up to a minute:

- `parse_prd` / `task-master parse-prd`
- `analyze_project_complexity` / `task-master analyze-complexity`
- `expand_task` / `task-master expand`
- `expand_all` / `task-master expand --all`
- `add_task` / `task-master add-task`
- `update` / `task-master update`
- `update_task` / `task-master update-task`
- `update_subtask` / `task-master update-subtask`

### File Management

- Never manually edit `tasks.json` - use commands instead
- Never manually edit `.taskmaster/config.json` - use `task-master models`
- Task markdown files in `tasks/` are auto-generated
- Run `task-master generate` after manual changes to tasks.json

### Claude Code Session Management

- Use `/clear` frequently to maintain focused context
- Create custom slash commands for repeated Task Master workflows
- Configure tool allowlist to streamline permissions
- Use headless mode for automation: `claude -p "task-master next"`

### Multi-Task Updates

- Use `update --from=<id>` to update multiple future tasks
- Use `update-task --id=<id>` for single task updates
- Use `update-subtask --id=<id>` for implementation logging

### Research Mode

- Add `--research` flag for research-based AI enhancement
- Requires a research model API key like Perplexity (`PERPLEXITY_API_KEY`) in environment
- Provides more informed task creation and updates
- Recommended for complex technical tasks

---

_This guide ensures Claude Code has immediate access to Task Master's essential functionality for agentic development workflows._
