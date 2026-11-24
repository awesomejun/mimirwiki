---
title: "Claude Ship"
subtitle: "Anthropic 开发的用于审查、修复和审批 GitHub 拉取请求的智能体套件"
canonical_url: https://mimirwiki.com/zh/wiki/claude-ship
language: zh
page_class: entity
revision_sha256: 1d16836d0a5e8f6a71ee34fdacff55f15758b24c923e1d291c7915fca7226327
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/zh/wiki/claude-ship.md
  txt: https://mimirwiki.com/zh/wiki/claude-ship.txt
  json: https://mimirwiki.com/zh/wiki/claude-ship.json
  jsonld: https://mimirwiki.com/zh/wiki/claude-ship.jsonld
translations:
  en: https://mimirwiki.com/wiki/claude-ship
  ko: https://mimirwiki.com/ko/wiki/claude-ship
  ja: https://mimirwiki.com/ja/wiki/claude-ship
---

# Claude Ship

> Claude Ship 是 Anthropic 面向 Claude Team 和 Enterprise 套餐推出的三款 GitHub 拉取请求智能体套件，包含 Code Review（正式发布）、PR Steward（公开测试版）和 Claude Approvals（公开测试版）。该套件于 2026-11-23 发布，可自动执行代码审查、修复提交和基于策略的审批检查，同时将合并强制控制交由仓库设置和 GitHub 规则处理。

Claude Ship 是 Anthropic 开发的一组 AI 智能体，用于对 GitHub 拉取请求执行代码审查、推送修复提交以及评估审批策略。Claude Ship 于 2026-11-23 发布，整合了三款智能体：Code Review（自 2026-10-15 起正式发布）、PR Steward（公开测试版）和 Claude Approvals（公开测试版）。Claude Ship 面向 Claude Team 和 Enterprise 套餐提供，并与仓库设置及 GitHub 分支保护或规则集控制机制协同运行。

**别名:** Claude Ship 智能体, /ship

## 关键事实

- **开发商:** Anthropic [1]
- **发布日期:** 2026-11-23 [1]
- **组件状态:** Code Review：正式发布；PR Steward 与 Claude Approvals：公开测试版 (截至 2026-11-24) [1]
- **适用套餐:** GitHub 上的 Claude Team 和 Enterprise 套餐 (截至 2026-11-24) [4]

## 事实摘要

- **开发商:** Anthropic [1]
- **发布日期:** 2026-11-23 [1]
- **组成组件:** Code Review、PR Steward、Claude Approvals [4]
- **Code Review 状态:** 正式发布（自 2026-10-15 起；研究预览版于 2026-03-09 推出） (截至 2026-11-24) [3]
- **PR Steward 状态:** 公开测试版 (截至 2026-11-24) [5]
- **Claude Approvals 状态:** 公开测试版 (截至 2026-11-24) [6]
- **支持平台:** GitHub（github.com；Code Review 和 PR Steward 支持 GitHub Enterprise Server） (截至 2026-11-24) [5]
- **适用套餐:** Claude Team 和 Enterprise (截至 2026-11-24) [4]
- **计费模式:** 按 Token 用量计费；Claude Approvals 无基础费用，但策略分类器和触发的 Code Review 按 Token 计费 (截至 2026-11-24) [1]
- **CLI 入口:** Claude Code 中的 /ship 命令 [4]

## Claude Ship 概述与发布历程

Claude Ship 是 [Anthropic](https://mimirwiki.com/zh/wiki/anthropic) 推出的一组智能体，旨在推动 GitHub 拉取请求完成审查、修复和基于策略的审批检查。[1][4] Anthropic 于 2026-11-23 宣布推出 Claude Ship，将现有的 Code Review 产品与两款新的公开测试版智能体 PR Steward 和 Claude Approvals 整合在一起。[1] 独立科技媒体 TechCrunch 和 The Verge 于同日对该发布进行了报道。[11][12]

Code Review 的推出早于 Claude Ship 整体发布：Anthropic 于 2026-03-09 面向 Team 和 Enterprise 组织推出了 Code Review 研究预览版，并于 2026-10-15 宣布正式发布。[2][3] 截至 2026-11-24，Code Review 已正式发布，而 PR Steward 和 Claude Approvals 仍处于公开测试阶段，尚未公布正式发布日期。[1][5][6] 开发者还可以在 Claude Code 中针对单个拉取请求调用 `/ship`，以推送变更、创建拉取请求、运行审查并处理反馈和失败的检查。[1][4]

## Claude Ship 智能体与拉取请求工作流

Claude Ship 将拉取请求处理划分给三款智能体，它们可在已配置的仓库上自动运行。[1][4]

- **Code Review** 通过多个并行智能体结合周边代码库检查拉取请求，验证发现结果以过滤误报，按严重程度对问题排序，并发布总览评论及受影响代码行的行内评论。[2][4] 管理员可为每个仓库选择 `Quick`、`Standard`（默认）或 `Deep` 审查级别。[3] Anthropic 在正式发布时表示，大多数审查可在 6 至 10 分钟内完成，而研究预览期间约为 20 分钟。[2][3] Anthropic 还报告称，在 Claude Code 团队内部，2026 年 6 月至 9 月期间合并的拉取请求数量翻了一倍以上，同时回滚比例下降了 40% 以上。[1]
- **PR Steward** 在云端会话中监控打开的拉取请求，并推送修复提交以解决由修改代码引发的 CI 检查失败、合并冲突、来自人工或 Code Review 等审查工具的反馈，以及 Claude Approvals 检查问题。[1][5] 每次推送后，PR Steward 都会发布评论，说明所做的更改以及撤销方式。[1] 开发者可以通过评论 `@claude` 并附上指令来引导 PR Steward，也可以通过评论 `@claude stop` 或移除 `claude-pr-steward-watching` 标签来停止它。[1][5] 默认情况下，PR Steward 会跳过草稿拉取请求、来自 Fork 的拉取请求、由机器人打开的拉取请求，以及无写入权限的作者所提交的拉取请求。[5] 产品文档指出，PR Steward 在设计上不会批准或合并拉取请求。[4][5]
- **Claude Approvals** 根据仓库中位于 `.claude/approvals.yml` 的策略文件评估拉取请求，并添加名为 `Claude Approvals` 的状态检查，报告仍需哪些人员批准。[6] 策略规则可指定文件路径模式、所需的人工审批席位（seats）、Claude 仅发表评论还是可以提交批准审查，以及基于拉取请求属性或自然语言分类器的条件。[1][6] 条件无法读取 CI 结果，因此 CI 检查必须在 GitHub 中继续作为独立的必需检查保留。[6] Anthropic 建议先在 `observe` 模式下启用策略，在该模式下检查仅报告策略的判定结果，而不阻止合并。[1][6]

## Claude Ship 与 GitHub 合并控制

Claude Ship 依赖仓库设置和 GitHub 治理控制机制来决定哪些更改可以实际合并。[4] Anthropic 在文档中指出，Claude Ship 使用 AI，可能会遗漏缺陷、安全漏洞或其他问题，因此建议各组织使用分支保护在合并前强制要求所需审批。[4]

在 Claude Approvals 中，该检查仅在 GitHub 中被配置为必需检查时才会阻止合并，而在 observe 模式下通常不会阻止合并。[4][6] 文档同时警示，如果未将该检查设为必需检查、规则允许作者本人占据唯一审批席位（`seats: 1`）或设为 `seats: 0`、GitHub 将 Claude 的批准审查计入单个必需批准，或规则允许 Claude 在未要求 Code Review 先行通过的情况下批准，拉取请求便可能在未经其他人工审查的情况下被合并。[6] 此外，添加 `.claude/approvals.yml` 策略文件后，除非规则中明确列出 `claude/code_review`，否则受覆盖文件的自动 Code Review 将停止运行。[6]

在 GitHub 端，合并强制执行依托多项平台功能运行，包括拉取请求合并队列（自 2023-07-12 起正式发布）、面向仓库规则集的必需审查者规则（自 2026-02-17 起正式发布，支持团队审批和 `!` 路径排除模式），以及从经典分支保护规则自动迁移至仓库规则集的功能（于 2026-08-11 发布）。[8][9][10]

## Claude Ship 的可用性、配置与计费

截至 2026-11-24，Claude Ship 面向使用 GitHub 仓库的 Claude Team 和 Enterprise 套餐提供。[1][4] Claude 组织的 Owner 可在 claude.ai 的 Organization settings > Claude Ship 中启用 Code Review 和 PR Steward，连接 GitHub 账号，并关联由 GitHub 组织所有者安装的 Claude GitHub App；审查在 Anthropic 基础设施上运行，无需向仓库添加工作流文件。[5][7] 满足先决条件后，只要拥有合并权限的用户将 `.claude/approvals.yml` 添加到默认分支，Claude Approvals 即会激活，但 Claude 组织的 Owner 可在全组织范围内关闭 Approvals。[1][6]

| 智能体 | 状态（截至 2026-11-24） | GitHub 环境 | 合规排除项 |
| --- | --- | --- | --- |
| Code Review | 正式发布 | github.com 和 GitHub Enterprise Server | Zero Data Retention、HIPAA 配置、CMEK |
| PR Steward | 公开测试版 | github.com 和 GitHub Enterprise Server（端口 443） | Zero Data Retention、HIPAA 配置、CMEK |
| Claude Approvals | 公开测试版 | github.com（含 GitHub Enterprise Cloud） | Zero Data Retention、HIPAA 配置、CMEK；启用 FERPA 或 Access Transparency 时无法启动 |

Code Review 和 PR Steward 的使用按 Token 计费，管理员可配置月度支出限额。[1][5] Claude Approvals 本身不收取基础费用，但分类器评估以及由策略触发的 Code Review（包括在 observe 模式下）均按 Token 计费。[1][6] 在 Claude Code 中本地运行 `/ship` 计入常规 Claude Code 用量。[1] 在 2026-11-23 的发布公告中，Anthropic 表示符合条件的 Claude Enterprise 组织可在 2027-01-15 前领取至少 10,000 美元的 Claude Ship 额度，领取后有效期为 30 天。[1]

## 常见问题

### Claude Ship 包含哪三款智能体？

Claude Ship 由 Code Review（正式发布）、PR Steward（公开测试版）和 Claude Approvals（公开测试版）组成。Code Review 发布按严重程度排序的审查发现，PR Steward 针对失败检查、冲突和审查评论推送修复提交，而 Claude Approvals 根据仓库策略文件评估拉取请求。 [1][4]

### PR Steward 能否批准或合并 GitHub 拉取请求？

不能。Anthropic 的文档说明 PR Steward 在设计上不会批准或合并拉取请求，团队必须依赖 GitHub 分支保护或规则集在合并前强制执行所需审批。 [4][5]

### Claude Approvals 的 observe 模式如何工作？

在 observe 模式下，Claude Approvals 检查会在拉取请求上运行，并显示 .claude/approvals.yml 中策略的判定结果，但不会强制阻止合并。在 observe 模式下，由策略触发的分类器运行和 Code Review 仍会按 Token 计费。 [1][6]

### 哪些组织无法使用 Claude Ship？

截至 2026-11-24，启用了 Zero Data Retention、应用了 HIPAA 配置或使用客户托管加密密钥（CMEK）的组织无法使用 Claude Ship。此外，启用了 FERPA 或 Access Transparency 设置的组织无法启动 Claude Approvals。 [1][6]

## 可引用的句子

- Anthropic 于 2026-11-23 面向 GitHub 上的 Claude Team 和 Enterprise 套餐宣布推出 Claude Ship。 [1]
- Code Review 于 2026-03-09 进入研究预览阶段，并于 2026-10-15 正式发布。 [2][3]
- 截至 2026-11-24，PR Steward 和 Claude Approvals 处于公开测试阶段。 [5][6]
- PR Steward 在设计上不会批准或合并拉取请求。 [4][5]
- Claude Approvals 从仓库中的 .claude/approvals.yml 策略文件读取规则，且无法在规则条件中读取 CI 结果。 [6]
- Claude Ship 的用量按 Token 计费，包括在 observe 模式下进行的分类器评估和策略触发的 Code Review。 [1][6]

## 时间线

- 2026-03-09: Anthropic 面向 Team 和 Enterprise 组织推出 Claude Code 的 Code Review 研究预览版。 [2]
- 2026-10-15: Anthropic 宣布正式发布 Code Review，并提供 Quick、Standard 和 Deep 三种仓库审查级别。 [3]
- 2026-11-23: Anthropic 宣布推出 Claude Ship，将正式发布的 Code Review 与公开测试版的 PR Steward 及 Claude Approvals 整合在一起。 [1]

## 来源

1. Introducing Claude Ship. Anthropic. 发布于 2026-11-23. https://claude.com/resources/articles/introducing-claude-ship (访问于 2026-11-24; tier 3: official site)
2. Bringing Code Review to Claude Code. Anthropic. 发布于 2026-03-09. https://claude.com/resources/articles/code-review (访问于 2026-11-24; tier 3: official site)
3. Code Review is now generally available. Anthropic. 发布于 2026-10-15. https://claude.com/resources/articles/code-review-is-now-generally-available (访问于 2026-11-24; tier 3: official site)
4. Claude Ship - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/claude-ship (访问于 2026-11-24; tier 3: official site)
5. PR Steward - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/pr-steward (访问于 2026-11-24; tier 3: official site)
6. Claude Approvals - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/approvals (访问于 2026-11-24; tier 3: official site)
7. Set up Code Review - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/code-review-setup (访问于 2026-11-24; tier 3: official site)
8. Required reviewer rule is now generally available. GitHub. 发布于 2026-02-17. https://github.blog/changelog/2026-02-17-required-reviewer-rule-is-now-generally-available/ (访问于 2026-11-24; tier 3: official site)
9. Automatically migrate branch protection rules to repository rulesets. GitHub. 发布于 2026-08-11. https://github.blog/changelog/2026-08-11-automatically-migrate-branch-protection-rules-to-repository-rulesets/ (访问于 2026-11-24; tier 3: official site)
10. Pull request merge queue is now generally available!. GitHub. 发布于 2023-07-12. https://github.blog/changelog/2023-07-12-pull-request-merge-queue-is-now-generally-available/ (访问于 2026-11-24; tier 3: official site)
11. Anthropic launches Claude Ship, letting AI agents review, fix, and approve code changes. TechCrunch. 发布于 2026-11-23. https://techcrunch.com/2026/11/23/anthropic-launches-claude-ship-letting-ai-agents-review-fix-and-approve-code-changes/ (访问于 2026-11-24; tier 2: academic or news)
12. Claude AI can review pull requests and ship fixes on its own now. The Verge. 发布于 2026-11-23. https://www.theverge.com/ai-artificial-intelligence/1040134/anthropic-claude-ship-ai-pull-requests (访问于 2026-11-24; tier 2: academic or news)

## 引用本页

Mimirwiki. "Claude Ship." 版本 1d16836d, 2026-11-24. https://mimirwiki.com/zh/wiki/claude-ship
