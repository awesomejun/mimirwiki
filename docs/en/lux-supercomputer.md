---
title: "Lux Supercomputer"
subtitle: "AMD-powered artificial intelligence and high-performance computing supercomputer at Oak Ridge National Laboratory"
canonical_url: https://mimirwiki.com/wiki/lux-supercomputer
language: en
page_class: entity
revision_sha256: 8707bcac60ddc6f4e8be112c21e78296bbc859baf231a73c8d903327eebf791e
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/wiki/lux-supercomputer.md
  txt: https://mimirwiki.com/wiki/lux-supercomputer.txt
  json: https://mimirwiki.com/wiki/lux-supercomputer.json
  jsonld: https://mimirwiki.com/wiki/lux-supercomputer.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/lux-supercomputer
  ja: https://mimirwiki.com/ja/wiki/lux-supercomputer
  zh: https://mimirwiki.com/zh/wiki/lux-supercomputer
  es: https://mimirwiki.com/es/wiki/lux-supercomputer
---

# Lux Supercomputer

> The Lux Supercomputer is an AMD-powered artificial intelligence and high-performance computing system built by Hewlett Packard Enterprise at the U.S. Department of Energy's Oak Ridge National Laboratory. Opened to scientific users on November 16, 2026, Lux debuted at No. 14 on the November 2026 TOP500 list with 220.79 petaflops on High Performance Linpack. As of 2026-11-23, it comprises 504 HPE ProLiant Compute XD685 nodes with 4,032 AMD Instinct MI355X GPUs and supports the DOE's Genesis Mission.

The Lux Supercomputer (also designated the Lux SI+HPC Supercomputer) is an artificial intelligence and high-performance computing cluster operated by the Oak Ridge Leadership Computing Facility (OLCF) at the U.S. Department of Energy's Oak Ridge National Laboratory (ORNL) in Oak Ridge, Tennessee. Developed through a public-private co-investment partnership among the Department of Energy, Advanced Micro Devices (AMD), and Hewlett Packard Enterprise (HPE), Lux opened to scientific users on November 16, 2026, as the first dedicated AI Factory for the DOE's Genesis Mission. On the same day, the system debuted at No. 14 on the 68th edition of the TOP500 list with 220.79 petaflops of High Performance Linpack (HPL) performance. As of 2026-11-23, OLCF documentation specifies that Lux consists of 504 HPE ProLiant Compute XD685 nodes equipped with dual 64-core AMD EPYC 9575F processors and eight AMD Instinct MI355X GPUs per node (4,032 GPUs and approximately 1.1 petabytes of HBM3E memory in total), delivering peak system performance of 317 petaflops at FP64, 20 exaflops at FP8, and 40 exaflops at FP4.

**Also known as:** Lux, Lux SI+HPC Supercomputer, AMD Lux SI Cluster, ORNL Lux

## Key facts

- **Operator and location:** Oak Ridge Leadership Computing Facility (OLCF), Oak Ridge National Laboratory, Tennessee [1]
- **TOP500 debut:** No. 14 on the November 2026 TOP500 list (220.79 petaflops HPL) (as of 2026-11-16) [1]
- **System architecture:** 504 HPE ProLiant Compute XD685 nodes; 1,008 AMD EPYC 9575F CPUs; 4,032 AMD Instinct MI355X GPUs (as of 2026-11-23) [4]
- **Peak performance:** 40 EFLOPS (FP4 inference), 20 EFLOPS (FP8 training), 317 PFLOPS (FP64 simulation) (as of 2026-11-23) [3]
- **Annual node-hour split:** 3.5 million node-hours/year: 50% DOE Genesis Mission, 50% AMD and paid partner allocations (as of 2026-11-23) [3]

## Basic facts

- **Facility and operator:** Oak Ridge Leadership Computing Facility (OLCF), Oak Ridge National Laboratory (ORNL), Oak Ridge, Tennessee, US [1]
- **Sponsors and builders:** U.S. Department of Energy (DOE), Advanced Micro Devices (AMD), Hewlett Packard Enterprise (HPE) [1]
- **Project announced:** 2025-10-27 (alongside the 2028 Discovery supercomputer) [6]
- **Scientific user opening:** 2026-11-16 [1]
- **TOP500 ranking:** No. 14 on the 68th TOP500 list (November 2026) at 220.79 petaflops HPL (as of 2026-11-16) [1]
- **Compute nodes and platform:** 504 HPE ProLiant Compute XD685 nodes (as of 2026-11-23) [4]
- **CPUs per node:** 2x 64-core AMD EPYC 9575F CPUs with 3 TB DDR5 memory (8 NUMA domains) (as of 2026-11-23) [4]
- **GPUs and HBM capacity:** 4,032 AMD Instinct MI355X GPUs (8 per node, 288 GB HBM3E at 8 TB/s each; ~1.1 PB total HBM) (as of 2026-11-23) [4]
- **Peak system performance:** 317 PFLOPS (FP64 HPC), 20 EFLOPS (FP8 AI training), 40 EFLOPS (FP4 AI inference) (as of 2026-11-23) [3]
- **Interconnect and storage:** AMD Pensando 400G Ultra Ethernet NIC per GPU; 8x 3.2 TB local NVMe per node; 679 PB Orion Lustre filesystem (as of 2026-11-23) [3]
- **OS and job schedulers:** Red Hat Enterprise Linux (RHEL) 9.8; AMD ROCm; Slurm and Kubernetes partitions (as of 2026-11-23) [4]
- **Annual capacity and allocation:** 3.5 million node-hours/year (50% DOE Genesis Mission, 50% AMD and paid partner allocations) (as of 2026-11-23) [3]

## Lux Supercomputer overview, public-private partnership, and TOP500 debut

The Lux Supercomputer is an artificial intelligence and high-performance computing (HPC) system housed at the Oak Ridge Leadership Computing Facility (OLCF), a U.S. Department of Energy (DOE) Office of Science user facility at Oak Ridge National Laboratory (ORNL) in Oak Ridge, Tennessee.[1][2] In U.S. federal and ORNL publications from late 2026, the system is designated an "SI+HPC" supercomputer, reflecting the federal transition under Executive Order 14434 to use the term "Super Intelligence" (SI) in place of "artificial intelligence" (AI).[1][2][7] Lux operates alongside Frontier, OLCF's 1.353-exaflop HPE Cray EX235a flagship system that broke the exascale barrier in 2022 and ranked No. 3 on the November 2026 TOP500 list.[1][3]

The DOE, ORNL, Advanced Micro Devices (AMD), and Hewlett Packard Enterprise (HPE) first announced Lux on October 27, 2025, alongside Discovery, an eighth OLCF flagship supercomputer based on the HPE Cray Supercomputing GX5000 architecture scheduled for delivery in 2028.[1][6] Unlike traditional multi-year leadership procurements, Lux was procured and deployed within roughly one year under a public-private co-investment partnership between the DOE and AMD to expand near-term AI and scientific computing capacity.[1][3][8]

On November 16, 2026, ORNL and AMD announced that Lux had opened to scientific users and debuted at No. 14 on the 68th edition of the TOP500 list of the world's most powerful supercomputers.[1][2][5] On the High Performance Linpack (HPL) benchmark used for TOP500 rankings, Lux achieved 220.79 petaflops (220.79 quadrillion floating-point operations per second) against an OLCF-listed FP64 theoretical system peak of 317 petaflops.[1][3][8] OLCF history notes that Lux follows seven flagship systems deployed at the facility since 2004, four of which (Jaguar, Titan in 2012, Summit in 2018, and Frontier in 2022) held the No. 1 position on the TOP500 at launch.[1][3][6]

## Lux Supercomputer hardware architecture and node specifications

The Lux Supercomputer is built on direct liquid-cooled HPE ProLiant Compute XD685 server nodes configured with AMD processors, accelerators, and networking.[1][4][8] According to the OLCF Lux User Guide as of 2026-11-23, the production cluster consists of 504 nodes and 4,032 GPUs, separated into login nodes (`login1` through `login3` at `lux.olcf.ornl.gov`) and compute nodes.[4] Each compute node contains two 64-core AMD EPYC 9575F CPUs (128 CPU cores per node) sharing 3 TB of DDR5 system memory across eight Non-Uniform Memory Access (NUMA) domains, with each NUMA domain mapped to 16 hardware threads and one GPU.[4]

Each of the 504 nodes houses eight AMD Instinct MI355X GPUs, for a total of 4,032 accelerators across the system.[4] Every MI355X GPU integrates eight Accelerated Compute Dies (XCDs) containing 256 compute units (64 XCDs per node) and 288 GB of HBM3E high-bandwidth memory operating at a peak memory bandwidth of 8 TB/s, providing approximately 1.1 petabytes of aggregate HBM3E across the cluster.[3][4] Within each node, the eight MI355X GPUs are linked via AMD Infinity Fabric GPU-to-GPU connections delivering a peak bidirectional bandwidth of 153.6 GB/s per connection.[4] Inter-node communication uses an AMD Pensando 400G Ultra Ethernet network interface card (NIC) per GPU, connected across HPE Juniper Networking switching infrastructure.[3][5][8]

| Specification | Per node / per GPU | Full system (504 nodes, 4,032 GPUs) |
| --- | --- | --- |
| Server platform | HPE ProLiant Compute XD685 | 504 nodes (login and compute) |
| Host processors | 2x 64-core AMD EPYC 9575F CPUs, 3 TB DDR5 RAM | 1,008 CPUs (64,512 CPU cores), ~1.5 PB DDR5 |
| GPU accelerators | 8x AMD Instinct MI355X (8 XCDs, 256 CUs per GPU) | 4,032 MI355X GPUs (32,256 XCDs) |
| High-bandwidth memory | 288 GB HBM3E per GPU at 8 TB/s bandwidth | ~1.1 PB total HBM3E |
| Intra-node and fabric links | 153.6 GB/s Infinity Fabric GPU-GPU; 400G Ultra Ethernet NIC/GPU | 4,032x 400G AMD Pensando Ultra Ethernet NICs |
| FP64 HPC performance | ~78.6 TFLOPS vector FP64 per GPU (78 TF listed on overview) | 317 PFLOPS theoretical peak; 220.79 PFLOPS HPL |
| Low-precision AI performance | 157.3 TFLOPS vector FP16; 5 PFLOPS FP8 training per GPU | 20 EFLOPS (FP8 training); 40 EFLOPS (FP4 inference) |
| Local node storage | 8x 3.2 TB NVMe SSDs (>24 TB per node) | >12 PB aggregate local NVMe storage |

As documented in the OLCF Lux User Guide and system overview as of 2026-11-23, each individual MI355X GPU is rated at 78.6 teraflops (rounded to 78 TF on the system overview page) of vector double-precision (FP64) performance for modeling and simulation, 157.3 teraflops of vector half-precision performance, and 5 petaflops of FP8 AI training performance.[3][4] At the system level, OLCF lists aggregate peaks of 317 petaflops for FP64 HPC workloads, 20 exaflops for FP8 AI training, and 40 exaflops for FP4 AI inference.[3]

## Lux Supercomputer software environment, scheduling, and storage

The Lux Supercomputer runs Red Hat Enterprise Linux (RHEL) version 9.8 and uses the AMD ROCm open software stack and ROCr runtime, where each AMD Instinct MI355X appears as an individual GPU to job schedulers and `ROCR_VISIBLE_DEVICES`.[1][4] To support both traditional supercomputing simulations and cloud-native AI workloads on the same hardware, OLCF divides Lux into two scheduling partitions managed by Slurm and Kubernetes.[1][3][4] The relative size of the Slurm and Kubernetes partitions is adjusted dynamically over time based on user demand.[3]

For local high-speed scratch input and output, each Lux compute node includes eight 3.2 TB Non-Volatile Memory Express (NVMe) solid-state drives, providing more than 24 TB of local NVMe storage per node.[3][4] For shared parallel storage, Lux mounts Orion (`/lustre/orion/`), OLCF's center-wide Lustre parallel file system built on HPE ClusterStor hardware.[3][4] The OLCF system overview describes Orion as having over 600 petabytes of capacity, while the Lux User Guide specifies a 679 PB usable namespace with Progressive File Layout (PFL) that adjusts file striping automatically as files grow.[3][4]

Because Orion is shared across Lux, Frontier, the Riker cluster, and OLCF data transfer nodes, research teams holding allocations on both Frontier and Lux can generate large simulation datasets on Frontier, write them directly to Orion, and train AI models on those datasets on Lux without external data movement.[3][4] Lux users also receive access to OLCF's center-wide Network File System (NFS) for home and project directories and to Kronos, OLCF's nearline archival storage system.[4]

## Lux Supercomputer allocation policy, commercial access, and security controls

The Lux Supercomputer provides 3.5 million node-hours per year under a co-investment governance model split equally between the U.S. Department of Energy and AMD.[1][3] Approximately half of Lux's annual node-hours are dedicated to the DOE's Genesis Mission for open scientific discovery, while the remaining half are allocated to AMD for technology development and testing and for paid access by public- and private-sector partners under the DOE User Facility rate.[1][3]

For paid proprietary or partner allocations, OLCF requires a minimum commitment of 175,000 node-hours per six-month period, with project durations ranging from six months to five years and flexible start dates in any month.[3] According to OLCF, a 175,000-node-hour commitment supports workloads such as 400-node (3,200-GPU) runs totaling 18 days over a six-month window or approximately 40 nodes of continuous execution for six months.[3] Partner jobs can scale from single-node runs up to nearly the full system, though full-system jobs are capped slightly below 4,000 GPUs to account for nodes reserved for persistent services.[3]

As of 2026-11-23, Lux operates under DOE Moderate security controls, the same security baseline used on Frontier, which permits export-controlled applications and data.[3] OLCF has announced plans to add DOE Moderate-Enhanced controls on Lux, which would extend eligibility to workloads governed by International Traffic in Arms Regulations (ITAR) and Protected Health Information (PHI) under HIPAA.[3]

## Lux Supercomputer role in the DOE Genesis Mission and scientific workloads

The Lux Supercomputer serves as the first dedicated AI Factory and major computing infrastructure addition for the U.S. Department of Energy's Genesis Mission, a national initiative integrating supercomputing, AI foundation models, quantum systems, and experimental facilities across the DOE's 17 national laboratories.[1][2][5] Within the Genesis Mission, ORNL also leads the American Science Cloud (AmSC), a federated discovery platform connecting laboratory computing, data, and high-performance networks.[2]

In the November 16, 2026 launch announcements, ORNL and AMD detailed three flagship Genesis Mission research allocations running on Lux:[1][2][5][8]

- Fusion power plant design (FADO): the Fusion Agentic Design Orchestrator uses agentic AI workflows to combine high-fidelity plasma and engineering simulations, robotic maintenance system design, and reliability, availability, maintainability, and inspectability (RAMI) criteria for fusion pilot plants.[1][5][8]
- Materials development and advanced manufacturing: an AI foundation model factory that trains custom multimodal foundation models for U.S. industry, including predicting and designing alloy microstructures for 3D-printed and additively manufactured components.[1][5][8]
- Earth system and long-range water prediction: an AI forecasting project predicting water availability, streamflow, and river temperature weeks to years in advance to guide hydropower generation and thermoelectric power plant cooling across the Tennessee Valley Authority (TVA) region.[1][5][8]

According to ORNL's November 16, 2026 release, ORNL researchers lead six additional Genesis Mission projects and participate in 30 multi-institutional projects in the mission's first phase, and lead six further projects in the mission's second phase.[1][2]

## Frequently asked questions

### What is the Lux Supercomputer and where is it located?

Lux is an AMD-powered Super Intelligence (SI, the U.S. federal designation for artificial intelligence under Executive Order 14434) and high-performance computing (HPC) supercomputer operated by the Oak Ridge Leadership Computing Facility (OLCF) at the U.S. Department of Energy's Oak Ridge National Laboratory in Oak Ridge, Tennessee. Built by Hewlett Packard Enterprise (HPE) under a public-private co-investment partnership between the DOE and AMD, Lux opened to scientific users on November 16, 2026. [1][2][4][5]

### What is Lux's TOP500 ranking and peak performance?

On the 68th edition of the TOP500 list released on November 16, 2026, Lux debuted at No. 14 worldwide with a High Performance Linpack (HPL) benchmark score of 220.79 petaflops. As of 2026-11-23, OLCF system specifications also list theoretical system peak capacities of 317 petaflops at FP64 for modeling and simulation, 20 exaflops at FP8 for AI training, and 40 exaflops at FP4 for AI inference. [1][3][5]

### What hardware and processors does each Lux compute node use?

As of 2026-11-23, the OLCF Lux User Guide documents 504 HPE ProLiant Compute XD685 nodes and 4,032 AMD Instinct MI355X GPUs. Each compute node contains two 64-core AMD EPYC 9575F CPUs with 3 TB of DDR5 system memory, eight AMD Instinct MI355X GPUs (each with 288 GB of HBM3E memory at 8 TB/s bandwidth and eight Accelerated Compute Dies), eight 3.2 TB local NVMe SSDs (over 24 TB per node), and 400G Ultra Ethernet AMD Pensando NICs. [3][4][5]

### How is computing time on Lux allocated between the Genesis Mission and partners?

OLCF allocates approximately half of Lux's 3.5 million annual node-hours to the U.S. Department of Energy's Genesis Mission for open scientific discovery, while the remaining half is available to AMD for development and testing and to public or private partners for paid proprietary use under the DOE User Facility rate. Paid partner allocations require a minimum commitment of 175,000 node-hours per six months and can run from six months to five years under DOE Moderate security controls. [1][3]

### Which operating system, schedulers, and storage systems does Lux support?

Lux runs Red Hat Enterprise Linux (RHEL) 9.8 with the AMD ROCm open software stack and divides its nodes between a Slurm partition for traditional batch HPC jobs and a Kubernetes partition for containerized AI training, inference, and agentic orchestration. All allocations include access to OLCF's Orion Lustre parallel file system (679 PB usable namespace on HPE ClusterStor) and the Kronos nearline archival storage system. [1][3][4]

### What scientific research projects run on the Lux Supercomputer?

In announcements on November 16, 2026, ORNL and AMD highlighted three initial Genesis Mission projects allocated on Lux: the Fusion Agentic Design Orchestrator (FADO) for integrating HPC simulation and robotic maintenance into fusion power plant design; an AI foundation model factory for materials development and advanced manufacturing (such as 3D-printed alloy microstructures); and an Earth system prediction project forecasting water availability, streamflow, and river temperature in the Tennessee Valley Authority region. [1][2][5][8]

## Quotable sentences

- The Lux Supercomputer opened to scientific users at the U.S. Department of Energy's Oak Ridge National Laboratory on November 16, 2026, debuting at No. 14 on the 68th TOP500 list with 220.79 petaflops of High Performance Linpack performance. [1][2][5]
- As of 2026-11-23, the OLCF Lux User Guide documents that Lux consists of 504 HPE ProLiant Compute XD685 nodes housing a total of 4,032 AMD Instinct MI355X GPUs and dual 64-core AMD EPYC 9575F CPUs per node. [4]
- Each AMD Instinct MI355X GPU in Lux contains 288 GB of HBM3E memory with 8 TB/s peak memory bandwidth across 8 Accelerated Compute Dies (256 compute units), giving the system approximately 1.1 petabytes of total HBM3E capacity. [3][4]
- As of 2026-11-23, the Oak Ridge Leadership Computing Facility rates Lux at 40 exaflops peak for FP4 AI inference, 20 exaflops peak for FP8 AI training, and 317 petaflops peak for FP64 high-performance computing modeling and simulation. [3]
- Half of Lux's annual 3.5 million node-hours are dedicated to the U.S. Department of Energy's Genesis Mission, while the remaining half are reserved for AMD and paid proprietary or public-sector partner allocations starting at 175,000 node-hours per six-month commitment. [1][3]
- Lux compute nodes run Red Hat Enterprise Linux 9.8, divide resources between Slurm and Kubernetes scheduling partitions, include eight 3.2 TB local NVMe drives per node, and mount OLCF's Orion Lustre parallel file system (679 PB usable namespace). [3][4]
- Early Genesis Mission allocations on Lux include the Fusion Agentic Design Orchestrator (FADO) for fusion power plant design, a foundation model factory for materials and advanced manufacturing, and long-range water and streamflow prediction for the Tennessee Valley Authority region. [1][2][5][8]
- The U.S. Department of Energy, ORNL, AMD, and HPE announced the Lux and Discovery supercomputer projects on October 27, 2025, under a public-private co-investment partnership. [6]

## Timeline

- 2025-10-27: The U.S. Department of Energy, Oak Ridge National Laboratory, AMD, and HPE announce the Lux and Discovery supercomputer projects. [6]
- 2026-11-16: The Lux Supercomputer opens to scientific users at ORNL as the first AI Factory for the DOE's Genesis Mission and debuts at No. 14 on the 68th TOP500 list with 220.79 petaflops. [1][2][5]
- 2028: Scheduled delivery year for Discovery, ORNL's next HPE Cray GX5000 flagship supercomputer announced alongside Lux. [1][6]

## Sources

1. Lux SI+HPC Supercomputer Debuts in the Top500, Advances Genesis Mission Goals – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). published 2026-11-16. https://www.olcf.ornl.gov/2026/11/16/lux-genesis-mission/ (checked 2026-11-23; tier 1: government or public registry)
2. Lux SI+HPC supercomputer debuts in the Top500, advances Genesis Mission goals – Oak Ridge National Lab. Oak Ridge National Laboratory. published 2026-11-16. https://www.ornl.gov/news/lux-sihpc-supercomputer-debuts-in-the-top500-advances-genesis-mission-goals/ (checked 2026-11-23; tier 1: government or public registry)
3. Lux – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). https://www.olcf.ornl.gov/olcf-resources/compute-systems/lux/ (checked 2026-11-23; tier 1: government or public registry)
4. Lux User Guide - OLCF User Documentation. Oak Ridge Leadership Computing Facility (ORNL). https://docs.olcf.ornl.gov/systems/lux_user_guide.html (checked 2026-11-23; tier 1: government or public registry)
5. Lux Supercomputer Opens to Scientific Users at Oak Ridge - AMD Newsroom. Advanced Micro Devices (AMD). published 2026-11-16. https://newsroom.amd.com/news/amd-powered-lux-supercomputer-opens-scientific-users/ (checked 2026-11-23; tier 3: official site)
6. ORNL, AMD, and HPE to Deliver DOE’s Newest AI Supercomputers: Discovery and Lux – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). published 2025-10-27. https://www.olcf.ornl.gov/2025/10/27/ornl-amd-and-hpe-to-deliver-does-newest-ai-supercomputers-discovery-and-lux/ (checked 2026-11-23; tier 1: government or public registry)
7. Oak Ridge National Laboratory unveils Lux supercomputer - DCD. Data Center Dynamics. published 2026-11-17. https://www.datacenterdynamics.com/en/news/oak-ridge-national-laboratory-unveils-lux-supercomputer/ (checked 2026-11-23; tier 2: academic or news)
8. AMD opens up its new Lux supercomputer, powering everything from nuclear fusion to weather predictions | TechRadar. TechRadar. published 2026-11-21. https://www.techradar.com/pro/amd-opens-up-its-new-lux-supercomputer-powering-everything-from-nuclear-fusion-to-weather-predictions (checked 2026-11-23; tier 2: academic or news)

## Cite this page

Mimirwiki. "Lux Supercomputer." Version 8707bcac, 2026-11-23. https://mimirwiki.com/wiki/lux-supercomputer
