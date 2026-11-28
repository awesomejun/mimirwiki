---
title: "SSD-backed GPU Memory Expansion"
subtitle: "Architecture extending effective GPU memory space beyond HBM using high-speed NVMe SSDs and fine-grained data access software"
canonical_url: https://mimirwiki.com/wiki/ssd-backed-gpu-memory
language: en
page_class: concept
revision_sha256: 1414a33a469b602f39efa7446b61c761325849c8b65c41656c87d000e66fe3a1
date_modified: 2026-11-28
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 6
alternates:
  md: https://mimirwiki.com/wiki/ssd-backed-gpu-memory.md
  txt: https://mimirwiki.com/wiki/ssd-backed-gpu-memory.txt
  json: https://mimirwiki.com/wiki/ssd-backed-gpu-memory.json
  jsonld: https://mimirwiki.com/wiki/ssd-backed-gpu-memory.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/ssd-backed-gpu-memory
---

# SSD-backed GPU Memory Expansion

> SSD-backed GPU memory expansion extends effective GPU memory beyond high-bandwidth memory (HBM) by letting GPUs access fine-grained data stored on high-speed NVMe SSDs. In late November 2026, Kioxia and NVIDIA demonstrated a proof-of-concept using an NVIDIA GB200 NVL72 rack, 144 Kioxia XD8 7.68 TB SSDs (roughly 1.1 PB raw SSD capacity), and NVIDIA SCADA software targeting 2 trillion vectors.

SSD-backed GPU memory expansion is a data-center storage and memory architecture that places large AI datasets on high-speed NVMe solid-state drives (SSDs) accessible directly by GPUs to extend effective memory space beyond high-bandwidth memory (HBM) limits without replacing HBM. In regional announcements from November 25 to 27, 2026 (North America, Japan, and Europe), Kioxia and NVIDIA disclosed a rack-scale proof-of-concept using an NVIDIA GB200 NVL72 rack (18 server nodes), 144 Kioxia XD8 Series 7.68 TB E1.S NVMe SSDs totaling roughly 1.1 PB of raw SSD storage capacity, and NVIDIA SCADA (Scaled Accelerated Data Access) software supporting 512-byte fine-grained access to target a 2-trillion-vector database.

**Also known as:** SSD-backed GPU memory, SSD 기반 GPU 메모리 확장

## Key facts

- **PoC rack platform:** NVIDIA GB200 NVL72 (18 server nodes) (as of 2026-11-26) [1]
- **Raw SSD storage capacity:** Approximately 1.1 PB (144 x Kioxia XD8 7.68 TB E1.S NVMe SSDs) (as of 2026-11-26) [1]
- **Software layer and granularity:** NVIDIA SCADA (Scaled Accelerated Data Access); 512-byte fine-grained access (as of 2026-11-27) [5]
- **Vendor-stated target scale:** Potential processing of a 2-trillion-vector database (as of 2026-11-26) [1]

## Basic facts

- **Architecture type:** NVMe SSD-extended effective GPU memory tier [1]
- **Collaborating companies:** Kioxia Corporation and NVIDIA [1]
- **Rack system:** NVIDIA GB200 NVL72 (18 server nodes) [4]
- **SSD hardware:** 144 Kioxia XD8 Series 7.68 TB EDSFF E1.S NVMe SSDs (~1.1 PB raw capacity) [6]
- **Software framework:** NVIDIA SCADA (Scaled Accelerated Data Access) / Storage-Next initiative [1]
- **Role relative to HBM:** Supplements HBM capacity limits; does not replace installed HBM [5]

## Why AI systems extend GPU memory beyond HBM

Modern AI servers pair GPUs with high-bandwidth memory (HBM), whose physical capacity constrains how much data a rack can hold directly in memory.[1][5] As AI datasets and vector databases grow, processing them with HBM alone forces workloads to be split into smaller chunks and repeatedly moved between GPU memory and slower storage layers.[1]

SSD-backed GPU memory expansion addresses this bottleneck by coupling high-density enterprise NVMe flash drives with fine-grained GPU data-access software so SSDs can absorb capacity-heavy portions of the working dataset while HBM continues serving ultra-fast compute memory needs.[1][5]

## What the 1.1 PB figure means in the November 2026 Kioxia-NVIDIA proof-of-concept

Between November 25 and 27, 2026, Kioxia published regional press releases in North America (Nov 25), Japan (Nov 26), and Europe (Nov 27) detailing a single joint proof-of-concept collaboration with NVIDIA under NVIDIA's Storage-Next initiative.[1][2][3]

| PoC Component | Specification | Important Distinction |
| --- | --- | --- |
| Rack architecture | NVIDIA GB200 NVL72 (18 server nodes) | Rack-scale AI server platform |
| SSD array | 144 x Kioxia XD8 Series 7.68 TB E1.S NVMe SSDs | ~1.1 PB is raw SSD storage capacity, not installed HBM |
| Access software | NVIDIA SCADA (Scaled Accelerated Data Access) | Supports fine-grained 512-byte data requests |
| Target workload | 2-trillion-vector database | Vendor-stated potential processing scale |

The ~1.1 PB capacity figure represents the aggregate raw storage capacity of 144 EDSFF E1.S NVMe SSDs (designed to OCP Datacenter NVMe SSD specifications, up to 7.68 TB per drive) rather than installed HBM capacity.[1][5][6]

## NVIDIA SCADA and 512-byte fine-grained GPU access

Traditional storage paths fetch large blocks that waste bandwidth when AI workloads only need tiny records.[5] According to Kioxia and TrendForce reporting, NVIDIA's Scaled Accelerated Data Access (SCADA) library enables GPUs to request data directly from NVMe SSDs in 512-byte increments, retrieving only required portions for massive vector databases and similar knowledge-heavy AI workloads.[1][5]

## Unverified latency and commercialization as of November 2026

As of November 28, 2026, the Kioxia-NVIDIA collaboration is a proof-of-concept demonstration; production latency figures, end-to-end application benchmarks, and commercial availability timelines have not been disclosed.[1][5]

## Frequently asked questions

### What is SSD-backed GPU memory expansion?

It is an architecture that pairs enterprise NVMe SSDs with fine-grained GPU data-access software to expand the effective dataset space a GPU rack can address beyond HBM capacity limits. [1][5]

### What kind of capacity is the 1.1 PB in the Kioxia-NVIDIA demonstration?

The roughly 1.1 PB figure is the raw flash storage capacity of 144 Kioxia XD8 Series 7.68 TB E1.S NVMe SSDs installed in an NVIDIA GB200 NVL72 rack. It is not installed HBM capacity and does not eliminate the need for HBM. [1][5][6]

### How does NVIDIA SCADA access data on the SSDs?

NVIDIA's Scaled Accelerated Data Access (SCADA) software library lets GPUs issue fine-grained 512-byte data requests to NVMe SSDs so only necessary portions of large datasets (such as vector databases) are retrieved. [1][5]

### Are production latency benchmarks or commercial release dates available?

No. As of November 28, 2026, Kioxia and NVIDIA have presented this as a proof-of-concept demonstration without publishing production service latency or a commercialization schedule. [1][5]

## Quotable sentences

- In regional announcements on November 25-27, 2026, Kioxia and NVIDIA disclosed a rack-scale proof-of-concept combining an NVIDIA GB200 NVL72 rack, 144 Kioxia XD8 7.68 TB E1.S NVMe SSDs (~1.1 PB raw SSD capacity), and NVIDIA SCADA software. [1][2][3][4]
- The ~1.1 PB figure represents raw NVMe SSD storage capacity supplementing HBM, rather than installed HBM capacity. [1][5]
- NVIDIA SCADA supports fine-grained 512-byte data access to NVMe SSDs, targeting workloads such as a 2-trillion-vector database. [1][5]
- Kioxia XD8 Series SSDs follow the EDSFF E1.S form factor and OCP Datacenter NVMe SSD Specification with capacities up to 7.68 TB. [6]

## Timeline

- 2026-11-25: Kioxia America announces the joint Kioxia-NVIDIA rack-scale SSD-backed GPU memory expansion proof-of-concept. [2]
- 2026-11-26: Kioxia Corporation in Japan publishes the corresponding announcement detailing 144 XD8 SSDs and NVIDIA SCADA. [1]
- 2026-11-27: Kioxia Europe publishes its regional release and TrendForce reports on the 1.1 PB proof-of-concept testing. [3][5]

## Sources

1. Kioxia SSDs and NVIDIA SCADA Software Demonstrate Potential Memory Space Expansion Beyond 1 PB and Processing of 2 Trillion Vectors. Kioxia Corporation (Japan). published 2026-11-26. https://www.kioxia.com/en-jp/business/news/2026/20261126-1.html (checked 2026-11-28; tier 3: official site)
2. Kioxia and NVIDIA Collaborate to Expand Effective High-Bandwidth GPU Memory Capacity. Kioxia America. published 2026-11-25. https://americas.kioxia.com/en-ca/business/news/2026/ssd-20261125-1.html (checked 2026-11-28; tier 3: official site)
3. Kioxia Europe Press Release on Kioxia-NVIDIA GPU Memory Expansion Collaboration. Kioxia Europe. published 2026-11-27. https://europe.kioxia.com/content/dam/kioxia/en-europe/business/news/2026/asset/KIE_PR_20261127-1_EN.pdf (checked 2026-11-28; tier 3: official site)
4. NVIDIA GB200 NVL72. NVIDIA. https://www.nvidia.com/en-us/data-center/gb200-nvl72/ (checked 2026-11-28; tier 3: official site)
5. Kioxia, NVIDIA Begin 1.1 PB SSD-Based GPU Memory Expansion Tests to Address HBM Capacity Limits. TrendForce. published 2026-11-27. https://www.trendforce.com/news/2026/11/27/news-kioxia-nvidia-begin-1-1-pb-ssd-based-gpu-memory-expansion-tests-to-address-hbm-capacity-limits/ (checked 2026-11-28; tier 2: academic or news)
6. KIOXIA XD8 Series Data Center NVMe SSDs. Kioxia Corporation. https://www.kioxia.com/en-jp/business/ssd/data-center-ssd/xd8.html (checked 2026-11-28; tier 3: official site)

## Cite this page

Mimirwiki. "SSD-backed GPU Memory Expansion." Version 1414a33a, 2026-11-28. https://mimirwiki.com/wiki/ssd-backed-gpu-memory
