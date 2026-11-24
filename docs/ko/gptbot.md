---
title: "GPTBot"
subtitle: "생성형 AI 파운데이션 모델 학습 데이터를 수집하는 오픈AI(OpenAI)의 자동화 웹 크롤러"
canonical_url: https://mimirwiki.com/ko/wiki/gptbot
language: ko
page_class: entity
revision_sha256: 1ce108e8aec3f9e1b43a51e8ec4b2892c72c04b9a43270fdac5303aa971ddd3f
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/ko/wiki/gptbot.md
  txt: https://mimirwiki.com/ko/wiki/gptbot.txt
  json: https://mimirwiki.com/ko/wiki/gptbot.json
  jsonld: https://mimirwiki.com/ko/wiki/gptbot.jsonld
translations:
  en: https://mimirwiki.com/wiki/gptbot
  ja: https://mimirwiki.com/ja/wiki/gptbot
  zh: https://mimirwiki.com/zh/wiki/gptbot
---

# GPTBot

> 2026년 11월 기준 GPTBot은 HTTP 요청 시 GPTBot/1.4 (+https://openai.com/gptbot) 사용자 에이전트(User-Agent) 토큰을 사용하며, openai.com/gptbot.json(2026년 9월 22일 기준 18개 IPv4 CIDR 블록)을 통해 공식 발신 IP 대역을 공개한다. 웹사이트 운영자는 robots.txt(RFC 9309)에서 GPTBot만 차단하여 AI 모델 학습을 거부하면서도 OAI-SearchBot(39개 IPv4 블록)은 허용해 챗GPT 검색 결과 노출을 유지할 수 있으며, IETF의 AI 선호도(aipref) 및 웹 봇 인증(webbotauth) 표준과 연동된다.

GPTBot은 오픈AI(OpenAI)가 생성형 인공지능(AI) 파운데이션 모델의 학습에 활용될 수 있는 공개 웹 콘텐츠를 탐색하고 수집하기 위해 운영하는 핵심 자동화 웹 크롤러이다. 오픈AI는 역할에 따라 웹 에이전트를 세분화하여 모델 학습용 GPTBot 외에도 챗GPT(ChatGPT) 검색 인덱싱 전용인 OAI-SearchBot, 광고 랜딩 페이지 검증용인 OAI-AdsBot, 그리고 사용자의 실시간 웹 브라우징 요청을 처리하는 ChatGPT-User를 별도로 운영한다.

**다른 이름:** GPTBot/1.4, OAI-SearchBot, OAI-AdsBot, ChatGPT-User

## 핵심 정보

- **운영사:** 오픈AI (OpenAI OpCo, LLC) [1]
- **현재 User-Agent 토큰:** GPTBot/1.4 (+https://openai.com/gptbot) (기준 2026-11-23) [1]
- **공식 공개 IP 대역:** openai.com/gptbot.json 내 18개 IPv4 CIDR 프리픽스 (2026-09-22 업데이트) (기준 2026-11-23) [2]
- **오픈AI 병행 에이전트:** OAI-SearchBot/1.4 (검색), OAI-AdsBot/1.0 (광고), ChatGPT-User/1.0 (사용자 액션) (기준 2026-11-23) [1]

## 기본 정보

- **운영사:** 오픈AI (OpenAI) [1]
- **주요 목적:** 생성형 AI 파운데이션 모델 학습용 공개 웹 콘텐츠 크롤링 [1]
- **User-Agent 문자열:** Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; GPTBot/1.4; +https://openai.com/gptbot) [1]
- **IP 검증 매니페스트:** https://openai.com/gptbot.json (2026-09-22 기준 18개 IPv4 프리픽스) [2]
- **검색 전용 크롤러:** OAI-SearchBot/1.4 (https://openai.com/searchbot.json, 39개 IPv4 프리픽스) [1]
- **제어 프로토콜:** 로봇 배제 표준 (IETF RFC 9309 / robots.txt) [5]
- **관련 IETF 표준화:** IETF AI Preferences (aipref) 및 IETF Web Bot Auth (webbotauth) [6]

## 개요 및 오픈AI 크롤러 분류 체계

2023년 8월 오픈AI(OpenAI)가 처음 도입하고 2026년 기준 버전 1.4까지 고도화된 **GPTBot**은 생성형 AI 파운데이션 모델의 학습 및 성능 개선을 위해 공개 인터넷 텍스트와 미디어를 수집하는 전용 웹 크롤러이다 [1]. 웹사이트 발행인이 AI 모델 학습용 데이터 수집과 검색 엔진 노출, 광고 정책 검증, 그리고 실제 사용자 요청에 의한 실시간 페이지 조회를 서로 구분하여 제어할 수 있도록 오픈AI는 자동화된 HTTP 트래픽을 독립된 `robots.txt` 규칙과 IP 매니페스트를 가진 4종의 사용자 에이전트(User-Agent)로 분리해 운영한다 [1]:

| User-Agent 토큰 | 현재 버전 | 주요 목적 및 모델 학습 사용 여부 | 공식 IP 매니페스트 URL |
| --- | --- | --- | --- |
| `GPTBot` | `GPTBot/1.4` | 오픈AI 생성형 AI 파운데이션 모델 학습에 사용될 수 있는 공개 콘텐츠 수집. 유료 장벽(Paywall), 개인식별정보(PII) 밀집 페이지 및 정책 위반 콘텐츠 제외 [1]. | `https://openai.com/gptbot.json` (2026-09-22 기준 18개 IPv4 프리픽스) [2] |
| `OAI-SearchBot` | `OAI-SearchBot/1.4` | 챗GPT(ChatGPT) 검색 기능에서 링크와 요약을 노출하기 위한 웹사이트 인덱싱 전용. **파운데이션 모델 학습에 사용되지 않음** [1]. | `https://openai.com/searchbot.json` (2026-01-02 기준 39개 IPv4 프리픽스) [3] |
| `OAI-AdsBot` | `OAI-AdsBot/1.0` | 광고주 랜딩 페이지의 품질, 안전성 및 정책 준수 여부 검증. **파운데이션 모델 학습에 사용되지 않음** [1]. | 오픈AI 크롤러 공식 문서 참조 [1] |
| `ChatGPT-User` | `ChatGPT-User/1.0` | 실제 사용자가 챗GPT 또는 커스텀 GPT(Custom GPT)에 특정 웹페이지 조회를 요청했을 때 실시간으로 대행 호출. **수동적 모델 학습에 사용되지 않음** [1]. | `https://openai.com/chatgpt-user.json` (2026-11-06 업데이트) [4] |

2026년 후반 기준 GPTBot이 전송하는 전체 HTTP `User-Agent` 헤더 문자열은 `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; GPTBot/1.4; +https://openai.com/gptbot)`이다 [1].

## Robots.txt 옵트아웃(Opt-Out) 및 세분화된 접근 제어

GPTBot은 **IETF RFC 9309**로 표준화된 로봇 배제 표준(Robots Exclusion Protocol)을 준수한다 [1][5]. 웹사이트 관리자는 루트 경로의 `/robots.txt` 파일에 `User-agent: GPTBot` 지시어를 추가하여 도메인 전체 또는 특정 디렉터리 경로에 대한 GPTBot의 스크래핑을 허용하거나 차단할 수 있다 [1][5].

오픈AI가 학습용 크롤링과 검색 인덱싱을 분리하고 있으므로, 자사 콘텐츠가 AI 모델 학습에 사용되는 것은 차단하되 챗GPT 검색 결과에는 계속 인용 링크로 노출되기를 원하는 발행인은 다음과 같이 `GPTBot`을 차단하고 `OAI-SearchBot`을 허용할 수 있다 [1]:

```text User-agent: GPTBot Disallow: /

User-agent: OAI-SearchBot Allow: / ```

오픈AI 공식 문서에 따르면 웹사이트가 `robots.txt` 규칙을 수정한 후 오픈AI의 분산 크롤러 플릿이 캐시된 정책을 갱신하여 요청을 중단하기까지 약 24시간이 소요될 수 있다 [1].

## IP 진위 검증 및 암호학적 웹 봇 인증(Web Bot Auth)

제3자 스크래퍼가 HTTP 헤더의 `GPTBot` User-Agent 문자열을 위조(Spoofing)하는 사례가 빈번하기 때문에, 단순 헤더 문자열만으로는 방화벽 정책이나 트래픽 분석을 정확히 수행할 수 없다 [1][8]. 이에 따라 오픈AI는 네트워크 운영자와 콘텐츠 전송 네트워크(CDN)가 IP 계층에서 실제 오픈AI 트래픽 여부를 검증할 수 있도록 기계 판독 가능한 JSON 형식의 CIDR 매니페스트를 공개하고 있다 [1][2][3][4]: - **`gptbot.json`**: 생성 타임스탬프 `2026-09-22T00:00:00Z` 기준 총 18개의 IPv4 CIDR 블록(`20.171.206.0/24`, `52.230.152.0/24`, `20.168.17.192/28`, `172.182.202.0/25`, `172.182.204.0/24`, `172.182.214.0/24` 등)을 포함한다 [2]. - **`searchbot.json`**: `2026-01-02T07:01:00.000000Z` 기준 39개의 IPv4 CIDR 블록을 포함한다 [3]. - **`chatgpt-user.json`**: `2026-11-06T00:00:00Z` 기준 업데이트된 다수의 리전별 발신 IPv4 CIDR 블록을 포함한다 [4].

나아가 클라우드플레어(Cloudflare) 등 엣지 보안 사업자와 **IETF 웹 봇 인증(`webbotauth`) 워킹그룹**은 자동화 에이전트를 위한 암호학적 HTTP 메시지 서명(RFC 9421 기반 HTTP Message Signatures) 표준화를 추진하고 있다 [7][8]. 암호학적 봇 인증 체계에서는 검증된 크롤러가 공개된 Ed25519 또는 RSA 키 디렉터리로 서명된 `Signature` 및 `Signature-Input` 헤더를 요청에 첨부하므로, 오리진 서버와 웹 방화벽(WAF)이 번거로운 IP 대역 대조 없이도 봇의 신원을 수학적으로 즉시 검증할 수 있다 [7][8].

## IETF AI 선호도(aipref) 표준화 및 웹 생태계 영향

AI 학습 크롤러의 급증은 원래 1994년 검색 엔진 크롤러의 서버 과부하를 막고 상호 검색 트래픽 유입을 전제로 설계되었던 `robots.txt`가 저작권 및 기계학습 활용 정책을 표현하기에 충분한지에 대한 광범위한 논의를 촉발했다 [5][6].

이 한계를 해결하기 위해 출범한 **IETF AI 선호도(`aipref`, AI Preferences) 워킹그룹**은 디지털 콘텐츠의 AI 시스템 활용 허용 범위를 기계 판독 가능한 방식으로 표현하는 표준 어휘와 전달 메커니즘을 제정하고 있다 [6]. 워킹그룹의 핵심 초안인 `draft-ietf-aipref-vocab`(AI 사용 선호도 표현 어휘)과 `draft-ietf-aipref-attach`(`robots.txt` 확장 및 HTTP `Content-Usage` 헤더를 통한 정책 부착 방식)는 일반 자동화 처리, 파운데이션 모델 학습(`train-ai` / `ai`), 검색 및 추론 그라운딩 용도를 명확히 구분한다 [6]. 클라우드플레어의 글로벌 AI 트래픽 분석에 따르면 `GPTBot`은 바이트스파이더(Bytespider), 클로드봇(ClaudeBot), 구글 익스텐디드(Google-Extended)와 함께 전 세계에서 가장 높은 요청 비중을 차지하는 AI 크롤러 중 하나로 집계되며, 웹 전반의 AI 크롤링 제어 및 크롤링 과금(pay-per-crawl) 인프라 도입을 견인하고 있다 [8].

## 자주 묻는 질문

### GPTBot과 OAI-SearchBot의 차이점은 무엇인가요?

GPTBot(GPTBot/1.4)은 오픈AI의 생성형 AI 파운데이션 모델 학습 데이터를 수집하기 위해 공개 웹페이지를 크롤링하는 에이전트입니다. 반면 OAI-SearchBot(OAI-SearchBot/1.4)은 챗GPT 검색(ChatGPT Search) 결과에 웹사이트 링크와 요약을 노출하기 위한 인덱싱 전용 크롤러이며 파운데이션 모델 학습에는 사용되지 않습니다. [1]

### 챗GPT 검색 노출은 유지하면서 AI 모델 학습용 크롤링만 차단하려면 어떻게 해야 하나요?

웹사이트 루트의 /robots.txt 파일에 'User-agent: GPTBot' 및 'Disallow: /'를 설정하여 모델 학습용 수집을 차단하고, 동시에 'User-agent: OAI-SearchBot' 및 'Allow: /'를 추가하면 모델 학습은 거부하면서 챗GPT 검색 결과 노출과 출처 링크 인용은 그대로 유지할 수 있습니다. [1][5]

### 접속한 GPTBot이 실제 오픈AI의 공식 크롤러인지 어떻게 검증하나요?

요청의 발신 IP 주소를 오픈AI가 https://openai.com/gptbot.json 에 공개한 공식 IPv4 CIDR 블록(2026년 9월 기준 18개 프리픽스)과 대조하거나, CDN의 검증된 봇(Verified Bot) 기능 및 IETF Web Bot Auth 프레임워크 기반의 암호학적 HTTP 메시지 서명을 통해 진위를 검증할 수 있습니다. [1][2][7][8]

### ChatGPT-User 에이전트는 언제 작동하며 GPTBot과 어떻게 다른가요?

ChatGPT-User(ChatGPT-User/1.0)는 실제 사용자가 챗GPT 대화창이나 커스텀 GPT 액션에서 특정 URL의 내용을 읽어달라고 실시간으로 요청할 때만 사용자를 대신해 웹페이지를 조회하는 에이전트입니다. 발신 IP는 https://openai.com/chatgpt-user.json 에 별도 공개되며 수동적인 파운데이션 모델 학습용 크롤링에 사용되지 않습니다. [1][4]

### GPTBot과 같은 AI 웹 크롤러와 관련된 IETF 표준에는 무엇이 있나요?

기본적인 robots.txt 준수는 IETF RFC 9309(로봇 배제 표준)를 따릅니다. 이에 더해 IETF AI Preferences(aipref) 워킹그룹이 AI 학습 옵트아웃 의사 표시를 위한 표준 어휘(draft-ietf-aipref-vocab)와 HTTP 헤더 부착 규격을 제정하고 있으며, IETF Web Bot Auth(webbotauth) 워킹그룹이 암호학적 봇 신원 인증 표준을 개발하고 있습니다. [5][6][7]

## 인용 문장

- 오픈AI는 웹 크롤링 및 자동화 트래픽을 GPTBot/1.4(모델 학습), OAI-SearchBot/1.4(검색 인덱싱), OAI-AdsBot/1.0(광고 랜딩 페이지 검증), ChatGPT-User/1.0(사용자 실시간 요청)의 4종으로 분리해 운영한다. [1]
- 오픈AI의 공식 GPTBot IP 매니페스트(https://openai.com/gptbot.json)는 2026년 9월 22일 업데이트 기준 18개의 IPv4 CIDR 프리픽스를 포함하고 있다. [2]
- 오픈AI의 공식 OAI-SearchBot IP 매니페스트(https://openai.com/searchbot.json)는 2026년 1월 2일 업데이트 기준 39개의 IPv4 CIDR 프리픽스를 포함하고 있다. [3]
- robots.txt에서 GPTBot을 차단하고 OAI-SearchBot을 허용하면 파운데이션 모델 학습 수집을 거부하면서도 챗GPT 검색 결과 내 인덱싱을 유지할 수 있다. [1][5]
- IETF AI Preferences(aipref) 워킹그룹은 기계 판독 가능한 AI 학습 및 콘텐츠 사용 선호도를 표준화하기 위해 draft-ietf-aipref-vocab과 draft-ietf-aipref-attach를 개발하고 있다. [6]

## 연표

- 2022-09: IETF가 로봇 배제 표준(robots.txt)을 공식 인터넷 표준인 RFC 9309로 제정. [5]
- 2023-08: 오픈AI가 robots.txt 옵트아웃 제어 및 공식 IP 대역 매니페스트를 갖춘 GPTBot을 최초 공개. [1]
- 2024-07: 오픈AI가 모델 학습용 크롤링(GPTBot)과 검색 인덱싱을 분리하기 위해 OAI-SearchBot을 도입. [1]
- 2026-01-02: 오픈AI가 OAI-SearchBot용 searchbot.json 매니페스트를 39개 IPv4 CIDR 블록으로 업데이트. [3]
- 2026-09-22: GPTBot의 User-Agent 버전이 GPTBot/1.4로 갱신되고 gptbot.json 매니페스트가 18개 IPv4 CIDR 프리픽스로 업데이트됨. [1][2]
- 2026-11-06: 실시간 사용자 요청을 처리하는 ChatGPT-User용 chatgpt-user.json 발신 IPv4 대역 업데이트. [4]

## 출처

1. Overview of OpenAI Crawlers (GPTBot/1.4, OAI-SearchBot/1.4, OAI-AdsBot/1.0, ChatGPT-User/1.0). OpenAI Platform Documentation. https://platform.openai.com/docs/bots (확인일 2026-11-23; tier 3: official site)
2. OpenAI GPTBot Official IPv4 CIDR Prefix Manifest (gptbot.json). OpenAI. 게시일 2026-09-22. https://openai.com/gptbot.json (확인일 2026-11-23; tier 3: official site)
3. OpenAI OAI-SearchBot Official IPv4 CIDR Prefix Manifest (searchbot.json). OpenAI. 게시일 2026-01-02. https://openai.com/searchbot.json (확인일 2026-11-23; tier 3: official site)
4. OpenAI ChatGPT-User Official IPv4 CIDR Prefix Manifest (chatgpt-user.json). OpenAI. 게시일 2026-11-06. https://openai.com/chatgpt-user.json (확인일 2026-11-23; tier 3: official site)
5. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 게시일 2022-09. https://www.rfc-editor.org/rfc/rfc9309 (확인일 2026-11-23; tier 1: government or public registry)
6. IETF AI Preferences (aipref) Working Group Charter and Active Drafts (draft-ietf-aipref-vocab, draft-ietf-aipref-attach). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/aipref/about/ (확인일 2026-11-23; tier 1: government or public registry)
7. IETF Web Bot Auth (webbotauth) Working Group Charter. Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/about/ (확인일 2026-11-23; tier 1: government or public registry)
8. From Googlebot to GPTBot: Who's Crawling Your Site and Cryptographic Bot Verification. Cloudflare. 게시일 2025-05. https://blog.cloudflare.com/from-googlebot-to-gptbot-whos-crawling-your-site-in-2025/ (확인일 2026-11-23; tier 2: academic or news)

## 이 문서 인용하기

Mimirwiki. "GPTBot." 버전 1ce108e8, 2026-11-24. https://mimirwiki.com/ko/wiki/gptbot
