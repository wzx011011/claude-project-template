# Claude Project Template

`.claude/` 目录结构模板，提供自主开发能力：需求拆分 → 任务执行 → 闭环验证 → 自我迭代。

## Quick Start

```bash
# 1. Clone
git clone <repo-url> claude-project-template

# 2. Copy .claude/ to your project
cp -r claude-project-template/.claude /path/to/your-project/

# 3. Open Claude Code
cd /path/to/your-project
claude

# 4. Adapt to your project
/adapting-project-structure
```

## Development Workflow

### Step 1: Plan
```
/planning-requirements 实现用户登录注册功能，包含 JWT 认证和权限管理
```
分析代码库，生成 `docs/task-queue.md`。

### Step 2: Execute
```
/executing-tasks all
```
按依赖顺序执行，每个任务闭环验证。

### Step 3: Autonomous Mode
```
/loop 5m /executing-tasks all
```
每 5 分钟自动推进一轮，直到全部完成。无需人工监督。

## Architecture

```
.claude/
├── rules/                              # Auto-loaded every session
│   ├── build-rules.md                      # Build commands (adapt to PM)
│   ├── code-quality.md                     # Framework conventions (trim to match)
│   ├── git-workflow.md                     # Git conventions (generic)
│   └── task-execution.md                   # Closed-loop rules (generic)
├── agents/
│   └── task-worker.md                      # Isolated task executor (generic)
└── skills/
    ├── adapting-project-structure/            # Init: detect & adapt
    ├── planning-requirements/                 # Decompose requirements
    │   └── reference/queue-format.md
    ├── executing-tasks/                       # Execute with closed-loop
    │   └── reference/
    │       ├── closed-loop.md
    │       ├── topology.md
    │       └── stop-conditions.md
    └── reviewing-code/                        # Read-only code analysis
        └── reference/output-format.md
```

## Three-Layer Design

| Layer | Purpose | When Loaded |
|-------|---------|-------------|
| `rules/` | Global constraints (what NOT to do) | Every session (auto) |
| `agents/` | Runtime constraints (tools, isolation, turns) | When delegated |
| `skills/` | User workflows (what to do) | When invoked |

## Key Concepts

- **Persistent State**: `docs/task-queue.md` survives sessions and compaction
- **Closed Loop**: Every task must pass build + test before marked complete
- **Dependency-Aware**: Topology-sorted scheduling, parallel where possible
- **Self-Iterating**: `/loop` integration for autonomous execution
- **Progressive Disclosure**: Reference files loaded on demand, not every session

## Adaptation

`/adapting-project-structure` auto-detects:
- Package manager (npm / pnpm / yarn)
- Framework (React / Vue / Angular / Svelte / Next / Nuxt)
- TypeScript, build tool, testing, linting, monorepo

And adapts template files accordingly (keeps relevant sections, removes others).
