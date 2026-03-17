# {project_name} Claude Code Instructions

This repository uses Claude Code for assisted development with autonomous task execution.

## Project Skills

- `/planning-requirements <需求>` — 拆分需求为结构化任务队列
- `/executing-tasks` — 从队列执行任务。追加 `all` 为批量模式。
- `/reviewing-code` — 只读代码质量分析
- `/adapting-project-structure` — 重新适配 .claude/ 结构（技术栈变更后）

## Development Workflow

### Full Pipeline
1. `/planning-requirements <需求>` — 拆分需求
2. 审批任务队列
3. `/executing-tasks all` — 闭环执行
4. `/loop 5m /executing-tasks all` — 无人监督持续执行

### Quick Tasks
- `/executing-tasks` — 每次执行一个任务
- `/executing-tasks T3` — 执行指定任务

## Build

**Build:** `{pm_build}`
**Dev:**   `{pm_dev}`
**Test:**  `{pm_test}`
**Lint:**  `{pm_lint}`

## Rules

See @.claude/rules/build-rules.md for build commands and constraints.
See @.claude/rules/code-quality.md for code style conventions.
See @.claude/rules/git-workflow.md for git conventions.
See @.claude/rules/task-execution.md for closed-loop execution rules.
