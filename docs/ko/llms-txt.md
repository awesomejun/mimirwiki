---
title: "llms.txt"
subtitle: "AI 에이전트에게 웹사이트의 핵심 콘텐츠를 안내하는 마크다운 파일 제안"
canonical_url: https://mimirwiki.com/ko/wiki/llms-txt
language: ko
page_class: anchor
revision_sha256: d2d68766ea0e86135e6a534c797362994c97d0e915be3a48cfca09ed5b030c71
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/ko/wiki/llms-txt.md
  txt: https://mimirwiki.com/ko/wiki/llms-txt.txt
  json: https://mimirwiki.com/ko/wiki/llms-txt.json
  jsonld: https://mimirwiki.com/ko/wiki/llms-txt.jsonld
translations:
  en: https://mimirwiki.com/wiki/llms-txt
  ja: https://mimirwiki.com/ja/wiki/llms-txt
  zh: https://mimirwiki.com/zh/wiki/llms-txt
---

# llms.txt

> llms.txt는 보통 /llms.txt 경로에 두는 마크다운 파일로, AI 에이전트에게 웹사이트의 간략한 개요와 주요 페이지의 마크다운 버전 링크를 제공하자는 웹 관례 제안이다. 제러미 하워드가 2024년 9월 3일 제안을 공개했고 2026년 8월 버전 2를 냈다. 커뮤니티 제안이며 파일 게시는 선택 사항이다.

llms.txt는 웹사이트가 llms.txt라는 이름의 마크다운(Markdown) 파일을 게시해 대규모 언어 모델과 AI 에이전트에게 사이트 개요와 더 자세한 LLM 친화적 콘텐츠로 가는 링크를 제공하자는 웹 관례 제안이다. 제러미 하워드(Jeremy Howard)가 2024년 9월 3일 llmstxt.org에 제안을 공개했고, 2026년 8월 두 번째 버전인 v2를 내놓았다. 파일은 사이트 루트(/llms.txt)나 임의의 하위 경로에 둘 수 있으며, 일반 파서로 읽을 수 있도록 정해진 구획 순서를 따른다. llmstxt.org는 llms.txt를 커뮤니티 의견을 계속 받는 제안으로 소개한다.

**다른 이름:** /llms.txt, The /llms.txt file, llms.txt 제안

## 핵심 정보

- **최초 공개:** 2024-09-03 [1]
- **현재 버전:** v2(2026년 8월) (기준 2026-11-21) [2]
- **작성자:** 제러미 하워드(Jeremy Howard) [1]
- **필수 요소:** 프로젝트나 사이트 이름을 적은 H1 제목 하나 [1]
- **위치:** 사이트 루트의 /llms.txt 또는 임의의 하위 경로 [1]

## 기본 정보

- **유형:** LLM과 AI 에이전트를 위한 마크다운 안내 파일에 관한 웹 관례 제안 [1]
- **작성자:** 제러미 하워드(Jeremy Howard) [1]
- **최초 공개:** 2024-09-03 [1]
- **현재 버전:** v2(2026년 8월) (기준 2026-11-21) [2]
- **파일 이름:** llms.txt [1]
- **위치:** 사이트 루트(/llms.txt) 또는 임의의 하위 경로(예: /docs/llms.txt) [1]
- **형식:** 구획 순서가 정해진 마크다운 [1]
- **필수 요소:** 프로젝트나 사이트 이름을 적은 H1 제목 [1]
- **탐색 수단:** 링크 관계 alternate(유형 text/markdown)와 describedby [1]
- **지위:** 커뮤니티 의견을 받고 있는 제안 [1]
- **저장소:** github.com/AnswerDotAI/llms-txt(Apache-2.0 라이선스) [3]
- **참조 도구:** llms_txt2ctx 명령을 포함한 llms-txt 파이썬 패키지 [4]

## llms.txt란

llms.txt는 웹사이트가 대규모 언어 모델(LLM)과 AI 에이전트에게 자기 콘텐츠를 간결하게 안내하려고 게시하는 [마크다운](https://mimirwiki.com/ko/wiki/markdown)(Markdown) 파일에 관한 제안이다.[1] 제안은 웹 페이지가 사람이 읽도록 만들어졌다는 점을 근거로 든다. HTML 페이지에서는 내비게이션, 광고, 스크립트가 정보를 둘러싸고 있고, 대부분의 웹사이트는 모델의 컨텍스트 윈도(context window)에 통째로 넣기에는 너무 크다.[1] 그래서 llms.txt 파일은 간단한 배경 설명과 안내, 더 자세한 마크다운 파일로 가는 링크를 한곳에 모은다.[1]

llms.txt 제안은 두 부분으로 이루어진다. 하나는 `llms.txt` 파일 자체다. 다른 하나는 에이전트에게 필요할 만한 각 페이지의 깔끔한 마크다운 버전으로, 원래 페이지와 같은 URL에 `.md` 확장자를 붙여 제공한다.[1] 에이전트는 llms.txt 파일을 읽거나 검색해 필요한 항목을 찾은 뒤 해당 링크를 따라가도록 되어 있어, 세부 내용은 필요할 때만 가져온다.[1]

제러미 하워드(Jeremy Howard)는 2024년 9월 3일 llms.txt 제안을 공개했고, 2026년 8월 v2로 표시한 개정본을 내놓았다.[1][2] 제안은 GitHub의 AnswerDotAI/llms-txt 저장소에서 Apache-2.0 라이선스로 관리된다.[3] 제안에 따르면 llms.txt 파일은 소프트웨어 문서에 가장 많이 쓰인다.[1]

## llms.txt 파일 형식

llms.txt 파일은 마크다운으로 작성하며, 다음 요소가 정해진 순서로 들어간다.[1]

- 선택 사항인 바이트 순서 표시(BOM)
- 프로젝트나 사이트의 이름을 적은 H1 제목. 유일한 필수 요소다
- 프로젝트를 짧게 요약한 인용문 블록
- 제목을 제외한 임의 형태의 마크다운 구획 0개 이상. 더 자세한 정보를 담는다
- H2 제목으로 시작하는 구획 0개 이상. 각 구획에는 세부 자료로 가는 링크 목록이 들어간다

llms.txt 링크 목록의 각 항목은 `[name](url)` 형식의 마크다운 하이퍼링크이며, 뒤에 콜론과 해당 파일에 대한 설명을 덧붙일 수 있다.[1] Optional이라는 제목의 구획에는 컨텍스트를 줄여야 할 때 에이전트가 건너뛰어도 되는 부차적인 링크를 둔다. v2에서는 이 구획에 기계적 의미를 부여하던 도구가 제안에서 빠졌기 때문에 관례로만 남아 있다.[1][2]

제안이 XML 같은 구조화 형식 대신 마크다운을 택한 이유는 이 파일을 언어 모델과 에이전트가 읽을 것으로 보기 때문이다. 그래도 배치가 고정되어 있어 일반적인 파서와 정규 표현식으로 처리할 수 있다.[1]

## llms.txt의 위치와 탐색

llms.txt 파일은 웹사이트의 루트 경로인 `/llms.txt`나 `/docs/llms.txt` 같은 임의의 하위 경로에 둘 수 있다. 파일은 자기 경로 아래의 URL을 담당하며, 둘 이상의 파일이 해당할 때 에이전트는 가장 구체적인 파일을 쓰도록 되어 있다.[1] 제안의 첫 버전은 하위 경로를 허용하면서도 그 의미를 정하지 않았고, v2에서 이 규칙이 추가됐다.[2]

개별 페이지에 대해 llms.txt 제안은 같은 URL에 `.md`를 덧붙이거나(`page.html.md`) 확장자를 바꾼(`page.md`) 마크다운 버전을 요구한다. 파일 이름이 없는 URL에는 `index.html.md`나 `index.md`를 쓴다.[1] 첫 버전은 덧붙이는 형식만 규정했다.[2]

버전 2에는 표준 링크 관계(link relation)를 이용한 탐색 방법이 추가됐다. `rel="alternate"`와 `type="text/markdown"`을 지정한 링크는 페이지의 마크다운 버전을, `rel="describedby"`는 그 페이지를 담당하는 llms.txt 파일을 가리킨다. 둘 다 HTML `link` 요소나 HTTP `Link` 헤더로 제공할 수 있다.[1][2] 관계 유형 `alternate`와 `describedby`는 IANA 링크 관계 레지스트리에 등록되어 있다.[9] 제안은 RFC 8615가 정의한 `/.well-known/` 경로 접두사를 쓰지 않는다. 웰노운 URI는 오리진 루트에만 존재하는데, 공유 호스트에서 특정 경로만 관리하는 작성자가 많다는 것이 그 이유다.[1][8]

## llms.txt와 robots.txt, sitemap.xml의 차이

llms.txt와 [robots.txt](https://mimirwiki.com/ko/wiki/robots-txt)는 목적이 다르다. IETF가 2022년 9월 RFC 9309로 발행한 로봇 배제 프로토콜(Robots Exclusion Protocol)은 서비스 소유자가 크롤러의 콘텐츠 접근 방식을 통제하게 해 준다.[7] llms.txt 제안은 접근 통제를 robots.txt의 몫으로 두고, 자신의 콘텐츠는 에이전트가 사용자를 돕다가 어떤 주제에 관한 정보가 필요할 때 그때그때 쓰는 정보라고 설명한다.[1]

llms.txt는 사이트에서 색인할 수 있는 사람용 페이지를 모두 나열하는 [사이트맵](https://mimirwiki.com/ko/wiki/sitemaps)(sitemap)과도 다르다. 제안은 사이트맵이 llms.txt를 대신할 수 없는 이유를 세 가지로 든다. 사이트맵에는 LLM이 읽기 좋은 버전의 페이지가 빠져 있는 경우가 많고, 외부 사이트의 URL이 들어가지 않으며, 사이트맵이 다루는 문서를 모두 합치면 대개 컨텍스트 윈도에 담기에 너무 크다.[1] 이에 비해 llms.txt는 선별한 개요로 설명된다.[1]

작성자는 llms.txt가 모델 학습보다는 추론, 곧 질문에 답하는 시점의 활용에 주로 쓸모가 있을 것으로 예상했다고 밝혔다. v2 본문은 실제로도 그렇게 쓰여 왔다고 전한다.[1]

## llms.txt의 채택 현황과 도구

작성자가 쓴 llms.txt 제안 v2 본문은 수천 개 사이트가 llms.txt 파일을 게시하고 있으며 OpenAI, Anthropic, Google의 Gemini API가 개발자 문서용 llms.txt를 게시한다고 밝힌다.[1] 파일을 자동으로 생성할 수 있는 플랫폼과 플러그인으로는 Mintlify, GitBook, Yoast SEO, AIOSEO, Wix를 든다.[1]

Mintlify 문서는 모든 문서 프로젝트의 루트에 llms.txt 파일을 호스팅하고 `llms-full.txt`라는 파일도 생성한다고 설명한다.[10] `llms-full.txt`라는 이름은 이런 플랫폼에서 나온 것으로, llmstxt.org 제안에는 등장하지 않는다.[1][10] 게시 사례로는 [모델 컨텍스트 프로토콜](https://mimirwiki.com/ko/wiki/model-context-protocol)(Model Context Protocol) 문서 사이트가 있으며, `modelcontextprotocol.io/llms.txt`에서 페이지 색인을 제공한다.[11]

llmstxt.org 사이트는 `llms-txt`라는 파이썬 패키지와 명령줄 도구 `llms_txt2ctx`를 문서화하고 있다. 이 도구는 llms.txt 파일을 해석해 XML 컨텍스트 파일을 만든다.[4] 제안의 첫 버전은 이 도구를 설명했지만, v2에서는 컨텍스트 확장이 제안 본문에서 빠졌다.[2]

## llms.txt의 지위와 한계

llms.txt는 제안 단계에 있다. llmstxt.org는 이 사양이 커뮤니티 의견을 받고 있다고 설명하며, 비공식 개요를 공개 GitHub 저장소에 두고 있다.[1] 2026년 5월 5일 마지막으로 갱신된 Chrome의 Lighthouse 문서는 llms.txt를 새로 떠오르는 관례라고 부른다. Lighthouse는 사이트가 이 파일에 404를 돌려주면 파일 제공이 선택 사항이라는 이유로 llms.txt 감사 항목을 해당 없음으로 처리하고, 파일을 가져오는 중에 서버 오류가 날 때만 페이지를 문제로 표시한다.[5]

llms.txt 게시는 Google의 AI 검색 기능에 노출되기 위한 요건이 아니다. 2025년 12월 10일 마지막으로 갱신된 Google 검색 센터 문서는 AI 개요(AI Overviews)나 AI 모드(AI Mode)에 나타나기 위해 새로운 기계 판독용 파일이나 AI 텍스트 파일을 만들 필요가 없다고 밝힌다.[6]

llms.txt는 다른 웹 관례를 대체하지 않는다. 크롤러 권한을 정하는 것은 여전히 robots.txt의 역할이고, llms.txt는 사이트맵처럼 모든 페이지를 빠짐없이 싣는 색인이 아니다.[1][7] 제안은 llms.txt 파일이 사이트에서 쓰는 구조화 데이터 마크업을 언급해 모델이 그 마크업을 맥락에 맞게 해석하도록 도울 수 있다고 덧붙인다.[1]

## 자주 묻는 질문

### llms.txt란 무엇인가요?

llms.txt는 웹사이트가 AI 에이전트에게 사이트의 간략한 개요와 더 자세한 콘텐츠로 가는 링크를 제공하려고 게시하는 마크다운 파일에 관한 제안입니다. 제러미 하워드가 2024년 9월 3일 제안을 공개했습니다. [1]

### llms.txt 파일은 어디에 두나요?

루트 경로인 /llms.txt나 /docs/llms.txt 같은 하위 경로에 둡니다. 파일은 자기 경로 아래의 URL을 담당하며, 여러 파일이 있으면 가장 구체적인 파일이 적용됩니다. [1]

### llms.txt는 공식 웹 표준인가요?

llmstxt.org는 llms.txt를 커뮤니티 의견을 받고 있는 제안으로 설명합니다. 2026년 5월 5일 마지막으로 갱신된 Chrome의 Lighthouse 문서는 이를 새로 떠오르는 관례라고 부르며 파일 제공을 선택 사항으로 취급합니다. [1][5]

### llms.txt는 robots.txt와 어떻게 다른가요?

RFC 9309로 규정된 robots.txt는 크롤러에게 사이트에 대한 어떤 접근이 허용되는지 알려 줍니다. llms.txt는 권한을 정하지 않으며, 에이전트가 필요할 때 읽고 사이트의 핵심 콘텐츠를 찾는 선별된 개요입니다. [1][7]

### Google의 AI 개요나 AI 모드에 노출되려면 llms.txt가 필요한가요?

아닙니다. 2025년 12월 10일 마지막으로 갱신된 Google 검색 센터 문서는 이 기능들에 나타나기 위해 새로운 기계 판독용 파일이나 AI 텍스트 파일이 필요하지 않다고 밝힙니다. [6]

### llms.txt v2에서는 무엇이 바뀌었나요?

2026년 8월 공개된 버전 2는 alternate와 describedby 링크 관계를 이용한 탐색을 추가하고, 마크다운 페이지 버전의 URL 형식을 두 가지로 허용했으며, 하위 경로에 둔 파일이 담당하는 범위를 정의하고, 컨텍스트 확장 도구를 제안에서 뺐습니다. [2]

## 인용 문장

- llms.txt 제안은 제러미 하워드가 2024년 9월 3일 공개했다. [1]
- llms.txt 제안의 버전 2는 2026년 8월 공개됐다. [2]
- llms.txt 파일에서 유일한 필수 요소는 프로젝트나 사이트의 이름을 적은 H1 제목이다. [1]
- llms.txt 파일은 웹사이트의 루트나 임의의 하위 경로에 둘 수 있으며, 자기 경로 아래의 URL을 담당한다. [1]
- llms.txt 제안 버전 2는 탐색 수단으로 text/markdown 유형의 alternate 링크 관계와 describedby 링크 관계를 권장한다. [1]
- 2026년 5월 5일 마지막으로 갱신된 Chrome의 Lighthouse 문서는 llms.txt 파일 제공을 선택 사항으로 설명한다. [5]
- Google 검색 센터 문서는 AI 개요나 AI 모드에 나타나기 위해 새로운 기계 판독용 파일이나 AI 텍스트 파일이 필요하지 않다고 밝힌다. [6]
- llms.txt 제안은 GitHub의 AnswerDotAI/llms-txt 저장소에서 Apache-2.0 라이선스로 관리된다. [3]

## 연표

- 2024-09-03: 제러미 하워드가 llms.txt 제안을 공개한다. [1]
- 2026-08: llms.txt 제안의 버전 2가 공개된다. [2]

## 출처

1. The /llms.txt file, v2 – llms-txt. llmstxt.org. 게시일 2024-09-03. https://llmstxt.org/ (확인일 2026-11-21; tier 3: official site)
2. Changes – llms-txt. llmstxt.org. 게시일 2026-08. https://llmstxt.org/changes.html (확인일 2026-11-21; tier 3: official site)
3. GitHub - AnswerDotAI/llms-txt: The /llms.txt file, helping language models use your website. AnswerDotAI (GitHub). https://github.com/AnswerDotAI/llms-txt (확인일 2026-11-21; tier 3: official site)
4. Python module & CLI – llms-txt. llmstxt.org. https://llmstxt.org/intro.html (확인일 2026-11-21; tier 3: official site)
5. llms.txt | Lighthouse | Chrome for Developers. Google (Chrome for Developers). 게시일 2026-05-05. https://developer.chrome.com/docs/lighthouse/agentic-browsing/llms-txt (확인일 2026-11-21; tier 3: official site)
6. AI Features and Your Website | Google Search Central | Documentation | Google for Developers. Google Search Central. 게시일 2025-12-10. https://developers.google.com/search/docs/appearance/ai-features (확인일 2026-11-21; tier 3: official site)
7. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 게시일 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (확인일 2026-11-21; tier 1: government or public registry)
8. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). 게시일 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (확인일 2026-11-21; tier 1: government or public registry)
9. Link Relations. Internet Assigned Numbers Authority (IANA). 게시일 2026-06-12. https://www.iana.org/assignments/link-relations/link-relations.xhtml (확인일 2026-11-21; tier 1: government or public registry)
10. llms.txt - Mintlify. Mintlify. https://www.mintlify.com/docs/ai/llmstxt (확인일 2026-11-21; tier 3: official site)
11. Model Context Protocol (llms.txt documentation index). Model Context Protocol project. https://modelcontextprotocol.io/llms.txt (확인일 2026-11-21; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "llms.txt." 버전 d2d68766, 2026-11-21. https://mimirwiki.com/ko/wiki/llms-txt
