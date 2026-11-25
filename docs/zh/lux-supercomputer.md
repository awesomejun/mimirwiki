---
title: "Lux 超级计算机"
subtitle: "位于橡树岭国家实验室的 AMD 驱动人工智能与高性能计算超级计算机"
canonical_url: https://mimirwiki.com/zh/wiki/lux-supercomputer
language: zh
page_class: entity
revision_sha256: 6b3904532928a02171543aace67b0cc1bec9c698c13381121fbc805d4eaebf1e
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/zh/wiki/lux-supercomputer.md
  txt: https://mimirwiki.com/zh/wiki/lux-supercomputer.txt
  json: https://mimirwiki.com/zh/wiki/lux-supercomputer.json
  jsonld: https://mimirwiki.com/zh/wiki/lux-supercomputer.jsonld
translations:
  en: https://mimirwiki.com/wiki/lux-supercomputer
  ko: https://mimirwiki.com/ko/wiki/lux-supercomputer
  ja: https://mimirwiki.com/ja/wiki/lux-supercomputer
  es: https://mimirwiki.com/es/wiki/lux-supercomputer
---

# Lux 超级计算机

> Lux 超级计算机是由慧与（HPE）在美国能源部橡树岭国家实验室建造的基于 AMD 芯片的人工智能与高性能计算系统。Lux 于 2026 年 11 月 16 日向科研用户开放，并以 220.79 千万亿次每秒的 High Performance Linpack 成绩首次登上 2026 年 11 月 TOP500 榜单第 14 位。截至 2026-11-23，该系统由 504 个 HPE ProLiant Compute XD685 节点和 4,032 颗 AMD Instinct MI355X GPU 组成，用于支持美国能源部的创世纪计划。

Lux 超级计算机（亦称 Lux SI+HPC 超级计算机）是一座由美国能源部（DOE）橡树岭国家实验室（ORNL）下属橡树岭领导计算设施（OLCF）运营的人工智能与高性能计算集群，位于美国田纳西州橡树岭。Lux 由美国能源部、超威半导体（AMD）与慧与（HPE）通过公私共同投资伙伴关系合作开发，于 2026 年 11 月 16 日作为美国能源部创世纪计划（Genesis Mission）的首座专用 AI 工厂向科研用户开放。同日，该系统以 220.79 千万亿次每秒的 High Performance Linpack（HPL）性能首次登上第 68 期 TOP500 榜单第 14 位。截至 2026-11-23，OLCF 官方文档记载 Lux 由 504 个 HPE ProLiant Compute XD685 节点构成，每节点配备两颗 64 核 AMD EPYC 9575F 处理器和 8 颗 AMD Instinct MI355X GPU（共计 4,032 颗 GPU 及约 1.1 PB HBM3E 内存），可提供 317 千万亿次每秒（FP64）、20 百亿亿次每秒（FP8）和 40 百亿亿次每秒（FP4）的峰值系统性能。

**别名:** Lux, Lux Supercomputer, Lux SI+HPC 超级计算机, AMD Lux SI 集群, ORNL Lux

## 关键事实

- **运营机构与地点:** 橡树岭领导计算设施（OLCF），橡树岭国家实验室，美国田纳西州 [1]
- **TOP500 首次排名:** 2026 年 11 月 TOP500 榜单第 14 位（HPL 220.79 千万亿次每秒） (截至 2026-11-16) [1]
- **系统架构:** 504 个 HPE ProLiant Compute XD685 节点；1,008 颗 AMD EPYC 9575F CPU；4,032 颗 AMD Instinct MI355X GPU (截至 2026-11-23) [4]
- **峰值性能:** 40 EFLOPS（FP4 推理）、20 EFLOPS（FP8 训练）、317 PFLOPS（FP64 仿真） (截至 2026-11-23) [3]
- **年度节点小时分配:** 350 万节点小时/年：50% DOE 创世纪计划，50% AMD 及付费合作伙伴分配 (截至 2026-11-23) [3]

## 事实摘要

- **设施与运营机构:** 橡树岭领导计算设施（OLCF），橡树岭国家实验室（ORNL），美国田纳西州橡树岭 [1]
- **资助方与建造方:** 美国能源部（DOE）、超威半导体（AMD）、慧与（HPE） [1]
- **项目宣布日期:** 2025-10-27（与 2028 年交付的 Discovery 超级计算机同期宣布） [6]
- **科研用户开放日期:** 2026-11-16 [1]
- **TOP500 排名:** 第 68 期 TOP500 榜单（2026 年 11 月）第 14 位，HPL 性能 220.79 千万亿次每秒 (截至 2026-11-16) [1]
- **计算节点与平台:** 504 个 HPE ProLiant Compute XD685 节点 (截至 2026-11-23) [4]
- **每节点 CPU:** 2 颗 64 核 AMD EPYC 9575F CPU，配备 3 TB DDR5 内存（8 个 NUMA 域） (截至 2026-11-23) [4]
- **GPU 与 HBM 容量:** 4,032 颗 AMD Instinct MI355X GPU（每节点 8 颗，每颗 288 GB HBM3E，带宽 8 TB/s；总 HBM 约 1.1 PB） (截至 2026-11-23) [4]
- **系统峰值性能:** 317 PFLOPS（FP64 HPC）、20 EFLOPS（FP8 AI 训练）、40 EFLOPS（FP4 AI 推理） (截至 2026-11-23) [3]
- **互连与存储:** 每颗 GPU 配备 AMD Pensando 400G Ultra Ethernet 网卡；每节点 8 块 3.2 TB 本地 NVMe；679 PB Orion Lustre 文件系统 (截至 2026-11-23) [3]
- **操作系统与作业调度器:** Red Hat Enterprise Linux（RHEL）9.8；AMD ROCm；Slurm 与 Kubernetes 分区 (截至 2026-11-23) [4]
- **年度容量与分配:** 350 万节点小时/年（50% DOE 创世纪计划，50% AMD 及付费合作伙伴分配） (截至 2026-11-23) [3]

## Lux 超级计算机概述、公私伙伴关系与 TOP500 首次上榜

Lux 超级计算机是一座部署于橡树岭领导计算设施（OLCF）的人工智能与高性能计算（HPC）系统，OLCF 是美国能源部（DOE）科学办公室设在田纳西州橡树岭国家实验室（ORNL）的用户设施。[1][2] 在 2026 年底的美国联邦政府和 ORNL 出版物中，该系统被称为“SI+HPC”超级计算机，这体现了美国联邦政府根据第 14434 号行政令将“人工智能”（AI）改称为“超级智能”（Super Intelligence，SI）的过渡政策。[1][2][7] Lux 与 Frontier 并行运行，后者是 OLCF 算力达 1.353 百亿亿次每秒的 HPE Cray EX235a 旗舰系统，于 2022 年率先突破百亿亿次计算门槛，并在 2026 年 11 月的 TOP500 榜单中排名第 3。[1][3]

美国能源部、ORNL、超威半导体（AMD）与慧与（HPE）于 2025 年 10 月 27 日首次宣布了 Lux 项目，同期宣布的还有计划于 2028 年交付、基于 HPE Cray Supercomputing GX5000 架构的第八台 OLCF 旗舰超级计算机 Discovery。[1][6] 与传统的多年期领导级采购模式不同，Lux 是在美国能源部与 AMD 的公私共同投资伙伴关系下推进的，并在约一年内完成了采购与部署，以迅速扩展近期的 AI 与科学计算能力。[1][3][8]

2026 年 11 月 16 日，ORNL 与 AMD 宣布 Lux 已向科研用户开放，并在全球最快超级计算机第 68 期 TOP500 榜单中首次位列第 14 位。[1][2][5] 在用于 TOP500 排名的 High Performance Linpack（HPL）基准测试中，Lux 取得了 220.79 千万亿次每秒（每秒 220.79 千万亿次浮点运算）的成绩，而 OLCF 列出的 FP64 理论系统峰值为 317 千万亿次每秒。[1][3][8] 根据 OLCF 的历史记录，Lux 承接了该设施自 2004 年以来部署的七台旗舰系统，其中四台（Jaguar、2012 年的 Titan、2018 年的 Summit 以及 2022 年的 Frontier）在推出时均曾位居 TOP500 榜首。[1][3][6]

## Lux 超级计算机硬件架构与节点规格

Lux 超级计算机基于采用直接液冷技术的 HPE ProLiant Compute XD685 服务器节点构建，全面配备 AMD 处理器、加速器和网络硬件。[1][4][8] 根据截至 2026-11-23 的 OLCF Lux 用户指南，生产集群由 504 个节点和 4,032 颗 GPU 组成，划分为登录节点（位于 `lux.olcf.ornl.gov` 的 `login1` 至 `login3`）和计算节点。[4] 每个计算节点配备两颗 64 核 AMD EPYC 9575F CPU（每节点 128 个 CPU 核心），在 8 个非统一内存访问（NUMA）域之间共享 3 TB DDR5 系统内存，每个 NUMA 域映射至 16 个硬件线程和 1 颗 GPU。[4]

504 个节点各配备 8 颗 AMD Instinct MI355X GPU，全系统总计拥有 4,032 颗加速器。[4] 每颗 MI355X GPU 集成 8 个加速计算芯片（XCD），包含 256 个计算单元（每节点 64 个 XCD），并配备 288 GB HBM3E 高带宽内存，峰值内存带宽达 8 TB/s，使整个集群具备约 1.1 PB 的 HBM3E 总容量。[3][4] 在单个节点内部，8 颗 MI355X GPU 通过 AMD Infinity Fabric GPU 间链路互连，每条链路的双向峰值带宽为 153.6 GB/s。[4] 节点间通信则通过每颗 GPU 配备的一张 AMD Pensando 400G Ultra Ethernet 网卡（NIC）实现，并经由 HPE Juniper Networking 交换基础设施互连。[3][5][8]

| 规格项 | 单节点 / 单 GPU | 全系统（504 节点、4,032 GPU） |
| --- | --- | --- |
| 服务器平台 | HPE ProLiant Compute XD685 | 504 个节点（含登录与计算节点） |
| 主机处理器 | 2 颗 64 核 AMD EPYC 9575F CPU，3 TB DDR5 内存 | 1,008 颗 CPU（64,512 个 CPU 核心），约 1.5 PB DDR5 |
| GPU 加速器 | 8 颗 AMD Instinct MI355X（每颗 GPU 8 个 XCD、256 个 CU） | 4,032 颗 MI355X GPU（32,256 个 XCD） |
| 高带宽内存 | 每颗 GPU 288 GB HBM3E，带宽 8 TB/s | 总计约 1.1 PB HBM3E |
| 节点内与集群互连 | 153.6 GB/s Infinity Fabric GPU 间链路；每颗 GPU 配 400G Ultra Ethernet 网卡 | 4,032 张 400G AMD Pensando Ultra Ethernet 网卡 |
| FP64 HPC 性能 | 每颗 GPU 矢量 FP64 约 78.6 TFLOPS（概览页标注为 78 TF） | 理论峰值 317 PFLOPS；HPL 实测 220.79 PFLOPS |
| 低精度 AI 性能 | 每颗 GPU 矢量 FP16 157.3 TFLOPS；FP8 训练 5 PFLOPS | FP8 训练 20 EFLOPS；FP4 推理 40 EFLOPS |
| 节点本地存储 | 8 块 3.2 TB NVMe SSD（每节点 >24 TB） | 总计 >12 PB 本地 NVMe 存储 |

根据截至 2026-11-23 的 OLCF Lux 用户指南与系统概览文档，每颗独立的 MI355X GPU 在面向建模与仿真的矢量双精度（FP64）算力方面额定为 78.6 万亿次每秒（系统概览页四舍五入为 78 TF），矢量半精度算力为 157.3 万亿次每秒，FP8 AI 训练算力为 5 千万亿次每秒。[3][4] 在系统层面，OLCF 公布的汇总峰值为 FP64 HPC 负载 317 千万亿次每秒、FP8 AI 训练 20 百亿亿次每秒以及 FP4 AI 推理 40 百亿亿次每秒。[3]

## Lux 超级计算机软件环境、调度与存储

Lux 超级计算机运行 Red Hat Enterprise Linux（RHEL）9.8 版本，采用 AMD ROCm 开放软件栈与 ROCr 运行时，每颗 AMD Instinct MI355X 在作业调度器和 `ROCR_VISIBLE_DEVICES` 中均作为独立 GPU 呈现。[1][4] 为在同一套硬件上同时支持传统超算仿真与云原生 AI 工作负载，OLCF 将 Lux 划分为分别由 Slurm 和 Kubernetes 管理的两个调度分区。[1][3][4] Slurm 与 Kubernetes 分区的相对规模会根据用户需求随时间动态调整。[3]

在本地高速暂存输入输出方面，每个 Lux 计算节点配备 8 块 3.2 TB 非易失性内存主机控制器接口规范（NVMe）固态硬盘，为每个节点提供超过 24 TB 的本地 NVMe 存储空间。[3][4] 在共享并行存储方面，Lux 挂载了基于 HPE ClusterStor 硬件构建的 OLCF 中心级 Lustre 并行文件系统 Orion（`/lustre/orion/`）。[3][4] OLCF 系统概览将 Orion 的容量描述为超过 600 PB，而 Lux 用户指南则明确其可用命名空间为 679 PB，并支持渐进式文件布局（PFL），可在文件增长时自动调整文件条带化配置。[3][4]

由于 Orion 在 Lux、Frontier、Riker 集群以及 OLCF 数据传输节点之间共享，同时拥有 Frontier 和 Lux 算力配额的研究团队可以在 Frontier 上生成大规模仿真数据集并直接写入 Orion，随后无需外部数据迁移即可在 Lux 上使用这些数据集训练 AI 模型。[3][4] 此外，Lux 用户还可以访问用于主目录和项目目录的 OLCF 中心级网络文件系统（NFS），以及 OLCF 的近线归档存储系统 Kronos。[4]

## Lux 超级计算机分配政策、商业访问与安全控制

Lux 超级计算机在美国能源部与 AMD 平分治理权的共同投资模式下，每年提供 350 万节点小时的算力资源。[1][3] Lux 年度节点小时中约一半专用于美国能源部的创世纪计划以支持开放科学研究，其余一半分配给 AMD 用于技术研发与测试，并按美国能源部用户设施费率向公共和私营部门合作伙伴提供付费访问。[1][3]

对于付费专有或合作伙伴分配，OLCF 要求每六个月至少承诺 175,000 节点小时，项目周期可在六个月至五年之间，且可在任意月份灵活启动。[3] 据 OLCF 介绍，175,000 节点小时的配额可支持在六个月窗口期内累计运行 18 天的 400 节点（3,200 GPU）作业，或支持约 40 个节点连续运行六个月。[3] 合作伙伴作业的规模可从单节点扩展至接近全系统，但考虑到为常驻服务预留的节点，全系统作业的上限略低于 4,000 颗 GPU。[3]

截至 2026-11-23，Lux 在 DOE 中等（Moderate）安全控制标准下运行，这与 Frontier 采用的安全基线相同，允许运行受出口管制的应用并处理相关数据。[3] OLCF 已宣布计划在 Lux 上增设 DOE 中等增强（Moderate-Enhanced）安全控制，从而将适用范围扩展至受《国际武器贸易条例》（ITAR）监管的工作负载以及受 HIPAA 规范的受保护健康信息（PHI）。[3]

## Lux 超级计算机在 DOE 创世纪计划中的作用与科学工作负载

Lux 超级计算机是美国能源部创世纪计划（Genesis Mission）的首座专用 AI 工厂及核心新增计算基础设施；该国家倡议旨在整合美国能源部下属 17 个国家实验室的超级计算、AI 基础模型、量子系统与实验设施。[1][2][5] 在创世纪计划框架内，ORNL 还牵头建设美国科学云（American Science Cloud，AmSC），这是一个连接实验室计算、数据与高速网络的联邦式科学发现平台。[2]

在 2026 年 11 月 16 日的启用公告中，ORNL 与 AMD 详细介绍了运行于 Lux 上的三个旗舰级创世纪计划研究分配项目：[1][2][5][8]

- 聚变发电厂设计（FADO）：核聚变智能体设计编排器（Fusion Agentic Design Orchestrator）利用智能体 AI 工作流，将高保真等离子体与工程仿真、机器人维护系统设计，以及面向聚变先导电站的可靠性、可用性、可维护性与可检查性（RAMI）准则相结合。[1][5][8]
- 材料研发与先进制造：一座为美国工业界训练定制化多模态基础模型的 AI 基础模型工厂，涵盖 3D 打印及增材制造构件的合金微结构预测与设计。[1][5][8]
- 地球系统与长期水资源预测：一项提前数周至数年预测水资源可用量、河川径流与河流水温的 AI 预报项目，用于指导田纳西河谷管理局（TVA）区域的水力发电调度与火电厂冷却运行。[1][5][8]

根据 ORNL 于 2026 年 11 月 16 日发布的新闻稿，ORNL 研究人员在创世纪计划第一阶段还牵头另外 6 个项目并参与 30 个多机构合作项目，并在该计划第二阶段进一步牵头 6 个项目。[1][2]

## 常见问题

### 什么是 Lux 超级计算机，它位于何处？

Lux 是一台基于 AMD 芯片的超级智能（SI，即美国联邦政府根据第 14434 号行政令对人工智能的官方称谓）与高性能计算（HPC）超级计算机，由位于田纳西州橡树岭的美国能源部橡树岭国家实验室（ORNL）下属橡树岭领导计算设施（OLCF）运营。该系统由慧与（HPE）在美国能源部与 AMD 的公私共同投资伙伴关系下建造，并于 2026 年 11 月 16 日向科研用户开放。 [1][2][4][5]

### Lux 的 TOP500 排名和峰值性能是多少？

在 2026 年 11 月 16 日发布的第 68 期 TOP500 榜单中，Lux 以 220.79 千万亿次每秒（petaflops）的 High Performance Linpack（HPL）基准测试成绩首次位列全球第 14 位。截至 2026-11-23，OLCF 系统规格还列出了其理论峰值算力：用于建模与仿真的 FP64 峰值为 317 千万亿次每秒，用于 AI 训练的 FP8 峰值为 20 百亿亿次每秒，用于 AI 推理的 FP4 峰值为 40 百亿亿次每秒。 [1][3][5]

### Lux 的每个计算节点使用哪些硬件和处理器？

截至 2026-11-23，OLCF Lux 用户指南记载该系统包含 504 个 HPE ProLiant Compute XD685 节点和 4,032 颗 AMD Instinct MI355X GPU。每个计算节点配备两颗 64 核 AMD EPYC 9575F CPU 与 3 TB DDR5 系统内存、8 颗 AMD Instinct MI355X GPU（每颗配备 288 GB HBM3E 内存、8 TB/s 带宽以及 8 个加速计算芯片）、8 块 3.2 TB 本地 NVMe 固态硬盘（每节点超过 24 TB），以及 400G Ultra Ethernet AMD Pensando 网卡。 [3][4][5]

### Lux 的计算时间如何在创世纪计划与合作伙伴之间分配？

OLCF 将 Lux 每年 350 万节点小时中约一半分配给美国能源部的创世纪计划（Genesis Mission）用于开放科学研究，其余一半供 AMD 进行研发测试，并按美国能源部用户设施费率向公共或私营合作伙伴提供付费专有使用。付费合作伙伴分配需每六个月至少承诺 175,000 节点小时，项目周期可在六个月至五年之间，并遵循 DOE 中等（Moderate）安全控制标准。 [1][3]

### Lux 支持哪些操作系统、作业调度器和存储系统？

Lux 运行 Red Hat Enterprise Linux（RHEL）9.8 与 AMD ROCm 开放软件栈，并将节点划分为用于传统批处理 HPC 作业的 Slurm 分区和用于容器化 AI 训练、推理及智能体编排的 Kubernetes 分区。所有分配项目均可访问 OLCF 的 Orion Lustre 并行文件系统（基于 HPE ClusterStor，可用命名空间 679 PB）以及 Kronos 近线归档存储系统。 [1][3][4]

### Lux 超级计算机上运行着哪些科学研究项目？

在 2026 年 11 月 16 日的公告中，ORNL 与 AMD 重点介绍了分配至 Lux 的三个首批创世纪计划项目：将 HPC 仿真与机器人维护融入聚变发电厂设计的核聚变智能体设计编排器（FADO）；面向材料研发与先进制造（如 3D 打印合金微结构）的 AI 基础模型工厂；以及预测田纳西河谷管理局区域水资源可用量、河川径流与河流水温的地球系统预测项目。 [1][2][5][8]

## 可引用的句子

- Lux 超级计算机于 2026 年 11 月 16 日在美国能源部橡树岭国家实验室向科研用户开放，并以 220.79 千万亿次每秒（petaflops）的 High Performance Linpack 性能首次登上第 68 期 TOP500 榜单第 14 位。 [1][2][5]
- 截至 2026-11-23，OLCF Lux 用户指南记载，Lux 由 504 个 HPE ProLiant Compute XD685 节点组成，总计配备 4,032 颗 AMD Instinct MI355X GPU，每个节点搭载两颗 64 核 AMD EPYC 9575F CPU。 [4]
- Lux 中的每颗 AMD Instinct MI355X GPU 配备 288 GB HBM3E 内存，跨 8 个加速计算芯片（256 个计算单元）提供 8 TB/s 峰值内存带宽，使全系统具备约 1.1 PB 的 HBM3E 总容量。 [3][4]
- 截至 2026-11-23，橡树岭领导计算设施（OLCF）公布的 Lux 峰值性能为：FP4 AI 推理 40 百亿亿次每秒（exaflops）、FP8 AI 训练 20 百亿亿次每秒，以及 FP64 高性能计算建模与仿真 317 千万亿次每秒。 [3]
- Lux 每年 350 万节点小时中有一半专用于美国能源部的创世纪计划（Genesis Mission），其余一半留给 AMD 以及按每六个月至少 175,000 节点小时起订的付费专有或公共部门合作伙伴。 [1][3]
- Lux 计算节点运行 Red Hat Enterprise Linux 9.8，将资源划分为 Slurm 和 Kubernetes 调度分区，每节点配备 8 块 3.2 TB 本地 NVMe 固态硬盘，并挂载 OLCF 的 Orion Lustre 并行文件系统（可用命名空间 679 PB）。 [3][4]
- Lux 上早期的创世纪计划分配项目包括用于聚变发电厂设计的核聚变智能体设计编排器（FADO）、面向材料与先进制造的基础模型工厂，以及面向田纳西河谷管理局区域的长期水资源与径流预测项目。 [1][2][5][8]
- 美国能源部、ORNL、AMD 与 HPE 于 2025 年 10 月 27 日在公私共同投资伙伴关系框架下宣布了 Lux 和 Discovery 超级计算机项目。 [6]

## 时间线

- 2025-10-27: 美国能源部、橡树岭国家实验室、AMD 与 HPE 宣布 Lux 和 Discovery 超级计算机项目。 [6]
- 2026-11-16: Lux 超级计算机作为美国能源部创世纪计划的首座 AI 工厂在 ORNL 向科研用户开放，并以 220.79 千万亿次每秒的成绩首次登上第 68 期 TOP500 榜单第 14 位。 [1][2][5]
- 2028: 与 Lux 同期宣布的 ORNL 下一代 HPE Cray GX5000 旗舰超级计算机 Discovery 的计划交付年份。 [1][6]

## 来源

1. Lux SI+HPC Supercomputer Debuts in the Top500, Advances Genesis Mission Goals – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). 发布于 2026-11-16. https://www.olcf.ornl.gov/2026/11/16/lux-genesis-mission/ (访问于 2026-11-23; tier 1: government or public registry)
2. Lux SI+HPC supercomputer debuts in the Top500, advances Genesis Mission goals – Oak Ridge National Lab. Oak Ridge National Laboratory. 发布于 2026-11-16. https://www.ornl.gov/news/lux-sihpc-supercomputer-debuts-in-the-top500-advances-genesis-mission-goals/ (访问于 2026-11-23; tier 1: government or public registry)
3. Lux – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). https://www.olcf.ornl.gov/olcf-resources/compute-systems/lux/ (访问于 2026-11-23; tier 1: government or public registry)
4. Lux User Guide - OLCF User Documentation. Oak Ridge Leadership Computing Facility (ORNL). https://docs.olcf.ornl.gov/systems/lux_user_guide.html (访问于 2026-11-23; tier 1: government or public registry)
5. Lux Supercomputer Opens to Scientific Users at Oak Ridge - AMD Newsroom. Advanced Micro Devices (AMD). 发布于 2026-11-16. https://newsroom.amd.com/news/amd-powered-lux-supercomputer-opens-scientific-users/ (访问于 2026-11-23; tier 3: official site)
6. ORNL, AMD, and HPE to Deliver DOE’s Newest AI Supercomputers: Discovery and Lux – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). 发布于 2025-10-27. https://www.olcf.ornl.gov/2025/10/27/ornl-amd-and-hpe-to-deliver-does-newest-ai-supercomputers-discovery-and-lux/ (访问于 2026-11-23; tier 1: government or public registry)
7. Oak Ridge National Laboratory unveils Lux supercomputer - DCD. Data Center Dynamics. 发布于 2026-11-17. https://www.datacenterdynamics.com/en/news/oak-ridge-national-laboratory-unveils-lux-supercomputer/ (访问于 2026-11-23; tier 2: academic or news)
8. AMD opens up its new Lux supercomputer, powering everything from nuclear fusion to weather predictions | TechRadar. TechRadar. 发布于 2026-11-21. https://www.techradar.com/pro/amd-opens-up-its-new-lux-supercomputer-powering-everything-from-nuclear-fusion-to-weather-predictions (访问于 2026-11-23; tier 2: academic or news)

## 引用本页

Mimirwiki. "Lux 超级计算机." 版本 6b390453, 2026-11-23. https://mimirwiki.com/zh/wiki/lux-supercomputer
