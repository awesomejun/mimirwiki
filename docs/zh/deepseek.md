---
title: "DeepSeek"
subtitle: "开发 DeepSeek-V4、DeepSeek-R1 与 DeepSeek-V3 基础模型的中国人工智能研究实验室"
canonical_url: https://mimirwiki.com/zh/wiki/deepseek
language: zh
page_class: entity
revision_sha256: 9ee56a50558eb2469325a0c10058548df05567a3da22ff46bd1993669cabb370
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/zh/wiki/deepseek.md
  txt: https://mimirwiki.com/zh/wiki/deepseek.txt
  json: https://mimirwiki.com/zh/wiki/deepseek.json
  jsonld: https://mimirwiki.com/zh/wiki/deepseek.jsonld
translations:
  en: https://mimirwiki.com/wiki/deepseek
  ko: https://mimirwiki.com/ko/wiki/deepseek
  ja: https://mimirwiki.com/ja/wiki/deepseek
---

# DeepSeek

> 截至 2026 年 11 月，DeepSeek 开发者平台提供两款主力 100 万 Token 上下文模型：deepseek-flash（DeepSeek-V4.1-Flash-1017）与 deepseek-v4-pro（DeepSeek-V4-Pro-0813），两者均支持最高 384K 输出 Token，并配套高峰与低谷动态定价、原生 Search/Fetch/OCR/Speech API 以及免费内置服务器端联网搜索功能（于 2026 年 11 月 18 日启用）。此前的开放权重里程碑包括 DeepSeek-V3（总参数 671B / 激活参数 37B）以及采用 MIT 许可证的 DeepSeek-R1 推理模型系列。

DeepSeek（官方运营实体为杭州深度求索人工智能有限公司与北京深度求索人工智能有限公司，英文名为 Hangzhou DeepSeek Artificial Intelligence Co., Ltd. 与 Beijing DeepSeek Artificial Intelligence Co., Ltd.）是一家成立于 2023 年、总部位于中国浙江省杭州市的人工智能研究公司。该公司研发基于多头潜在注意力（Multi-head Latent Attention，MLA）与 DeepSeekMoE 架构的开放权重及 API 托管大语言模型，涵盖 DeepSeek-V2、DeepSeek-V3、强化学习推理模型 DeepSeek-R1 以及多模态 DeepSeek-V4 系列。

**别名:** 杭州深度求索人工智能有限公司, 北京深度求索人工智能有限公司, 深度求索, Hangzhou DeepSeek Artificial Intelligence Co., Ltd., Beijing DeepSeek Artificial Intelligence Co., Ltd.

## 关键事实

- **运营实体:** 杭州深度求索人工智能有限公司 / 北京深度求索人工智能有限公司 [7]
- **当前生产模型:** deepseek-flash（DeepSeek-V4.1-Flash-1017）与 deepseek-v4-pro（DeepSeek-V4-Pro-0813） (截至 2026-11-23) [1]
- **上下文与最大输出:** 1M Token 上下文窗口；最高 384K 最大输出 Token (截至 2026-11-23) [1]
- **开放权重推理里程碑:** DeepSeek-R1（MIT 许可证，2025 年 1 月）与 DeepSeek-V3（671B/37B MoE，2024 年 12 月） [4]

## 事实摘要

- **官方名称:** 杭州深度求索人工智能有限公司（Hangzhou DeepSeek Artificial Intelligence Co., Ltd.） [7]
- **总部地点:** 中国浙江省杭州市 [7]
- **核心架构:** 多头潜在注意力（MLA）、DeepSeekMoE、多 Token 预测（MTP） [5]
- **旗舰 API 模型（2026 年 11 月）:** DeepSeek-V4.1-Flash-1017（deepseek-flash）、DeepSeek-V4-Pro-0813（deepseek-v4-pro） [1]
- **API 上下文与输出:** 1,000,000 上下文 Token / 384,000 最大输出 Token（默认 64K） [1]
- **API 并发限制:** 2,500 并发请求（deepseek-flash）；500 并发请求（deepseek-v4-pro） [2]
- **多模态与工具 API:** Search API、Fetch API、OCR API、Speech-to-Text API、服务器端 search_Option [1]
- **开源许可证（R1）:** MIT 许可证（DeepSeek-R1 及蒸馏模型的权重与代码） [4]

## DeepSeek 公司概况与架构基础

DeepSeek 通过杭州深度求索人工智能有限公司（Hangzhou DeepSeek Artificial Intelligence Co., Ltd.）与北京深度求索人工智能有限公司（Beijing DeepSeek Artificial Intelligence Co., Ltd.）开展运营，构建前沿基础模型与开发者 API。[1][7] 该实验室在 2024 年至 2025 年间发布了详尽的架构技术报告，并以远低于常规前沿模型算力预算的训练成本推出了开放权重混合专家（Mixture-of-Experts，MoE）模型与推理模型，从而获得全球关注。[4][5][6]

DeepSeek 的基础模型建立在 **DeepSeek-V2**（2024 年 5 月，总参数量 236B，每 Token 激活 21B 参数）所引入、并在 **DeepSeek-V3**（2024 年 12 月，总参数量 671B，每 Token 激活 37B 参数）中进一步扩展的两项核心结构创新之上。[5][6] - **多头潜在注意力（Multi-head Latent Attention，MLA）**：在推理阶段将键值（KV）缓存表征压缩为低秩潜在向量，大幅降低长上下文序列的内存带宽开销。[5][6] - **无辅助损失负载均衡的 DeepSeekMoE（Auxiliary-Loss-Free Load Balancing）**：将细粒度路由专家与共享专家相结合，以动态偏置调整路由策略取代会损害模型性能的辅助负载均衡损失，并引入多 Token 预测（Multi-Token Prediction，MTP）训练目标。[5] DeepSeek-V3 采用 FP8 混合精度训练，仅消耗 278.8 万 H800 GPU 小时即完成了 14.8 万亿 Token 的预训练。[5]

## DeepSeek-R1 与面向推理的强化学习

2025 年 1 月，DeepSeek 在宽松的 MIT 许可证下发布了 **DeepSeek-R1** 与 **DeepSeek-R1-Zero**，证明无需预先进行监督微调（SFT），仅依靠大规模纯强化学习（RL）即可在语言模型中诱发自我验证、反思以及长思维链（Chain-of-Thought，CoT）推理能力。[4]

`DeepSeek-R1-Zero` 直接在基座模型上应用组相对策略优化（Group Relative Policy Optimization，GRPO），而 `DeepSeek-R1` 则结合冷启动 CoT 数据与拒绝采样开展了多阶段训练，以消除语言混杂现象并提升可读性，在数学、编程竞赛及 STEM 推理基准测试中达到了与 OpenAI-o1-1217 相当的表现。[4] DeepSeek 还同步发布了 6 款基于 DeepSeek-R1 输出蒸馏而成的稠密模型（参数规模覆盖 1.5B 至 70B，基于 Qwen 与 Llama 架构）。[4]

## DeepSeek-V4 系列、定价与开发者平台（2026 年）

至 2026 年底，DeepSeek 已将其生产 API 平台（`api.deepseek.com`）全面迁移至多模态 **DeepSeek-V4** 架构，将对话、推理（`thinking`）、视觉与音频输入整合进两款主力模型端点，均提供 **1,000,000 Token 上下文窗口**与最高 **384,000 最大输出 Token**（默认 64K）。[1]

| API 模型别名 | 底层模型版本 | 高峰时段定价（08:00-24:00 UTC+8） | 低谷时段定价（00:00-08:00 UTC+8） | 并发限制 |
| --- | --- | --- | --- | --- |
| `deepseek-flash` | `DeepSeek-V4.1-Flash-1017`（2026 年 10 月 20 日发布） | 输入：$0.03/M（缓存命中），$0.30/M（未命中，<=256K），$0.50/M（>256K）；输出：$1.50-$2.50/M | 输入：$0.03/M（缓存命中），$0.15/M（<=256K），$0.25/M（>256K）；输出：$0.75-$1.25/M | 2,500 并发请求 [1][2] |
| `deepseek-v4-pro` | `DeepSeek-V4-Pro-0813`（2026 年 8 月 19 日发布） | 输入：$0.20/M（缓存命中），$2.00/M（未命中，<=256K），$4.00/M（>256K）；输出：$12.00-$18.00/M | 输入：$0.20/M（缓存命中），$1.00/M（<=256K），$2.00/M（>256K）；输出：$6.00-$9.00/M | 500 并发请求 [1][2] |

两款模型均支持文本、图像与音频输入，并输出文本、JSON 模式、函数工具调用以及推理内容（Reasoning Content）。[1] 当提交音频 Token 时，音频输入按更高的每百万 Token 费率计费（依据上下文区间与缓存状态，`deepseek-flash` 为 $1.00-$4.00/M，`deepseek-v4-pro` 为 $7.00-$28.00/M）。[1] 旧版别名如 `deepseek-chat` 与 `deepseek-reasoner` 会自动映射至 V4 系列端点。[1]

## DeepSeek 内置联网搜索、实用工具 API 与速率治理

2026 年 11 月 18 日，DeepSeek 升级了其对话补全（chat completions）端点，通过 `search_Option` 参数支持原生服务器端联网搜索与网页抓取，并在推广阶段免除按次计费的额外搜索费用。[1][3] 面向独立的程序化流水线，DeepSeek 还开放了专用实用工具端点。[1] - **Search API**：每 1,000 次查询 $5.00。[1] - **Fetch API**：每 1,000 次 URL 抓取 $1.00。[1] - **OCR API**：每 1,000 页文档 $1.00。[1] - **Speech-to-Text API**：每小时音频转录 $0.10。[1]

与按消费等级实施严格每分钟 Token 数（TPM）或每分钟请求数（RPM）上限的服务商不同，DeepSeek 主要通过活跃在途并发数进行吞吐量治理（`deepseek-flash` 为 2,500 并发请求，`deepseek-v4-pro` 为 500 并发请求）。[2] 为防止多租户应用遭到单一用户滥用，开发者可在 API 请求载荷中传入 `user_id` 参数，将单个终端用户 ID 限制在 **10 个并发请求**以内（超限时仅对该 `user_id` 返回 HTTP `429 Too Many Requests`，而不影响所属组织的全局并发池）。[2]

## DeepSeek 数据治理与隐私政策

根据 DeepSeek 的《隐私政策》，其面向消费者的网页端、移动应用及平台服务由杭州深度求索人工智能有限公司与北京深度求索人工智能有限公司运营。[7] 通过 DeepSeek 服务收集的用户提示词、上传文件、对话历史及交互日志均存储于位于**中华人民共和国**境内的服务器，并受中国数据保护与网络安全法律法规管辖。[7] 除在适用情况下选择退出外，消费者交互数据可能会被用于安全合规审查及服务改进；而 DeepSeek-V2、DeepSeek-V3 与 DeepSeek-R1 的开放权重发行版则允许企业在私有基础设施上自托管模型权重，实现零外部遥测。[4][5][7]

## 常见问题

### 截至 2026 年 11 月，DeepSeek 的主要 API 模型有哪些？

DeepSeek 提供两款主力生产级 API 模型：面向高吞吐多模态推理与编程的 deepseek-flash（底层为 DeepSeek-V4.1-Flash-1017），以及面向前沿深度推理的 deepseek-v4-pro（底层为 DeepSeek-V4-Pro-0813）。两款模型均具备 100 万 Token 上下文窗口，并支持最高 384,000 最大输出 Token。 [1][3]

### DeepSeek 的高峰与低谷时段 API 定价是如何运作的？

DeepSeek 在低谷时段（北京时间 / UTC+8 的 00:00 至 08:00，对应 UTC 16:00 至 00:00）对缓存未命中的输入 Token 与输出 Token 提供 50% 的价格折扣。例如，deepseek-flash 的输入（<=256K 上下文，缓存未命中）从高峰时段的 $0.30/M Token 降至低谷时段的 $0.15/M Token，输出则从 $1.50/M 降至 $0.75/M。 [1]

### DeepSeek 的 API 速率限制与 user_id 并发控制是如何运作的？

DeepSeek 对在途并发请求设置了上限：deepseek-flash 为 2,500 个并发请求，deepseek-v4-pro 为 500 个并发请求。如果开发者在 user_id 字段中传入终端用户标识符，DeepSeek 会将该特定 user_id 限制为 10 个并发请求，从而避免单个终端用户耗尽开发者的全账户配额。 [2]

### DeepSeek-V3 与 DeepSeek-R1 凭借哪些架构创新受到关注？

DeepSeek-V3（总参数量 671B，每 Token 激活 37B）结合了用于低内存 KV 缓存的多头潜在注意力（MLA）、无辅助损失的 DeepSeekMoE 路由器以及 FP8 训练。随后的 DeepSeek-R1 采用大规模纯强化学习（GRPO）与多阶段冷启动训练，在开源 MIT 许可证下实现了前沿级推理性能。 [4][5]

### 发送至 DeepSeek 托管网页应用与 API 的数据存储在哪里？

根据 DeepSeek 的《隐私政策》，传输至 DeepSeek 托管消费者服务与平台服务的数据存储于中华人民共和国境内的服务器，并由杭州深度求索人工智能有限公司管理。需要本地数据驻留的机构可以自托管 DeepSeek 的开放权重模型。 [4][7]

## 可引用的句子

- DeepSeek 的生产 API 端点 deepseek-flash（DeepSeek-V4.1-Flash-1017）与 deepseek-v4-pro（DeepSeek-V4-Pro-0813）均支持 1M Token 上下文窗口及最高 384K 输出 Token。 [1][3]
- DeepSeek 在 00:00 至 08:00 UTC+8（16:00-00:00 UTC）期间，为 deepseek-flash 与 deepseek-v4-pro 的缓存未命中输入及输出提供 50% 的低谷定价折扣。 [1]
- DeepSeek 将 API 并发上限设定为 deepseek-flash 2,500 个在途请求、deepseek-v4-pro 500 个在途请求，并支持通过 user_id 参数为单个终端用户设置 10 个并发请求的可选上限。 [2]
- 2026 年 11 月 18 日，DeepSeek 在其对话补全 API 中启用了内置服务器端联网搜索与网页抓取功能，免收额外搜索查询费用。 [1][3]
- DeepSeek-V3 是一款总参数量 671B、每 Token 激活 37B 参数、基于 14.8T Token 训练的混合专家模型；DeepSeek-R1 则于 2025 年 1 月在 MIT 许可证下发布。 [4][5]

## 时间线

- 2024-05: DeepSeek 发布 DeepSeek-V2 技术报告，引入多头潜在注意力（MLA）及 236B/21B MoE 架构。 [6]
- 2024-12: DeepSeek 发布 DeepSeek-V3，该模型为 671B 参数（激活 37B）的混合专家模型，采用 FP8 精度在 14.8 万亿 Token 上完成预训练。 [5]
- 2025-01: DeepSeek 在开源 MIT 许可证下发布 DeepSeek-R1、DeepSeek-R1-Zero 及 6 款蒸馏推理模型。 [4]
- 2026-08-19: DeepSeek 在其 API 平台上线 DeepSeek-V4-Pro-0813（deepseek-v4-pro），支持 1M 上下文以及文本、图像与音频多模态输入。 [1][3]
- 2026-10-20: DeepSeek 部署 DeepSeek-V4.1-Flash-1017，作为高吞吐 deepseek-flash 端点的底层模型。 [1][3]
- 2026-11-18: DeepSeek 在其对话补全 API 中启用内置服务器端联网搜索与网页抓取功能，且不收取额外搜索费用。 [1][3]

## 来源

1. DeepSeek API Models & Pricing (deepseek-flash, deepseek-v4-pro, Search, Fetch, OCR, Speech). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/pricing (访问于 2026-11-23; tier 3: official site)
2. DeepSeek API Rate Limits and Concurrency Controls (user_id Isolation). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/rate_limit (访问于 2026-11-23; tier 3: official site)
3. DeepSeek API Change Log and Release Notes (2025-2026). DeepSeek Platform Documentation. 发布于 2026-11-18. https://api-docs.deepseek.com/updates (访问于 2026-11-23; tier 3: official site)
4. DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning (arXiv:2501.12948). DeepSeek-AI / arXiv. 发布于 2025-01-22. https://arxiv.org/abs/2501.12948 (访问于 2026-11-23; tier 2: academic or news)
5. DeepSeek-V3 Technical Report (arXiv:2412.19437). DeepSeek-AI / arXiv. 发布于 2024-12-27. https://arxiv.org/abs/2412.19437 (访问于 2026-11-23; tier 2: academic or news)
6. DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model (arXiv:2405.04434). DeepSeek-AI / arXiv. 发布于 2024-05-07. https://arxiv.org/abs/2405.04434 (访问于 2026-11-23; tier 2: academic or news)
7. DeepSeek Privacy Policy. Hangzhou DeepSeek Artificial Intelligence Co., Ltd.. https://cdn.deepseek.com/policies/en-US/deepseek-privacy-policy.html (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "DeepSeek." 版本 9ee56a50, 2026-11-23. https://mimirwiki.com/zh/wiki/deepseek
