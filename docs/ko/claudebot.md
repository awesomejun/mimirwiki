---
title: "ClaudeBot"
subtitle: "Anthropic이 AI 모델 학습용 공개 웹 콘텐츠를 수집하기 위해 운영하는 웹 크롤러"
canonical_url: https://mimirwiki.com/ko/wiki/claudebot
language: ko
page_class: entity
revision_sha256: 4fd4f3a027e27ed3eb4ca97f52f052bb5b92e8a131adc18d16d897afa6894867
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 10
alternates:
  md: https://mimirwiki.com/ko/wiki/claudebot.md
  txt: https://mimirwiki.com/ko/wiki/claudebot.txt
  json: https://mimirwiki.com/ko/wiki/claudebot.json
  jsonld: https://mimirwiki.com/ko/wiki/claudebot.jsonld
translations:
  en: https://mimirwiki.com/wiki/claudebot
  ja: https://mimirwiki.com/ja/wiki/claudebot
  zh: https://mimirwiki.com/zh/wiki/claudebot
---

# ClaudeBot

> ClaudeBot은 Anthropic이 생성형 AI 모델용 공개 웹 콘텐츠를 수집하기 위해 운영하는 학습용 웹 크롤러이다. Anthropic은 검색 색인을 담당하는 Claude-SearchBot과 사용자 요청에 따라 페이지를 불러오는 Claude-User를 ClaudeBot과 구분해 운영한다. 사이트 소유자는 robots.txt 지시문으로 ClaudeBot을 차단하거나 속도를 제한할 수 있으며, Anthropic은 2026년 10월 30일부터 IETF aipref 초안 기반의 학습 선호 신호도 인식한다.

ClaudeBot은 Anthropic이 Claude를 비롯한 생성형 AI 모델 학습에 활용될 수 있는 공개 웹 콘텐츠를 수집하기 위해 운영하는 자동화 웹 크롤러(web crawler)이다. Anthropic은 ClaudeBot과 함께 검색 색인용 Claude-SearchBot과 사용자 질의에 응답해 페이지를 조회하는 Claude-User를 별도의 웹 로봇으로 문서화하고 있다. 웹사이트 소유자는 RFC 9309에 규정된 robots.txt 지시문과 비표준 Crawl-delay 확장으로 ClaudeBot을 제한하거나 속도를 조절할 수 있으며, Anthropic은 2026년 10월 30일부터 IETF aipref 실무그룹 초안에 기반한 기계 판독형 AI 학습 거부 신호도 인식하기 시작했다. 2024년에는 여러 사이트 운영자가 ClaudeBot의 대량 요청을 보고했고, Anthropic이 2026년 11월 17일 제출한 Form S-1/A-3에는 웹 크롤링 관행과 관련한 계류 중인 소송이 공시되어 있다.

**다른 이름:** 클로드봇, Anthropic 웹 크롤러

## 핵심 정보

- **운영 주체:** Anthropic (기준 2026-11-23) [4]
- **제품 토큰:** ClaudeBot (기준 2026-11-23) [4]
- **명시된 목적:** 생성형 AI 모델 학습용 공개 웹 콘텐츠 수집 (기준 2026-11-23) [4]
- **병행 운영 봇:** Claude-SearchBot(검색 색인) 및 Claude-User(사용자 요청 페이지 조회) (기준 2026-11-23) [4]
- **옵트아웃 제어 수단:** robots.txt 지시문, Crawl-delay 확장, IETF aipref 초안 기반 학습 선호 신호(2026-10-30부터) (기준 2026-11-23) [4]

## 기본 정보

- **이름:** ClaudeBot [4]
- **유형:** 자동화 웹 크롤러(학습용 크롤러) [4]
- **운영 주체:** Anthropic (기준 2026-11-23) [4]
- **운영 법인명:** Anthropic, PBC(미국 델라웨어주 공익법인, 캘리포니아주 샌프란시스코 소재) (기준 2026-11-17) [2]
- **제품 토큰:** ClaudeBot (기준 2026-11-23) [4]
- **명시된 목적:** AI 모델 학습용 공개 웹 콘텐츠 수집 (기준 2026-11-23) [4]
- **Anthropic 병행 운영 봇:** Claude-SearchBot(검색 색인), Claude-User(사용자 요청 기반 조회) (기준 2026-11-23) [4]
- **배제 프로토콜:** 로봇 배제 프로토콜(robots.txt, IETF RFC 9309) [1]
- **속도 제한 지시문:** Crawl-delay(비표준 robots.txt 확장) (기준 2026-11-23) [4]
- **학습 선호 신호:** IETF aipref 초안 기반 AI 학습 거부 신호(2026-10-30부터 인식) (기준 2026-11-23) [4]
- **우회 방지 정책:** 크롤링 대상 사이트의 CAPTCHA 우회를 시도하지 않음 (기준 2026-11-23) [4]
- **개인정보 관련 문서:** Anthropic 개인정보 처리방침(2026-09-10 발효) 및 별도의 비사용자 개인정보 처리방침 (기준 2026-09-10) [5]
- **공개 IP 목록 주소:** https://claude.com/crawling/bots.json (IPv4 프리픽스 14개, creationTime 2026-10-20T00:00:00Z) (기준 2026-11-23) [10]

## ClaudeBot과 Anthropic의 웹 로봇 구성

ClaudeBot은 [Anthropic](https://mimirwiki.com/ko/wiki/anthropic)이 웹 콘텐츠 수집, 검색 색인 생성, [Claude](https://mimirwiki.com/ko/wiki/claude) 사용자 요청에 따른 페이지 조회를 위해 운영하는 세 종류의 웹 로봇 가운데 학습용 웹 크롤러(web crawler)이다.[4] 2026-11-23 기준 Anthropic 크롤러 문서는 웹사이트 소유자가 모델 학습, 검색 색인, 사용자 요청 기반 조회에 대해 접근 정책을 각각 따로 정할 수 있도록 세 개의 로봇을 구분해 안내한다.[4]

| 봇 | 명시된 기능 | robots.txt로 비활성화할 때의 효과 |
| --- | --- | --- |
| ClaudeBot | 생성형 AI 모델 학습에 활용될 수 있는 웹 콘텐츠 수집 | 해당 사이트의 향후 자료를 Anthropic AI 모델 학습 데이터셋에서 제외하라는 신호로 처리 |
| Claude-SearchBot | 사용자 검색 결과의 관련성과 정확도를 높이기 위해 웹 콘텐츠를 탐색하고 분석 | 검색 최적화를 위한 사이트 색인을 중단하며, 사용자 검색 결과에서의 노출과 정확도가 낮아질 수 있음 |
| Claude-User | 사용자가 Claude에 질문할 때 웹 사이트에 접근해 콘텐츠를 조회 | 사용자 질의에 응답하는 과정에서 해당 사이트 콘텐츠 조회를 중단하며, 사용자 지시 웹 검색에서의 노출이 줄어들 수 있음 |

Anthropic은 이 세 가지 크롤러 및 페처(fetcher)를 Claude Duet의 Claude-Agent를 포함해 사용자를 대신해 작업을 수행하는 Anthropic 호스팅 브라우저와 구분해 별도 문서로 안내한다.[4]

2026-11-23 기준 Anthropic은 자사 웹 로봇의 네 가지 운영 원칙을 밝히고 있다.[4]

- 문서화된 세 가지 봇 이름을 통한 투명한 식별
- 개별 도메인에 대한 요청 속도 조절 및 적절한 경우 `Crawl-delay` 준수
- `robots.txt`에 기재된 크롤링 금지 지시문 준수
- 크롤링 대상 사이트의 CAPTCHA 우회를 시도하지 않는 등 우회 방지 기술 존중

## robots.txt와 IETF aipref를 통한 ClaudeBot 제어

ClaudeBot은 국제인터넷표준화기구(IETF)가 RFC 9309로 표준화한 텍스트 파일인 [robots.txt](https://mimirwiki.com/ko/wiki/robots-txt)에 게시된 사이트 단위 접근 지시문을 따른다.[1][4] 2022년 9월 발행된 RFC 9309는 Martijn Koster가 1994년 정의한 로봇 배제 프로토콜(Robots Exclusion Protocol)을 규정하고 확장한다.[1] RFC 9309에 따르면 `robots.txt` 파일은 `allow`와 `disallow` 규칙을 `user-agent` 제품 토큰(product token)으로 시작하는 그룹으로 묶으며, 제품 토큰은 ASCII 영문자, 밑줄(`_`), 하이픈(`-`)만 포함하고 크롤러는 대소문자를 구분하지 않고 일치하는 그룹을 찾은 뒤 일치 항목이 없으면 와일드카드 그룹(`user-agent: *`)을 따른다.[1] 경로 일치는 URI 경로의 첫 번째 옥텟(octet)부터 대소문자를 구분해 비교하며 가장 길게 일치하는 규칙을 적용하고, RFC 9309는 `robots.txt` 규칙이 접근 인가(access authorization) 수단이 아님을 명시한다.[1]

사이트 전체에서 ClaudeBot을 차단하려면 2026-11-23 기준 Anthropic 문서 안내에 따라 최상위 디렉터리의 `robots.txt` 파일에 `User-agent: ClaudeBot`과 `Disallow: /`를 추가하고, 제외하려는 모든 하위 도메인에도 같은 설정을 적용한다.[4] 크롤링 속도를 제한하기 위해 Anthropic은 `robots.txt`의 비표준 `Crawl-delay` 확장을 지원한다(예: `User-agent: ClaudeBot` 아래 `Crawl-delay: 1`).[1][4]

2026-11-23 기준 Anthropic은 크롤링 옵트아웃을 위해 `robots.txt` 파일을 수정해야 한다고 안내한다.[4] Anthropic 봇이 사용하는 출발지 IP 주소를 차단하면 크롤러가 사이트의 `robots.txt` 파일을 읽지 못하게 되어, IP 주소 차단 방식은 안정적으로 작동하지 않거나 지속적인 옵트아웃을 보장하지 못할 수 있다고 설명한다.[4] Anthropic은 요청이 자사 크롤러에서 왔는지 판별할 수 있도록 출발지 IP 주소 목록을 함께 참조 안내한다.[4]

Anthropic은 2026년 10월 30일부터 웹사이트 소유자가 AI 학습 거부 의사를 표현할 수 있는 기계 판독형 선호 신호를 인식하기 시작했다.[4] 이 신호는 IETF `aipref` 실무그룹의 초안 작업에 기반하며, Anthropic은 전 세계 서비스 전반에 걸쳐 점진적으로 적용하고 있고 표준이 발전함에 따라 해석과 적용 방식이 바뀔 수 있다고 밝힌다.[4] 특정 경로에 대해 `robots.txt`가 `ClaudeBot`을 직접 명시하면 일반 선호 설정과 다르더라도 `ClaudeBot` 규칙이 우선 적용되며, `robots.txt`에 `ClaudeBot` 언급이 없을 때 일반 선호 설정을 따른다.[4]

## Anthropic의 학습 데이터 및 개인정보 처리방침에서의 ClaudeBot

ClaudeBot이 수집하는 공개 웹 콘텐츠는 Anthropic의 개인정보 처리방침과 증권 신고서에 기재된 학습 데이터 출처 가운데 한 범주에 해당한다.[2][4][5] 2026년 9월 10일 발효된 Anthropic 개인정보 처리방침(Privacy Policy)은 모델 학습을 위해 수집하거나 제공받는 데이터 출처 여섯 가지를 나열한다.[5]

- 인터넷을 통해 공개적으로 이용 가능한 정보
- 제3자 기업과의 상업적 계약을 통해 확보한 데이터셋
- 계정 설정에서 옵트아웃하지 않은 경우 서비스의 입력(Inputs) 및 출력(Outputs)을 포함해 사용자나 크라우드 워커가 제공한 데이터
- 사용자가 Anthropic 서비스에 대해 명시적으로 제공한 피드백
- 안전성, 보안 또는 정책 검토를 위해 표시된 자료
- Anthropic이 내부적으로 생성한 데이터

Anthropic의 개인정보 처리방침은 Enterprise 계정 등 기업용 상품 고객을 대신해 처리하는 콘텐츠에는 적용되지 않으며 해당 데이터는 고객 계약의 규율을 받는다고 명시하고, 제3자 출처 개인정보를 이용한 대규모 언어 모델 학습과 비사용자 선택권에 대해서는 별도의 비사용자 개인정보 처리방침(Non-User Privacy Policy)을 안내한다.[5] 개인 사용자가 계정 설정에서 모델 학습을 거부하더라도 대화가 안전성 검토 대상으로 표시되거나 피드백 기능으로 명시적 신고된 경우에는 모델 개선에 입력과 출력이 활용될 수 있다.[5]

Anthropic, PBC가 2026년 11월 17일 [SEC EDGAR](https://mimirwiki.com/ko/wiki/sec-edgar)에 제출한 Form S-1 수정신고서 제3호(등록번호 333-299633)는 공개 인터넷 정보, 제3자로부터 라이선스하거나 의뢰한 데이터셋, 자체 모델이 생성한 합성 데이터를 사전 학습(pre-training)과 사후 학습(post-training) 단계 전반에 사용한다고 밝힌다.[2] 같은 신고서는 공개 정보 수집 방식으로 웹 스크래핑(web scraping) 또는 웹 크롤링 기법, 도서 스캔 등을 기재한다.[2] Anthropic은 관련 법률, `robots.txt` 고지, 유료 장벽(paywall)이나 로그인 같은 기술적 조치를 준수하기 위한 절차를 두고 있으나 그 노력이 항상 성공하지는 않을 수 있으며, 수집된 정보가 개인정보, 저작권 또는 기타 지식재산권 법령의 보호 대상인지 검증하지 못할 경우가 있을 수 있다고 공시했다.[2]

## ClaudeBot과 Cloudflare의 AI 크롤러 제어

ClaudeBot은 [Cloudflare](https://mimirwiki.com/ko/wiki/cloudflare) 같은 네트워크 사업자가 자동화 트래픽을 분류하고 사이트 소유자에게 AI 크롤러에 대한 세부 제어 기능을 제공하는 웹 인프라 환경에서 동작한다.[6][7] Cloudflare가 2025년 7월 1일 공개한 2024년 5월부터 2025년 5월까지의 트래픽 분석에 따르면, AI 및 검색 크롤러 트래픽은 18% 증가했으며 [OpenAI](https://mimirwiki.com/ko/wiki/openai)의 [GPTBot](https://mimirwiki.com/ko/wiki/gptbot)은 305%, Googlebot은 96% 늘어났다.[9]

Cloudflare는 2026년 7월 1일 모든 요금제 고객이 Search, Agent, Training 트래픽을 구분해 관리할 수 있는 AI 트래픽 제어 옵션을 도입했다.[7] 같은 날 Cloudflare는 BotBase 분류 체계를 개편해 추적 대상 봇을 행동 유형과 운영자 접근 방식으로 분류하고, 기존의 Verified bot과 서명된 에이전트(signed agent) 구분을 `Direct`와 `Intermediary` 접근 필드로 표현하도록 바꿨다.[6]

| BotBase 분류 기준 | 항목 | Cloudflare 정의(2026-11-12 갱신 문서 기준) |
| --- | --- | --- |
| 행동 유형(관리형 AI 프리셋) | Training | 모델 학습 또는 미세조정(fine-tuning)을 위한 크롤링 |
| 행동 유형(관리형 AI 프리셋) | Search | 검색 색인 또는 RAG 데이터베이스 구축을 위한 크롤링 |
| 행동 유형(관리형 AI 프리셋) | Agent | 사람을 대신해 페이지를 방문하는 사용자 지시형 에이전트 |
| 운영자 접근 라벨 | Direct | 보통 자체 인프라에서 단일 운영자가 직접 운영하는 봇 |
| 운영자 접근 라벨 | Intermediary | 다수의 최종 사용자가 구동하는 에이전트 서비스로, 전이적 신뢰(transitive trust)가 발생 |

2026년 11월 12일 마지막으로 갱신된 Cloudflare Verified bots 문서에 따르면, Verified bot 자격을 얻으려면 암호화 기반 [Web Bot Auth](https://mimirwiki.com/ko/wiki/web-bot-auth) 서명, 고정 사용자 에이전트와 공개 IP 목록, 또는 역방향 DNS를 통한 결정적 신원 확인과 함께 `robots.txt` 및 크롤링 지시문 준수, 합리적인 요청 속도 유지라는 두 가지 요건을 충족해야 한다.[6] `AI Crawler`, `AI Search`, `AI Assistant` 같은 기존 WAF 범주도 하위 호환성을 위해 계속 사용할 수 있다.[6] Cloudflare는 `robots.txt`의 `crawl-delay` 지시문을 지키지 않는 AI 크롤러를 정책 위반 사례로 명시해 전역 허용 목록에서 제외할 수 있으며, 한 조직이 반복적으로 정책을 위반하거나 일부 봇만 정책을 준수하는 경우 해당 조직이 운영하는 모든 봇의 Verified 자격을 취소할 수 있다고 밝힌다.[6]

Cloudflare는 2026년 9월 15일에도 사이트 소유자가 AI 학습은 거부하면서 검색 색인은 유지할 수 있는 `Disallow AI Training` 설정과 `Accountable` 지정 제도를 발표했으며, Apple, Google, Microsoft가 이 설정을 따르고 있거나 따르기로 약속했다고 밝혔다.[8]

## ClaudeBot 관련 게시자 보고와 크롤링 소송

ClaudeBot은 높은 요청량과 관련해 웹사이트 관리자들의 공개 보고 대상이 되었고, Anthropic의 웹 크롤링 관행 전반은 법적 소송의 대상이 되었다.[2][3] 2024년 7월 25일 *The Verge* 보도에 따르면, iFixit 최고경영자 Kyle Wiens는 ClaudeBot이 24시간 동안 iFixit 서버에 거의 100만 건의 요청을 보내 경보가 울리고 데브옵스(DevOps) 팀이 대응해야 했다고 밝혔다.[3]

iFixit의 이용약관(Terms of Use)은 사전 서면 허가 없이 사이트 콘텐츠를 복제, 복사 또는 배포하는 행위를 금지하며, 기계학습이나 AI 모델 학습 목적을 명시적으로 포함하고 있었다.[3] 404 Media가 이에 관해 질의하자 Anthropic은 크롤러를 `robots.txt`로 차단할 수 있다고 안내하는 FAQ 페이지 링크를 제시했다.[3] iFixit이 `robots.txt`에 `crawl-delay` 규칙을 추가한 뒤 Wiens는 서버 로그상 ClaudeBot의 요청이 중단됐다고 *The Verge*에 밝혔으며, Anthropic 대변인 Jennifer Martinez는 Anthropic이 `robots.txt`를 존중하고 iFixit이 해당 신호를 적용한 뒤 크롤러가 이를 따랐다고 전했다.[3]

Wiens가 X에 올린 같은 2024년 7월 게시글 스레드에서 Read the Docs 공동 창립자 Eric Holscher와 Freelancer.com 최고경영자 Matt Barrie도 자사 사이트가 Anthropic 크롤러의 대량 수집 대상이 됐다고 밝혔다.[3] *The Verge*는 이에 앞서 2024년 4월 Linux Mint 웹 포럼이 사이트 장애의 원인으로 ClaudeBot 크롤링에 따른 서버 부하를 지목했다고 전했다.[3]

Anthropic, PBC는 2026년 11월 17일 제출한 Form S-1/A-3에서 자사의 스크래핑, 웹 크롤링 및 데이터 수집 활동이 위법성을 주장하는 소송으로 이어졌고 현재도 소송 대상이라고 공시했다.[2] 구체적으로 신고서는 Reddit, Inc.가 자사 플랫폼 게시물에 대한 부당한 접근을 주장하며 제기한 `Reddit, Inc. v. Anthropic PBC` 소송을 기재했다.[2] Anthropic은 2025년 7월 3일 연방 법원 이송 통지를 제출했고 사건은 2026년 3월 30일 주 법원으로 환송되었으며, 2026년 11월 17일 공시 시점 기준으로 계류 중이었다.[2] Anthropic은 또한 크롤링 관련 소송에서 불리한 합의나 판결이 나올 경우 특정 스크래핑이나 크롤링 기법 중단, 대안 기술 개발, 또는 상당한 금액의 지급이 요구될 수 있다는 점을 사업 위험 요소로 공시했다.[2]

## 자주 묻는 질문

### ClaudeBot은 어떤 용도로 쓰이나요?

2026-11-23 기준 Anthropic은 생성형 AI 모델 학습에 활용될 수 있는 공개 웹 콘텐츠를 수집하기 위해 ClaudeBot을 사용합니다. 검색 색인용 Claude-SearchBot과 사용자 질의에 응답해 웹 페이지를 불러오는 Claude-User는 별도의 봇으로 운영합니다. [4]

### 웹사이트 소유자는 ClaudeBot을 어떻게 차단하거나 속도를 제한하나요?

웹사이트 소유자는 제외하려는 도메인과 모든 하위 도메인의 최상위 디렉터리 robots.txt 파일에 User-agent: ClaudeBot과 Disallow: /를 추가해 ClaudeBot을 차단할 수 있습니다. 요청 빈도를 낮추려면 비표준 Crawl-delay 지시문을 사용할 수 있으며, Anthropic은 2026년 10월 30일부터 IETF aipref 초안 기반의 AI 학습 거부 선호 신호도 인식합니다. [1][4]

### ClaudeBot을 차단하면 사용자 대화 중에 Claude가 웹 페이지를 불러오는 것도 막히나요?

아니요. ClaudeBot 접근을 제한하면 해당 사이트의 향후 콘텐츠를 Anthropic AI 모델 학습 데이터셋에서 제외하겠다는 신호로 처리됩니다. 사용자 요청에 따른 페이지 조회는 Claude-User가, 검색 색인은 Claude-SearchBot이 담당하므로 사이트 소유자는 세 봇에 대해 robots.txt 규칙을 각각 따로 설정할 수 있습니다. [4]

### Anthropic은 왜 IP 주소 차단만으로 ClaudeBot을 막지 말라고 안내하나요?

2026-11-23 기준 Anthropic 크롤러 문서에 따르면, Anthropic 봇이 사용하는 IP 주소를 차단하면 크롤러가 사이트의 robots.txt 파일을 읽지 못하게 되어 안정적이거나 지속적인 옵트아웃이 보장되지 않을 수 있습니다. Anthropic은 크롤러가 자사에서 보낸 요청인지 확인할 수 있도록 출발지 IP 주소 목록을 별도로 안내합니다. [4]

### Cloudflare는 ClaudeBot 같은 학습용 크롤러를 어떻게 분류하나요?

Cloudflare는 2026년 7월 1일 도입한 BotBase 분류 체계에서 봇을 모델 학습 및 미세조정용 Training, 검색 색인이나 RAG 데이터베이스 구축용 Search, 사용자 지시에 따른 Agent 등의 행동 유형으로 분류하며 모든 요금제에서 관리형 프리셋을 제공합니다. 또한 Verified bot 자격을 유지하려면 결정적 신원 확인과 crawl-delay를 포함한 robots.txt 지시문 준수가 필요합니다. [6][7]

### Anthropic은 웹 크롤링과 관련해 어떤 소송을 SEC 공시에 기재했나요?

Anthropic, PBC는 2026년 11월 17일 SEC에 제출한 Form S-1 수정신고서 제3호(S-1/A-3)에서 Reddit 플랫폼 게시물에 부당하게 접근했다고 주장하는 Reddit, Inc. v. Anthropic PBC 소송이 계류 중임을 공시했습니다. Anthropic은 2025년 7월 3일 연방 법원 이송 통지를 제출했으며, 사건은 2026년 3월 30일 주 법원으로 환송되었습니다. [2]

## 인용 문장

- 2026-11-23 기준 Anthropic은 AI 모델 학습용 데이터 수집을 맡는 ClaudeBot, 검색 색인을 담당하는 Claude-SearchBot, 사용자 요청에 따라 페이지를 불러오는 Claude-User 세 가지 웹 로봇을 문서화하고 있다. [4]
- 2026-11-23 기준 Anthropic은 자사 웹 봇이 robots.txt 지시문을 준수하고 비표준 Crawl-delay 확장을 지원하며 CAPTCHA 우회를 시도하지 않는다고 밝힌다. [4]
- Anthropic은 2026년 10월 30일부터 IETF aipref 실무그룹 초안 작업에 기반한 기계 판독형 AI 학습 거부 선호 신호를 인식하기 시작했으며, ClaudeBot을 명시한 robots.txt 규칙이 일반 선호 신호보다 우선한다. [4]
- IETF가 2022년 9월 발행한 RFC 9309는 로봇 배제 프로토콜을 규정하며 robots.txt 규칙이 접근 인가 수단이 아님을 명시한다. [1]
- 2024년 7월 iFixit 최고경영자 Kyle Wiens는 ClaudeBot이 24시간 동안 자사 서버에 거의 100만 건의 요청을 보냈으며, iFixit이 robots.txt에 crawl-delay 지시문을 추가한 뒤 중단됐다고 밝혔다. [3]
- 2026년 9월 10일 발효된 Anthropic 개인정보 처리방침은 모델 학습에 사용하는 여섯 가지 데이터 출처 가운데 하나로 인터넷의 공개 정보를 기재한다. [5]
- Anthropic, PBC가 2026년 11월 17일 미국 증권거래위원회(SEC)에 제출한 Form S-1/A-3에 따르면, Reddit, Inc. v. Anthropic PBC 소송은 2026년 3월 30일 주 법원으로 환송된 뒤 계류 중이다. [2]
- Cloudflare가 2025년 7월 1일 공개한 크롤러 분석에 따르면 2024년 5월부터 2025년 5월 사이 AI 및 검색 크롤러 트래픽은 18% 증가했으며, GPTBot은 305%, Googlebot은 96% 늘어났다. [9]

## 연표

- 2022-09: IETF가 로봇 배제 프로토콜(robots.txt)을 표준화한 RFC 9309를 발행했다. [1]
- 2024-04: Linux Mint 웹 포럼이 ClaudeBot 크롤링에 따른 서버 부하를 사이트 장애 원인으로 지목했다. [3]
- 2024-07-25: The Verge가 ClaudeBot의 24시간 내 약 100만 건 요청과 iFixit의 robots.txt crawl-delay 추가 이후 중단 사실을 보도했다. [3]
- 2025-07-01: Cloudflare가 2024년 5월부터 2025년 5월 사이 AI 및 검색 크롤러 트래픽 18% 증가와 GPTBot 305%, Googlebot 96% 증가를 보고한 분석을 공개했다. [9]
- 2025-07-03: Anthropic이 Reddit 게시물 부당 접근을 다투는 Reddit, Inc. v. Anthropic PBC 소송에서 연방 법원 이송 통지를 제출했다. [2]
- 2026-03-30: Reddit, Inc. v. Anthropic PBC 소송이 연방 법원에서 주 법원으로 환송됐다. [2]
- 2026-07-01: Cloudflare가 모든 고객을 대상으로 Search, Agent, Training 트래픽 제어 옵션을 도입하고 BotBase에 Direct 및 Intermediary 접근 라벨을 추가했다. [6][7]
- 2026-09-10: 공개 인터넷 정보를 포함한 여섯 가지 모델 학습 데이터 출처를 명시한 Anthropic 개인정보 처리방침이 발효됐다. [5]
- 2026-09-15: Cloudflare가 검색 색인을 유지하면서 AI 학습을 거부하는 Disallow AI Training 설정과 Accountable 지정을 발표하고, Apple, Google, Microsoft가 이 설정을 따르고 있거나 따르기로 약속했다고 밝혔다. [8]
- 2026-10-30: Anthropic이 IETF aipref 실무그룹 초안 작업에 기반한 기계 판독형 AI 학습 거부 선호 신호를 인식하기 시작했다. [4]
- 2026-11-17: Anthropic, PBC가 SEC에 Form S-1/A-3를 제출해 웹 크롤링 방식, robots.txt 준수 한계 및 계류 중인 크롤링 소송을 공시했다. [2]

## 출처

1. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 게시일 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (확인일 2026-11-23; tier 1: government or public registry)
2. Anthropic, PBC - S-1/A-3. U.S. Securities and Exchange Commission (EDGAR). 게시일 2026-11-17. https://www.sec.gov/Archives/edgar/data/2130357/000162828026074338/anthropicpbc-sx1ax3.htm (확인일 2026-11-23; tier 1: government or public registry)
3. Anthropic’s crawler is ignoring websites’ anti-AI scraping policies | The Verge. The Verge. 게시일 2024-07-25. https://www.theverge.com/2024/7/25/24205943/anthropic-ai-web-crawler-claudebot-ifixit-scraping-training-data (확인일 2026-11-23; tier 2: academic or news)
4. Does Anthropic crawl data from the web, and how can site owners block the crawler? | Claude Help Center. Anthropic. https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler (확인일 2026-11-23; tier 3: official site)
5. Privacy Policy \ Anthropic. Anthropic. 게시일 2026-09-10. https://www.anthropic.com/legal/privacy (확인일 2026-11-23; tier 3: official site)
6. Verified bots · Cloudflare bot solutions docs. Cloudflare. 게시일 2026-11-12. https://developers.cloudflare.com/bots/concepts/bot/verified-bots/ (확인일 2026-11-23; tier 3: official site)
7. Your site, your rules: new AI traffic options for all customers | Cloudflare Blog. The Cloudflare Blog. 게시일 2026-07-01. https://blog.cloudflare.com/content-independence-day-ai-options/ (확인일 2026-11-23; tier 3: official site)
8. Have it both ways: stay discoverable in search while disallowing AI training | Cloudflare Blog. The Cloudflare Blog. 게시일 2026-09-15. https://blog.cloudflare.com/accountable-mixed-use-ai-crawlers/ (확인일 2026-11-23; tier 3: official site)
9. From Googlebot to GPTBot: Who’s crawling your site in 2025 | Cloudflare Blog. The Cloudflare Blog. 게시일 2025-07-01. https://blog.cloudflare.com/from-googlebot-to-gptbot-whos-crawling-your-site-in-2025/ (확인일 2026-11-23; tier 3: official site)
10. Anthropic Crawler IP Prefixes (bots.json). Anthropic. 게시일 2026-10-20. https://claude.com/crawling/bots.json (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "ClaudeBot." 버전 4fd4f3a0, 2026-11-25. https://mimirwiki.com/ko/wiki/claudebot
