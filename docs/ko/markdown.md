---
title: "마크다운"
subtitle: "읽기 쉬운 일반 텍스트를 HTML 등으로 변환하는 경량 마크업 언어와 text/markdown 미디어 타입 및 CommonMark, GFM 사양"
canonical_url: https://mimirwiki.com/ko/wiki/markdown
language: ko
page_class: anchor
revision_sha256: 8df6030b73d87e36e86eb7cc0ec84b33938d9a9e39167cf61f2aefe1c04a8a0b
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 8
alternates:
  md: https://mimirwiki.com/ko/wiki/markdown.md
  txt: https://mimirwiki.com/ko/wiki/markdown.txt
  json: https://mimirwiki.com/ko/wiki/markdown.json
  jsonld: https://mimirwiki.com/ko/wiki/markdown.jsonld
translations:
  en: https://mimirwiki.com/wiki/markdown
  ja: https://mimirwiki.com/ja/wiki/markdown
  zh: https://mimirwiki.com/zh/wiki/markdown
---

# 마크다운

> 마크다운(Markdown)은 존 그루버가 에런 스워츠의 기여를 받아 2004년 만든 경량 마크업 언어로, 읽기 쉬운 일반 텍스트를 작성해 HTML로 변환하는 서식 문법이다. 주요 방언으로는 CommonMark와 GitHub Flavored Markdown이 있다. IETF는 2016년 3월 RFC 7763으로 text/markdown 미디어 타입을 등록했으며, llms.txt 같은 제안은 AI 에이전트를 위한 문서 형식으로 마크다운을 사용한다.

마크다운(Markdown)은 읽기 쉬운 일반 텍스트를 HTML 같은 공식 마크업 언어(markup language)로 변환하는 경량 마크업 언어이자 일반 텍스트 서식 문법 계열이다. 존 그루버(John Gruber)가 에런 스워츠(Aaron Swartz)의 주요 기여를 받아 2004년 마크다운을 개발했으며, 문법 설명과 함께 BSD 계열 오픈소스 라이선스로 배포된 펄(Perl) 변환 도구 Markdown.pl을 공개했다. 초기 문법 설명의 모호함으로 구현체마다 해석이 달라지자 명확한 파싱 규칙을 정의하는 CommonMark 사양이 2014년 시작됐고, 2016년 3월 국제인터넷표준화기구(IETF)는 RFC 7763으로 text/markdown 미디어 타입을 등록하고 동반 문서 RFC 7764를 발행했다. GitHub Flavored Markdown(GFM) 같은 방언은 표와 작업 목록 등의 기능으로 CommonMark를 확장하며, llms.txt 같은 웹 관례는 대규모 언어 모델(LLM)과 AI 에이전트에게 구조화된 문서를 제공하는 형식으로 마크다운을 사용한다.

**다른 이름:** Markdown, text/markdown, CommonMark, GFM, GitHub Flavored Markdown

## 핵심 정보

- **개발자:** 존 그루버(에런 스워츠 기여) [2]
- **최초 공개:** 2004년(Markdown 1.0.1은 2004-12-17 공개) [3]
- **MIME 미디어 타입:** text/markdown(RFC 7763, 2016년 3월) [1]
- **공식 핵심 사양:** CommonMark(2014년 시작) [5]
- **주요 확장 방언:** GitHub Flavored Markdown(GFM), 버전 0.29-gfm(2019-04-06) (기준 2026-11-23) [6]

## 기본 정보

- **유형:** 경량 마크업 언어 및 일반 텍스트 서식 문법 [1]
- **개발자:** 존 그루버(John Gruber, 에런 스워츠 주요 기여) [2]
- **최초 공개:** 2004년 [2]
- **초기 변환 도구:** Markdown.pl 1.0.1(Perl, 18KB, 2004-12-17, BSD 계열 오픈소스 라이선스) [3]
- **MIME 미디어 타입:** text/markdown(필수 매개변수: charset, 선택 매개변수: variant) [1]
- **IETF 문서:** RFC 7763 및 RFC 7764(정보용, 2016년 3월, 저자 S. Leonard) [2]
- **핵심 사양:** CommonMark(2014년 시작, 존 맥팔레인 작성) [7]
- **참조 구현:** cmark(C) 및 commonmark.js(JavaScript), BSD 라이선스 [7]
- **CommonMark 관리진:** 존 맥팔레인(John MacFarlane), 마틴 우드워드(Martin Woodward), 제프 애트우드(Jeff Atwood) (기준 2026-11-23) [5]
- **GFM 사양:** 버전 0.29-gfm(2019-04-06), CommonMark의 엄격한 상위 집합 (기준 2026-11-23) [6]
- **AI 웹 관례:** llms.txt 제안(/llms.txt 및 .md 페이지 버전)에 사용 [8]

## 마크다운의 기원과 설계 철학

마크다운(Markdown)은 2004년 존 그루버(John Gruber)가 에런 스워츠(Aaron Swartz)의 주요 기여를 받아 개발했다.[2][5] 그루버는 마크다운을 일반 텍스트 서식 문법과 그 서식을 구조적으로 유효한 HTML로 변환하는 펄(Perl) 소프트웨어 도구(`Markdown.pl`)라는 두 가지 의미로 정의했다.[3] BSD 계열 오픈소스 라이선스의 자유 소프트웨어로 배포된 Markdown 1.0.1(18KB)은 2004년 12월 17일에 공개됐으며, 이것이 `Markdown.pl`의 마지막 갱신판이었다.[3][5]

`Markdown.pl`은 Perl 5.6.0 이상과 표준 모듈 `Digest::MD5`를 필요로 했다.[3] 기본 설정에서는 빈 요소 태그를 XHTML 형식으로 출력하며, 명령줄 옵션 `--html4tags`나 Movable Type의 `MTMarkdownOptions` 컨테이너 태그를 사용해 HTML 4 출력을 설정할 수 있었다.[3] 그루버가 문서화한 초기 지원 환경에는 Movable Type 2.6 이상(인쇄용 따옴표와 대시, 말줄임표를 처리하는 SmartyPants 1.5 이상과의 연동 포함), Blosxom 2.0 이상, Mac OS X용 BBEdit 6.1 이상(및 Mac OS 8.6 이상에서 MacPerl 5.6.1과 함께 쓰는 BBEdit 5.1 이상), 유닉스 명령줄 실행이 포함됐다.[3] 그루버는 문법 피드백과 테스트, `html2text` 유틸리티를 제공한 에런 스워츠와 피드백을 준 너새니얼 아이언스(Nathaniel Irons), 댄 벤저민(Dan Benjamin), 대니얼 보건(Daniel Bogan), 제이슨 퍼킨스(Jason Perkins)에게 감사를 표했으며, 미셸 포르탱(Michel Fortin)의 PHP 포팅 구현도 소개했다.[3]

마크다운의 최우선 설계 목표는 가독성이다. 서식을 적용한 문서는 태그나 서식 지시문으로 덮여 보이지 않고 일반 텍스트 그대로 게시할 수 있어야 한다.[3][4] 그루버는 Setext, atx, Textile, reStructuredText, Grutatext, EtText 같은 기존 텍스트-HTML 변환 필터의 영향을 받았다고 밝히면서도 가장 큰 영감의 원천으로 일반 텍스트 이메일 형식을 꼽았다.[4] 그루버는 HTML을 출판 형식으로, 마크다운을 HTML 태그의 작은 부분집합에 대응하는 글쓰기 형식으로 설명했다.[1][4] RFC 7764에 따르면 그루버는 신디케이션 피드(syndicated feed)의 엄격한 XML 및 XHTML 처리에서 겪은 문제 이후 비공식적 형식으로 마크다운을 설계했으며, 블로그 글 하나에 들어간 유효하지 않은 XHTML이 트랙백을 통해 여러 웹사이트를 중단시킨 마크 필그림(Mark Pilgrim)의 사고 실험을 언급했다.[2] 포스텔의 법칙(Postel's Law)과 XML 1.0의 치명적 오류 규정을 대비한 결과, 초기 마크다운은 유효하지 않은 문법이라는 개념을 배제하며 단일 표준 관리 기구 없이 운영된다.[1][2]

## 마크다운 문법과 인라인 HTML

마크다운은 구조적 의미와 시각적으로 닮은 출력 가능 구두점 문자를 사용하며, 초기 문법에서는 출력 가능한 US-ASCII 문자로 제한됐다.[1][4] 문법은 문서를 블록 요소(단락, 제목, 인용문, 목록, 코드 블록, 가로줄 또는 주제 구분선)와 스팬(span) 또는 인라인 요소(링크, 강조, 강한 강조, 코드 스팬, 이미지, 자동 링크, 백슬래시 이스케이프)로 구분한다.[4][6]

| 요소 | 초기 마크다운 문법 | CommonMark의 추가 및 명확화 |
| --- | --- | --- |
| 단락 | 빈 줄로 구분된 하나 이상의 연속된 줄, 강제 줄바꿈된 텍스트 지원 | 동일 규칙 유지, 공백이나 탭만 있는 줄을 빈 줄로 간주 |
| 강제 줄바꿈 | 줄 끝에 공백 두 개 이상을 둔 뒤 줄바꿈 | 줄 끝 백슬래시 문법 추가 |
| 제목 | Setext 방식(H1은 `=`, H2는 `-` 밑줄)과 ATX 방식(줄 시작에 `#` 1~6개) | 공백 처리와 블록 우선순위 규칙 표준화 |
| 인용문 | 이메일 방식의 `>` 접두사, 느슨한 줄바꿈과 중첩 및 내부 블록 포함 지원 | 빈 줄로 떨어진 `>` 블록을 별도 인용문으로 유지 |
| 순서 없는 목록 | `*`, `+`, `-` 뒤에 공백 사용 | 글머리 기호가 바뀌면 새 목록 시작 |
| 순서 있는 목록 | 숫자 뒤에 마침표(`.`) 사용(HTML 출력에서 원본 숫자는 무시) | `.` 또는 `)` 구분자 허용, 시작 번호 보존, 구분자 변경 시 새 목록 시작 |
| 코드 블록 | 공백 4칸 또는 탭으로 들여쓴 줄 | 백틱 또는 물결표로 감싸는 펜스 코드 블록 추가 |

마크다운 문법이 다루지 않는 마크업이 필요할 때는 모드 전환 구분자 없이 원시 HTML을 문서 안에 직접 쓸 수 있다.[4] 초기 마크다운에서 `div`, `table`, `pre`, `p` 같은 블록 수준 HTML 요소는 앞뒤를 빈 줄로 띄우고 들여쓰지 않아야 하며, 블록 수준 HTML 태그 내부의 마크다운 문법은 처리되지 않는다.[4] `span`, `cite`, `del` 같은 스팬 수준 HTML 요소는 단락, 목록 항목, 제목 안에 넣을 수 있으며 그 안의 마크다운 문법은 정상적으로 처리된다.[4]

마크다운은 여는 꺾쇠괄호와 앰퍼샌드 문자를 자동으로 이스케이프(escape)한다.[4] 앰퍼샌드가 `&copy;` 같은 기존 HTML 엔티티의 일부이거나 꺾쇠괄호가 HTML 태그 구분자로 쓰이면 그대로 두고, 일반 문자로 쓰인 여는 꺾쇠괄호와 앰퍼샌드는 HTML 엔티티로 변환한다.[4] 마크다운 코드 스팬과 코드 블록 안에서는 꺾쇠괄호와 앰퍼샌드가 항상 자동으로 이스케이프된다.[4]

## 마크다운 미디어 타입 등록 (RFC 7763 및 RFC 7764)

마크다운 콘텐츠는 국제인터넷표준화기구(IETF)가 2016년 3월 RFC 7763을 발행하면서 공식 MIME 미디어 타입(media type)인 `text/markdown`을 부여받았다.[1] Penango, Inc.의 S. 레너드(S. Leonard)가 작성한 정보용(Informational) RFC 7763은 MIME을 지원하는 시스템에서 작성 중인 마크다운 문서를 식별하고 교환하기 위해 `text/troff`(RFC 4263)에서 영감을 받아 `text/markdown`을 등록했다.[1] RFC 7763은 분할 화면 실시간 미리보기 편집기를 핵심 사용 사례로 제시하며, 데스크톱 편집기(MarkdownPad, MultiMarkdown Composer), 브라우저 도구(Dillinger, Markable), 웹 통합 위젯(Discourse, GitHub), 범용 텍스트 편집기(emacs, vi, Notepad) 간 상호운용성을 언급한다.[1]

RFC 7763에 따라 `text/markdown` 미디어 타입은 필수 매개변수 하나와 선택 매개변수 하나를 정의한다.[1] `charset` 매개변수는 RFC 6838 제4.2.1절에 따라 필수이며, 초기 마크다운 규칙이 특정 인코딩을 지정하지 않고 문자 단위로 동작하기 때문에 기본값이 없다.[1] 선택 매개변수인 `variant`는 작성자가 의도한 마크다운 변형을 알리는 대소문자 비구분 US-ASCII 식별자로, 수신 측에 대한 힌트 역할을 한다. 수신 측은 지정된 변형대로 해석하거나 힌트를 무시할 수 있으며, 변형 식별자는 RFC 7763 제6.1절이 규정한 IANA 마크다운 변형(Markdown Variants) 레지스트리에 등록할 수 있다.[1]

2016년 3월 RFC 7763과 함께 S. 레너드가 발행한 동반 정보용 문서 RFC 7764는 마크다운의 설계 철학, 로컬 저장 전략, 변형 등록 템플릿을 다룬다.[2] RFC 7764는 미디어 타입과 매개변수 정보를 로컬 환경에서 유지하는 6가지 일반 전략(파일명 및 속성에 매핑, 인접 파일에 헤더 저장, 콘텐츠에 MIME 헤더 직접 부여, 로컬 배치 스크립트 작성, 마크다운 사전 처리, 문맥 의존)과 Subversion 및 Git용 세부 방식을 정리한다.[2] 아울러 MultiMarkdown, GitHub-Flavored Markdown, Pandoc, Fountain(Fountain.io), CommonMark, `kramdown-rfc2629`(RFC용 마크다운), `rfc7328`(Pandoc2rfc), PHP Markdown Extra 등 8개 주요 마크다운 문법의 등록 템플릿을 수록한다.[2]

RFC 7763은 보안 고려 사항에서 마크다운을 순수 일반 텍스트로만 표시할 경우 텍스트 방향을 바꾸는 유니코드 제어 문자 등을 편집기가 적절히 처리하면 위험이 제한적이라고 설명한다.[1] 반면 마크다운을 HTML 같은 대상 형식으로 변환하면 스크립트 실행, 페이지 리디렉션, 원격 콘텐츠 다운로드, 개인식별정보 전송 등 대상 형식의 보안 위험을 그대로 물려받으며, 내부에 포함된 원시 공식 마크업 조각에 대한 분석과 정화(sanitization)가 필요하다.[1]

## 마크다운을 위한 CommonMark 사양

CommonMark는 마크다운 구현체 간 파싱 차이를 해소하기 위해 2014년 시작된 명확한 마크다운 공식 사양이다.[5] 그루버의 초기 문법 설명에는 하위 목록 들여쓰기, 인용문이나 제목 또는 들여쓰기 코드 블록 앞의 빈 줄 필요 여부, 촘촘한 목록과 느슨한 목록의 구분 규칙, 혼합 목록 기호, 블록과 인라인 요소 간 우선순위 같은 경계 사례가 규정되어 있지 않았다.[5][6] 초기 구현자들은 `Markdown.pl` 코드를 참고했지만 해당 스크립트에는 버그가 있었고 2004년 12월 17일 이후 갱신되지 않았다.[5] 그 뒤 10년 동안 여러 프로그래밍 언어로 수십 개의 구현체가 만들어지면서 GitHub 위키와 Pandoc 등 시스템마다 같은 문서가 다르게 렌더링되는 현상이 생겼고, 마크다운에는 구문 오류 개념이 없어 차이가 바로 드러나지 않았다.[5][6] 기존 테스트 도구 MDTest는 구식이 됐으며 BabelMark 2와 Babelmark 3가 20개 이상의 구현체 출력을 비교하는 데 쓰였다.[5][7]

CommonMark 작업은 2014년 존 맥팔레인(John MacFarlane, Pandoc), 데이비드 그린스팬(David Greenspan, Meteor), 비센트 마르티(Vicent Marti, GitHub), 닐 윌리엄스(Neil Williams, Reddit), 벤야민 둠케폰데어에헤(Benjamin Dumke-von der Ehe, Stack Overflow / Stack Exchange), 제프 애트우드(Jeff Atwood, Discourse)가 시작했다.[5][7] 사양 본문은 `pandoc`, `peg-markdown`, `lunamark`를 개발한 존 맥팔레인이 작성했으며, 카를리스 강기스(Kārlis Gaņģis)가 강조, 링크, 이미지 규칙을 다듬는 데 기여했다.[7] 2026-11-23 기준 `commonmark.org`에는 존 맥팔레인, 마틴 우드워드(Martin Woodward, GitHub), 제프 애트우드가 관리진으로 올라 있다.[5]

CommonMark 사양은 사람 작성자의 관점에서 구조 요소를 선언적으로 기술한 `spec.txt`로 관리된다.[7] 모든 유니코드 코드 포인트 시퀀스는 유효한 CommonMark 문서로 취급되며, 보안을 위해 `U+0000`은 유니코드 대체 문자 `U+FFFD`로 치환된다.[6] 공백이 블록 구조를 결정하는 문맥에서 탭은 4문자 탭 간격으로 동작하고 내부 탭은 문자 그대로 유지된다.[6] 파싱은 2단계로 진행되며, 1단계에서 블록 구조(제목, 단락, 주제 구분선, 코드 블록, HTML 블록, 링크 참조 정의 같은 리프 블록과 인용문, 목록 같은 컨테이너 블록)를 해석한 뒤 2단계에서 인라인 구조를 해석하며 블록 구조 지시자가 항상 인라인 지시자보다 우선한다.[6]

CommonMark가 초기 마크다운과 달리 명시한 주요 변경 사항으로는 모든 ASCII 구두점 기호의 백슬래시 이스케이프 허용, 줄 끝 백슬래시를 이용한 강제 줄바꿈 추가, 인라인 및 참조 링크 모두에서 작은따옴표 링크 제목 허용, 과도한 역추적(backtracking)을 피하는 HTML 블록 규칙 개정, 빈 줄로 분리된 `>` 블록을 별도 인용문으로 유지, 글머리 기호나 순서 목록 구분자(`. ` 또는 `)`) 변경 시 새 목록 시작, 순서 있는 목록의 시작 번호 보존, 백틱 또는 물결표 펜스 코드 블록 지원이 있다.[7] 사양 저장소(`github.com/commonmark/commonmark-spec`)에는 `test/spec_tests.py`로 실행하고 `commonmark-spec` npm 패키지로 JSON 추출할 수 있는 500건 이상의 마크다운-HTML 병렬 적합성 테스트가 들어 있으며, BSD 라이선스의 C(`cmark`) 및 JavaScript(`commonmark.js`) 참조 구현이 별도 저장소에 제공된다.[7] 2026-11-23 기준 `commonmark.org`는 Discourse, GitHub, GitLab, Reddit, Qt, Stack Overflow / Stack Exchange, Swift를 CommonMark 채택 사이트 및 프로젝트로 열거한다.[5]

## GitHub Flavored Markdown(GFM)

GitHub Flavored Markdown(GFM)은 GitHub.com과 GitHub Enterprise의 사용자 콘텐츠에서 지원하는 마크다운 방언이다.[6] 2026-11-23 기준 공식 GFM 사양은 존 맥팔레인의 CommonMark 사양을 바탕으로 한 2019년 4월 6일자 버전 0.29-gfm이다.[6] GFM은 CommonMark의 엄격한 상위 집합으로 정의되며, CommonMark의 2단계 블록-인라인 파싱 모델을 유지하면서 GitHub 사용자 콘텐츠용 확장을 규정한다.[6]

GFM 사양은 CommonMark에 더해 다음 5가지 공식 확장을 명시한다.[6]

- 표(Tables, 제4.10절): 구조화된 리프 블록 표 문법 추가
- 작업 목록 항목(Task list items, 제5.3절): 체크리스트용 컨테이너 목록 항목 확장
- 취소선(Strikethrough, 제6.5절): 인라인 삭제 텍스트 서식 추가
- 자동 링크 확장(Autolinks extension, 제6.9절): 기본 CommonMark 자동 링크를 넘어선 자동 링크 인식 확장
- 허용되지 않는 원시 HTML(Disallowed Raw HTML, 제6.11절): 렌더링 시 특정 원시 HTML 태그 필터링

GitHub.com과 GitHub Enterprise는 GFM 입력을 HTML로 변환한 뒤 보안과 화면 일관성을 유지하기 위해 추가 후처리와 정화(sanitization)를 수행한다.[6] GitHub-Flavored Markdown은 RFC 7764가 수록한 8개 `text/markdown` 변형 등록 템플릿에도 포함되어 있다.[2]

## 출판과 llms.txt에서의 마크다운 활용

마크다운은 Reddit, Stack Overflow, GitHub, GitLab, Discourse 같은 주요 웹 플랫폼은 물론 도서, 기사, 슬라이드쇼, 편지, 강의 노트, 학술 글쓰기, 시나리오(Fountain), 수학 공식, IETF 인터넷 초안 및 RFC(`kramdown-rfc2629`, `rfc7328`) 작성에도 쓰인다.[1][2][5][6]

AI 및 웹 문서 워크플로에서 마크다운은 제러미 하워드(Jeremy Howard)가 2024년 9월 3일 공개하고 2026년 8월 10일 버전 2로 갱신한 [llms.txt](https://mimirwiki.com/ko/wiki/llms-txt) 제안의 기반 형식이다.[8] 일반 HTML 페이지는 핵심 정보 주변에 내비게이션, 광고, JavaScript가 섞여 있기 때문에 `llms.txt`는 웹사이트의 `/llms.txt`나 `/docs/llms.txt` 같은 하위 경로에 마크다운 안내 파일을 두어 대규모 언어 모델(LLM)과 AI 에이전트에게 간결한 배경 정보와 선별된 링크를 제공하자고 제안한다.[8] `llms.txt` 파일은 선택적 바이트 순서 표시(BOM), 필수 H1 사이트 또는 프로젝트 제목, 선택적 인용문 요약, 선택적 본문 구획, 마크다운 링크 목록을 담은 H2 구획의 정해진 순서를 따르므로 언어 모델뿐 아니라 일반 파서와 정규 표현식으로도 처리할 수 있다.[8]

`llms.txt` 제안은 개별 페이지에 대해서도 원래 URL에 `.md`를 덧붙이거나(`page.html.md`) 확장자를 바꾼(`page.md`) 깔끔한 마크다운 버전을 제공하고, 파일명이 없는 디렉터리 URL에는 `index.html.md`나 `index.md`를 쓰도록 권고한다.[8] 자동 탐색을 위해 `llms.txt` v2는 페이지 마크다운 버전을 가리키는 `rel="alternate"` 및 `type="text/markdown"`(RFC 7763 미디어 타입)과 담당 `llms.txt` 파일을 가리키는 `rel="describedby"`를 HTML `link` 요소나 HTTP `Link` 응답 헤더로 제공하도록 안내한다.[1][8] 2026년 8월 기준 `llms.txt` v2 본문에 따르면 수천 개 웹사이트가 `llms.txt` 파일을 게시하고 있으며 Mintlify와 GitBook 같은 문서 플랫폼이 이를 자동 생성하고, `nbdev` 소프트웨어 문서 프로젝트(Answer.AI, fast.ai, FastHTML 문서 포함)는 기본적으로 모든 페이지의 `.md` 버전을 생성한다.[8] 또한 Chrome의 Lighthouse는 에이전트 브라우징 감사에 `llms.txt` 항목을 포함하며, [OpenAI](https://mimirwiki.com/ko/wiki/openai), [Anthropic](https://mimirwiki.com/ko/wiki/anthropic), [Google Gemini](https://mimirwiki.com/ko/wiki/google-gemini) 같은 AI 제공사들도 [robots.txt](https://mimirwiki.com/ko/wiki/robots-txt) 및 [사이트맵](https://mimirwiki.com/ko/wiki/sitemaps) 같은 기존 웹 관례와 함께 개발자 문서용 `llms.txt` 파일을 게시한다.[8]

## 자주 묻는 질문

### 마크다운이란 무엇인가요?

마크다운(Markdown)은 일반 텍스트 상태에서도 읽기 쉽게 유지하면서 HTML 같은 공식 마크업 언어로 변환할 수 있도록 만든 경량 마크업 언어이자 일반 텍스트 서식 문법입니다. 주로 일반 텍스트 이메일의 서식 관례에서 영감을 받은 구두점 문자를 사용하며 원시 HTML을 직접 섞어 쓸 수 있습니다. [1][3][4]

### 마크다운은 누가 언제 만들었나요?

존 그루버가 에런 스워츠의 주요 기여를 받아 2004년 마크다운을 개발했습니다. 그루버는 2004년 12월 17일 BSD 계열 오픈소스 라이선스로 초기 펄 변환기 Markdown.pl의 마지막 갱신판인 Markdown 1.0.1을 공개했습니다. [2][3][5]

### 마크다운의 공식 MIME 미디어 타입은 무엇인가요?

마크다운의 공식 MIME 미디어 타입은 text/markdown이며, IETF가 2016년 3월 정보용 문서 RFC 7763을 통해 등록했습니다. 기본값이 없는 charset 매개변수가 필수이고 대소문자를 구분하지 않는 US-ASCII 형식의 variant 매개변수를 선택적으로 받으며, 동반 안내 문서는 RFC 7764입니다. [1][2]

### CommonMark는 초기 마크다운과 어떤 관계인가요?

CommonMark는 존 그루버의 초기 문법 설명과 Markdown.pl 이후 생긴 파싱 모호성과 구현체 간 차이를 해결하려고 2014년 시작한 명확한 마크다운 사양입니다. 핵심 마크다운 요소를 유지하면서 펜스 코드 블록, 줄 끝 백슬래시 강제 줄바꿈 문법, 500건 이상의 적합성 테스트 예제를 포함합니다. [5][7]

### GitHub Flavored Markdown은 CommonMark에 어떤 확장을 추가하나요?

버전 0.29-gfm(2019-04-06)으로 규정된 GitHub Flavored Markdown(GFM)은 CommonMark의 엄격한 상위 집합으로 표, 작업 목록 항목, 취소선, 확장 자동 링크, 허용되지 않는 원시 HTML의 5가지 확장을 추가합니다. GitHub.com과 GitHub Enterprise는 GFM을 HTML로 변환한 뒤 추가 후처리와 정화(sanitization)도 수행합니다. [6]

### AI 에이전트를 위한 llms.txt 제안에서 마크다운은 어떻게 쓰이나요?

llms.txt 제안은 정해진 구획 순서를 따르는 마크다운 파일을 /llms.txt나 /docs/llms.txt 같은 하위 경로에 두어 언어 모델과 AI 에이전트가 사이트 개요를 읽고 세부 문서 링크를 따라가게 합니다. 개별 페이지에 대해서도 .md 확장자를 붙인 깔끔한 마크다운 버전을 제공하고 rel="alternate" 및 type="text/markdown" 링크로 탐색하는 방식을 제안합니다. [8]

## 인용 문장

- 마크다운은 2004년 존 그루버가 에런 스워츠의 주요 기여를 받아 개발했다. [2][5]
- 존 그루버는 2004년 12월 17일 BSD 계열 오픈소스 라이선스로 18KB 크기의 펄 스크립트인 Markdown 1.0.1을 공개했다. [3]
- 초기 마크다운은 인라인 원시 HTML을 지원하고 HTML 엔티티를 유지하면서 일반 여는 꺾쇠괄호와 앰퍼샌드를 자동 이스케이프하며 일반 텍스트 이메일에서 주된 문법 영감을 얻었다. [4]
- 국제인터넷표준화기구(IETF)가 2016년 3월 발행한 RFC 7763은 필수 charset 매개변수와 선택 variant 매개변수를 갖춘 text/markdown 미디어 타입을 등록한다. [1]
- RFC 7763의 정보용 동반 문서로 2016년 3월 발행된 RFC 7764는 MultiMarkdown, GitHub-Flavored Markdown, Pandoc, CommonMark를 포함한 8개 마크다운 변형의 등록 템플릿을 제공한다. [2]
- 2014년 시작된 CommonMark 사양은 500건 이상의 내장 적합성 테스트 예제와 함께 BSD 라이선스의 C(cmark) 및 JavaScript(commonmark.js) 참조 구현을 제공한다. [5][7]
- 2019년 4월 6일자 GitHub Flavored Markdown(GFM) 버전 0.29-gfm은 CommonMark의 엄격한 상위 집합으로, 표, 작업 목록 항목, 취소선, 확장 자동 링크, 허용되지 않는 원시 HTML의 5가지 확장을 규정한다. [6]
- 제러미 하워드가 2024년 9월 3일 공개하고 2026년 8월 10일 v2로 갱신한 llms.txt 제안은 언어 모델과 AI 에이전트를 위해 /llms.txt 마크다운 파일과 type="text/markdown" 링크 관계로 탐색하는 .md 페이지 버전을 사용한다. [8]

## 연표

- 2004: 존 그루버가 에런 스워츠의 주요 기여를 받아 일반 텍스트 서식 문법과 펄 변환기 Markdown.pl을 포함한 마크다운을 개발한다. [2][3][5]
- 2004-12-17: 존 그루버가 초기 Markdown.pl 스크립트의 마지막 갱신판인 Markdown 1.0.1을 공개한다. [3][5]
- 2014: 존 맥팔레인, 데이비드 그린스팬, 비센트 마르티, 닐 윌리엄스, 벤야민 둠케폰데어에헤, 제프 애트우드가 CommonMark 사양 작업을 시작한다. [5][7]
- 2016-03: IETF가 text/markdown 미디어 타입을 등록하는 정보용 문서 RFC 7763과 동반 안내 문서 RFC 7764를 발행한다. [1][2]
- 2019-04-06: GitHub이 CommonMark를 기반으로 한 GitHub Flavored Markdown 사양 버전 0.29-gfm을 발행한다. [6]
- 2024-09-03: 제러미 하워드가 언어 모델과 AI 에이전트에게 웹사이트를 안내하는 마크다운 파일 기반 llms.txt 제안을 공개한다. [8]
- 2026-08-10: 마크다운 개요 파일, .md 페이지 버전, type="text/markdown" 링크 관계 탐색을 기술한 llms.txt 제안 버전 2가 llmstxt.org에서 갱신된다. [8]

## 출처

1. RFC 7763: The text/markdown Media Type. Internet Engineering Task Force (IETF). 게시일 2016-03. https://www.rfc-editor.org/rfc/rfc7763.txt (확인일 2026-11-23; tier 1: government or public registry)
2. RFC 7764: Guidance on Markdown: Design Philosophies, Stability Strategies, and Select Registrations. Internet Engineering Task Force (IETF). 게시일 2016-03. https://www.rfc-editor.org/rfc/rfc7764.txt (확인일 2026-11-23; tier 1: government or public registry)
3. Daring Fireball: Markdown. Daring Fireball. https://daringfireball.net/projects/markdown/ (확인일 2026-11-23; tier 3: official site)
4. Daring Fireball: Markdown Syntax Documentation. Daring Fireball. https://daringfireball.net/projects/markdown/syntax (확인일 2026-11-23; tier 3: official site)
5. CommonMark. CommonMark. https://commonmark.org/ (확인일 2026-11-23; tier 3: official site)
6. GitHub Flavored Markdown Spec. GitHub. 게시일 2019-04-06. https://github.github.com/gfm/ (확인일 2026-11-23; tier 3: official site)
7. GitHub - commonmark/commonmark-spec: CommonMark spec, with reference implementations in C and JavaScript · GitHub. CommonMark (GitHub). https://github.com/commonmark/commonmark-spec (확인일 2026-11-23; tier 3: official site)
8. The /llms.txt file, v2 – llms-txt. llmstxt.org. 게시일 2024-09-03. https://llmstxt.org/ (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "마크다운." 버전 8df6030b, 2026-11-23. https://mimirwiki.com/ko/wiki/markdown
