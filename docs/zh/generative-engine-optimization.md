---
title: "生成式引擎优化"
subtitle: "用于提升网页内容在生成式 AI 搜索回答中可见性与引用率的方法和评估指标"
canonical_url: https://mimirwiki.com/zh/wiki/generative-engine-optimization
language: zh
page_class: concept
revision_sha256: cd93181fae12b3ef5afb8020e50415546f6fd09cb378ac8a62d2864ff53da5bc
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/zh/wiki/generative-engine-optimization.md
  txt: https://mimirwiki.com/zh/wiki/generative-engine-optimization.txt
  json: https://mimirwiki.com/zh/wiki/generative-engine-optimization.json
  jsonld: https://mimirwiki.com/zh/wiki/generative-engine-optimization.jsonld
translations:
  en: https://mimirwiki.com/wiki/generative-engine-optimization
  ko: https://mimirwiki.com/ko/wiki/generative-engine-optimization
  ja: https://mimirwiki.com/ja/wiki/generative-engine-optimization
---

# 生成式引擎优化

> 生成式引擎优化（GEO）是一套内容与结构方法，旨在提升网页来源在 AI 搜索系统所生成回答中的可见性和引用率。GEO 由 Aggarwal 等人于 2023 年 11 月连同 GEO-bench 基准一起提出，作用于多阶段检索与生成流水线，其可测量的效果取决于文档是否已被检索以及所属领域。

生成式引擎优化（Generative Engine Optimization，GEO）是一种网页内容优化范式，旨在提升来源文档在生成式搜索引擎综合回答中的出现概率、引用可能性和显著性。Pranjal Aggarwal、Vishvak Murahari、Tanmay Rajpurohit、Ashwin Kalyan、Karthik Narasimhan 和 Ameet Deshpande 于 2023 年 11 月 16 日在 arXiv:2311.09735 中正式提出该术语，该论文被第 30 届 ACM SIGKDD 知识发现与数据挖掘大会（KDD 2024）录用。传统搜索引擎返回排序后的链接列表，而生成式引擎则通过搜索后端检索网页文档，并利用大语言模型生成带有行内引文、以检索内容为依据的自然语言回答。2026 年 7 月的一篇批判性综述将 GEO 描述为一个跨越抓取与索引、检索、重排序、引用与保真度的随机、部分可观测流水线；同时，Google 搜索中心文档截至 2026 年 11 月 23 日声明，现有的搜索技术要求和 SEO 基本原则直接适用于其 AI 功能，无需单独优化。

**别名:** GEO, Generative Engine Optimization, 答案引擎优化, 对话式 SEO

## 关键事实

- **首次提出:** 2023-11-16（arXiv:2311.09735；被 KDD 2024 录用） [1]
- **原始作者:** Aggarwal、Murahari、Rajpurohit、Kalyan、Narasimhan 和 Deshpande [1]
- **初始基准:** GEO-bench（跨多个领域的 10,000 条查询） [2]
- **初始基准提升幅度:** 基准测试中可见性最高提升 40%；Perplexity.ai 上最高提升 37% (截至 2024-06-28) [2]
- **Google 搜索要求:** 除 Google 搜索技术要求外，无额外技术要求或特殊优化 (截至 2026-11-23) [7]

## 事实摘要

- **类型:** 信息检索与网页内容优化范式 [1]
- **缩写:** GEO [1]
- **首次提出:** 2023-11-16（arXiv:2311.09735 v1） [1]
- **会议发表:** 第 30 届 ACM SIGKDD 知识发现与数据挖掘大会（KDD '24），2024 年 8 月 25 日至 29 日 [2]
- **原始作者:** Pranjal Aggarwal、Vishvak Murahari、Tanmay Rajpurohit、Ashwin Kalyan、Karthik Narasimhan、Ameet Deshpande [1]
- **作者所属机构:** 印度理工学院德里分校、普林斯顿大学、独立研究人员 [2]
- **初始基准:** GEO-bench（10,000 条多领域用户查询） [2]
- **综述文献规模:** 2023 年 11 月至 2026 年 7 月间的 45 项研究（Martinez，2026） (截至 2026-07-15) [5]
- **结构优化结果:** 六个引擎平均引用率提升 17.3%，主观质量提升 18.5%（GEO-SFE） (截至 2026-03-31) [4]
- **Google 搜索指南:** 标准 SEO 基本原则和摘要资格同样适用于 AI 概览和 AI 模式 (截至 2026-11-23) [7]

## 什么是生成式引擎优化

生成式引擎优化（Generative Engine Optimization，GEO）是一套用于改善网页内容在生成式搜索引擎综合回答中的呈现方式和来源归属的框架。[1][2] Pranjal Aggarwal、Vishvak Murahari、Tanmay Rajpurohit、Ashwin Kalyan、Karthik Narasimhan 和 Ameet Deshpande 于 2023 年 11 月 16 日在预印本 `arXiv:2311.09735` 第 1 版中提出了这一术语，于 2024 年 6 月 28 日发布修订版 v3，并将论文发表于 2024 年 8 月 25 日至 29 日在巴塞罗那举行的第 30 届 ACM SIGKDD 知识发现与数据挖掘大会（KDD '24）论文集。[1][2] 作者隶属于印度理工学院德里分校、普林斯顿大学以及西雅图的独立研究机构或个人身份。[2]

该论文将生成式引擎（GE）形式化为结合搜索引擎后端与多个大语言模型（LLM）的搜索系统，并列举 BingChat、Google 的 SGE 和 [Perplexity](https://mimirwiki.com/zh/wiki/perplexity)（Perplexity.ai）作为实际部署示例。[2] 在形式化定义中，生成式引擎通过模块化步骤将用户查询及可选的用户个性化上下文映射为自然语言回答：查询改写模型将输入查询扩展为子查询，搜索引擎检索排序后的网页来源，摘要模型对每个来源进行压缩，回答生成模型则撰写嵌入行内引文的结构化答案。[2] 行内归因为用户提供了核查论断的机制并有助于抑制 LLM 幻觉，其效果通过引文召回率（陈述是否得到相关引文支持）和引文精确率（所附引文是否确实支持对应陈述）加以评估。[2]

生成式引擎优化回应了网站所有者和内容发布者面临的结构性关切。[1][2] 直接综合生成的回答降低了用户点击进入来源网站的必要性，从而可能减少自然引荐流量，而专有的生成流水线又限制了创作者了解页面如何被摄取和引用的透明度。[2] Martinez 2026 年的综述使用答案引擎优化（answer engine optimization）、对话式 SEO（conversational SEO）、AI 搜索可见性（AI search visibility）和引用吸收（citation absorption）等检索词查找文献。[6]

## 生成式引擎优化框架、指标与 GEO-bench

生成式引擎优化（GEO）最初由 Aggarwal 等人形式化为一种黑盒优化框架：以原始网页作为输入，输出经过呈现方式、文本风格和内容调整的修订版本，以提高在专有生成式引擎中的可见性。[1][2] 在这一框架下，内容发布者力图最大化其引文在生成回答中的可见性或曝光函数，而生成式引擎则通过不透明的内部函数在引文曝光度与查询相关性之间取得平衡。[2]

生成式引擎中的可见性不同于传统搜索结果中网页以线性列表排列时的平均排名。[2] 生成式回答以结构化文本呈现，在段落长度、位置和风格各异的叙述中穿插多条行内引文。[2] 为从上述维度评估来源归属，GEO 框架定义了可定制的可见性指标，同时从客观与主观两个视角衡量相关性及引文影响力。[2]

为系统测试 GEO 策略，Aggarwal 等人发布了 GEO-bench 基准，包含来自不同领域并配有相关网页来源的 10,000 条用户查询。[1][2] 在 GEO-bench 的综合评估中，作者报告 GEO 方法将来源可见性最高提升了 40%。[1][2] 添加引文、相关来源引语和统计数据在多种查询中实现了超过 40% 的可见性增长，而不同策略的有效性因领域而异。[1][2] 作者还在实际运行的生成式引擎 [Perplexity](https://mimirwiki.com/zh/wiki/perplexity)（Perplexity.ai）上测试了这些方法，报告可见性最高提升了 37%。[2]

## 2025 年与 2026 年生成式引擎优化实证研究

生成式引擎优化研究在 2025 年和 2026 年显著拓展，覆盖了商业 AI 搜索平台、文档结构以及方法论审计。[3][4][5] 2025 年 9 月至 2026 年 7 月间发布的三篇 arXiv 论文体现了研究重心从单一基准文本改写向多引擎对比、结构工程与批判性综合的演变。[3][4][5]

| 研究 | 日期 | 范围 | 主要报告发现 |
| --- | --- | --- | --- |
| Aggarwal 等人（arXiv:2311.09735 / KDD '24） | 2023-11-16（v3: 2024-06-28） | 10,000 条查询的 GEO-bench 与 Perplexity.ai | 基准测试中可见性最高提升 40%；添加引文、引语和统计数据提升超过 40%；Perplexity.ai 上最高提升 37%。[1][2] |
| Chen 等人（arXiv:2509.08919） | 2025-09-10 | 跨垂直领域、语言和改写查询的 ChatGPT、Perplexity、Gemini 与 Google 搜索对比 | 相对于品牌自有和社交来源，对第三方赢得媒体存在系统性偏好；各引擎在多样性、时效性和措辞敏感度上差异显著。[3] |
| Yu 等人（arXiv:2603.29979） | 2026-03-31 | 覆盖六个生成式引擎的结构特征工程（GEO-SFE） | 宏观、中观与微观结构优化在保持语义完整性的同时，将引用率提高 17.3%，主观质量提高 18.5%。[4] |
| Martinez（arXiv:2607.14035） | 2026-07-15 | 对 45 项研究（2023 年 11 月至 2026 年 7 月）的批判性范围综述 | 将 GEO 建模为多阶段随机流水线；发现证据集中于已检索来源，尚未证实对自然可发现性或流量具有稳定的跨平台因果效应。[5][6] |

2025 年 9 月，Mahe Chen、Xiaoxuan Wang、Kaiwen Chen 和 Nick Koudas 跨多个垂直领域、语言和查询改写条件，将 [ChatGPT](https://mimirwiki.com/zh/wiki/chatgpt)、[Perplexity](https://mimirwiki.com/zh/wiki/perplexity) 和 [Google Gemini](https://mimirwiki.com/zh/wiki/google-gemini) 与传统 Google 网页搜索进行了对比。[3] 受控实验表明，与 Google 更为均衡的来源构成相反，AI 搜索引擎对赢得媒体（权威第三方来源）相对于品牌自有内容和社交内容表现出系统性偏好。[3] 该研究还记录了各 AI 搜索服务在域名多样性、时效性、跨语言稳定性及措辞敏感度上的显著差异，并据此提出四项实务重点：面向机器扫描与论据支撑组织内容结构、建设赢得媒体影响力、按引擎和语言定制策略，以及帮助小众站点应对大品牌偏见。[3]

2026 年 3 月，Junwei Yu、Mufeng Yang、Yepeng Ding 和 Hiroyuki Sato 提出了结构特征工程框架 GEO-SFE，在语义文本编辑之外系统研究文档布局的作用。[4] GEO-SFE 将网页结构分解为三个层级：宏观结构（文档架构）、中观结构（信息分块）和微观结构（视觉强调）。[4] 作者在六个生成式引擎上评估了架构感知策略，报告称在保持语义完整性的前提下，引用率稳定提升 17.3%，主观质量提升 18.5%。[4]

2026 年 7 月，Olivier Martinez 发表了一项批判性范围综述，涵盖 2023 年 11 月 16 日至 2026 年 7 月 14 日间发表或录用的 45 项 GEO 研究，以及一篇于 2023 年 12 月发表在 EMNLP 的早期预印本和相关的检索增强生成评估文献。[5][6] 该综述将 GEO 形式化为跨越搜索触发、抓取与索引、检索、重排序与上下文分配、引用、显著性、事实吸收、保真度以及用户行为的多阶段流水线，并配套提出了区分可发现性、引用、吸收与经济结果的可见性向量。[5]

## 生成式引擎优化与 SEO、RAG、robots.txt 和 llms.txt 的关系

生成式引擎优化与搜索引擎优化（SEO）、检索增强生成（RAG）、抓取程序访问控制以及新兴机器可读发布规范相互交织。[2][5][7][9] 传统 SEO 侧重于提高网页在链接列表中的排名，而 GEO 关注语言模型如何摄取、总结和引用已检索页面。[2] 由于生成式搜索引擎依赖底层搜索索引和检索模型，上游 SEO 机制仍与下游引用结果紧密耦合。[5][7] Martinez 2026 年的综述指出，改善流水线某一阶段的干预可能会损害另一阶段，尤其是仅针对引用进行的窄幅改写可能会削弱上游检索表现。[5][6]

抓取程序访问规则决定了网页内容能否进入生成式搜索索引。[7][9] 依据 [robots.txt](https://mimirwiki.com/zh/wiki/robots-txt) 规范，网站所有者可为搜索索引机器人和抓取程序指定允许的自动化访问方式。[9] Google 搜索中心明确规定，在 `robots.txt` 以及内容分发网络（CDN）或托管层允许抓取，仍是出现在 AI 搜索功能中的基本前提。[7] [OpenAI](https://mimirwiki.com/zh/wiki/openai) 维护着独立的开发者文档来说明其网页抓取程序。[10] 在网络基础设施层面，[Cloudflare](https://mimirwiki.com/zh/wiki/cloudflare) 于 2026 年 7 月 1 日宣布向所有客户提供流量管理选项，将 AI 流量控制划分为搜索、智能体和训练三个独立类别。[11]

内容发布者也广泛讨论了 [llms.txt](https://mimirwiki.com/zh/wiki/llms-txt)，这是一项由 Jeremy Howard 于 2024 年 9 月 3 日提出并于 2026 年 8 月 10 日更新至 v2 的网页规范。[9] 该提案定义了一个放置在 `/llms.txt` 或 `/docs/llms.txt` 等子路径下的精选 Markdown 概览文件，并辅以各独立页面的精简 `.md` 版本，这些版本可通过使用 `alternate`（`type="text/markdown"`）和 `describedby` 链接关系的 HTML `<link>` 元素或 HTTP `Link` 标头加以发现。[9] 该提案将 `llms.txt` 与管理抓取权限的 `robots.txt` 区分开来，也将其与列出全部可索引人类可读页面的站点地图（`sitemap.xml`）区分开来，因为站点地图汇总后的内容通常超出 LLM 的上下文窗口容量。[9] 此外，该提案避开了 RFC 8615 定义的源站根路径 `/.well-known/` 前缀，使共享主机上的作者能够发布限定在子路径范围内的文件。[9] 截至 2026 年 8 月，v2 规范指出 `llms.txt` 主要用于推理阶段，Mintlify 和 GitBook 等文档平台已支持自动生成，且 [OpenAI](https://mimirwiki.com/zh/wiki/openai)、[Anthropic](https://mimirwiki.com/zh/wiki/anthropic) 以及 Google 的 Gemini 均已为其开发者文档发布 `llms.txt` 文件；OpenAI 的抓取程序文档页面本身也指向了 `llms.txt` 和 `.md` 页面 URL。[9][10]

## 生成式引擎优化的平台指南

针对生成式引擎优化，Google 搜索中心就 Google 搜索中的 AI 概览（AI Overviews）和 AI 模式（AI Mode）发布了明确的平台指南。[7][8] 截至 2026 年 11 月 23 日，Google 官方文档指出，基础 SEO 实践仍适用于 Google 搜索中的 AI 功能，网站所有者无需满足额外技术要求或进行特殊优化即可出现在 AI 概览或 AI 模式中。[7] 网页若要具备在这两项功能中作为参考链接展示的资格，必须在标准搜索技术要求下被编入索引并符合在 Google 搜索中显示摘要的条件，但满足要求并不保证一定会被抓取、编入索引或展示。[7]

Google 将 AI 概览描述为用于能够在传统搜索之外提供额外价值的查询的摘要功能，并指出该功能在许多情况下不会触发；而 AI 模式对需要进一步探索、推理或复杂比较的查询特别有帮助。[7] 这两项功能在生成回答时均可能采用“查询扇出（query fan-out）”技术，针对子主题和多个数据源并发执行多条相关搜索，从而识别更广泛的参考网页集合。[7] 由于 AI 概览和 AI 模式可能依赖不同的模型与技术，二者展示的回答和参考链接可能会有所不同。[7]

Google 列出了继续适用于 AI 搜索功能的 SEO 基本原则。[7]

- 在 `robots.txt` 以及 CDN 或托管基础设施中允许抓取
- 通过网站内部链接使页面可被发现
- 提供良好的页面体验，并确保重要内容以文本形式呈现
- 在适当情况下以高质量图片和视频辅助文本内容
- 确保结构化数据与页面上的可见文本一致
- 保持 Merchant Center 和商家资料（Business Profile）信息的最新状态

在 Google 搜索中心博客上，Google 于 2025 年 5 月发布了关于内容在 AI 搜索体验中表现的指南，于 2026 年 5 月宣布推出专门面向 Google 搜索生成式 AI 优化的资源，并于 2026 年 6 月在 Search Console 中推出了搜索生成式 AI 效果报告。[8]

## 生成式引擎优化的方法论局限与证据边界

生成式引擎优化面临着 2025 年和 2026 年多项审计研究记录的显著方法论与实证边界。[3][5][6] Olivier Martinez 在其 2026 年 7 月涵盖 45 项研究的批判性综述中指出，商业宣传常将 Aggarwal 等人最高 40% 的可见性提升数据改述为在 ChatGPT 中获得高排名的普遍承诺，尽管该结果实际上是在五篇候选文档已置于模型上下文中的模拟器内测得的相对可见性。[5][6] 纵观受审文献，现有证据表明修改已被检索到的文档能够因果性地改变其在回答中的引用或使用，但没有任何受审技术证明对自然可发现性或流量、转化等下游用户行为具有稳定、长期、跨平台的因果效应。[5][6]

实证结论同样对实验设置和竞争动态高度敏感。[5][6] 在受审研究中，主题相关性和上下文位置是影响引用的最具可复现性的因素，而通用启发式规则在不同领域与模型间的迁移效果较差。[5] 当多个发布者采用相似修改时，多方竞争可能抵消个体优化收益，这有助于解释单方研究与 Puerto 等人（2025）等多方研究之间看似矛盾的结果。[5][6] 对商业生成式引擎的审计还报告称，不同平台间的来源重叠度较低、多次运行间的波动较大、对查询改写敏感，并且持续存在保真度缺口，即来源可能在未支持论断的情况下被引用，或在未附带链接的情况下被转述。[3][5][6]

由于合规的内容改写、对抗性文本序列以及间接提示注入都会修改生成式引擎所读取的文本，Martinez 认为优化与操纵共享同一条技术通道。[6] 在这一分析框架下，区分可接受的 GEO 实践与操纵行为依赖于真实性、语义保持、信息披露以及不存在隐藏指令。[6] Martinez 还指出，2023 年至 2026 年的 GEO 文献混杂了同行评审会议论文、正式录用的待刊文章、研讨会论文和预印本，因此提出了一套可复现的评估协议，纳入重复测量、查询改写、对照条件、人工验证以及多方干扰测试。[5][6]

## 常见问题

### 什么是生成式引擎优化（GEO）？

生成式引擎优化（GEO）是一种黑盒优化框架，通过调整网页内容的呈现方式、文本风格和文档结构，提升网页在生成式搜索引擎所生成回答中的可见性与引用率。Aggarwal 等人于 2023 年 11 月 16 日在 arXiv:2311.09735 中首次提出该术语，该论文随后被 KDD 2024 录用。 [1][2]

### 生成式引擎优化与传统 SEO 有何区别？

传统的搜索引擎优化（SEO）以链接排序列表中的平均排名为目标。生成式引擎优化则面向多阶段检索与生成流水线，关注多文档综合、行内引文位置、显著性以及事实归因。 [2][5]

### 最初的 GEO-bench 研究发现了什么？

在包含 10,000 条查询的 GEO-bench 数据集评估中，Aggarwal 等人报告称各类查询的可见性最高提升 40%，添加引文、引语和统计数据可带来超过 40% 的提升，在 Perplexity.ai 上的提升最高达 37%。Olivier Martinez 于 2026 年 7 月发表的综述指出，这些基准提升是在五篇候选文档已置于上下文中的模拟器中测得的，因此不能证明自然可发现性或持久的流量效果。 [2][5][6]

### 2025 年和 2026 年的学术研究对 GEO 效果有何发现？

Chen 等人 2025 年 9 月的研究发现，ChatGPT、Perplexity 和 Gemini 相对于品牌自有内容和社交内容更偏好第三方赢得媒体，且各引擎在多样性、时效性和措辞敏感度方面差异显著。Yu 等人 2026 年 3 月的研究报告称，结构特征工程在六个引擎上实现了 17.3% 的引用率提升和 18.5% 的主观质量提升；而 Martinez 2026 年 7 月对 45 项研究的综述则指出，主题相关性和上下文位置是最具可复现性的因素。 [3][4][5]

### Google 是否要求采用专门的 GEO 技术才能出现在 AI 概览和 AI 模式中？

不需要。截至 2026 年 11 月 23 日，Google 搜索中心文档表明，凡是已被编入索引并符合 Google 搜索摘要展示资格的网页，无需额外的技术规范或特殊优化即可作为参考链接出现在 AI 概览或 AI 模式中。 [7]

### robots.txt 和 llms.txt 与生成式引擎优化有何关系？

robots.txt 用于设定自动化抓取程序的访问规则，Google 要求在 robots.txt 和托管基础设施中允许抓取以具备 AI 功能展示资格。截至 2026 年 7 月，Cloudflare 也支持网站所有者将搜索、智能体和训练三类 AI 流量控制相互分离；而 llms.txt 则是另一项拟议的 Markdown 概览文件规范，旨在供语言模型和智能体在推理时按需调用。 [7][9][11]

## 可引用的句子

- Pranjal Aggarwal、Vishvak Murahari、Tanmay Rajpurohit、Ashwin Kalyan、Karthik Narasimhan 和 Ameet Deshpande 于 2023 年 11 月 16 日在 arXiv:2311.09735 中首次提出生成式引擎优化这一术语，该论文被 KDD 2024 录用。 [1][2]
- GEO-bench 基准由来自不同领域和网页来源的 10,000 条查询组成，用于评估生成式引擎可见性优化方法。 [2]
- Aggarwal 等人报告称，在基准评估中各类查询的可见性最高提升了 40%，在 Perplexity.ai 上最高提升了 37%，其中添加引文、相关来源引语和统计数据带来了超过 40% 的提升。 [2]
- Chen 等人于 2025 年 9 月发表的实证研究发现，与 Google 网页搜索相比，ChatGPT、Perplexity 和 Gemini 在来源选择上相对于品牌自有内容和社交内容，对第三方赢得媒体表现出系统性偏好。 [3]
- 结构特征工程框架 GEO-SFE 于 2026 年 3 月报告称，在六个生成式引擎上实现了 17.3% 的引用率提升和 18.5% 的主观质量提升。 [4]
- Olivier Martinez 于 2026 年 7 月发表的批判性综述审查了 45 项研究并得出结论：已被检索到的内容可以对引用或使用产生因果影响，但没有任何受审技术证明在自然可发现性或下游用户行为上具有稳定、长期、跨平台的因果效应。 [5]
- 截至 2026 年 11 月 23 日，Google 搜索中心文档明确表示，凡是已被编入索引并符合 Google 搜索摘要展示资格的网页，在 AI 概览或 AI 模式中展示时无需满足额外技术要求或进行特殊优化。 [7]
- 2026 年 7 月 1 日，Cloudflare 推出了流量管理选项，允许网站所有者分别识别并控制搜索、智能体和训练三类 AI 流量。 [11]

## 时间线

- 2023-11-16: Pranjal Aggarwal、Vishvak Murahari、Tanmay Rajpurohit、Ashwin Kalyan、Karthik Narasimhan 和 Ameet Deshpande 向 arXiv 提交《GEO: Generative Engine Optimization》第 1 版，提出 GEO 术语与 GEO-bench 基准。 [1]
- 2024-06-28: Aggarwal 等人在 KDD 2024 巴塞罗那大会（2024 年 8 月 25 日至 29 日）报告前于 arXiv 发布 GEO 论文修订版 v3。 [1][2]
- 2024-09-03: Jeremy Howard 发布 /llms.txt 提案，用于向语言模型和 AI 智能体提供精选的 Markdown 站点概览。 [9]
- 2025-05: Google 搜索中心博客发布关于内容在 Google AI 搜索体验中表现的指南。 [8]
- 2025-09-10: Chen 等人提交针对 ChatGPT、Perplexity、Gemini 与 Google 搜索的对比研究（arXiv:2509.08919），记录了赢得媒体偏好与跨引擎差异。 [3]
- 2026-03-31: Yu 等人提交 GEO-SFE 结构特征工程研究（arXiv:2603.29979），报告在六个生成式引擎上实现了引用率与主观质量提升。 [4]
- 2026-06: 继 2026 年 5 月发布面向 Google 搜索生成式 AI 优化的资源后，Google 搜索中心博客宣布在 Search Console 中推出搜索生成式 AI 效果报告。 [8]
- 2026-07-01: Cloudflare 推出 AI 流量控制功能，允许网站所有者分别识别并管理搜索、智能体和训练流量。 [11]
- 2026-07-15: Olivier Martinez 发表涵盖 2023 年 11 月至 2026 年 7 月间 45 项 GEO 研究的批判性综述（arXiv:2607.14035），提出多阶段流水线模型与可复现评估协议。 [5][6]
- 2026-08-10: Jeremy Howard 将 /llms.txt 提案更新至 v2，v2 说明了将文件放在子路径的做法，以及通过 alternate 和 describedby 链接关系发现文件的方式。 [9]

## 来源

1. [2311.09735] GEO: Generative Engine Optimization. arXiv. 发布于 2023-11-16. https://arxiv.org/abs/2311.09735 (访问于 2026-11-23; tier 2: academic or news)
2. GEO: Generative Engine Optimization. arXiv. 发布于 2024-06-28. https://arxiv.org/html/2311.09735v3 (访问于 2026-11-23; tier 2: academic or news)
3. [2509.08919] Generative Engine Optimization: How to Dominate AI Search. arXiv. 发布于 2025-09-10. https://arxiv.org/abs/2509.08919 (访问于 2026-11-23; tier 2: academic or news)
4. [2603.29979] Structural Feature Engineering for Generative Engine Optimization: How Content Structure Shapes Citation Behavior. arXiv. 发布于 2026-03-31. https://arxiv.org/abs/2603.29979 (访问于 2026-11-23; tier 2: academic or news)
5. [2607.14035] Optimizing Visibility in Generative Engines: A Critical Survey of Generative Engine Optimization (2023-2026). arXiv. 发布于 2026-07-15. https://arxiv.org/abs/2607.14035 (访问于 2026-11-23; tier 2: academic or news)
6. Optimizing Visibility in Generative Engines: A Critical Survey of Generative Engine Optimization (2023–2026). arXiv. 发布于 2026-07-15. https://arxiv.org/html/2607.14035v1 (访问于 2026-11-23; tier 2: academic or news)
7. AI Features and Your Website | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/ai-features (访问于 2026-11-23; tier 3: official site)
8. Top ways to ensure your content performs well in Google's AI experiences on Search | Google Search Central Blog | Google for Developers. Google Search Central Blog. 发布于 2025-05. https://developers.google.com/search/blog/2025/05/succeeding-in-ai-search (访问于 2026-11-23; tier 3: official site)
9. The /llms.txt file, v2 – llms-txt. llmstxt.org. 发布于 2024-09-03. https://llmstxt.org/ (访问于 2026-11-23; tier 3: official site)
10. Overview of OpenAI Crawlers. OpenAI. https://developers.openai.com/api/docs/bots (访问于 2026-11-23; tier 3: official site)
11. Your site, your rules: new AI traffic options for all customers | Cloudflare Blog. The Cloudflare Blog. 发布于 2026-07-01. https://blog.cloudflare.com/content-independence-day-ai-options/ (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "生成式引擎优化." 版本 cd93181f, 2026-11-25. https://mimirwiki.com/zh/wiki/generative-engine-optimization
