---
title: "DeepSeek"
subtitle: "开发 DeepSeek-V4、DeepSeek-R1 与 DeepSeek-V3 基础模型的中国人工智能研究实验室"
canonical_url: https://mimirwiki.com/zh/wiki/deepseek
language: zh
page_class: entity
revision_sha256: 8decd9b114b2d2a573529edac49bd0ea0b67180fe1d29e4f41f278287ff9651f
date_modified: 2026-11-25
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
  es: https://mimirwiki.com/es/wiki/deepseek
---

# DeepSeek

> 截至 2026 年 11 月，DeepSeek 的 API 列出两个模型，上下文长度均为 1M，最大输出均为 384K：deepseek-flash（DeepSeek-V4.1-Flash-1017）与 deepseek-v4-pro（DeepSeek-V4-Pro-0813）。低谷时段价格为高峰时段的一半，另单独提供 Search、Fetch、OCR 与语音 API。自 2026 年 11 月 18 日 12:00（北京时间）起，调用模型时触发的服务器端搜索与网页抓取工具调用不再计费。此前的模型包括 DeepSeek-V3（总参数 671B，激活参数 37B）与推理模型 DeepSeek-R1。

DeepSeek 是一家中国人工智能公司，其服务由注册地址位于中国的 Hangzhou DeepSeek Artificial Intelligence Co., Ltd. 提供。该公司研发基于多头潜在注意力（Multi-head Latent Attention，MLA）与 DeepSeekMoE 架构的大语言模型，包括 DeepSeek-V2、DeepSeek-V3、强化学习推理模型 DeepSeek-R1，以及通过 API 提供的 DeepSeek-V4 系列。

**别名:** 杭州深度求索人工智能有限公司, 深度求索, Hangzhou DeepSeek Artificial Intelligence Co., Ltd.

## 关键事实

- **运营实体:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. [7]
- **当前生产模型:** deepseek-flash（DeepSeek-V4.1-Flash-1017）与 deepseek-v4-pro（DeepSeek-V4-Pro-0813） (截至 2026-11-25) [1]
- **上下文与最大输出:** 1M Token 上下文窗口；最高 384K 最大输出 Token (截至 2026-11-25) [1]
- **开放权重推理里程碑:** DeepSeek-R1（MIT 许可证，2025 年 1 月）与 DeepSeek-V3（671B/37B MoE，2024 年 12 月） [4]

## 事实摘要

- **官方名称:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. [7]
- **注册地址:** 中国 [7]
- **核心架构:** 多头潜在注意力（MLA）、DeepSeekMoE、多 Token 预测（MTP） [5]
- **旗舰 API 模型（2026 年 11 月）:** DeepSeek-V4.1-Flash-1017（deepseek-flash）、DeepSeek-V4-Pro-0813（deepseek-v4-pro） [1]
- **API 上下文与输出:** 上下文长度 1M / 最大输出 384K [1]
- **API 并发限制:** 2,500 并发请求（deepseek-flash）；500 并发请求（deepseek-v4-pro） [2]
- **多模态与工具 API:** Search API、Fetch API、文件解析与 OCR API、语音识别（ASR）、语音合成（TTS） [1]
- **开源许可证（R1）:** MIT 许可证（DeepSeek-R1 及蒸馏模型的权重与代码） [4]

## DeepSeek 公司概况与架构基础

DeepSeek 的服务由 Hangzhou DeepSeek Artificial Intelligence Co., Ltd. 提供。[7] 该公司发布了关于模型架构的技术报告，并推出了混合专家（Mixture-of-Experts，MoE）模型与推理模型。[4][5][6]

DeepSeek 的模型采用两种架构，它们在 **DeepSeek-V2**（2024 年 5 月，总参数 236B，每个 Token 激活 21B）中提出，并在 **DeepSeek-V3**（2024 年 12 月，总参数 671B，每个 Token 激活 37B）中沿用。[5][6] - **多头潜在注意力（MLA）**：将键值（KV）缓存压缩为潜在向量，使推理更高效。[5][6] - **DeepSeekMoE**：采用路由专家与共享专家的稀疏计算结构。DeepSeek-V3 在此基础上加入了无辅助损失的负载均衡策略和多 Token 预测（MTP）训练目标。[5][6] DeepSeek-V3 采用 FP8 混合精度训练，在 14.8 万亿 Token 上完成预训练；技术报告称完整训练需要 278.8 万 H800 GPU 小时。[5]

## DeepSeek-R1 与面向推理的强化学习

2025 年 1 月 22 日提交至 arXiv 的 DeepSeek-R1 论文介绍了 **DeepSeek-R1** 与 **DeepSeek-R1-Zero**。论文报告称，不依赖人工标注的推理轨迹，仅通过纯强化学习（RL）即可激发大语言模型的推理能力，训练过程中出现了自我反思与验证等行为。[4]

`DeepSeek-R1-Zero` 在强化学习之前不经过监督微调阶段，使用组相对策略优化（GRPO）训练。由于该模型存在可读性差和语言混杂的问题，`DeepSeek-R1` 采用了结合冷启动思维链数据、拒绝采样、强化学习与监督微调的多阶段训练。[4] 论文报告称，其在数学任务上与 OpenAI-o1-1217 表现相当，而在偏工程的编码任务上 OpenAI-o1-1217 优于 DeepSeek-R1。[4] DeepSeek 还公开了 6 个基于 Qwen 与 Llama 模型的蒸馏模型，参数规模从 1.5B 到 70B。[4]

## DeepSeek-V4 系列、定价与开发者平台（2026 年）

DeepSeek 的 API（`api.deepseek.com`）于 2026 年 4 月 24 日加入 DeepSeek-V4-Pro 与 DeepSeek-V4-Flash。[3] 截至 2026 年 11 月，定价页面列出两个模型，**上下文长度均为 1M**，**最大输出均为 384K**。[1]

| 模型名称 | 模型版本 | 输入，缓存命中（高峰 / 低谷） | 输入，缓存未命中（高峰 / 低谷） | 输出（高峰 / 低谷） | 并发限制 |
| --- | --- | --- | --- | --- | --- |
| `deepseek-flash` | `DeepSeek-V4.1-Flash-1017` | $0.006 / $0.003 | $0.30 / $0.15 | $1.20 / $0.60 | 2,500 |
| `deepseek-v4-pro` | `DeepSeek-V4-Pro-0813` | $0.044 / $0.022 | $1.32 / $0.66 | $3.96 / $1.98 | 500 |

价格按每 100 万 Token 计。[1][2] 低谷时段价格为高峰时段的一半。高峰时段为周一至周五的 01:00-04:00 与 06:00-10:00（UTC），中国法定节假日除外。[1] 两个模型均支持思考模式与非思考模式、JSON 输出、工具调用、Responses API 和 Anthropic 格式的 API。视觉能力由 `deepseek-flash` 支持，`deepseek-v4-pro` 不支持。[1] 旧模型名称 `deepseek-v4-flash` 与 `deepseek-v4-flash-vision-exp` 的请求由 DeepSeek-V4.1-Flash-1017 处理。[1]

更新日志显示，DeepSeek-V4-Pro 正式版（GA）于 2026 年 8 月 13 日上线，DeepSeek-V4.1-Flash 于 2026 年 9 月 10 日发布，并于 2026 年 10 月 17 日升级为 DeepSeek-V4.1-Flash-1017。[3]

## DeepSeek 内置联网搜索、实用工具 API 与速率治理

2026 年 11 月 13 日，DeepSeek 在 `deepseek-flash` 模型的 Messages、Responses 与 Chat Completions API 中向开发者开放了联网搜索、文件输入、URL 读取与模型安全功能，并将 Search 与 Fetch、OCR、ASR、TTS 作为独立 API 提供。[3] 定价页面列出的价格如下。[1] - **Search API（文本）**：每 1,000 次成功请求 $0.75。[1] - **Fetch API**：每 1,000 次成功请求 $0.75。[1] - **文件解析与 OCR API**：每 1,000 页 $0.225。[1] - **语音识别（ASR）**：每小时音频标价 $0.116，限时价格 $0.058。[1] - **语音合成（TTS）**：每 1 万字符标价 $0.45，限时价格 $0.225。[1]

自 2026 年 11 月 18 日 12:00（北京时间，UTC+8）起，调用模型时触发的服务器端搜索与网页抓取工具调用不再计费。返回的结果会加入模型上下文，并按模型 Token 用量计费。[1]

并发限制按账户计算：`deepseek-flash` 为 2,500，`deepseek-v4-pro` 为 500。超出限制的请求会收到 HTTP 429 错误码。[2] 开发者可以传入 `user_id` 参数，DeepSeek 将其用于内容安全隔离、KVCache 隔离与调度隔离。对普通 API 用户，所有 `user_id` 合并计算并发限制。对已提高并发额度的账户，每个 `user_id` 也分别适用 `deepseek-flash` 2,500、`deepseek-v4-pro` 500 的限制。[2]

## DeepSeek 数据治理与隐私政策

根据 DeepSeek 隐私政策（最近更新于 2026 年 2 月 10 日），服务由注册地址位于中国的 Hangzhou DeepSeek Artificial Intelligence Co., Ltd. 提供并控制。[7] 政策称，DeepSeek 在**中华人民共和国**收集、处理和存储个人数据。[7] 政策还列出了拒绝将个人数据用于训练模型或优化技术的权利。[7] 开发者使用 DeepSeek 开放平台开发的应用，其终端用户的个人数据不适用该政策；政策说明，此时运营应用的开发者是个人数据处理的控制者。[7] DeepSeek 还公开了 DeepSeek-R1 的蒸馏模型。[4]

## 常见问题

### 截至 2026 年 11 月，DeepSeek 的主要 API 模型有哪些？

DeepSeek 的 API 列出两个模型：deepseek-flash（模型版本 DeepSeek-V4.1-Flash-1017）与 deepseek-v4-pro（模型版本 DeepSeek-V4-Pro-0813）。两者的上下文长度均为 1M，最大输出均为 384K。 [1][3]

### DeepSeek 的高峰与低谷时段 API 定价是如何运作的？

低谷时段价格为高峰时段的一半。高峰时段为周一至周五的 01:00-04:00 与 06:00-10:00（UTC），中国法定节假日除外，其余时间均为低谷时段。例如，deepseek-flash 的缓存未命中输入在高峰时段为每 100 万 Token $0.30，低谷时段为 $0.15；输出在高峰时段为 $1.20，低谷时段为 $0.60。 [1]

### DeepSeek 的 API 速率限制与 user_id 并发控制是如何运作的？

并发限制按账户计算：deepseek-flash 为 2,500，deepseek-v4-pro 为 500。超出限制的请求会收到 HTTP 429 错误码。对普通 API 用户，所有 user_id 合并计算并发限制。对已提高并发额度的账户，每个 user_id 也分别适用 deepseek-flash 2,500、deepseek-v4-pro 500 的限制。 [2]

### DeepSeek-V3 与 DeepSeek-R1 凭借哪些架构创新受到关注？

DeepSeek-V3（总参数量 671B，每 Token 激活 37B）结合了用于低内存 KV 缓存的多头潜在注意力（MLA）、无辅助损失的 DeepSeekMoE 路由器以及 FP8 训练。随后的 DeepSeek-R1 采用大规模纯强化学习（GRPO）与多阶段冷启动训练，在开源 MIT 许可证下实现了前沿级推理性能。 [4][5]

### 发送至 DeepSeek 托管网页应用与 API 的数据存储在哪里？

DeepSeek 隐私政策称，其在中华人民共和国收集、处理和存储个人数据，服务由 Hangzhou DeepSeek Artificial Intelligence Co., Ltd. 提供并控制。开发者使用 DeepSeek 开放平台开发的应用，其终端用户不适用该政策。 [4][7]

## 可引用的句子

- DeepSeek 的生产 API 端点 deepseek-flash（DeepSeek-V4.1-Flash-1017）与 deepseek-v4-pro（DeepSeek-V4-Pro-0813）均支持 1M Token 上下文窗口及最高 384K 输出 Token。 [1][3]
- DeepSeek API 的低谷时段价格为高峰时段的一半；高峰时段为周一至周五的 01:00-04:00 与 06:00-10:00（UTC），中国法定节假日除外。 [1]
- DeepSeek API 的账户级并发限制为 deepseek-flash 2,500、deepseek-v4-pro 500；对已提高额度的账户，每个 user_id 也适用相同的限制。 [2]
- 自 2026 年 11 月 18 日 12:00（北京时间）起，调用 DeepSeek 模型时触发的服务器端搜索与网页抓取工具调用不再计费，返回的结果按模型 Token 用量计费。 [1]
- DeepSeek-V3 是一款总参数量 671B、每 Token 激活 37B 参数、基于 14.8T Token 训练的混合专家模型；DeepSeek-R1 则于 2025 年 1 月在 MIT 许可证下发布。 [4][5]

## 时间线

- 2024-05: DeepSeek 发布 DeepSeek-V2 技术报告，引入多头潜在注意力（MLA）及 236B/21B MoE 架构。 [6]
- 2024-12: DeepSeek 发布 DeepSeek-V3，该模型为 671B 参数（激活 37B）的混合专家模型，采用 FP8 精度在 14.8 万亿 Token 上完成预训练。 [5]
- 2025-01: DeepSeek 在开源 MIT 许可证下发布 DeepSeek-R1、DeepSeek-R1-Zero 及 6 款蒸馏推理模型。 [4]
- 2026-08-13: DeepSeek-V4-Pro 正式版（GA）在 App、网页端与 API 上线（模型名称 deepseek-v4-pro）。 [1][3]
- 2026-10-17: DeepSeek V4.1 Flash 升级为 DeepSeek-V4.1-Flash-1017（模型名称 deepseek-flash）。 [1][3]
- 2026-11-18: 自北京时间 12:00 起，调用模型时触发的服务器端搜索与网页抓取工具调用不再计费。 [1]

## 来源

1. DeepSeek API Models & Pricing (deepseek-flash, deepseek-v4-pro, Search, Fetch, OCR, Speech). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/pricing (访问于 2026-11-25; tier 3: official site)
2. DeepSeek API Rate Limits and Concurrency Controls (user_id Isolation). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/rate_limit (访问于 2026-11-25; tier 3: official site)
3. DeepSeek API Change Log and Release Notes (2025-2026). DeepSeek Platform Documentation. 发布于 2026-11-13. https://api-docs.deepseek.com/updates (访问于 2026-11-25; tier 3: official site)
4. DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning (arXiv:2501.12948). DeepSeek-AI / arXiv. 发布于 2025-01-22. https://arxiv.org/abs/2501.12948 (访问于 2026-11-23; tier 2: academic or news)
5. DeepSeek-V3 Technical Report (arXiv:2412.19437). DeepSeek-AI / arXiv. 发布于 2024-12-27. https://arxiv.org/abs/2412.19437 (访问于 2026-11-23; tier 2: academic or news)
6. DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model (arXiv:2405.04434). DeepSeek-AI / arXiv. 发布于 2024-05-07. https://arxiv.org/abs/2405.04434 (访问于 2026-11-23; tier 2: academic or news)
7. DeepSeek Privacy Policy. Hangzhou DeepSeek Artificial Intelligence Co., Ltd.. https://cdn.deepseek.com/policies/en-US/deepseek-privacy-policy.html (访问于 2026-11-25; tier 3: official site)

## 引用本页

Mimirwiki. "DeepSeek." 版本 8decd9b1, 2026-11-25. https://mimirwiki.com/zh/wiki/deepseek
