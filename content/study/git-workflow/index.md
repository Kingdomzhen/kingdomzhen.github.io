+++
title = "Git 协作工作流最佳实践"
date = "2026-02-18"
description = "团队协作中的 Git 分支策略与 commit 规范"
tags = ["Git", "协作", "DevOps"]
categories = ["技术"]
+++

## 分支策略

我们团队采用 **Trunk-Based Development** 的变体：

| 分支 | 用途 | 生命周期 |
|------|------|----------|
| `main` | 生产环境 | 永久 |
| `develop` | 开发集成分支 | 永久 |
| `feature/*` | 功能开发 | 1-3 天 |
| `hotfix/*` | 紧急修复 | 几小时 |
| `release/*` | 发布准备 | 1 周 |

## Commit 规范

采用 **Conventional Commits**：

```
<type>(<scope>): <subject>

<body>
```

常用 type：

- `feat` — 新功能
- `fix` — 修复 Bug
- `docs` — 文档变更
- `refactor` — 重构
- `test` — 测试用例
- `chore` — 构建/工具

### 示例

```
feat(auth): 添加 JWT 登录验证

使用 jsonwebtoken 库实现无状态认证，
Token 有效期 24 小时，支持 refresh 机制。
```

## Pull Request 流程

1. **fork** — 从 develop 创建 feature 分支
2. **commit** — 小步提交，保持 commit 原子性
3. **rebase** — `git rebase develop` 保持历史整洁
4. **push** — 推送并创建 PR
5. **review** — 至少一人 Code Review
6. **squash merge** — 合并到 develop

## Code Review 清单

- [ ] 代码逻辑是否正确？
- [ ] 是否有边界情况未处理？
- [ ] 命名是否清晰？
- [ ] 是否有必要的测试？
- [ ] 是否引入性能问题？

## 小结

好的 Git 习惯能让团队协作效率翻倍。核心是 **小步提交** + **清晰的 commit message** + **及时的 Code Review**。
