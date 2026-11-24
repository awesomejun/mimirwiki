---
title: "Inkling 2 Mini"
subtitle: "Thinking Machines Lab 面向本地笔记本电脑与工作站推理设计的开放权重循环混合专家视觉语言模型"
canonical_url: https://mimirwiki.com/zh/wiki/inkling-2-mini
language: zh
page_class: entity
revision_sha256: 42daab077f93129bc32a4f64f78d855384d02483734a7c8e67e89d6798f949b6
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 6
alternates:
  md: https://mimirwiki.com/zh/wiki/inkling-2-mini.md
  txt: https://mimirwiki.com/zh/wiki/inkling-2-mini.txt
  json: https://mimirwiki.com/zh/wiki/inkling-2-mini.json
  jsonld: https://mimirwiki.com/zh/wiki/inkling-2-mini.jsonld
translations:
  en: https://mimirwiki.com/wiki/inkling-2-mini
  ko: https://mimirwiki.com/ko/wiki/inkling-2-mini
  ja: https://mimirwiki.com/ja/wiki/inkling-2-mini
---

# Inkling 2 Mini

> Inkling 2 Mini（`thinkingmachines/Inkling-2-Mini`）于 2026 年 11 月 20 日基于 Apache 2.0 许可证发布，是一款拥有 26.4B 总参数量和 100 万 token 上下文窗口的循环混合专家视觉语言模型。通过在每个 token 上将中间 12 层循环执行三次（48 次逻辑层访问、3.4B 唯一激活参数、5.4B 有效激活）并原生采用 4 位 NVFP4 与 8 位 MXFP8 精度训练（约 20 GB 占用），它可在消费级笔记本电脑上离线运行，同时在 DeepSWE v1.1 上取得 48.2%、在 SWE-bench Verified 上取得 79.2%、在 Artificial Analysis Intelligence Index v5.0 上取得 20.1 的成绩。

Inkling 2 Mini 是由前 OpenAI 首席技术官米拉·穆拉蒂（Mira Murati）领导的人工智能研究公司 Thinking Machines Lab 于 2026 年 11 月 20 日发布的开放权重视觉语言模型。该模型基于总参数量 264 亿的 24 层循环混合专家（MoE）Transformer 架构，在每个 token 上将中间 12 层连续执行三次，从而仅凭 34 亿唯一激活参数便实现 48 次有效层应用与每 token 54 亿有效权重激活，并在 Apache 2.0 许可证下以约 20 GB 的混合精度（NVFP4/MXFP8）内存占用在本地运行。

**别名:** Inkling 2 Mini, Thinking Machines Lab, 循环 Transformer, 混合专家模型, 开放权重 AI, 本地大语言模型

## 关键事实

- **发布日期与许可证:** 2026 年 11 月 20 日；Apache 2.0（附带可接受使用政策） [1]
- **架构:** 24 层循环 MoE（48 次层访问；从 128 个 SwiGLU 专家中路由 8 个） [2]
- **参数规模:** 总计 26.4B，唯一激活 3.4B，每 token 有效激活 5.4B [1]
- **原生精度与占用:** NVFP4（前 20 层）+ MXFP8（后 4 层）；约 20 GB 检查点（4 位 GGUF 为 17.5 GB） [3]
- **核心基准成绩:** DeepSWE v1.1 48.2%、SWE-bench Verified 79.2%、SWE-bench Pro v2 Hard 77.9%、AAv5 20.1 [1]

## 事实摘要

- **开发方:** Thinking Machines Lab [1]
- **发布日期:** 2026 年 11 月 20 日 [1]
- **模型 ID:** thinkingmachines/Inkling-2-Mini [2]
- **配套研究模型:** thinkingmachines/TML-d24-varloop-research（可变 1-5 次循环遍数） [2]
- **架构:** 循环稀疏混合专家 Transformer（24 物理层 / 48 逻辑层） [2]
- **参数量:** 总计 26.4B / 唯一激活 3.4B / 每 token 有效权重激活 5.4B [1]
- **上下文窗口:** 1,000,000 tokens [5]
- **模态:** 文本与图像输入；文本输出 [5]
- **数值精度:** 原生 NVFP4（第 0-19 层）与 MXFP8（第 20-23 层） [1]
- **内存需求:** 原生检查点约 20 GB（推荐 32 GB RAM/VRAM；4 位 GGUF 需 17-18 GB） [5]
- **官方 API 定价:** 输入 $0.15 / 100 万；输出 $0.50 / 100 万；缓存命中 $0.015 / 100 万（Tinker 平台） [4]
- **许可证:** Apache 2.0（附带模型可接受使用政策） [5]

## Inkling 2 Mini 概述与循环混合专家架构

总部位于旧金山、由前 OpenAI 首席技术官米拉·穆拉蒂（Mira Murati）创立并领导的人工智能研究公司 Thinking Machines Lab 于 2026 年 11 月 20 日发布了 Inkling 2 Mini，这是一款面向本地笔记本电脑、桌面工作站及自主编程智能体的开放权重视觉语言模型。[1][3] Inkling 2 Mini 源自 Thinking Machines 的主线预测缩放阶梯，定位低于更大规模的 Inkling 2 Small 模型，采用 Apache 2.0 许可证（附带模型可接受使用政策），支持在 100 万 token 上下文窗口内处理文本与图像多模态输入。[1][2][5]

Inkling 2 Mini 并非仅依赖冗长的外显思维链（CoT）文本或扩大参数规模，而是引入了循环混合专家（MoE）Transformer 设计。[1][2][3] 其文本解码器存储 24 个物理层，隐藏维度为 2,304（为 Inkling 2 Small 的 4,608 宽度的一半），专家中间宽度为 1,152，每次层访问会将每个 token 路由至 128 个 SwiGLU 专家中的 8 个（Inkling 2 Small 为从 384 个专家中路由 8 个）。[2] 这 24 个物理层被组织为四个 6 层块，在每个 token 上执行 48 次逻辑层访问：[1][2]

- **前导块（第 0-5 层）**：每个 token 执行一次，用于将嵌入向量投影为内部表征。[1][2]
- **循环核心块（第 6-17 层）**：中间的两个 6 层块在共享同一组存储权重的前提下，每个 token 连续执行三遍（`6 + 3 * 12 + 6 = 48` 次层应用）。[1][2] 在覆盖 28 项评估的内部缩放研究中，循环中间 12 层在 27 项任务上优于循环末尾 12 层，在训练第 2,000 步时带来了 1.51 倍至 1.91 倍的算力等效损失收益（在 512K token 智能体轨迹上，非循环基线需要多消耗 140% 的推理算力才能达到同等损失）。[1][3]
- **终末块（第 18-23 层）**：每个 token 执行一次，用于解码精炼后的内部表征。[1][2]

每个 6 层块均由 5 个滑动窗口注意力层（局部窗口为 1,024 tokens）和 1 个全注意力层组成，后者配备动态键与值短卷积、24 个查询头、8 个键值头、可学习相对位置 logits、可学习注意力汇点（attention sink）以及输出门控。[2] 尽管第 6-17 层的三次遍历复用相同的参数权重，但这 48 次访问各自维护独立的 KV 缓存与短卷积状态。[2] 为在迭代之间传递信息，Inkling 2 Mini 实现了注意力残差（基于 Kimi Team 于 2026 年提出的注意力残差公式）：每次进入循环核心均以前导块的输出为起点，而第 2 遍与第 3 遍还会通过可学习查询和四个秩为 64（rank-64）的门控控制器，对前一遍的两个残差块（“跨遍消息”）施加注意力，将前一遍消息混入查询、键、值及 MoE 输入中。[1][2]

总体而言，Inkling 2 Mini 包含 264 亿物理参数，单遍激活 34 亿唯一参数（每个文本 token 激活 31 亿唯一权重），并在三遍循环中实现每 token 54 亿有效权重激活。[1][4][5]

## 专家剪枝、蒸馏修复与原生 NVFP4 训练

为了将具备前沿推理能力的架构压缩至可装入消费级笔记本电脑内存的约 20 GB 占用空间，Thinking Machines 通过训练中期专家剪枝与原生低比特精度训练改造了其主线训练管线：[1][3]

1. **三分之二专家剪枝与蒸馏修复**：从每层拥有 384 个专家的更宽主线检查点出发，Thinking Machines 剪除了三分之二的专家，将其缩减至每层 128 个专家。[1][2][3] 随后，团队使用更大的内部 Inkling 模型对剪枝后的网络蒸馏 1 万亿 tokens 以进行“修复（healing）”，接着开展监督微调（SFT）与 2.2 万亿 tokens 的强化学习（RL）。[3] 2. **原生 NVFP4 与 MXFP8 精度**：为避免训练后量化可能导致的智能体编程精度下降，Thinking Machines 在训练与部署阶段直接将前 20 个物理层原生设为 4 位 NVFP4 精度，并将最后 4 层设为 8 位 MXFP8 精度。[1][3] 由于分发权重与训练时的数值格式完全一致，上游混合精度检查点仅需约 20 GB 内存，且不存在训练后量化损失。[3][5] 3. **可配置数值推理力度（Reasoning Effort）**：该模型的对话模板接受 `reasoning_effort` 参数，既可指定命名档位，也可传入 `0.0` 至 `0.99` 之间的连续浮点数，并以系统消息形式注入提示词：`none`（`0.0`）、`minimal`（`0.1`）、`low`（`0.2`）、`medium`（`0.7`）、`high`（`0.9`，默认值）、`xhigh`（`0.99`）以及 `max`（`0.99`）。[2] 即使设为最低档位，内部推理也不会被完全关闭。[5]

## Inkling 2 Mini 基准性能与能效表现

在对比 100B 参数以下开放权重模型（涵盖阿里巴巴的稠密模型 Qwen3.8-27B、Google DeepMind 的 Gemma 4 31B、Meta 的 Muse Glimmer 以及 NVIDIA 的 124.5B 模型 Nemotron 3.5 Super VL）的 48 项标准化基准测试中，Inkling 2 Mini 在 32 项评估中位列第一。[1][2] 在 Artificial Analysis Intelligence Index v5.0（AAv5）上，Inkling 2 Mini 取得 20.1 分，与稠密模型 Qwen3.8-27B 并列第一，同时激活参数量减少约 5 倍，总计算量（激活参数乘以 token 数）降低 2.8 倍，单任务实际耗时缩短至四分之一（9.0 分钟对比 38.2 分钟），单任务成本降低至六分之一（按 Thinking Machines 官方 Tinker API 输入 $0.15/1M、输出 $0.50/1M、缓存命中 $0.015/1M 费率计算，为 $0.59 对比 $3.53）。[1][3][4]

| 基准测试 | 类别 | Inkling 2 Mini（有效 5.4B / 26.4B） | Qwen3.8-27B（27B 稠密） | Gemma 4 31B（30.7B 稠密） | Muse Glimmer（30B 稠密） | Nemotron 3.5 Super VL（12B / 124.5B） |
| --- | --- | --- | --- | --- | --- | --- |
| AA Intelligence Index v5.0 | 综合智能 | 20.1（并列第 1） | 20.1（并列第 1） | 4.4 | 6.3 | 13.6 |
| Vals Index v2.2 | 综合企业 / 编程 | 46.5% | - | - | - | 29.8% |
| DeepSWE v1.1 | 智能体软件工程 | 48.2% | 42.2% | 0.3% | 4.4% | 24.7% |
| SWE-bench Pro v2 (Hard) | 高难度软件工程（51 项任务） | 77.9% | 73.8% | 14.2% | 44.3% | 44.1% |
| SWE-bench Verified | 纯 Bash 软件工程 | 79.2% | 77.8% | 46.1% | 76.0% | 71.1% |
| FrontierCode v2.0 | 开源 PR 合并 | 15.1% | 14.9% | 0.0% | 1.5% | 6.1% |
| Terminal Bench v4.0 | 终端智能体执行 | 5.6%（并列第 1） | 5.6%（并列第 1） | 0.0% | 0.5% | 0.0% |
| BrowseComp | 智能体网页浏览（含压缩） | 79.0% | 61.6% | 37.0% | 63.9% | 78.9% |
| DeepSearchQA | 深度搜索问答 | 85.3% | 79.7% | 61.7% | 74.6% | 77.7% |
| MCP Atlas Public | Model Context Protocol 工具使用 | 82.7% | 77.3% | 54.2% | 75.5% | 67.7% |
| OmniDocBench v1.6 | 文档视觉理解 | 92.8% | 91.5% | 82.5% | 90.4% | 77.9% |
| LongBench v2 | 长上下文推理 | 66.9% | 52.3% | 52.9% | 33.1% | 62.1% |
| AA-Omniscience v1.1 | 参数事实性 / 非幻觉率 | -8.6 (63.4%) | -6.4 (71.4%) | -48.5 (14.5%) | -32.2 (16.4%) | -2.9 (69.5%) |

在斯坦福大学 Hazy Research Lab 与 Scaling Intelligence Lab 研究人员基于 NVIDIA DGX Spark（128 GB）采用 Intelligence per Watt 方法开展的能效测试中，Inkling 2 Mini（以 MXFP8 精度和 low 推理力度运行）达到 0.703 intelligence per joule，超越了 Qwen3.6-35B-A3B（NVFP4 下为 0.430）、Gemma-4-26B-A4B（NVFP4 下为 0.159）以及 Qwen3.5-27B（INT4 下为 0.036）。[1][3]

由于循环机制仅增加每个 token 的串行推理算力而未扩充存储参数总量，其参数化事实召回能力仍受限于 26.4B 总权重容量：在 AA-Omniscience v1.1 上，Inkling 2 Mini 得分为 -8.6，非幻觉率为 63.4%，在禁用搜索工具时落后于稠密模型。[1][3] 此外，它在多轮对话约束方面亦落后于 Qwen3.8-27B（MultiChallenge 为 50.0%，ComplexConstraints v1.1 为 33.4%），并且在长时间调试会话中可能出现重复推理循环。[1][5]

## 思维链可监控性与可变循环研究

围绕循环 Transformer 的一项核心 AI 安全问题是，在潜在空间内部执行多次递归遍历是否会使模型无需将思考外显为文本即可完成推理，从而降低思维链（CoT）的可监控性。[1][3] 为支持系统性的监督研究，Thinking Machines 同步发布了配套的可变循环研究检查点 `thinkingmachines/TML-d24-varloop-research`，该模型经训练可在中间 12 层执行 1 至 5 遍循环（推理时可通过 `text_config={"loop_num_passes": N}` 配置），并与 National Deep Inference Fabric（NDIF）及 Goodfire 合作开展机制可解释性研究。[1][2][3]

在 Thinking Machines 基于该可变循环模型开展的可监控性实验中：[1][3]

- **潜在无 CoT 时间跨度扩展**：当限制模型输出可见思维链 token 时，模型的有效任务时间跨度从 1 次循环遍数时的 16 秒翻倍以上增至 3 次循环遍数时的 37 秒，且其在串行推理任务上的准确率一直提升至 10 次循环遍数（为训练期最大深度的两倍）。[1][3]
- **CoT 压缩与可读性**：随着循环深度增加，模型可见的思维链文本缩短超过 50%，但人工与自动化监控器均发现保留下来的 CoT 轨迹依然清晰可读且忠实可信。[1][3]
- **蓄意破坏与不当行为评估**：在 LinuxArena 控制基准上，增加递归循环遍数并未导致隐蔽智能体蓄意破坏呈上升趋势。[1][3] 在内部安全评估中，Inkling 2 Mini 的一般不当行为（9.8%）、隐蔽不当行为（8.3%）和破坏性行为（10.2%）发生率均低于 Gemma 4 31B、Muse Glimmer、Qwen3.8-27B 及 Nemotron 3.5 Super VL，同时在 FORTRESS（对抗性）上取得 89.5%，在 StrongREJECT 上取得 97.8%。[1]

## 本地部署、硬件需求与运行时生态

Inkling 2 Mini 发布当日即获得跨云端与本地运行时的同步支持，涵盖 Thinking Machines 的 Tinker 平台、Hugging Face `transformers`（`AutoModelForMultimodalLM`）、`llama.cpp` 与 Llama App、LM Studio、Unsloth Desktop、Apple Silicon 上的 MLX、Ollama、EXO 以及面向数据中心 GPU 的 SGLang，并附带 DSpark 投机解码草稿模型。[1][2][3][5][6] Thinking Machines 演示了该模型在开启飞行模式的 Apple M5 Pro MacBook Pro（48 GB 统一内存）上完全离线运行：它在数分钟内构建出一款可游玩的 3D 飞行模拟器，并同时在“Thinkyville”城镇模拟中驱动 20 名常驻自主 AI 村民。[1][3]

| 量化 / 格式 | 约略文件大小 | 最低 RAM / VRAM | 说明与运行时兼容性 |
| --- | --- | --- | --- |
| 上游混合精度（NVFP4 + MXFP8） | 约 20.0 GB | 推荐 32 GB | 原生训练精度；适用于 32 GB 以上 Apple Silicon Mac 或 32 GB 以上 GPU 显存 |
| 8 位 GGUF（`UD-Q8_K_XL` / `Q8_0`） | 约 24.0 GB | 24 GB | 面向 llama.cpp 与 Unsloth 的无损全精度等效版本 |
| 4 位 GGUF（`UD-Q4_K_XL` / `IQ4_NL`） | 17.5 - 17.6 GB | 17 - 18 GB | 推荐的本地 GGUF 量化版本；需约 18 GB 系统内存 |
| 3 位 / 2 位 / 1 位动态 GGUF | 9.0 - 15.0 GB | 9 - 15 GB | 面向 16 GB 消费级笔记本电脑的 Unsloth Dynamic 3.0 GGUF |
| 视觉投影器（`mmproj-F16.gguf`） | +639 MB | +0.7 GB | 在 GGUF 中启用图像与文档多模态输入所需的附加投影器 |

在 `llama.cpp` 或 Unsloth 中进行本地 GGUF 推理时，推荐采样参数为 `temperature = 1.0`、`top_p = 1.0`、`top_k = 0` 和 `min_p = 0.0`，并需使用支持循环层布局及逐专家 NVFP4 缩放因子的构建版本（如 `ggml-org/Inkling-2-Mini-GGUF` 或 `unsloth/Inkling-2-Mini-GGUF`）。[2][6]

## 常见问题

### Inkling 2 Mini 的循环 Transformer 架构是如何运作的？

Inkling 2 Mini 并非让每个 token 仅通过其 24 个物理层一次，而是将解码器划分为四个 6 层块。第一块（第 0-5 层）执行一次，中间两块（第 6-17 层）复用相同的存储权重循环执行三次，最后一块（第 18-23 层）执行一次。门控注意力残差消息在各次循环迭代间传递中间信息，从而在仅存储 24 层（总参数 264 亿、唯一激活参数 34 亿）的条件下，实现每 token 48 次层应用与 54 亿有效权重激活。 [2]

### 在本地运行 Inkling 2 Mini 需要什么硬件配置？

上游混合精度检查点（原生以 4 位 NVFP4 和 8 位 MXFP8 训练）约为 20 GB，Thinking Machines Lab 建议配备至少 32 GB 统一内存的 Apple Silicon Mac 或 32 GB 显存的 GPU。若在 LM Studio、llama.cpp 或 Unsloth Desktop 中使用 4 位 GGUF 量化版本（如 UD-Q4_K_XL 或 IQ4_NL，约 17.5-17.6 GB），该模型可在配备 16 GB 至 18 GB 内存的系统上运行，而 8 位无损 GGUF 则需要 24 GB 内存。 [5]

### Inkling 2 Mini 与 Qwen3.8-27B 相比表现如何？

在 Artificial Analysis Intelligence Index v5.0 上，Inkling 2 Mini 以 20.1 分与阿里巴巴的稠密模型 Qwen3.8-27B 打平，同时在 DeepSWE v1.1（48.2% 对比 42.2%）、SWE-bench Verified（79.2% 对比 77.8%）和 BrowseComp（79.0% 对比 61.6%）等智能体编程与搜索基准上胜出。由于 Inkling 2 Mini 每个 token 仅激活 5.4B 有效参数（稠密 Qwen 模型为 27B），其计算量减少约 2.8 倍，完成 Intelligence Index 任务的速度快 4 倍（9.0 分钟对比 38.2 分钟），单任务成本降低 6 倍（$0.59 对比 $3.53）。不过，Qwen3.8-27B 在无工具参数事实召回（AA-Omniscience）和多约束对话指令上得分更高。 [4]

### 与 Inkling 2 Mini 一同发布的 TML-d24-varloop-research 是什么模型？

TML-d24-varloop-research 是一款开放权重研究检查点，与 Inkling 2 Mini 共享相同的 24 层 MoE 架构，但经训练可通过 loop_num_passes 配置参数在其中间 12 层接受可变的循环遍数（训练范围为 1 至 5 次，测试可达 10 次）。Thinking Machines Lab 发布该模型旨在帮助安全与可解释性研究人员衡量潜在空间递归循环如何影响思维链长度、可监控性以及推理深度。 [2]

## 可引用的句子

- Thinking Machines Lab 于 2026 年 11 月 20 日基于 Apache 2.0 许可证发布了 Inkling 2 Mini，这是一款总参数量 264 亿、支持 100 万 token 上下文窗口的循环混合专家视觉语言模型。 [1][2][5]
- Inkling 2 Mini 的 24 个物理解码器层通过将第 0-5 层执行一次、以共享权重和跨遍注意力残差消息将第 6-17 层循环执行三次，再将第 18-23 层执行一次，在每个 token 上完成 48 次逻辑层访问，实现 3.4B 唯一激活参数与每 token 5.4B 有效权重激活。 [1][2][5]
- 该模型通过剪除三分之二的专家（每层从 384 个缩减至 128 个）、从更大规模的 Inkling 模型蒸馏 1 万亿修复 tokens 并进行 2.2 万亿 RL tokens 训练，以及将前 20 层原生训练为 NVFP4、后 4 层原生训练为 MXFP8，最终压缩至约 20 GB 占用空间。 [1][2][3]
- 在标准化评估中，Inkling 2 Mini 在 DeepSWE v1.1（48.2%）、SWE-bench Pro v2 Hard（77.9%）、SWE-bench Verified（79.2%）、BrowseComp（79.0%）、DeepSearchQA（85.3%）和 OmniDocBench v1.6（92.8%）上领先所有 100B 参数以下的开放权重模型，并在 Artificial Analysis Intelligence Index v5.0 上以 20.1 分与 Qwen3.8-27B 并列第一。 [1][3][4]
- 在斯坦福大学于 NVIDIA DGX Spark 上开展的 Intelligence per Watt 评估中，Inkling 2 Mini 取得 0.703 intelligence per joule，超越了 Qwen3.6-35B-A3B（0.430）、Gemma-4-26B-A4B（0.159）和 Qwen3.5-27B（0.036）。 [1][3]
- 基于配套可变循环检查点（TML-d24-varloop-research）的实验表明，将循环遍数从 1 次增至 3 次后，模型的无 CoT 推理时间跨度从 16 秒扩展至 37 秒，同时保持了思维链可读性且未出现智能体蓄意破坏增加。 [1][2][3]

## 时间线

- 2018: Dehghani 等人发表 Universal Transformers，奠定了 Thinking Machines Lab 所引用的权重共享递归 Transformer 层基础概念。 [1]
- 2026-11-20: Thinking Machines Lab 基于 Apache 2.0 许可证发布 Inkling 2 Mini 及配套的 TML-d24-varloop-research 检查点，并在 Transformers、llama.cpp、MLX、SGLang、LM Studio 与 Unsloth 上提供首发日支持。 [1]
- 2026-11-21: 独立基准分析确认 Inkling 2 Mini 以 20.1 分位列 Artificial Analysis Intelligence Index v5.0 帕累托前沿。 [3]

## 来源

1. Introducing Inkling 2 Mini - Thinking Machines Lab. Thinking Machines Lab. 发布于 2026-11-20. https://thinkingmachines.ai/news/inkling-2-mini/ (访问于 2026-11-23; tier 3: official site)
2. Welcome Inkling 2 Mini, Cutting-edge Performance for your Local Setup. Hugging Face. 发布于 2026-11-20. https://huggingface.co/blog/inkling2mini (访问于 2026-11-23; tier 3: official site)
3. Thinking Machines wows with Inkling 2 Mini looped transformer model that runs locally on laptops. VentureBeat. 发布于 2026-11-21. https://venturebeat.com/technology/thinking-machines-wows-with-inkling-2-mini-looped-transformer-model-that-runs-locally-on-laptops (访问于 2026-11-23; tier 2: academic or news)
4. Thinking Machines has released Inkling 2 Mini, an open weights looped transformer. Artificial Analysis. 发布于 2026-11-20. https://artificialanalysis.ai/articles/inkling-2-mini (访问于 2026-11-23; tier 2: academic or news)
5. Inkling 2 Mini - LM Studio Model Directory. Element Labs (LM Studio). https://lmstudio.ai/models/inkling-2-mini (访问于 2026-11-23; tier 3: official site)
6. Inkling 2 Mini - Run Locally Guide | Unsloth Documentation. Unsloth. https://unsloth.ai/docs/models/inkling-2-mini (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "Inkling 2 Mini." 版本 42daab07, 2026-11-23. https://mimirwiki.com/zh/wiki/inkling-2-mini
