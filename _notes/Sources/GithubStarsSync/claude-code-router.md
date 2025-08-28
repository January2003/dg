---
aliases:
- ccr
created_date: 2025-02-25
date created: 2025-06-18
date modified: 2025-06-18
description: Use Claude Code as the foundation for coding infrastructure, allowing
  you to decide how to interact with the model while enjoying updates from Anthropic.
forks: 60
is_fork: false
issues: 15
language: TypeScript
license: MIT License
publish: true
pushed_date: 2025-06-19
repo_name: musistudio/claude-code-router
repo_url: https://github.com/musistudio/claude-code-router
size_kb: 3679
star_date: 2025-06-12 18:15:17
stars: 669
title: claude-code-router
topics: []
updated_date: 2025-06-19
分类:
- '[[Atlas/Categories/github开源 - fileclass]]'
---
更简洁的竞品：[[Cards/y-router]]
部署在服务器上的竞品：[[Cards/claude-relay-service]]

如果是使用官方的key，则一般直接提供claude code的兼容api，可以直接使用：[[Cards/kimi v2用于claude code-官方token-不用ccr的情况下]]

vi ~/.claude-code-router/config.json

```
npm install -g @musistudio/claude-code-router
```

##

```
ccr code --dangerously-skip-permissions --model ZhipuAI/GLM-4.5

ccr code --dangerously-skip-permissions --model Qwen/Qwen3-235B-A22B-Thinking-2507

ccr code --dangerously-skip-permissions --model moonshotai/Kimi-K2-Instruct
```