---
title: "ClaudeBot"
subtitle: "Anthropic 运营的用于为 AI 模型训练采集公开网络内容的网络爬虫"
canonical_url: https://mimirwiki.com/zh/wiki/claudebot
language: zh
page_class: entity
revision_sha256: 147eeb853adbfa19734dddacc684f99f0bd4551a9d61ac5d48931902cb6a24b5
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 10
alternates:
  md: https://mimirwiki.com/zh/wiki/claudebot.md
  txt: https://mimirwiki.com/zh/wiki/claudebot.txt
  json: https://mimirwiki.com/zh/wiki/claudebot.json
  jsonld: https://mimirwiki.com/zh/wiki/claudebot.jsonld
translations:
  en: https://mimirwiki.com/wiki/claudebot
  ko: https://mimirwiki.com/ko/wiki/claudebot
  ja: https://mimirwiki.com/ja/wiki/claudebot
  es: https://mimirwiki.com/es/wiki/claudebot
---

# ClaudeBot

> ClaudeBot 是 Anthropic 运营的训练类网络爬虫，用于为生成式 AI 模型采集公开网络内容。Anthropic 将其与用于搜索索引的 Claude-SearchBot 以及用于用户发起请求的 Claude-User 区分开来。网站所有者可以通过 robots.txt 屏蔽或限制 ClaudeBot 的速率；自 2026 年 10 月 30 日起，Anthropic 也开始识别基于 IETF aipref 草案的训练偏好信号。

ClaudeBot 是 Anthropic 运营的自动化网络爬虫，用于采集可能有助于训练其生成式 AI 模型（包括 Claude）的公开网络内容。Anthropic 在文档中将 ClaudeBot 与另外两种独立的网络机器人并列说明：用于搜索索引的 Claude-SearchBot 以及用于响应用户发起查询而检索页面的 Claude-User。网站所有者可以通过 RFC 9309 定义的 robots.txt 指令（包括非标准的 Crawl-delay 扩展）限制或限速 ClaudeBot；自 2026 年 10 月 30 日起，Anthropic 开始识别基于 IETF aipref 草案工作的机器可读禁止 AI 训练偏好信号。2024 年多家网站运营方报告称 ClaudeBot 产生了大量请求，Anthropic 在 2026 年 11 月 17 日提交的 Form S-1/A-3 申报文件中披露了围绕其网络抓取实践的未决诉讼。

**别名:** Anthropic 网络爬虫, ClaudeBot 爬虫

## 关键事实

- **运营方:** Anthropic (截至 2026-11-23) [4]
- **产品标识符:** ClaudeBot (截至 2026-11-23) [4]
- **声明用途:** 采集用于生成式 AI 模型训练的公开网络内容 (截至 2026-11-23) [4]
- **配套机器人:** Claude-SearchBot（搜索索引）和 Claude-User（用户发起的页面抓取） (截至 2026-11-23) [4]
- **退出控制手段:** robots.txt 指令、Crawl-delay 扩展及 IETF aipref 草案偏好信号（自 2026-10-30 起） (截至 2026-11-23) [4]

## 事实摘要

- **名称:** ClaudeBot [4]
- **类型:** 自动化网络爬虫（训练类爬虫） [4]
- **运营方:** Anthropic (截至 2026-11-23) [4]
- **运营法律实体:** Anthropic, PBC（特拉华州公益公司，位于加利福尼亚州旧金山） (截至 2026-11-17) [2]
- **产品标识符:** ClaudeBot (截至 2026-11-23) [4]
- **声明用途:** 采集用于 AI 模型训练的公开网络内容 (截至 2026-11-23) [4]
- **Anthropic 配套机器人:** Claude-SearchBot（搜索索引）、Claude-User（用户指令检索） (截至 2026-11-23) [4]
- **排除协议:** 机器人排除协议（robots.txt，IETF RFC 9309） [1]
- **速率限制指令:** Crawl-delay（非标准 robots.txt 扩展） (截至 2026-11-23) [4]
- **训练偏好信号:** IETF aipref 草案禁止 AI 训练信号（自 2026-10-30 起识别） (截至 2026-11-23) [4]
- **反规避政策:** 不尝试绕过被抓取网站的 CAPTCHA (截至 2026-11-23) [4]
- **隐私文档:** Anthropic 隐私政策（2026-09-10 生效）及单独的非用户隐私政策 (截至 2026-09-10) [5]
- **公开 IP 列表 URL:** https://claude.com/crawling/bots.json（14 个 IPv4 前缀，creationTime 2026-10-20T00:00:00Z） (截至 2026-11-23) [10]

## ClaudeBot 与 Anthropic 的网络机器人套件

ClaudeBot 是 [Anthropic](https://mimirwiki.com/zh/wiki/anthropic) 运营的训练类网络爬虫，属于其用于采集网络内容、索引搜索结果以及为 [Claude](https://mimirwiki.com/zh/wiki/claude) 用户抓取页面的三机器人体系的一部分。[4] 截至 2026 年 11 月 23 日，Anthropic 的爬虫文档将自动化访问划分为三个具名机器人，以便网站所有者针对模型训练、搜索索引和用户发起检索分别设定访问策略。[4]

| 机器人 | 声明功能 | 通过 robots.txt 禁用后的效果 |
| --- | --- | --- |
| ClaudeBot | 采集可能有助于训练生成式 AI 模型的网络内容 | 表明应将该网站未来的材料排除在 Anthropic AI 模型训练数据集之外 |
| Claude-SearchBot | 浏览并分析网络内容以提高搜索结果的相关性和准确性 | 阻止为搜索优化对网站内容建立索引，可能降低在用户搜索结果中的可见度和准确性 |
| Claude-User | 响应 Claude 用户提出的问题而访问网站 | 阻止响应用户查询而检索网站内容，可能降低在用户指令网络搜索中的可见度 |

Anthropic 将这三种爬虫与抓取器同 Claude 代表用户完成任务时所使用的 Anthropic 托管浏览器（包括 Claude Duet 中的 Claude-Agent）区分开来，并对后者另行提供文档说明。[4]

截至 2026 年 11 月 23 日，Anthropic 为其网络机器人列出了四项运营原则。[4]

- 通过文档记录的三个机器人名称进行透明身份识别
- 在单个域名上保持非侵入式的抓取节奏，包括在适当情况下遵循 `Crawl-delay`
- 遵循 `robots.txt` 中发布的禁止抓取指令
- 尊重反规避技术，包括不对被抓取网站尝试绕过 CAPTCHA

## 基于 robots.txt 与 IETF aipref 的 ClaudeBot 控制机制

ClaudeBot 遵循发布在 [robots.txt](https://mimirwiki.com/zh/wiki/robots-txt) 中的站点级访问指令，该文本文件由互联网工程任务组（IETF）通过 RFC 9309 进行标准化。[1][4] 发布于 2022 年 9 月的 RFC 9309 规范并扩展了 Martijn Koster 于 1994 年最初定义的机器人排除协议。[1] 根据 RFC 9309，`robots.txt` 文件将 `allow` 和 `disallow` 规则归入以 `user-agent` 产品标识符开头的规则组中，产品标识符仅包含 ASCII 字母、下划线和连字符，爬虫以不区分大小写的方式进行匹配，若无特定规则组匹配则回退至通配符规则组 `user-agent: *`。[1] 路径匹配从 URI 路径的第一个八位字节开始，应区分大小写并应用最长匹配规则；RFC 9309 还明确指出 `robots.txt` 规则并非访问授权方式。[1]

若要在整个网站中排除 ClaudeBot，截至 2026 年 11 月 23 日的 Anthropic 文档指示网站所有者在网站顶级目录的 `robots.txt` 文件中添加 `User-agent: ClaudeBot` 和 `Disallow: /`，并在每个希望退出的子域名上重复该配置。[4] 为限制请求频率，Anthropic 支持 `robots.txt` 的非标准 `Crawl-delay` 扩展（例如在 `User-agent: ClaudeBot` 后添加 `Crawl-delay: 1`）。[1][4]

截至 2026 年 11 月 23 日，Anthropic 表示退出抓取需要更新 `robots.txt`。[4] 屏蔽 Anthropic 机器人运行的源 IP 地址可能会阻止爬虫读取网站的 `robots.txt` 文件，因此 Anthropic 指出 IP 屏蔽可能无法可靠生效或持久保证退出抓取。[4] Anthropic 在 `https://claude.com/crawling/bots.json` 以 JSON 格式公开其爬虫 IP 前缀；截至 2026 年 11 月 23 日，该文件的 `creationTime` 为 `2026-10-20T00:00:00Z`，共列出 14 个 IPv4 前缀，包括 `216.73.216.0/22` 和 13 个单主机 `/32` 地址。[4][10]

2026 年 10 月 30 日，Anthropic 开始识别允许网站所有者表达“禁止 AI 训练”设置的机器可读偏好信号。[4] 该信号基于 IETF `aipref` 工作组的草案工作，Anthropic 表示正逐步在其全球服务范围内推出支持，同时指出其解释方式可能会随着草案标准的发展而演进。[4] 对于任意给定路径，明确指定 `ClaudeBot` 的 `robots.txt` 规则优先于通用偏好信号，即使通用信号指定了不同的设置；当 `robots.txt` 未提及 `ClaudeBot` 时，Anthropic 则应用通用偏好设置。[4]

## Anthropic 训练数据与隐私政策中的 ClaudeBot

ClaudeBot 采集的公开网络内容属于 Anthropic 隐私政策及证券申报文件中所述训练数据的一个类别。[2][4][5] 于 2026 年 9 月 10 日生效的 Anthropic 隐私政策（Privacy Policy）列举了为训练 Anthropic 模型而收集或接收的六类数据来源。[5]

- 通过互联网公开获取的信息
- 通过与第三方企业签订商业协议获得的数据集
- 用户或众包工作者提供的数据，除非用户通过账户设置选择退出，否则包括 Anthropic 服务的输入（Inputs）和输出（Outputs）
- 用户就 Anthropic 服务明确提供的反馈
- 被标记用于安全性、安保或政策审查的材料
- Anthropic 内部生成的数据

Anthropic 隐私政策声明其不适用于代表企业客户（如 Enterprise 账户）处理的内容，此类内容受客户协议管辖，并指引读者查阅单独的非用户隐私政策（Non-User Privacy Policy），以了解大语言模型如何使用第三方个人数据进行训练以及适用于非用户的选择。[5] 即使个人消费者用户通过账户设置选择退出模型训练，Anthropic 也表示，如果对话被标记用于安全审查或通过反馈机制明确举报，其输入和输出仍可能被用于模型改进。[5]

在 2026 年 11 月 17 日向 [SEC EDGAR](https://mimirwiki.com/zh/wiki/sec-edgar) 提交的 Form S-1 第 3 号修订文件（注册号 333-299633）中，Anthropic, PBC 表示其在模型开发的预训练（pre-training）和后训练（post-training）阶段均使用公开可用的互联网信息、获许可或委托制作的第三方数据集以及由其自身模型生成的合成数据。[2] 该申报文件指出，网络抓取或网络爬虫技术、图书扫描及其他方法是 Anthropic 采集公开信息的途径。[2] Anthropic 在同一份文件中表示，尽管其采取了旨在遵守适用法律、`robots.txt` 声明以及付费墙或登录等技术措施的步骤，但这些努力未必总能成功，且 Anthropic 可能无法核实所采集的材料是否受隐私、版权或其他知识产权法律保护。[2]

## ClaudeBot 与 Cloudflare 的 AI 爬虫控制机制

ClaudeBot 运行在更广泛的网络基础设施环境中，[Cloudflare](https://mimirwiki.com/zh/wiki/cloudflare) 等网络服务商在该环境中对自动化流量进行分类，并为网站所有者提供针对 AI 爬虫的精细化控制。[6][7] 在 2025 年 7 月 1 日发布的一份涵盖 2024 年 5 月至 2025 年 5 月的流量分析中，Cloudflare 报告称AI 与搜索爬虫流量增长了 18%，其中 [OpenAI](https://mimirwiki.com/zh/wiki/openai) 的 [GPTBot](https://mimirwiki.com/zh/wiki/gptbot) 增长 305%，Googlebot 增长 96%。[9]

2026 年 7 月 1 日，Cloudflare 面向所有客户套餐推出 AI 流量选项，使网站所有者能够分别区分和管理 Search、Agent 和 Training 流量。[7] 同日，Cloudflare 更新了其 BotBase 分类体系，使每个被追踪的机器人都按行为和运营方访问类型进行分类，以 `Direct` 与 `Intermediary` 访问字段取代此前 Verified bots 与签名代理之间的划分。[6]

| BotBase 分类维度 | 类别 | Cloudflare 定义（文档更新于 2026-11-12） |
| --- | --- | --- |
| 行为（托管 AI 预设） | Training | 为训练或微调模型而进行的抓取 |
| 行为（托管 AI 预设） | Search | 为构建搜索索引或 RAG 数据库而进行的抓取 |
| 行为（托管 AI 预设） | Agent | 代表人类访问页面的用户指令代理 |
| 运营方访问标签 | Direct | 由单一、特定运营方运营，通常位于其自有基础设施上 |
| 运营方访问标签 | Intermediary | 由众多终端用户驱动的代理服务，引入了传递性信任 |

根据 Cloudflare 的 Verified bots 文档（最后更新于 2026 年 11 月 12 日），获得 Verified 状态需要通过加密的 [Web Bot Auth](https://mimirwiki.com/zh/wiki/web-bot-auth) 签名、带有稳定用户代理的公开 IP 列表或反向 DNS 实现确定性自我识别，并配合非滥用行为，以合理请求速率遵循 `robots.txt` 及抓取指令。[6] `AI Crawler`、`AI Search` 和 `AI Assistant` 等旧版 WAF 类别仍与更新后的分类体系并行保留，以维持向后兼容性。[6] Cloudflare 将不遵守 `robots.txt` 中 `crawl-delay` 指令列为可能导致 AI 爬虫被移出其全局允许列表的政策违规行为，并指出某组织反复违规或其旗下不同机器人合规不一致，可能导致该组织运营的所有机器人的 Verified 状态被撤销。[6]

2026 年 9 月 15 日，Cloudflare 还宣布了 Disallow AI Training 设置及 Accountable 认定，允许网站所有者在禁止 AI 训练的同时保持搜索索引，并表示 Apple、Google 和 Microsoft 已遵守或承诺遵守该设置。[8]

## ClaudeBot 相关发布者报告与抓取诉讼

ClaudeBot 因高请求量引发了网站管理员的公开运营报告，而 Anthropic 更广泛的网络抓取实践已成为法律诉讼的对象。[2][3] 2024 年 7 月 25 日，*The Verge* 报道称，iFixit 首席执行官 Kyle Wiens 表示 ClaudeBot 在 24 小时内向 iFixit 服务器发送了近 100 万次请求，触发了运营警报并需要 iFixit 的 DevOps 团队介入处理。[3]

iFixit 的使用条款（Terms of Use）禁止在未经明确事先书面许可的情况下复制、拷贝或分发网站内容，并明确涵盖机器学习或 AI 模型训练。[3] 在 404 Media 询问此事时，Anthropic 提供了指向其常见问题页面的链接，说明可通过 `robots.txt` 屏蔽其爬虫。[3] 在 iFixit 向其 `robots.txt` 文件添加 `crawl-delay` 规则后，Wiens 告诉 *The Verge* 服务器日志显示 ClaudeBot 已停止访问，Anthropic 发言人 Jennifer Martinez 表示 Anthropic 尊重 `robots.txt`，在 iFixit 实施该信号后其爬虫予以遵守。[3]

在 Wiens 于 2024 年 7 月在 X 上发起的同一讨论帖中，Read the Docs 联合创始人 Eric Holscher 和 Freelancer.com 首席执行官 Matt Barrie 表示，他们的网站也遭遇了 Anthropic 爬虫的大量抓取。[3] *The Verge* 还指出，2024 年 4 月 Linux Mint 网络论坛将一次网站宕机归因于 ClaudeBot 抓取活动造成的服务器负载压力。[3]

在 2026 年 11 月 17 日提交的 Form S-1 第 3 号修订文件中，Anthropic, PBC 披露其抓取、网络爬虫和数据采集活动已经引发且仍是控告违法的诉讼对象。[2] 该申报文件具体援引了 `Reddit, Inc. v. Anthropic PBC` 一案，Reddit 在案中指控 Anthropic 违反 Reddit 的合法权利，不当访问存储在 Reddit 平台上的帖子。[2] Anthropic 于 2025 年 7 月 3 日提交了移送联邦法院的通知，该案于 2026 年 3 月 30 日被发回州法院，截至 2026 年 11 月 17 日仍处于未决状态。[2] Anthropic 还将此列为业务风险，披露称抓取诉讼中的不利和解或判决可能要求其停止某些抓取或爬虫技术、开发替代数据采集方法或支付巨额款项。[2]

## 常见问题

### ClaudeBot 的用途是什么？

截至 2026 年 11 月 23 日，Anthropic 使用 ClaudeBot 采集可能用于训练其生成式 AI 模型的公开网络内容。Anthropic 另行运营用于搜索索引的 Claude-SearchBot 和用于响应用户查询抓取网页的 Claude-User。 [4]

### 网站所有者如何屏蔽或限制 ClaudeBot 的访问速率？

网站所有者可以在需要排除的每个域名和子域名的顶级 robots.txt 文件中添加 User-agent: ClaudeBot 和 Disallow: / 来屏蔽 ClaudeBot。网站所有者也可以使用非标准的 Crawl-delay 扩展来限制抓取频率；自 2026 年 10 月 30 日起，Anthropic 还开始识别基于 IETF aipref 草案的禁止 AI 训练偏好信号。 [1][4]

### 屏蔽 ClaudeBot 会阻止 Claude 在用户对话期间抓取网页吗？

不会。限制 ClaudeBot 仅表示应将该网站未来的内容排除在 Anthropic 的 AI 模型训练数据集之外。用户发起的页面检索使用 Claude-User，搜索索引使用 Claude-SearchBot，网站所有者可以为每个机器人分别配置 robots.txt 规则。 [4]

### 为什么 Anthropic 建议不要仅通过 IP 地址屏蔽 ClaudeBot？

截至 2026 年 11 月 23 日，Anthropic 的爬虫文档指出，屏蔽其机器人使用的 IP 地址会阻碍爬虫读取网站的 robots.txt 文件，因此 IP 屏蔽可能无法可靠生效或持久保证退出抓取。Anthropic 公布了源 IP 地址列表，以便管理员核实爬虫是否来自 Anthropic。 [4]

### Cloudflare 如何对 ClaudeBot 等训练类爬虫进行分类？

在 2026 年 7 月 1 日推出的 BotBase 分类体系下，Cloudflare 按行为对机器人进行分类，包括用于模型训练或微调的 Training、用于搜索索引或 RAG 数据库的 Search 以及用于用户指令浏览的 Agent，并在所有套餐中提供托管预设。Cloudflare 还要求 Verified bots 进行确定性身份识别，并遵循包括 crawl-delay 在内的 robots.txt 指令。 [6][7]

### Anthropic 在 SEC 申报文件中披露了哪些与网络抓取相关的诉讼？

Anthropic, PBC 在 2026 年 11 月 17 日向 SEC 提交的 Form S-1 第 3 号修订文件中披露了未决诉讼 Reddit, Inc. v. Anthropic PBC，该诉讼指控其不当访问存储在 Reddit 平台上的帖子。Anthropic 于 2025 年 7 月 3 日提交了移送联邦法院的通知，该案于 2026 年 3 月 30 日被发回州法院。 [2]

## 可引用的句子

- 截至 2026 年 11 月 23 日，Anthropic 在文档中记录了三种网络机器人：用于采集 AI 模型训练数据的 ClaudeBot、用于搜索索引的 Claude-SearchBot 以及用于用户发起页面抓取的 Claude-User。 [4]
- 截至 2026 年 11 月 23 日，Anthropic 表示其网络机器人遵循 robots.txt 指令，支持非标准的 Crawl-delay 扩展，且不尝试绕过 CAPTCHA。 [4]
- 自 2026 年 10 月 30 日起，Anthropic 开始识别基于 IETF aipref 工作组草案的机器可读禁止 AI 训练偏好信号，其中明确指定 ClaudeBot 的 robots.txt 规则具有更高优先级。 [4]
- IETF 于 2022 年 9 月发布的 RFC 9309 规范了机器人排除协议，并指出 robots.txt 规则并非访问授权方式。 [1]
- 2024 年 7 月，iFixit 首席执行官 Kyle Wiens 报告称，ClaudeBot 在 24 小时内向 iFixit 服务器发送了近 100 万次请求，在 iFixit 向 robots.txt 添加 crawl-delay 指令后停止。 [3]
- Anthropic 于 2026 年 9 月 10 日生效的隐私政策将公开可用的互联网信息列为用于训练 Anthropic 模型的六个数据来源之一。 [5]
- Anthropic, PBC 在 2026 年 11 月 17 日向 SEC 提交的 Form S-1 第 3 号修订文件（S-1/A-3）中披露，Reddit, Inc. v. Anthropic PBC 诉讼在 2026 年 3 月 30 日被发回州法院后仍处于未决状态。 [2]
- Cloudflare 于 2025 年 7 月 1 日发布的爬虫分析报告称，2024 年 5 月至 2025 年 5 月期间AI 与搜索爬虫流量增长了 18%，其中 GPTBot 流量增长 305%，Googlebot 流量增长 96%。 [9]

## 时间线

- 2022-09: IETF 发布 RFC 9309，将机器人排除协议（robots.txt）标准化。 [1]
- 2024-04: Linux Mint 网络论坛将一次网站宕机归因于 ClaudeBot 抓取活动造成的服务器负载压力。 [3]
- 2024-07-25: The Verge 报道称，ClaudeBot 在 24 小时内向 iFixit 发送了近 100 万次请求，在 iFixit 向 robots.txt 添加 crawl-delay 指令后停止。 [3]
- 2025-07-01: Cloudflare 发布爬虫流量分析报告，指出 2024 年 5 月至 2025 年 5 月AI 与搜索爬虫流量增长 18%，其中 GPTBot 增长 305%，Googlebot 增长 96%。 [9]
- 2025-07-03: Anthropic 在指控其不当访问 Reddit 帖子的 Reddit, Inc. v. Anthropic PBC 诉讼中提交了移送联邦法院的通知。 [2]
- 2026-03-30: Reddit, Inc. v. Anthropic PBC 一案由联邦法院发回州法院。 [2]
- 2026-07-01: Cloudflare 面向所有客户推出独立的 Search、Agent 和 Training 流量选项，并在 BotBase 中新增 Direct 与 Intermediary 访问标签。 [6][7]
- 2026-09-10: Anthropic 更新后的隐私政策生效，将公开可用的互联网信息列为六个模型训练数据来源之一。 [5]
- 2026-09-15: Cloudflare 宣布推出允许在禁止 AI 训练的同时保持搜索索引的 Disallow AI Training 设置及 Accountable 认定，并表示 Apple、Google 和 Microsoft 已遵守或承诺遵守该设置。 [8]
- 2026-10-30: Anthropic 开始识别基于 IETF aipref 工作组草案的机器可读禁止 AI 训练偏好信号。 [4]
- 2026-11-17: Anthropic, PBC 向 SEC 提交 Form S-1 第 3 号修订文件，披露网络抓取方法、robots.txt 合规局限性以及未决抓取诉讼。 [2]

## 来源

1. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 发布于 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (访问于 2026-11-23; tier 1: government or public registry)
2. Anthropic, PBC - S-1/A-3. U.S. Securities and Exchange Commission (EDGAR). 发布于 2026-11-17. https://www.sec.gov/Archives/edgar/data/2130357/000162828026074338/anthropicpbc-sx1ax3.htm (访问于 2026-11-23; tier 1: government or public registry)
3. Anthropic’s crawler is ignoring websites’ anti-AI scraping policies | The Verge. The Verge. 发布于 2024-07-25. https://www.theverge.com/2024/7/25/24205943/anthropic-ai-web-crawler-claudebot-ifixit-scraping-training-data (访问于 2026-11-23; tier 2: academic or news)
4. Does Anthropic crawl data from the web, and how can site owners block the crawler? | Claude Help Center. Anthropic. https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler (访问于 2026-11-23; tier 3: official site)
5. Privacy Policy \ Anthropic. Anthropic. 发布于 2026-09-10. https://www.anthropic.com/legal/privacy (访问于 2026-11-23; tier 3: official site)
6. Verified bots · Cloudflare bot solutions docs. Cloudflare. 发布于 2026-11-12. https://developers.cloudflare.com/bots/concepts/bot/verified-bots/ (访问于 2026-11-23; tier 3: official site)
7. Your site, your rules: new AI traffic options for all customers | Cloudflare Blog. The Cloudflare Blog. 发布于 2026-07-01. https://blog.cloudflare.com/content-independence-day-ai-options/ (访问于 2026-11-23; tier 3: official site)
8. Have it both ways: stay discoverable in search while disallowing AI training | Cloudflare Blog. The Cloudflare Blog. 发布于 2026-09-15. https://blog.cloudflare.com/accountable-mixed-use-ai-crawlers/ (访问于 2026-11-23; tier 3: official site)
9. From Googlebot to GPTBot: Who’s crawling your site in 2025 | Cloudflare Blog. The Cloudflare Blog. 发布于 2025-07-01. https://blog.cloudflare.com/from-googlebot-to-gptbot-whos-crawling-your-site-in-2025/ (访问于 2026-11-23; tier 3: official site)
10. Anthropic Crawler IP Prefixes (bots.json). Anthropic. 发布于 2026-10-20. https://claude.com/crawling/bots.json (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "ClaudeBot." 版本 147eeb85, 2026-11-25. https://mimirwiki.com/zh/wiki/claudebot
