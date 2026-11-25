---
title: "퍼플렉시티 (Perplexity)"
subtitle: "실시간 웹 검색과 다중 모델 라우팅을 결합한 AI 답변 엔진 및 에이전트·오케스트레이터·서치 등 7대 개발자 API 플랫폼"
canonical_url: https://mimirwiki.com/ko/wiki/perplexity
language: ko
page_class: entity
revision_sha256: 486ea3645a3c69ede1416283bc5f4e3b897ee95bcea2b106d6c07baf6cb151cf
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/ko/wiki/perplexity.md
  txt: https://mimirwiki.com/ko/wiki/perplexity.txt
  json: https://mimirwiki.com/ko/wiki/perplexity.json
  jsonld: https://mimirwiki.com/ko/wiki/perplexity.jsonld
translations:
  en: https://mimirwiki.com/wiki/perplexity
  ja: https://mimirwiki.com/ja/wiki/perplexity
  zh: https://mimirwiki.com/zh/wiki/perplexity
  es: https://mimirwiki.com/es/wiki/perplexity
---

# 퍼플렉시티 (Perplexity)

> 퍼플렉시티는 실시간 웹 그라운딩 기반의 AI 답변 엔진과 7종 개발자 API(Agent, Orchestrator, Search, Context, Monitor, Embeddings, Decisions API)를 운영한다. 2026년 9월 27일 소나 챗 컴플리션 지원을 종료하고 오픈 리스폰스(Open Responses) 표준과 호환되는 에이전트 API(`POST https://api.perplexity.ai/v1/agent`)로 전환했으며, 이를 통해 소나(Sonar)뿐만 아니라 오픈AI·앤스로픽·구글·xAI·Z.AI·문샷AI·엔비디아 모델을 단일 API에서 웹·금융·인물 검색, 코드 샌드박스, MCP 도구와 결합해 호출할 수 있다. 서치 API는 토큰 과금 없이 1,000건당 표준 5달러(고속 검색 1달러, 요청당 최대 5개 쿼리 묶음 가능)로 제공된다.

퍼플렉시티(Perplexity)는 실시간 웹 색인·검색 기술과 대형 언어 모델(LLM)을 결합하여 출처가 인용된 답변과 자율 에이전트 리서치를 제공하는 인공지능 답변 엔진이자 개발자 API 플랫폼이다. 2026년 9월 27일 구형 소나 챗 컴플리션(Sonar Chat Completions) 지원 종료 이후 퍼플렉시티 개발자 플랫폼(`docs.perplexity.ai`)은 다중 모델 기반의 에이전트 API(Agent API), 오케스트레이터 API(Orchestrator API), 서치 API(Search API), 컨텍스트 API(Context API), 모니터 API(Monitor API), 임베딩 API(Embeddings API), 디시전 API(Decisions API)의 7대 핵심 서비스와 `pplx` CLI 및 공식 모델 컨텍스트 프로토콜(MCP) 서버로 구성되어 있다.

**다른 이름:** Perplexity, Agent API, Orchestrator API, Search API, PerplexityBot, 답변 엔진

## 핵심 정보

- **7대 개발자 API 제품군:** Agent API, Orchestrator API, Search API, Context API, Monitor API, Embeddings API, Decisions API [7]
- **소나(Sonar) API 전환일:** 2026년 9월 27일 (Sonar Chat Completions 지원 종료, 동기·스트리밍 요청은 Agent API로 자동 변환) [5]
- **에이전트 API 핵심 기능:** Open Responses 표준, 5단계 노력 수준(fast~xhigh), 8대 모델군 선택, 코드 샌드박스, 금융·인물 검색 [5]
- **서치 및 모니터 API 요금:** Search API: 1,000요청당 $5(Fast Search $1, 요청당 최대 5쿼리) / Monitor API: 1,000회 실행·URL당 $1 [4]
- **공식 웹 크롤러 및 IP:** PerplexityBot/1.0(21개 IPv4 대역) 및 Perplexity-User/1.0(10개 IPv4 대역), 두 봇 모두 파운데이션 모델 학습 미사용 [1]

## 기본 정보

- **플랫폼 명칭:** 퍼플렉시티 (Perplexity API Platform & Answer Engine) [7]
- **에이전트 API 엔드포인트:** POST https://api.perplexity.ai/v1/agent [6]
- **API 호환 표준:** Open Responses 표준(Agent API) / OpenAI 및 Anthropic 요청 포맷(Orchestrator API) [5]
- **지원 모델 패밀리:** Perplexity Sonar, OpenAI, Anthropic, Google, xAI, Z.AI, Moonshot AI, NVIDIA [5]
- **에이전트 노력(Effort) 프리셋:** fast (기본값), low, medium, high, xhigh [5]
- **Search API 요금:** 1,000요청당 $5.00 (표준 웹 검색) / 1,000요청당 $1.00 (search_type: "fast") [4]
- **Monitor API 요금:** 성공한 Search 실행당 $0.001 ($1/1K) / 성공한 Page 실행 내 수집 URL당 $0.001 ($1/1K) [4]
- **구형 Sonar 지원 종료일:** 2026년 9월 27일 (Sonar Chat Completions 공식 지원 종료) [5]
- **CLI 및 MCP 도구:** Perplexity CLI(pplx), Perplexity API MCP 서버, Perplexity Computer MCP 서버, Decider for Mac [7]
- **공식 웹 크롤러:** PerplexityBot/1.0 (perplexitybot.json) 및 Perplexity-User/1.0 (perplexity-user.json) [1]

## 퍼플렉시티 7대 개발자 API 플랫폼 아키텍처

2026년 하반기 기준 퍼플렉시티(Perplexity)의 개발자 플랫폼(`docs.perplexity.ai`)은 기존의 단일 검색 결합형 챗 엔드포인트에서 벗어나 목적별로 분리된 7종의 REST API와 공식 파이썬·타입스크립트 SDK(`perplexity`, `@perplexity-ai/perplexity_ai`), 터미널용 명령줄 도구 `pplx`(Perplexity CLI), 퍼플렉시티 API MCP 서버 및 퍼플렉시티 컴퓨터(Perplexity Computer) MCP 서버로 구성되어 있다.[5][6][7]

1. **에이전트 API (Agent API, `POST https://api.perplexity.ai/v1/agent`)**: 단일 요청 내에서 다중 모델 추론과 도구 호출 루프를 자율 실행하여 검색 출처(`search_results` 항목)와 인용이 포함된 최종 답변(`message` 항목)을 타입화된 `output` 배열로 반환하는 주력 에이전트 인터페이스이다.[5][6] 2. **오케스트레이터 API (Orchestrator API)**: 단일 퍼플렉시티 API 키로 오픈AI(OpenAI) 또는 앤스로픽(Anthropic) 요청 포맷을 그대로 사용해 앤스로픽, 오픈AI, 구글, xAI 및 오픈웨이트 모델을 호출하는 라우팅 게이트웨이이다. `perplexity/auto` 자동 모델 선택, 배포 장애 시 자동 페일오버(failover), 턴 간 추론 유지, 프롬프트 캐싱을 지원한다.[7] 3. **서치 API (Search API, `POST /search`)**: 언어 모델 생성이나 토큰 과금 없이 웹 검색 순위 결과와 각 페이지에서 추출한 텍스트 스니펫(`snippet`)을 JSON으로 반환하는 순수 검색 API이다.[4][7] 4. **컨텍스트 API (Context API)**: 지정된 URL에서 정제된 마크다운(Markdown), HTML, 링크, 쿼리 연관 하이라이트, 최신성 및 사용자 정의 기준 점수를 추출한다.[7] 5. **모니터 API (Monitor API)**: 특정 검색어(Search)나 웹페이지(Page)의 변화를 주기적으로 추적·감시한다.[4][7] 6. **임베딩 API (Embeddings API)**: 표준 임베딩, 문맥화 임베딩(Contextualized Embeddings) 및 문맥화 임베딩 v2 벡터를 생성한다.[4][7] 7. **디시전 API (Decisions API)**: 의사결정 및 예측 과업을 위해 보정된 확률(calibrated probabilities)을 산출하며 맥용 클라이언트인 '디사이더 포 맥(Decider for Mac)'과 연동된다.[4][7]

## 소나(Sonar) 챗 컴플리션 지원 종료 및 에이전트 API 전환

퍼플렉시티는 2026년 9월 27일부로 구형 소나 챗 컴플리션(Sonar Chat Completions, `POST https://api.perplexity.ai/v1/sonar`)에 대한 공식 지원을 종료했다.[5] 기존 운영 환경의 하위 호환성을 위해 동기식(synchronous) 및 스트리밍(streaming) 소나 요청은 백엔드에서 모델별로 순차 적용되는 자동 변환을 통해 에이전트 API 요청으로 재구성되어 계속 작동하지만, 비동기식(asynchronous) 소나 요청은 자동 변환되지 않고 지원이 중단되어 에이전트 API의 백그라운드 모드(background mode)로 이전해야 한다.[5]

`messages` 배열을 입력받아 자체 소나 모델만 호출하고 `choices` 배열을 반환하던 소나 API와 달리, 에이전트 API는 이식성을 보장하고 벤더 종속(lock-in)을 방지하는 오픈 리스폰스(Open Responses) 표준을 따른다.[5] 개발자는 단일 인터페이스에서 퍼플렉시티의 자체 소나(Sonar) 모델뿐만 아니라 오픈AI(예: `openai/gpt-5.6-luna`), 앤스로픽, 구글, xAI, Z.AI, 문샷AI(Moonshot AI), 엔비디아(NVIDIA)의 8개 모델 패밀리를 자유롭게 선택하고 모델 폴백(fallback) 체인을 구성할 수 있다.[4][5]

에이전트 API는 과업 강도에 따라 연구 기반으로 튜닝된 5단계 노력 수준(`effort`: `fast`, `low`, `medium`, `high`, `xhigh`)과 재사용·버전 관리가 가능한 프로파일(Profiles)을 제공하며, 다음과 같은 내장 에이전트 도구와 결합된다.[5][7]

- **코드로서의 검색(Search as Code) 및 프리미엄 데이터 소스**: 실시간 웹 검색, URL 본문 수집(fetching), 금융 검색(Finance Search), 인물 검색(People Search)을 기본 내장하고 있다.[5]
- **격리 코드 실행 샌드박스 (Code Sandbox)**: 요청을 벗어나지 않고 안전한 컨테이너 샌드박스 내에서 생성된 코드를 직접 실행해 정확한 수치 계산과 데이터 분석을 수행하고 생성된 파일을 반환한다.[5][7]
- **MCP 서버 및 사용자 정의 함수**: 외부 모델 컨텍스트 프로토콜(MCP) 서버를 연결하거나 자체 커스텀 함수를 정의해 사내 데이터 및 외부 도구를 에이전트 루프에 통합할 수 있다.[5]

## 서치·모니터·에이전트 API 과금 구조 및 요금표

퍼플렉시티 API 플랫폼의 모든 서비스는 별도의 월정액 구독 없이 사용한 만큼만 지불하는 종량제(pay-as-you-go)로 운영된다.[6] 에이전트 API와 오케스트레이터 API에서는 모델별 입출력 토큰 요금이 투명하게 공개되어 과금되며, 도구 사용료는 토큰 요금과 별도로 청구된다(예를 들어 코드 샌드박스는 컨테이너 실행 시작 시점 기준 20분 블록 단위 요금과 샌드박스 내부에서 호출된 SDK 웹 검색 횟수로 과금되며, 일부 내장 도구는 1,000회 호출당 1.00달러가 부과된다).[4][6]

검색(Search)과 감시(Monitor) API는 토큰 과금 없이 오직 성공한 요청 또는 실행 단위로만 과금된다.[4]

| API 서비스 | 모드 / 과금 단위 | 1,000단위당 요금 | 단위당 단가 및 세부 과금 규칙 |
| --- | --- | --- | --- |
| Search API | 표준 웹 검색 (`POST /search`) | $5.00 / 1,000요청 | 성공한 요청 1건당 $0.005 / 단일 요청에 최대 5개 쿼리 배열(결과 최대 20개)을 담아 보내도 1개 과금 단위로만 청구 |
| Search API | 고속 검색 (`search_type: "fast"`) | $1.00 / 1,000요청 | 성공한 요청 1건당 $0.001 / 동일한 JSON 응답 포맷의 저지연 검색 (최대 5개 쿼리 배열도 1단위로 청구) |
| Monitor API | 검색 모니터 (Search Monitor) | $1.00 / 1,000회 실행 | 성공한 Search 실행 1회당 $0.001 (실행 내부의 검색 횟수나 결과 수와 무관) |
| Monitor API | 페이지 모니터 (Page Monitor) | $1.00 / 1,000개 URL | 성공한 Page 실행에서 수집(fetch)된 유효 URL 1개당 $0.001 |

서치 API에서 잘못된 요청(invalid), 속도 제한 초과(`429`), 업스트림 장애는 과금되지 않으며, 정상 처리된 응답은 검색 결과가 0건이더라도 1단위로 과금된다.[4] 모니터 API에서도 실패하거나 건너뛴(skipped) 실행에는 요금이 부과되지 않는다.[4]

## 퍼플렉시티 웹 크롤러(PerplexityBot·Perplexity-User) 및 WAF 방화벽 설정

퍼플렉시티는 웹 정보 색인과 사용자 질의 응답을 위해 두 가지 독립적인 웹 에이전트를 운영하며, 공식 문서를 통해 두 에이전트 모두 AI 파운데이션 모델 학습용 콘텐츠 수집에는 절대 사용되지 않는다고 명시하고 있다.[1]

1. **`PerplexityBot`**: 퍼플렉시티 검색 결과에 웹사이트를 노출하고 링크하기 위해 작동하는 자동 검색 크롤러이다.[1] 사이트의 `robots.txt` 규칙을 준수하며(변경 사항 반영에 최대 24시간 소요), 사용자 에이전트 문자열은 `Mozilla/5.0 (compatible; PerplexityBot/1.0; +https://perplexity.ai/perplexitybot)`, 공식 공개 IP 목록 엔드포인트는 `https://www.perplexity.ai/perplexitybot.json`이다.[1] `2026-11-18T16:30:18` 갱신 기준 `perplexitybot.json`에는 `107.20.236.150/32`, `18.210.92.235/32`, `18.97.1.228/32`, `18.97.9.96/32`~`18.97.9.103/32`, `3.222.232.239/32`, `3.224.62.45/32`, `3.41.218.160/32`~`3.41.218.167/32` 등 총 21개의 `/32` IPv4 프리픽스가 등록되어 있다.[2] 2. **`Perplexity-User`**: 사용자가 퍼플렉시티에 질문을 입력했을 때 정확한 답변과 출처 링크를 제공하기 위해 특정 웹페이지를 실시간 방문하는 사용자 요청 대행 페처(fetcher)이다.[1] 사용자의 직접 요청에 의해 작동하므로 일반적으로 `robots.txt` 규칙을 무시하며, 사용자 에이전트 문자열은 `Mozilla/5.0 (compatible; Perplexity-User/1.0; +https://perplexity.ai/perplexity-user)`, 공식 IP 엔드포인트는 `https://www.perplexity.ai/perplexity-user.json`(`2026-10-28T16:48:51` 기준 `18.97.43.80/32`~`18.97.43.87/32`, `34.193.163.52/32`, `44.208.221.197/32`의 총 10개 `/32` IPv4 프리픽스 등록)이다.[1][3]

클라우드플레어(Cloudflare WAF)나 AWS WAF 등 웹 애플리케이션 방화벽을 사용하는 사이트 운영자의 경우, `User-Agent` 헤더 문자열과 공식 JSON 엔드포인트의 IP 대역을 `AND` 조건으로 함께 검증하는 허용(Allow) 또는 건너뛰기(Skip) 규칙을 차단 규칙보다 높은 우선순위로 배치해야 한다.[1] 단, 클라우드플레어 무료 요금제의 '봇 파이트 모드(Bot Fight Mode)'는 WAF 사용자 정의 Skip 규칙으로도 우회할 수 없어 활성화 시 퍼플렉시티 봇을 차단할 수 있다.[1]

## 자주 묻는 질문

### 퍼플렉시티의 기존 소나(Sonar) Chat Completions API는 어떻게 되었나요?

소나 Chat Completions에 대한 공식 지원은 2026년 9월 27일 종료되었으며 차세대 에이전트 API(POST https://api.perplexity.ai/v1/agent)로 대체되었습니다. 기존 동기식 및 스트리밍 소나 요청은 퍼플렉시티가 백엔드에서 에이전트 API 요청으로 자동 재구성해 주므로 계속 작동하지만, 비동기식 소나 요청은 더 이상 작동하지 않으므로 에이전트 API의 백그라운드 모드로 마이그레이션해야 합니다. [5]

### 퍼플렉시티 서치 API(Search API)의 요금과 과금 단위는 어떻게 계산되나요?

서치 API는 LLM 답변 생성이나 토큰 비용 없이 순위가 매겨진 웹 검색 결과와 본문 추출 스니펫을 JSON으로 반환합니다. 표준 검색은 성공한 요청 1,000건당 5.00달러(건당 $0.005), 고속 검색(search_type: "fast")은 1,000건당 1.00달러(건당 $0.001)입니다. 특히 한 번의 POST /search 요청에 최대 5개의 쿼리를 배열로 묶어 보내도 단 1개의 과금 단위로만 청구되며, 실패하거나 속도 제한에 걸린 요청은 과금되지 않습니다. [4]

### 에이전트 API(Agent API)와 오케스트레이터 API(Orchestrator API)의 차이점은 무엇인가요?

에이전트 API는 오픈 리스폰스(Open Responses) 표준을 기반으로 단일 요청 안에서 웹·금융·인물 검색, URL 본문 수집, 20분 단위로 과금되는 코드 실행 샌드박스, MCP 서버 등 도구를 자율 호출해 인용이 포함된 최종 답변과 검색 결과를 반환하는 에이전트 루프 API입니다. 반면 오케스트레이터 API는 오픈AI 또는 앤스로픽 요청 포맷을 그대로 사용해 단일 API 키로 앤스로픽·오픈AI·구글·xAI·오픈웨이트 모델을 호출하고 perplexity/auto 자동 라우팅과 배포 장애 페일오버를 제공하는 멀티 프로바이더 모델 게이트웨이입니다. [7]

### PerplexityBot과 Perplexity-User 크롤러의 차이는 무엇이며 모델 학습에 사용되나요?

두 에이전트 모두 AI 파운데이션 모델 학습용 데이터를 수집하지 않습니다. PerplexityBot/1.0은 검색 결과에 사이트를 노출하기 위한 자동 색인 크롤러로 사이트의 robots.txt 규칙을 준수합니다(IP 목록: perplexity.ai/perplexitybot.json). 반면 Perplexity-User/1.0은 사용자가 질문을 입력했을 때 실시간으로 웹페이지를 방문해 답변과 인용 링크를 생성하는 에이전트로, 사용자의 직접 요청에 의해 작동하므로 일반적으로 robots.txt 규칙을 무시합니다(IP 목록: perplexity.ai/perplexity-user.json). [1]

## 인용 문장

- 퍼플렉시티는 2026년 9월 27일 구형 소나 챗 컴플리션(Sonar Chat Completions) 지원을 종료하고, 동기식 및 스트리밍 요청은 에이전트 API 요청으로 자동 변환하는 한편 비동기식 소나 요청은 지원을 중단해 백그라운드 모드로 전환하도록 했다. [5]
- 퍼플렉시티 API 플랫폼은 Agent, Orchestrator, Search, Context, Monitor, Embeddings, Decisions의 7대 API와 터미널용 pplx CLI 및 공식 MCP 서버로 구성된다. [4][7]
- 에이전트 API(POST https://api.perplexity.ai/v1/agent)는 오픈 리스폰스 표준을 따르며 5단계 노력 수준(fast, low, medium, high, xhigh)과 소나·오픈AI·앤스로픽·구글·xAI·Z.AI·문샷AI·엔비디아 모델 선택, 웹·금융·인물 검색, 코드 샌드박스, MCP 연동을 지원한다. [5][6]
- 퍼플렉시티 서치 API는 토큰 과금 없이 성공한 요청 1,000건당 표준 5.00달러, 고속 검색(Fast Search) 1.00달러를 부과하며, 단일 요청에 최대 5개의 쿼리 배열을 담아 보내도 1개 과금 단위로만 계산한다. [4]
- 퍼플렉시티는 검색 색인용 PerplexityBot/1.0(2026년 11월 18일 기준 21개 IPv4 대역)과 실시간 사용자 요청 페처인 Perplexity-User/1.0(2026년 10월 28일 기준 10개 IPv4 대역)을 운영하며, 두 봇 모두 AI 파운데이션 모델 학습용 데이터를 수집하지 않는다. [1][2][3]

## 연표

- 2026-09-27: 퍼플렉시티가 구형 소나 챗 컴플리션(Sonar Chat Completions) 공식 지원을 종료하고 오픈 리스폰스 기반 에이전트 API로 전환. [5]
- 2026-10-28: 사용자 요청 대행 페처인 Perplexity-User의 공식 IPv4 허용 목록(perplexity-user.json, 10개 프리픽스)을 갱신. [3]
- 2026-11-18: 검색 색인 크롤러인 PerplexityBot의 공식 IPv4 허용 목록(perplexitybot.json, 21개 프리픽스)을 갱신. [2]

## 출처

1. Perplexity Crawlers - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/resources/perplexity-crawlers (확인일 2026-11-23; tier 3: official site)
2. PerplexityBot Published IPv4 Prefixes (perplexitybot.json). Perplexity. 게시일 2026-11-18. https://www.perplexity.ai/perplexitybot.json (확인일 2026-11-23; tier 3: official site)
3. Perplexity-User Published IPv4 Prefixes (perplexity-user.json). Perplexity. 게시일 2026-10-28. https://www.perplexity.ai/perplexity-user.json (확인일 2026-11-23; tier 3: official site)
4. Pricing - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/getting-started/pricing (확인일 2026-11-23; tier 3: official site)
5. Migrate from Sonar to the Agent API - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/agent-api/migrate-from-sonar/overview (확인일 2026-11-23; tier 3: official site)
6. Agent API Quickstart - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/agent-api/quickstart (확인일 2026-11-23; tier 3: official site)
7. Perplexity API Documentation Index (llms.txt). Perplexity. https://docs.perplexity.ai/llms.txt (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "퍼플렉시티 (Perplexity)." 버전 486ea364, 2026-11-23. https://mimirwiki.com/ko/wiki/perplexity
