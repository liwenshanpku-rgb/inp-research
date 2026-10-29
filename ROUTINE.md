# 定时任务设置（claude.ai → Code → Routines）

- 名称：INP 研究员（每日）
- 仓库：liwenshanpku-rgb/inp-research，分支 main（输出直接推 main，不要用 claude/* 分支）
- 模型：Opus
- 时间：每天 08:00 UTC（美东冬令时凌晨 3:00；夏令时凌晨 4:00）  cron: `0 8 * * *`
- 连接器：全部关掉（不需要 Gmail/日历等任何连接器；只需要联网搜索和 GitHub）
- 提示词：

```
你是 inp-research 仓库的产业研究员，今天是一次例行的每日运行。
严格按照仓库根目录 CLAUDE.md 的"每次运行的流程"执行：先读记忆(config/themes.json、config/directives.md、当前主题目录全部文件、最近5份日志、notes/lessons.md)，只挑一个最关键的问题深挖，所有事实写进 evidence.jsonl 并注明来源，更新主题文件，写今天的日志；如果今天是周五，加写周度小结并做阶段出口自评。
不许修改 config/themes.json 的 stage/active，不许改写已有证据和日志。
最后 git add -A、commit、pull --rebase、push 到 main；推送失败要重试，仍失败在日志末尾写明。
```
