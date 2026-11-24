---
title: "럭스 슈퍼컴퓨터"
subtitle: "미국 오크리지 국립연구소(ORNL)에 구축된 AMD 기반 인공지능 및 고성능 컴퓨팅 슈퍼컴퓨터"
canonical_url: https://mimirwiki.com/ko/wiki/lux-supercomputer
language: ko
page_class: entity
revision_sha256: 4d01a7042adea4542d0b0a8c6a43937f3b820610dce851ac2a76679629125a92
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/ko/wiki/lux-supercomputer.md
  txt: https://mimirwiki.com/ko/wiki/lux-supercomputer.txt
  json: https://mimirwiki.com/ko/wiki/lux-supercomputer.json
  jsonld: https://mimirwiki.com/ko/wiki/lux-supercomputer.jsonld
translations:
  en: https://mimirwiki.com/wiki/lux-supercomputer
  ja: https://mimirwiki.com/ja/wiki/lux-supercomputer
  zh: https://mimirwiki.com/zh/wiki/lux-supercomputer
---

# 럭스 슈퍼컴퓨터

> 럭스 슈퍼컴퓨터(Lux Supercomputer)는 미국 에너지부 산하 오크리지 국립연구소(ORNL)에 설치된 AMD 기반 인공지능 및 고성능 컴퓨팅 시스템으로 휴렛팩커드 엔터프라이즈(HPE)가 제작했다. 2026년 11월 16일 과학 연구자에게 개방되었으며, 같은 날 발표된 2026년 11월 TOP500 목록에서 HPL 성능 220.79페타플롭스로 14위에 올랐다. 2026-11-23 기준 HPE ProLiant Compute XD685 노드 504대와 AMD Instinct MI355X GPU 4,032개로 구성되어 미국 에너지부의 제네시스 미션을 지원한다.

럭스 슈퍼컴퓨터(Lux Supercomputer, 공식 명칭 Lux SI+HPC Supercomputer)는 미국 테네시주 오크리지에 있는 미국 에너지부(DOE) 산하 오크리지 국립연구소(ORNL)의 오크리지 리더십 컴퓨팅 시설(Oak Ridge Leadership Computing Facility, OLCF)이 운영하는 인공지능 및 고성능 컴퓨팅(High-Performance Computing, HPC) 클러스터이다. 미국 에너지부, AMD(Advanced Micro Devices), 휴렛팩커드 엔터프라이즈(Hewlett Packard Enterprise, HPE)의 민관 공동 투자 파트너십을 통해 구축되었으며, 2026년 11월 16일 DOE 제네시스 미션(Genesis Mission)의 첫 전용 AI 팩토리(AI Factory)로 과학 연구자들에게 개방되었다. 같은 날 발표된 제68회 TOP500 슈퍼컴퓨터 목록에서는 고성능 린팩(High Performance Linpack, HPL) 기준 220.79페타플롭스(초당 22경 790조 회의 부동소수점 연산)를 기록해 세계 14위로 진입했다. 2026-11-23 기준 OLCF 기술 문서에 따르면 럭스는 노드당 64코어 AMD EPYC 9575F 프로세서 2개와 AMD Instinct MI355X GPU 8개를 장착한 HPE ProLiant Compute XD685 서버 504대(총 4,032개 GPU, 약 1.1페타바이트 HBM3E 메모리)로 구성되며, FP64 기준 317페타플롭스, FP8 기준 20엑사플롭스, FP4 기준 40엑사플롭스의 최대 이론 성능을 제공한다.

**다른 이름:** Lux, Lux Supercomputer, Lux SI+HPC Supercomputer, AMD Lux SI Cluster, ORNL Lux

## 핵심 정보

- **운영 기관 및 위치:** 미국 테네시주 오크리지 국립연구소(ORNL) 오크리지 리더십 컴퓨팅 시설(OLCF) [1]
- **TOP500 진입 성적:** 2026년 11월 제68회 TOP500 14위(HPL 220.79페타플롭스) (기준 2026-11-16) [1]
- **시스템 구성:** HPE ProLiant Compute XD685 노드 504대, AMD EPYC 9575F CPU 1,008개, AMD Instinct MI355X GPU 4,032개 (기준 2026-11-23) [4]
- **최대 이론 성능:** FP4 추론 40 EFLOPS, FP8 학습 20 EFLOPS, FP64 시뮬레이션 317 PFLOPS (기준 2026-11-23) [3]
- **연간 연산 자원 배분:** 연간 350만 노드시간: 50% DOE 제네시스 미션, 50% AMD 및 유료 파트너 배정 (기준 2026-11-23) [3]

## 기본 정보

- **운영 시설 및 위치:** 미국 테네시주 오크리지 국립연구소(ORNL) 산하 오크리지 리더십 컴퓨팅 시설(OLCF) [1]
- **주관 및 제작:** 미국 에너지부(DOE), AMD, 휴렛팩커드 엔터프라이즈(HPE) [1]
- **구축 계획 발표:** 2025-10-27(2028년 도입 예정인 Discovery와 동시 발표) [6]
- **과학 연구자 개방:** 2026-11-16 [1]
- **TOP500 순위:** 제68회 TOP500(2026년 11월) 세계 14위(HPL 220.79페타플롭스) (기준 2026-11-16) [1]
- **노드 수 및 서버 플랫폼:** HPE ProLiant Compute XD685 노드 504대 (기준 2026-11-23) [4]
- **노드당 CPU 및 메모리:** 64코어 AMD EPYC 9575F CPU 2개, DDR5 메모리 3 TB(8개 NUMA 도메인) (기준 2026-11-23) [4]
- **GPU 및 HBM 총용량:** AMD Instinct MI355X GPU 4,032개(노드당 8개, GPU당 8 TB/s 288 GB HBM3E, 총 약 1.1 PB HBM) (기준 2026-11-23) [4]
- **시스템 최대 이론 성능:** FP64 HPC 317 PFLOPS, FP8 AI 학습 20 EFLOPS, FP4 AI 추론 40 EFLOPS (기준 2026-11-23) [3]
- **인터커넥트 및 스토리지:** GPU당 AMD Pensando 400G Ultra Ethernet NIC; 노드당 3.2 TB NVMe 8개; 679 PB Orion Lustre 파일 시스템 (기준 2026-11-23) [3]
- **운영체제 및 스케줄러:** Red Hat Enterprise Linux (RHEL) 9.8; AMD ROCm; Slurm 및 Kubernetes 파티션 (기준 2026-11-23) [4]
- **연간 가용 자원 및 배분:** 연간 350만 노드시간(50% DOE 제네시스 미션, 50% AMD 및 유료 파트너 배정) (기준 2026-11-23) [3]

## 럭스 슈퍼컴퓨터 개요, 민관 파트너십 및 TOP500 진입

럭스 슈퍼컴퓨터(Lux Supercomputer)는 미국 테네시주 오크리지의 오크리지 국립연구소(ORNL) 내 미국 에너지부(DOE) 과학국 사용자 시설인 오크리지 리더십 컴퓨팅 시설(OLCF)에 설치된 인공지능 및 고성능 컴퓨팅(HPC) 시스템이다.[1][2] 2026년 하반기 미국 연방 기관 및 ORNL 공식 발표에서는 행정명령 제14434호에 따라 인공지능(AI) 대신 초지능(Super Intelligence, SI)이라는 용어를 사용하여 이 시스템을 'SI+HPC 슈퍼컴퓨터'로 표기한다.[1][2][7] 럭스는 2022년 세계 최초로 엑사스케일(exascale) 장벽을 돌파하고 2026년 11월 TOP500 목록에서 1.353엑사플롭스로 세계 3위를 유지한 OLCF의 플래그십 시스템 프런티어(Frontier, HPE Cray EX235a)와 나란히 운영된다.[1][3]

DOE, ORNL, AMD, HPE는 2025년 10월 27일 2028년 도입 예정인 차세대 플래그십 슈퍼컴퓨터 디스커버리(Discovery, HPE Cray Supercomputing GX5000 기반)와 함께 럭스 구축 계획을 처음 발표했다.[1][6] 수년이 걸리는 기존 대형 슈퍼컴퓨터 조달 절차와 달리, 럭스는 단기 과학용 AI 연산 역량을 신속히 확충하기 위해 DOE와 AMD가 공동 투자하는 민관 파트너십 모델로 추진되어 발표 후 약 1년 만에 구축과 개방을 마쳤다.[1][3][8]

2026년 11월 16일 ORNL과 AMD는 럭스가 과학 연구자들에게 공식 개방되었으며 같은 날 발표된 제68회 TOP500 세계 슈퍼컴퓨터 목록에서 14위로 진입했다고 발표했다.[1][2][5] TOP500 순위 산정에 쓰이는 고성능 린팩(High Performance Linpack, HPL) 벤치마크에서 럭스는 OLCF가 공시한 FP64 이론적 최대 성능 317페타플롭스 대비 약 70% 효율에 해당하는 220.79페타플롭스(초당 22경 790조 회 연산)를 기록했다.[1][3][8] OLCF는 2004년 설립 이후 총 7대의 플래그십 슈퍼컴퓨터를 구축했으며, 이 가운데 재규어(Jaguar), 타이탄(Titan, 2012년), 서밋(Summit, 2018년), 프런티어(Frontier, 2022년) 4대가 도입 당시 세계 1위를 기록한 바 있다.[1][3][6]

## 럭스 슈퍼컴퓨터 하드웨어 아키텍처와 노드 사양

럭스 슈퍼컴퓨터는 AMD 프로세서, 가속기, 네트워크 장비를 탑재한 직접 수랭식 HPE ProLiant Compute XD685 서버 노드를 기반으로 구축되었다.[1][4][8] 2026-11-23 기준 OLCF 럭스 사용자 설명서(Lux User Guide)에 따르면 전체 시스템은 504개 노드와 4,032개 GPU로 구성되며, 접속 및 작업 제출용 로그인 노드(`lux.olcf.ornl.gov`의 `login1`~`login3`)와 병렬 연산용 계산 노드로 구분된다.[4] 각 계산 노드는 64코어 AMD EPYC 9575F CPU 2개(노드당 128코어)와 3 TB의 DDR5 시스템 메모리를 갖추고 있으며, 8개의 불균일 기억 장치 접근(NUMA) 도메인으로 나뉘어 각 도메인이 하드웨어 스레드 16개와 GPU 1개에 일대일로 매핑된다.[4]

504개 노드 각각에는 8개의 AMD Instinct MI355X GPU가 장착되어 시스템 전체로 4,032개의 가속기를 제공한다.[4] 개별 MI355X GPU는 8개의 가속 연산 다이(Accelerated Compute Dies, XCD)에 걸친 256개 연산 유닛(노드당 64개 XCD)과 최대 8 TB/s 대역폭을 내는 288 GB의 HBM3E 고대역폭 메모리를 내장하여, 클러스터 전체에 약 1.1페타바이트의 HBM3E 메모리를 형성한다.[3][4] 노드 내부의 GPU 8개는 양방향 최대 153.6 GB/s 대역폭의 AMD Infinity Fabric GPU 간 연결로 묶여 있다.[4] 노드 간 네트워크는 GPU마다 하나씩 배정된 400G Ultra Ethernet 규격의 AMD Pensando 네트워크 인터페이스 카드(NIC)와 HPE Juniper Networking 스위치로 구성된다.[3][5][8]

| 사양 항목 | 노드당 / GPU당 사양 | 전체 시스템 사양 (504개 노드, 4,032개 GPU) |
| --- | --- | --- |
| 서버 플랫폼 | HPE ProLiant Compute XD685 | 504대(로그인 노드 및 계산 노드 포함) |
| 호스트 CPU 및 메모리 | 64코어 AMD EPYC 9575F 2개, 3 TB DDR5 RAM | CPU 1,008개(64,512코어), DDR5 약 1.5 PB |
| GPU 가속기 | AMD Instinct MI355X 8개(GPU당 8 XCD, 256 CU) | MI355X GPU 4,032개(32,256 XCD) |
| 고대역폭 메모리(HBM) | GPU당 288 GB HBM3E(대역폭 8 TB/s) | 총 약 1.1 PB HBM3E |
| 노드 내·노드 간 연결 | 153.6 GB/s Infinity Fabric; GPU당 400G Ultra Ethernet NIC | 400G AMD Pensando Ultra Ethernet NIC 4,032개 |
| FP64 HPC 성능 | GPU당 벡터 FP64 78.6 TFLOPS(개요 페이지 78 TF 표기) | 이론 피크 317 PFLOPS; HPL 실측 220.79 PFLOPS |
| 저정밀도 AI 성능 | GPU당 벡터 FP16 157.3 TFLOPS; FP8 학습 5 PFLOPS | FP8 학습 20 EFLOPS; FP4 추론 40 EFLOPS |
| 노드 로컬 스토리지 | 3.2 TB NVMe SSD 8개(노드당 24 TB 이상) | 총 12 PB 이상의 로컬 NVMe 스토리지 |

2026-11-23 기준 OLCF 사용자 설명서와 시스템 개요에 따르면 개별 AMD Instinct MI355X GPU는 모델링 및 시뮬레이션용 벡터 배정밀도(FP64) 연산에서 78.6테라플롭스(개요 페이지에는 78 TF로 표기), 벡터 반정밀도(FP16) 연산에서 157.3테라플롭스, FP8 AI 학습 연산에서 5페타플롭스의 피크 성능을 낸다.[3][4] 이를 합산한 시스템 전체 피크 성능은 FP64 HPC 317페타플롭스, FP8 AI 학습 20엑사플롭스, FP4 AI 추론 40엑사플롭스로 공시되어 있다.[3]

## 럭스 슈퍼컴퓨터 소프트웨어 환경, 스케줄링 및 스토리지

럭스 슈퍼컴퓨터는 운영체제로 Red Hat Enterprise Linux(RHEL) 9.8 버전을 구동하며 AMD ROCm 오픈 소프트웨어 스택과 ROCr 런타임을 사용한다. 이 환경에서 각 AMD Instinct MI355X는 스케줄러와 `ROCR_VISIBLE_DEVICES`에 개별 GPU로 인식된다.[1][4] 전통적인 슈퍼컴퓨팅 시뮬레이션과 클라우드 네이티브 AI 워크로드를 동시에 수용하기 위해 OLCF는 럭스의 계산 노드를 Slurm(HPC) 파티션과 Kubernetes 파티션으로 나누어 운영하며, 두 파티션의 규모는 사용자 수요에 따라 유동적으로 조정된다.[1][3][4]

고속 로컬 입출력을 위해 각 계산 노드에는 3.2 TB 용량의 비휘발성 메모리 익스프레스(NVMe) SSD 8개가 장착되어 노드당 24 TB 이상의 로컬 스토리지를 제공한다.[3][4] 공유 병렬 스토리지로는 HPE ClusterStor 하드웨어와 Lustre 기반의 OLCF 공용 병렬 파일 시스템인 오리온(Orion, 마운트 경로 `/lustre/orion/`)이 연결되어 있다.[3][4] OLCF 시스템 개요 페이지는 오리온의 용량을 600페타바이트 이상으로 안내하며, 럭스 사용자 설명서는 파일 크기가 커질수록 스트라이핑(striping) 구성을 자동 조정하는 점진적 파일 레이아웃(Progressive File Layout, PFL) 기능과 함께 가용 네임스페이스를 679 PB로 명시한다.[3][4]

오리온 파일 시스템은 럭스뿐만 아니라 프런티어(Frontier), 라이커(Riker) 클러스터, OLCF 데이터 전송 노드에서 동시에 마운트된다. 따라서 프런티어와 럭스 두 시스템에 모두 할당량을 보유한 연구팀은 프런티어에서 대규모 시뮬레이션 데이터셋을 생성해 오리온에 직접 기록한 뒤 별도의 외부 데이터 전송 없이 럭스에서 곧바로 AI 모델을 학습시킬 수 있다.[3][4] 이 밖에 럭스 사용자에게는 홈 및 프로젝트 디렉터리용 센터 공용 NFS 파일 시스템과 근거리 아카이브 스토리지 시스템인 크로노스(Kronos)가 함께 제공된다.[4]

## 럭스 슈퍼컴퓨터 자원 배분 정책, 유료 파트너십 및 보안 통제

럭스 슈퍼컴퓨터는 연간 총 350만 노드시간(node-hours)의 연산 자원을 제공하며, DOE와 AMD의 공동 투자 모델에 따라 절반씩 나뉘어 배분된다.[1][3] 연간 노드시간의 약 절반은 미국 에너지부의 제네시스 미션(Genesis Mission)을 통한 개방형 과학 연구에 배정되고, 나머지 절반은 AMD의 자체 기술 개발·검증과 DOE 사용자 시설 요율(DOE User Facility rate)에 따른 공공·민간 부문 파트너의 유료 전용(proprietary) 사용에 배정된다.[1][3]

유료 파트너 할당을 신청하려면 6개월당 최소 17만 5,000노드시간 이상을 약정해야 하며, 프로젝트 기간은 6개월에서 최대 5년까지로 어느 달에나 시작할 수 있다.[3] OLCF에 따르면 6개월간 17만 5,000노드시간을 약정할 경우 6개월 동안 총 18일 분량의 400노드(3,200 GPU) 대규모 작업을 실행하거나 약 40개 노드를 6개월 내내 연속으로 사용할 수 있다.[3] 파트너는 단일 노드 작업부터 전체 시스템 규모 작업까지 자유롭게 자원을 소비할 수 있으나, 상시 서비스용으로 예약된 노드 때문에 단일 작업의 최대 크기는 4,000개 미만의 GPU로 제한될 수 있다.[3]

2026-11-23 기준 럭스는 프런티어와 동일한 수준인 DOE 중등도(Moderate) 보안 통제를 적용해 수출 통제(export-controlled) 대상 애플리케이션과 데이터를 처리할 수 있다.[3] OLCF는 향후 럭스에 DOE 중등도 강화(Moderate-Enhanced) 보안 통제를 추가하여 국제무기거래규정(ITAR) 적용 데이터와 미국 의료보험 이동성 및 책임에 관한 법률(HIPAA)상의 보호대상 건강정보(PHI) 워크로드까지 지원할 계획이다.[3]

## 럭스 슈퍼컴퓨터의 DOE 제네시스 미션 역할과 주요 과학 워크로드

럭스 슈퍼컴퓨터는 미국 에너지부(DOE) 산하 17개 국립연구소의 슈퍼컴퓨팅, AI 파운데이션 모델, 양자 시스템, 첨단 실험 장비를 통합하는 국가 과학 이니셔티브인 제네시스 미션(Genesis Mission)의 첫 주요 컴퓨팅 인프라 확충이자 첫 전용 AI 팩토리 역할을 맡고 있다.[1][2][5] ORNL은 제네시스 미션 내에서 17개 국립연구소의 컴퓨팅 시설과 데이터 자원, 초고속 네트워크를 연합 형태로 묶는 미국 과학 클라우드(American Science Cloud, AmSC) 구축도 주도하고 있다.[2]

2026년 11월 16일 개방 발표에서 ORNL과 AMD는 럭스에서 수행되는 제네시스 미션의 대표 연구 과제 세 가지를 공개했다.[1][2][5][8]

- 핵융합 발전소 설계(FADO): 핵융합 에이전트형 설계 오케스트레이터(Fusion Agentic Design Orchestrator, FADO)는 고성능 컴퓨팅 시뮬레이션과 로봇 유지보수 시스템 설계, 신뢰성·가용성·유지보수성·검사성(RAMI) 지표를 통합해 상용 핵융합 실증로 설계를 자동화한다.[1][5][8]
- 신소재 개발 및 첨단 제조: 미국 산업계가 활용할 수 있도록 적층 제조(3D 프린팅) 합금의 미세구조 설계 등을 위한 맞춤형 파운데이션 모델을 생성하는 '파운데이션 모델 팩토리(foundation model factory)'를 구축한다.[1][5][8]
- 지구 시스템 및 장기 수자원 예측: 테네시강 유역청(Tennessee Valley Authority, TVA) 권역의 수력 발전 및 화력 발전소 운영을 지원하기 위해 수자원 가용량, 하천 유량, 수온을 수주에서 수년 앞서 예측한다.[1][5][8]

2026년 11월 16일 ORNL 발표에 따르면 ORNL 연구진은 제네시스 미션 1단계에서 위 과제 외에 6개 프로젝트를 직접 주도하고 타 국립연구소·대학·산업계가 주도하는 30개 프로젝트에 참여하고 있으며, 최근 발표된 2단계에서도 6개 프로젝트를 추가로 주도하고 있다.[1][2]

## 자주 묻는 질문

### 럭스 슈퍼컴퓨터는 어떤 시스템이며 어디에 설치되어 있나요?

럭스 슈퍼컴퓨터(Lux Supercomputer)는 미국 테네시주 오크리지에 위치한 미국 에너지부(DOE) 산하 오크리지 국립연구소(ORNL)의 오크리지 리더십 컴퓨팅 시설(OLCF)이 운영하는 인공지능(미국 연방 정부 행정명령 제14434호에 따른 공식 명칭은 초지능, Super Intelligence, SI) 및 고성능 컴퓨팅(HPC) 슈퍼컴퓨터입니다. DOE와 AMD의 민관 공동 투자 파트너십에 따라 휴렛팩커드 엔터프라이즈(HPE)가 제작했으며, 2026년 11월 16일 과학 연구자들에게 개방되었습니다. [1][2][4][5]

### 럭스의 TOP500 순위와 최대 연산 성능은 어느 정도인가요?

2026년 11월 16일 발표된 제68회 TOP500 목록에서 럭스는 고성능 린팩(HPL) 벤치마크 기준 220.79페타플롭스를 기록해 세계 14위로 진입했습니다. 2026-11-23 기준 OLCF 시스템 사양표는 이와 함께 FP64 모델링 및 시뮬레이션 최대 317페타플롭스, FP8 AI 학습 최대 20엑사플롭스, FP4 AI 추론 최대 40엑사플롭스의 이론적 피크 성능을 명시하고 있습니다. [1][3][5]

### 럭스 계산 노드에는 어떤 하드웨어와 프로세서가 탑재되어 있나요?

2026-11-23 기준 OLCF 럭스 사용자 설명서에 따르면 럭스는 직접 수랭식 HPE ProLiant Compute XD685 서버 노드 504대와 AMD Instinct MI355X GPU 4,032개로 구성됩니다. 각 계산 노드에는 64코어 AMD EPYC 9575F CPU 2개와 3 TB DDR5 메모리, 8 TB/s 대역폭의 288 GB HBM3E 메모리 및 가속 연산 다이(XCD) 8개를 갖춘 MI355X GPU 8개, 3.2 TB 로컬 NVMe SSD 8개(노드당 24 TB 이상), 그리고 GPU당 400G Ultra Ethernet AMD Pensando 네트워크 카드를 탑재하고 있습니다. [3][4][5]

### 럭스의 연산 시간은 제네시스 미션과 외부 파트너 사이에 어떻게 배분되나요?

OLCF는 연간 350만 노드시간(node-hours)에 달하는 럭스 가용 자원의 절반을 미국 에너지부의 제네시스 미션(Genesis Mission) 과학 연구에 배정하고, 나머지 절반을 AMD의 기술 개발·검증과 DOE 사용자 시설 요율에 따른 공공·민간 파트너의 유료 전용 과제로 배정합니다. 유료 파트너 과제는 DOE 중등도(Moderate) 보안 통제 아래 6개월당 최소 17만 5,000노드시간 이상을 약정해야 하며, 6개월에서 최대 5년까지 이용할 수 있습니다. [1][3]

### 럭스는 어떤 운영체제, 작업 스케줄러, 스토리지를 지원하나요?

럭스는 Red Hat Enterprise Linux(RHEL) 9.8 운영체제와 AMD ROCm 오픈 소프트웨어 스택을 구동하며, 전통적인 배치 HPC 작업용 Slurm 파티션과 컨테이너 기반 AI 학습·추론 및 에이전트 오케스트레이션용 Kubernetes 파티션으로 자원을 나누어 운영합니다. 모든 배정 과제는 HPE ClusterStor 기반의 679 PB 가용 네임스페이스를 갖춘 Orion Lustre 병렬 파일 시스템과 Kronos 아카이브 스토리지를 함께 사용할 수 있습니다. [1][3][4]

### 럭스 슈퍼컴퓨터에서는 어떤 과학 연구 프로젝트가 수행되나요?

2026년 11월 16일 ORNL과 AMD 발표에서는 제네시스 미션의 초기 배정 과제로 세 가지가 소개되었습니다. 첫째는 시뮬레이션과 로봇 유지보수 설계를 결합해 핵융합 실증로를 설계하는 FADO(Fusion Agentic Design Orchestrator), 둘째는 3D 프린팅 합금 미세구조 등 신소재·첨단 제조용 맞춤형 모델을 구축하는 파운데이션 모델 팩토리, 셋째는 테네시강 유역청(TVA) 권역의 수력·화력 발전 운영을 위해 수자원 가용량과 하천 유량·수온을 수주에서 수년 앞서 예측하는 지구 시스템 예측 프로젝트입니다. [1][2][5][8]

## 인용 문장

- 럭스 슈퍼컴퓨터(Lux Supercomputer)는 2026년 11월 16일 미국 에너지부(DOE) 오크리지 국립연구소(ORNL)에서 과학 연구자들에게 개방되었으며, 같은 날 발표된 제68회 TOP500 목록에서 HPL 성능 220.79페타플롭스로 세계 14위에 올랐다. [1][2][5]
- 2026-11-23 기준 OLCF 럭스 사용자 설명서에 따르면 럭스는 HPE ProLiant Compute XD685 노드 504대로 구성되며, 노드당 64코어 AMD EPYC 9575F CPU 2개와 전체 4,032개의 AMD Instinct MI355X GPU를 탑재한다. [4]
- 럭스에 탑재된 각 AMD Instinct MI355X GPU는 8개의 가속 연산 다이(XCD, 총 256개 연산 유닛)와 8 TB/s 대역폭의 288 GB HBM3E 메모리를 갖추어 시스템 전체로 약 1.1페타바이트의 HBM3E 용량을 제공한다. [3][4]
- 2026-11-23 기준 오크리지 리더십 컴퓨팅 시설(OLCF)이 공시한 럭스의 이론적 최대 성능은 FP4 AI 추론 40엑사플롭스, FP8 AI 학습 20엑사플롭스, FP64 고성능 컴퓨팅(HPC) 모델링 및 시뮬레이션 317페타플롭스이다. [3]
- 럭스의 연간 가용 자원인 350만 노드시간(node-hours) 중 절반은 미국 에너지부의 제네시스 미션(Genesis Mission) 과학 연구에 배정되고, 나머지 절반은 AMD 및 최소 6개월간 17만 5,000노드시간 이상을 약정한 유료 파트너에 배정된다. [1][3]
- 럭스 계산 노드는 Red Hat Enterprise Linux 9.8 환경에서 Slurm과 Kubernetes 파티션으로 나뉘어 운영되며, 노드당 3.2 TB 로컬 NVMe SSD 8개와 679 PB 가용 네임스페이스를 갖춘 Orion Lustre 병렬 파일 시스템을 사용한다. [3][4]
- 럭스에 초기 배정된 제네시스 미션 연구 과제로는 핵융합 발전소 설계용 에이전트 오케스트레이터(FADO), 신소재 및 첨단 제조용 파운데이션 모델 팩토리, 테네시강 유역청(TVA) 권역의 중장기 수자원·하천 유량 예측 프로젝트가 있다. [1][2][5][8]
- 미국 에너지부, ORNL, AMD, HPE는 2025년 10월 27일 민관 공동 투자 파트너십을 통해 럭스(Lux)와 차세대 플래그십 슈퍼컴퓨터 디스커버리(Discovery) 구축 계획을 발표했다. [6]

## 연표

- 2025-10-27: 미국 에너지부(DOE), 오크리지 국립연구소(ORNL), AMD, HPE가 럭스(Lux)와 디스커버리(Discovery) 슈퍼컴퓨터 구축 계획을 발표했다. [6]
- 2026-11-16: 럭스 슈퍼컴퓨터가 DOE 제네시스 미션의 첫 AI 팩토리로 ORNL에서 과학 연구자들에게 개방되었으며, 제68회 TOP500 목록에서 220.79페타플롭스로 14위에 올랐다. [1][2][5]
- 2028: 럭스와 함께 발표된 ORNL의 차세대 HPE Cray GX5000 기반 플래그십 슈퍼컴퓨터 디스커버리(Discovery)가 도입될 예정이다. [1][6]

## 출처

1. Lux SI+HPC Supercomputer Debuts in the Top500, Advances Genesis Mission Goals – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). 게시일 2026-11-16. https://www.olcf.ornl.gov/2026/11/16/lux-genesis-mission/ (확인일 2026-11-23; tier 1: government or public registry)
2. Lux SI+HPC supercomputer debuts in the Top500, advances Genesis Mission goals – Oak Ridge National Lab. Oak Ridge National Laboratory. 게시일 2026-11-16. https://www.ornl.gov/news/lux-sihpc-supercomputer-debuts-in-the-top500-advances-genesis-mission-goals/ (확인일 2026-11-23; tier 1: government or public registry)
3. Lux – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). https://www.olcf.ornl.gov/olcf-resources/compute-systems/lux/ (확인일 2026-11-23; tier 1: government or public registry)
4. Lux User Guide - OLCF User Documentation. Oak Ridge Leadership Computing Facility (ORNL). https://docs.olcf.ornl.gov/systems/lux_user_guide.html (확인일 2026-11-23; tier 1: government or public registry)
5. Lux Supercomputer Opens to Scientific Users at Oak Ridge - AMD Newsroom. Advanced Micro Devices (AMD). 게시일 2026-11-16. https://newsroom.amd.com/news/amd-powered-lux-supercomputer-opens-scientific-users/ (확인일 2026-11-23; tier 3: official site)
6. ORNL, AMD, and HPE to Deliver DOE’s Newest AI Supercomputers: Discovery and Lux – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). 게시일 2025-10-27. https://www.olcf.ornl.gov/2025/10/27/ornl-amd-and-hpe-to-deliver-does-newest-ai-supercomputers-discovery-and-lux/ (확인일 2026-11-23; tier 1: government or public registry)
7. Oak Ridge National Laboratory unveils Lux supercomputer - DCD. Data Center Dynamics. 게시일 2026-11-17. https://www.datacenterdynamics.com/en/news/oak-ridge-national-laboratory-unveils-lux-supercomputer/ (확인일 2026-11-23; tier 2: academic or news)
8. AMD opens up its new Lux supercomputer, powering everything from nuclear fusion to weather predictions | TechRadar. TechRadar. 게시일 2026-11-21. https://www.techradar.com/pro/amd-opens-up-its-new-lux-supercomputer-powering-everything-from-nuclear-fusion-to-weather-predictions (확인일 2026-11-23; tier 2: academic or news)

## 이 문서 인용하기

Mimirwiki. "럭스 슈퍼컴퓨터." 버전 4d01a704, 2026-11-23. https://mimirwiki.com/ko/wiki/lux-supercomputer
