---
aliases: ccr
created: '2025-06-18'
cssclasses: ''
description: Use Claude Code as the foundation for coding infrastructure, allowing
  you to decide how to interact with the model while enjoying updates from Anthropic.
modified: '2025-06-18'
permalink: /Sources/GithubStarsSync/claude-code-router.md
publish: true
tags:
- github开源
title: claude-code-router
---
如果是使用官方的key，则一般直接提供claude code的兼容api，可以直接使用：[[📥 Inbox/kimi v2用于claude code-官方token-不用ccr的情况下]]

vi ~/.claude-code-router/config.json

```
npm install -g @musistudio/claude-code-router
```

##

```
ccr code --dangerously-skip-permissions --model ZhipuAI/GLM-4.5

ccr code --dangerously-skip-permissions --model ZhipuAI/GLM-4.5

ccr code --dangerously-skip-permissions --model moonshotai/Kimi-K2-Instruct
```