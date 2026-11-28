---
title: "SSD 기반 GPU 메모리 확장 (SSD-backed GPU Memory Expansion)"
subtitle: "고대역폭 메모리(HBM) 밖의 고속 NVMe SSD와 세밀한 접근 소프트웨어를 결합해 GPU가 다루는 유효 메모리 공간을 넓히는 아키텍처"
canonical_url: https://mimirwiki.com/ko/wiki/ssd-backed-gpu-memory
language: ko
page_class: concept
revision_sha256: 59ef3b7806e1067f70087bd12cfd54c6bb415b7953429ffbd67c84c94b8ec75c
date_modified: 2026-11-28
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 6
alternates:
  md: https://mimirwiki.com/ko/wiki/ssd-backed-gpu-memory.md
  txt: https://mimirwiki.com/ko/wiki/ssd-backed-gpu-memory.txt
  json: https://mimirwiki.com/ko/wiki/ssd-backed-gpu-memory.json
  jsonld: https://mimirwiki.com/ko/wiki/ssd-backed-gpu-memory.jsonld
translations:
  en: https://mimirwiki.com/wiki/ssd-backed-gpu-memory
---

# SSD 기반 GPU 메모리 확장 (SSD-backed GPU Memory Expansion)

> SSD 기반 GPU 메모리 확장은 고속 NVMe SSD와 세밀한 데이터 접근 소프트웨어를 결합해 HBM 용량 한계 너머의 대용량 데이터를 GPU가 다루도록 돕는 방식이다. 2026년 11월 키옥시아와 엔비디아는 GB200 NVL72 랙, 7.68TB XD8 SSD 144개(원시 용량 약 1.1PB), SCADA 소프트웨어로 2조 벡터 처리 개념검증을 발표했다.

SSD 기반 GPU 메모리 확장(SSD-backed GPU Memory Expansion)은 고대역폭 메모리(HBM)를 대체하지 않으면서도 GPU가 고속 NVMe SSD에 저장된 대용량 데이터를 직접 세밀하게 읽어 들일 수 있도록 해 유효 메모리 처리 범위를 넓히는 데이터센터 아키텍처이다. 키옥시아(Kioxia)와 엔비디아(NVIDIA)는 2026년 11월 25~27일(북미·일본·유럽 지역별 공지) NVIDIA GB200 NVL72 랙(서버 노드 18개), 키옥시아 XD8 시리즈 7.68TB E1.S NVMe SSD 144개(원시 저장 용량 약 1.1PB), 512바이트 단위 접근을 지원하는 NVIDIA SCADA 소프트웨어를 결합해 2조 벡터 데이터베이스 처리 가능성을 실증하는 개념검증(PoC)을 공개했다.

**다른 이름:** SSD-backed GPU Memory Expansion, SSD GPU 메모리 확장

## 핵심 정보

- **개념검증 랙 플랫폼:** NVIDIA GB200 NVL72 (서버 노드 18개) (기준 2026-11-26) [1]
- **SSD 원시 저장 용량:** 약 1.1PB (키옥시아 XD8 7.68TB E1.S NVMe SSD 144개) (기준 2026-11-26) [1]
- **소프트웨어 및 접근 단위:** NVIDIA SCADA (Scaled Accelerated Data Access), 512바이트 단위 접근 (기준 2026-11-27) [5]
- **업체 제시 목표 처리 규모:** 2조 벡터 데이터베이스 처리 가능성 실증 (기준 2026-11-26) [1]

## 기본 정보

- **기술 분류:** NVMe SSD 연계 유효 GPU 메모리 확장 계층 [1]
- **협력 기업:** 키옥시아(Kioxia) 및 엔비디아(NVIDIA) [1]
- **실증 랙 시스템:** NVIDIA GB200 NVL72 (서버 노드 18개) [4]
- **사용 SSD:** 키옥시아 XD8 시리즈 7.68TB EDSFF E1.S NVMe SSD 144개 (원시 용량 약 1.1PB) [6]
- **소프트웨어 계층:** NVIDIA SCADA / Storage-Next 이니셔티브 [1]
- **HBM과의 관계:** HBM 용량 한계 보완 (장착 HBM을 대체하지 않음) [5]

## HBM 용량 한계와 SSD 기반 확장의 배경

AI 서버는 GPU에 고대역폭 메모리(HBM)를 결합해 쓰지만, AI 데이터셋과 벡터 데이터베이스 규모가 커지면서 HBM만으로 전체 데이터를 담기 어려워졌다.[1][5] HBM만으로 초대형 데이터셋을 처리하면 작업을 작게 분할해 메모리와 느린 스토리지 사이를 반복 이동시켜야 하는 병목이 발생한다.[1]

SSD 기반 GPU 메모리 확장은 HBM을 없애는 대신 고속 엔터프라이즈 NVMe SSD와 GPU 직접 접근 소프트웨어를 결합해 용량 집약적인 데이터를 SSD 계층에 두고 필요한 부분만 빠르게 불러오는 보완 아키텍처이다.[1][5]

## 2026년 11월 키옥시아-엔비디아 실증의 1.1PB 용량 의미

키옥시아는 2026년 11월 25일(북미), 26일(일본), 27일(유럽) 지역별 보도자료를 통해 엔비디아의 Storage-Next 이니셔티브를 지원하는 공동 개념검증(PoC)을 발표했다(세 공지는 동일 실증의 지역별 발표이다).[1][2][3]

| 실증 구성 요소 | 사양 | 해석상 유의점 |
| --- | --- | --- |
| 랙 시스템 | NVIDIA GB200 NVL72 (서버 노드 18개) | 랙 단위 AI 서버 플랫폼 |
| SSD 구성 | 키옥시아 XD8 시리즈 7.68TB E1.S NVMe SSD 144개 | 약 1.1PB는 SSD 원시 저장 용량(장착 HBM 용량 아님) |
| 접근 소프트웨어 | NVIDIA SCADA (Scaled Accelerated Data Access) | 512바이트 단위 세밀한 데이터 요청 지원 |
| 목표 워크로드 | 2조 벡터 데이터베이스 | 업체가 제시한 처리 가능 규모 |

실증에 제시된 약 1.1PB는 OCP 데이터센터 NVMe 규격의 EDSFF E1.S 폼팩터 XD8 SSD(개당 최대 7.68TB) 144개의 원시 저장 용량 합계이며, GPU에 장착된 HBM 용량이 아니다.[1][5][6]

## NVIDIA SCADA와 512바이트 단위 세밀한 접근

기존 스토리지 경로는 큰 블록 단위로 데이터를 읽어와 소규모 레코드만 필요한 AI 검색·벡터 작업에서 대역폭 비효율이 컸다.[5] 키옥시아와 트렌드포스(TrendForce)에 따르면 NVIDIA SCADA 라이브러리는 GPU가 NVMe SSD에서 512바이트 단위로 필요한 부분만 직접 요청해 가져올 수 있게 해 대규모 벡터 데이터베이스 처리 효율을 높이는 데 초점을 맞추었다.[1][5]

## 2026년 11월 기준 미확인 사항

2026년 11월 28일 기준 키옥시아-엔비디아 협력은 개념검증(PoC) 단계이며, 실제 서비스 환경에서의 응답 지연시간(latency), 독립 워크로드 벤치마크, 상용화 일정은 공개되지 않았다.[1][5]

## 자주 묻는 질문

### SSD 기반 GPU 메모리 확장이란 무엇인가요?

엔터프라이즈 NVMe SSD와 세밀한 GPU 데이터 접근 소프트웨어를 결합해, HBM 용량 한계 너머의 대용량 데이터를 GPU가 다룰 수 있도록 유효 메모리 공간을 넓히는 아키텍처입니다. [1][5]

### 키옥시아-엔비디아 실증의 약 1.1PB는 어떤 용량인가요?

NVIDIA GB200 NVL72 랙에 장착된 키옥시아 XD8 7.68TB E1.S NVMe SSD 144개의 원시 저장 용량 합계입니다. GPU에 탑재된 HBM 용량이 아니며 HBM을 대체하는 것도 아닙니다. [1][5][6]

### NVIDIA SCADA 소프트웨어는 어떤 역할을 하나요?

Scaled Accelerated Data Access의 약자로, GPU가 NVMe SSD에서 512바이트 단위로 필요한 데이터만 직접 요청해 가져올 수 있게 지원하는 소프트웨어 라이브러리입니다. [1][5]

### 실제 서비스 지연시간과 상용화 일정이 공개되었나요?

아니요. 2026년 11월 28일 기준 개념검증(PoC) 발표 단계이며, 실제 지연시간 수치와 상용화 일정은 미공개입니다. [1][5]

## 인용 문장

- 2026년 11월 25~27일 키옥시아와 엔비디아는 GB200 NVL72 랙, XD8 7.68TB E1.S NVMe SSD 144개(원시 용량 약 1.1PB), NVIDIA SCADA를 결합한 개념검증을 공개했다. [1][2][3][4]
- 실증의 약 1.1PB는 SSD 144개의 원시 저장 용량이며 HBM 용량을 대체하는 수치가 아니다. [1][5]
- NVIDIA SCADA는 512바이트 단위의 세밀한 데이터 접근을 지원하며 2조 벡터 데이터베이스 처리 가능성을 겨냥한다. [1][5]
- 키옥시아 XD8 시리즈 SSD는 EDSFF E1.S 규격과 OCP 데이터센터 NVMe SSD 사양을 따르며 최대 7.68TB 용량을 지원한다. [6]

## 연표

- 2026-11-25: 키옥시아 아메리카가 엔비디아와의 SSD 기반 GPU 메모리 확장 개념검증을 북미에서 발표한다. [2]
- 2026-11-26: 키옥시아 일본 본사가 XD8 SSD 144개와 NVIDIA SCADA 구성을 담은 동일 실증 공지를 발표한다. [1]
- 2026-11-27: 키옥시아 유럽이 지역 공지를 발표하고 트렌드포스가 1.1PB 개념검증 테스트를 보도한다. [3][5]

## 출처

1. Kioxia SSDs and NVIDIA SCADA Software Demonstrate Potential Memory Space Expansion Beyond 1 PB and Processing of 2 Trillion Vectors. Kioxia Corporation (Japan). 게시일 2026-11-26. https://www.kioxia.com/en-jp/business/news/2026/20261126-1.html (확인일 2026-11-28; tier 3: official site)
2. Kioxia and NVIDIA Collaborate to Expand Effective High-Bandwidth GPU Memory Capacity. Kioxia America. 게시일 2026-11-25. https://americas.kioxia.com/en-ca/business/news/2026/ssd-20261125-1.html (확인일 2026-11-28; tier 3: official site)
3. Kioxia Europe Press Release on Kioxia-NVIDIA GPU Memory Expansion Collaboration. Kioxia Europe. 게시일 2026-11-27. https://europe.kioxia.com/content/dam/kioxia/en-europe/business/news/2026/asset/KIE_PR_20261127-1_EN.pdf (확인일 2026-11-28; tier 3: official site)
4. NVIDIA GB200 NVL72. NVIDIA. https://www.nvidia.com/en-us/data-center/gb200-nvl72/ (확인일 2026-11-28; tier 3: official site)
5. Kioxia, NVIDIA Begin 1.1 PB SSD-Based GPU Memory Expansion Tests to Address HBM Capacity Limits. TrendForce. 게시일 2026-11-27. https://www.trendforce.com/news/2026/11/27/news-kioxia-nvidia-begin-1-1-pb-ssd-based-gpu-memory-expansion-tests-to-address-hbm-capacity-limits/ (확인일 2026-11-28; tier 2: academic or news)
6. KIOXIA XD8 Series Data Center NVMe SSDs. Kioxia Corporation. https://www.kioxia.com/en-jp/business/ssd/data-center-ssd/xd8.html (확인일 2026-11-28; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "SSD 기반 GPU 메모리 확장 (SSD-backed GPU Memory Expansion)." 버전 59ef3b78, 2026-11-28. https://mimirwiki.com/ko/wiki/ssd-backed-gpu-memory
