---
title: "SEC EDGAR"
subtitle: "미국 증권거래위원회의 전자 공시 서류 제출 및 공개 시스템"
canonical_url: https://mimirwiki.com/ko/wiki/sec-edgar
language: ko
page_class: anchor
revision_sha256: 3c257dcb8ff3bc5c672bc5dfbaebbea2bc1b230dfe933e07965a9e1674b51bbd
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/ko/wiki/sec-edgar.md
  txt: https://mimirwiki.com/ko/wiki/sec-edgar.txt
  json: https://mimirwiki.com/ko/wiki/sec-edgar.json
  jsonld: https://mimirwiki.com/ko/wiki/sec-edgar.jsonld
translations:
  en: https://mimirwiki.com/wiki/sec-edgar
---

# SEC EDGAR

> EDGAR(Electronic Data Gathering, Analysis, and Retrieval)는 미국 증권거래위원회(SEC)가 Form 10-K, 10-Q, 8-K 같은 증권 공시 서류를 제출받는 주된 시스템이다. 공개 데이터베이스는 무료로 검색할 수 있고, 제출인은 중앙 색인 키(CIK)로 식별된다. data.sec.gov의 JSON API는 API 키가 필요 없으며, 자동화된 접근은 초당 10건으로 제한된다.

EDGAR(Electronic Data Gathering, Analysis, and Retrieval)는 미국 증권거래위원회(Securities and Exchange Commission, SEC)의 주된 전자 공시 시스템으로, 기업을 비롯한 제출인이 1933년 증권법, 1934년 증권거래법, 1939년 신탁증서법, 1940년 투자회사법에 따른 서류를 이 시스템으로 제출한다. EDGAR의 공개 데이터베이스는 무료로 이용할 수 있다. EDGAR는 제출인마다 중앙 색인 키(Central Index Key, CIK)를, 접수된 제출 건마다 접수 번호(accession number)를 부여한다. SEC는 또한 제출 이력과 추출된 XBRL 재무 데이터를 data.sec.gov의 REST API를 통해 JSON으로 제공하며, 이 API에는 인증이나 API 키가 필요 없다.

**다른 이름:** EDGAR, Electronic Data Gathering, Analysis, and Retrieval, 에드가, SEC 전자 공시 시스템, data.sec.gov

## 핵심 정보

- **운영 기관:** 미국 증권거래위원회(EDGAR 사무국) [1]
- **제출인 식별자:** 중앙 색인 키(CIK), API URL에서는 0으로 채운 10자리 [2]
- **요청 속도 한도:** 이용자당 초당 10건 (기준 2026-11-21) [3]
- **API 인증:** 없음, API 키 불필요 (기준 2026-11-21) [2]
- **전문 검색 범위:** 2001년 이후의 전자 제출 서류 (기준 2026-11-21) [6]

## 기본 정보

- **정식 명칭:** Electronic Data Gathering, Analysis, and Retrieval [1]
- **운영 기관:** 미국 증권거래위원회(SEC) [1]
- **담당 부서:** EDGAR 사무국(EDGAR Business Office) [1]
- **제출인 식별자:** 중앙 색인 키(CIK) [3]
- **제출 건 식별자:** 접수 번호(accession number), 예: 0001193125-15-118890 [3]
- **일반 공개:** 무료 [1]
- **데이터 API:** JSON을 반환하는 data.sec.gov REST API: submissions, company concept, company facts, frames [2]
- **API 인증:** 필요 없음(2026-11-21 기준) [2]
- **요청 속도 한도:** 초당 10건(2026-11-21 기준) [3]
- **접수 시간:** 영업일 미국 동부 시간 오전 6시부터 오후 10시까지 [3]
- **전문 검색 범위:** 2001년 이후의 전자 제출 서류 [6]
- **제출인 로그인:** Login.gov 개인 계정 자격 증명과 다중 요소 인증 [7]

## SEC EDGAR의 개요와 제출 대상

EDGAR(Electronic Data Gathering, Analysis, and Retrieval)는 SEC의 설명에 따르면 1933년 증권법(Securities Act of 1933), 1934년 증권거래법(Securities Exchange Act of 1934), 1939년 신탁증서법(Trust Indenture Act of 1939), 1940년 투자회사법(Investment Company Act of 1940)에 따라 기업을 비롯한 제출인이 서류를 제출할 때 쓰는 주된 시스템이다.[1] 2025년 11월 28일 최종 검토된 SEC 페이지에 따르면 이 시스템은 하루 약 4,700건의 공시 서류를 처리하고, 해마다 3,000테라바이트의 데이터를 일반에 제공하며, 연평균 40,000곳의 신규 제출인을 받아들인다.[1] EDGAR 사무국(EDGAR Business Office)이 이 시스템의 운영 책임 부서로서 거버넌스, 전략 기획, 제출인 지원을 맡는다.[1]

SEC는 외국 기업과 미국 기업 모두 증권신고서(registration statement), 정기 보고서 등 각종 서식을 EDGAR를 통해 전자적으로 제출해야 하며, 누구나 이 정보를 무료로 열람하고 내려받을 수 있다고 밝힌다.[3] 공개 데이터베이스에는 기업 공시 서류 외에 뮤추얼 펀드, 상장지수펀드(ETF), 변액연금, 개인이 제출한 정보도 들어 있다.[1] EDGAR는 영업일인 월요일부터 금요일까지 미국 동부 시간으로 오전 6시부터 오후 10시까지 새 공시 서류를 접수한다. 동부 시간 오후 5시 30분 이후에 시작된 일부 제출 건은 다음 영업일에 공개되며, 소유 지분 보고 서식인 Form 3, 4, 5는 이 기준 시각이 오후 10시다.[3]

SEC는 1983년에 전자 공시 시스템 개발을 시작했고, 1992년 7월 15일 실제 운영되는 EDGAR 시스템을 자발적으로 참여하는 제출인에게 개방했다. 1993년 2월 23일 공표된 규칙으로 전자 제출이 의무화되어 1993년 4월 26일부터 단계적 도입이 시작되었고, 외국 발행인에게 EDGAR 제출을 의무화한 규칙은 2002년 11월 4일 발효되었다.[9] SEC의 데이터 접근 안내 페이지는 EDGAR가 1994/1995년에 시작되었고, 색인 파일에는 1994년 3분기 이후의 모든 공개 공시 서류가 수록되어 있다고 설명한다.[3]

## EDGAR 식별자: CIK와 접수 번호

EDGAR는 제출인이 SEC에 서류를 제출하기 위해 등록할 때 중앙 색인 키(Central Index Key, CIK)라는 고유한 숫자 식별자를 부여한다. CIK 번호는 해당 제출인에게만 쓰이며 다른 제출인에게 재사용되지 않는다.[3] 제출인에는 기업, 펀드, 개인이 모두 포함되며, 기업이나 펀드의 명칭이 바뀐 경우에는 하나의 CIK에 여러 명칭이 연결될 수 있다.[3] data.sec.gov API의 URL에서는 CIK를 앞자리를 0으로 채운 10자리 숫자로 표기한다.[2]

접수된 제출 건마다 EDGAR가 자동으로 부여하는 고유 식별자인 접수 번호(accession number)가 붙는다. SEC가 예로 든 0001193125-15-118890에서 앞의 10자리는 서류를 제출한 주체의 CIK이며, 제출 주체는 해당 기업일 수도 있고 제3자 제출 대행인(filer agent)일 수도 있다. 이어지는 두 자리는 연도이고, 마지막 숫자 묶음은 그 CIK가 제출한 건수를 차례로 센 일련번호다. 이 일련번호는 대개 매년 초에 초기화되지만 항상 그런 것은 아니다.[3] 두 식별자의 형식을 정리하면 다음과 같다.[2][3]

| 식별자 | SEC 문서의 표기 형식 | 식별 대상 |
| --- | --- | --- |
| 중앙 색인 키(CIK) | API URL에서 `CIK##########`, 0으로 채운 10자리 | 제출인(기업, 펀드, 개인) |
| 접수 번호 | `0001193125-15-118890`: 제출 주체의 CIK, 연도 두 자리, 일련번호 | 접수된 제출 건 하나 |

공시 서류는 두 식별자를 조합한 경로에 저장된다. SEC가 예로 든 경로 `/Archives/edgar/data/1122304/000119312515118890/`에서 첫 번째 디렉터리는 CIK 디렉터리이고, 두 번째는 접수 번호에서 하이픈을 뺀 형태다. 이 경로 형식은 2000년 5월 26일 이후에 제출된 서류에 쓸 수 있다. CIK 디렉터리와 접수 번호 디렉터리는 디렉터리 탐색이 허용되지만, 상위의 `/Archives/edgar/data/` 디렉터리는 탐색할 수 없다.[3] SEC는 종목 코드(ticker), CIK, 회사명을 연결한 `company_tickers.json` 파일도 공개하는데, 주기적으로 갱신하되 정확성이나 수록 범위는 보장하지 않는다고 밝힌다.[3]

## 자주 쓰이는 EDGAR 서식 유형

EDGAR는 공시 서류를 서식 유형(form type)으로 구분하며, 10-K/A처럼 서식 유형 뒤에 "/A"가 붙으면 정정 서류를 뜻한다.[5] 아래 서식 유형은 SEC가 공시 서류 조사 안내와 Form D 안내에서 설명하는 것들 가운데 일부다.[5][11]

| 서식 유형 | 설명 |
| --- | --- |
| 10-K | 감사받은 연간 재무제표가 포함된 연차보고서 |
| 10-Q | 감사받지 않은 분기 재무제표가 포함된 분기보고서 |
| 8-K | 중요한 사건이나 정보를 다음 정기 보고서 전에 공개하는 수시보고서 |
| S-1 | 일반 투자자 대상 증권 공모를 위한 증권신고서로, 기업공개(IPO) 때 흔히 제출 |
| 4 | 기업 내부자의 실질 소유 지분 변동 보고서로, 거래 후 2영업일 이내 제출 |
| 20-F | 외국 민간 발행인(foreign private issuer)의 연차보고서 또는 증권신고서 |
| D | 레귤레이션 D(Regulation D)에 따른 등록 면제 증권 발행 통지 |

EDGAR에 제출하는 Form D는 레귤레이션 D가 SEC 제출을 요구하는 등록 면제 증권 발행 통지로, 증권을 처음 판매한 날부터 15일 안에 제출해야 한다. 2026년 4월 24일 최종 검토된 SEC 페이지에 따르면 SEC는 EDGAR 계정의 개설과 유지, Form D 통지나 정정 서류의 제출에 수수료를 부과하지 않는다.[11] 기업이 Form D를 제출하려면 먼저 EDGAR 계정이 있어야 하고, 계정에는 CIK가 부여된다.[11]

EDGAR의 여러 서식 유형에 담긴 재무제표는 구조화된 데이터로도 제공된다. data.sec.gov의 XBRL API는 Form 10-Q, 10-K, 8-K, 20-F, 40-F, 6-K와 그 변형 서식을 다루며, SEC는 2009년에 XBRL 제출을 처음 의무화했다고 밝힌다.[2] SEC의 설명에 따르면 XBRL은 재무제표 보고에 쓰는 XML 기반 형식으로, 별도의 XML 파일로 제출하거나 HTML 보고서 안에 인라인 XBRL(inline XBRL)로 넣어 제출한다.[2]

## data.sec.gov API, XBRL 프레임, SEC의 공정 접근 규칙

SEC는 EDGAR 데이터를 JSON으로 제공하는 RESTful API를 data.sec.gov에서 운영한다. 2026-11-21 기준으로 이 API는 인증이나 API 키가 필요 없으며, 제출인별 제출 이력과 재무제표의 XBRL 데이터를 제공한다.[2] 문서에 나온 엔드포인트는 다음과 같다.[2]

| 엔드포인트 | 반환 내용 |
| --- | --- |
| `https://data.sec.gov/submissions/CIK##########.json` | 한 제출인의 제출 이력과 현재 명칭, 이전 명칭, 거래소, 종목 코드 등의 메타데이터 |
| `https://data.sec.gov/api/xbrl/companyconcept/CIK##########/us-gaap/AccountsPayableCurrent.json` | 한 기업이 한 가지 개념(concept)에 대해 공시한 모든 XBRL 값 |
| `https://data.sec.gov/api/xbrl/companyfacts/CIK##########.json` | 한 기업의 모든 개념 데이터를 한 번의 호출로 반환 |
| `https://data.sec.gov/api/xbrl/frames/us-gaap/AccountsPayableCurrent/USD/CY2019Q1I.json` | 요청한 역년 기간에 대해 보고 주체마다 사실(fact) 하나씩 |

submissions 엔드포인트는 최소 1년 치 공시 서류 또는 가장 최근의 1,000건 가운데 더 많은 쪽을 돌려주며, 그보다 오래된 서류는 추가 파일로 안내한다. frames 엔드포인트는 기간을 연간 데이터는 `CY####`, 분기 데이터는 `CY####Q#`, 특정 시점 데이터는 `CY####Q#I` 형식으로 받아, 각 보고 주체의 사실 가운데 해당 역년 기간에 가장 가까운 것을 돌려준다. XBRL 엔드포인트는 us-gaap, ifrs-full, dei, srt처럼 기업이 자체 정의하지 않은 택소노미(taxonomy)를 쓰고 제출 주체 전체에 적용되는 사실만 집계한다.[2] API는 공시 서류가 공개되는 대로 실시간 갱신되며, 통상적인 처리 지연은 제출 이력이 1초 미만, XBRL 데이터가 1분 미만이다. 두 데이터 세트의 대량 압축 파일(`submissions.zip`, `companyfacts.zip`)은 매일 밤 미국 동부 시간 오전 3시경에 다시 게시된다.[2]

EDGAR에 대한 자동화된 접근에는 SEC의 공정 접근(fair access) 규칙이 적용된다. 2026-11-21 기준 최대 요청 속도는 초당 10건이며, SEC는 자동화 클라이언트가 요청 헤더에 사용자 에이전트를 밝히도록 요청한다. SEC가 제시하는 `User-Agent` 예시 값은 회사명 뒤에 관리 담당자의 이메일 주소를 적은 형태다.[3] 이 한도는 요청에 쓰는 기기 수와 관계없이 이용자별로 적용되며, SEC는 과도한 요청을 보내는 IP 주소를 차단할 권리를 보유한다.[4] data.sec.gov는 CORS를 지원하지 않으며, SEC는 스크립트를 이용한 다운로드 절차의 개발이나 디버깅에 대해서는 기술 지원을 제공할 수 없다고 밝힌다.[2]

## EDGAR Next: 제출인 접근 및 계정 관리 제도 변경

EDGAR Next는 SEC가 2024년 9월 27일 채택한 EDGAR 제출인 접근 및 계정 관리에 관한 규칙·서식 개정을 가리키는 이름이다.[8] 개정에 따라 제출인은 EDGAR 계정을 관리할 개인을 지정해 권한을 부여해야 하고, 제출인을 대신해 업무를 처리하는 개인은 Login.gov에서 발급받은 개인 계정 자격 증명을 제시해야 한다. 또한 EDGAR 접근 신청서인 Form ID가 개편되었고, 제출인이 서류 제출, 정보 조회, 계정 관리 업무에 쓸 수 있는 선택 사항인 API가 도입되었다.[8] 개정된 Form ID는 2025년 3월 24일부터 준수해야 했으며, 모든 개정 사항이 같은 날 발효되었다. 개정 사항 전체의 준수 기한은 2025년 9월 15일이었다.[8]

2025년 12월 22일 최종 검토된 SEC의 EDGAR Next 페이지는 EDGAR에 서류를 제출하려면 EDGAR Next를 준수해야 하며 등록(enrollment) 절차는 종료되었다고 밝힌다. 제출인은 EDGAR Next에 등록을 마쳤거나 2025년 3월 24일 이후에 Form ID 신청을 승인받은 상태여야 하며, 접근 권한이 없는 제출인은 EDGAR Filer Management 웹사이트에서 Form ID를 제출해 신청한다.[7] 세 개의 EDGAR 웹사이트(EDGAR Filer Management, EDGAR Online Forms, EDGAR Filing)에 로그인하려면 Login.gov 개인 계정 자격 증명과 다중 요소 인증이 필요하고, 기존 로그인 방식은 폐지되었다.[7] 제출인용 API는 공개용 data.sec.gov API와 별도로 문서화되어 있으며, 해당 안내서는 제출인 API 토큰과 사용자 API 토큰을 다룬다.[2]

## EDGAR 공시 서류가 보증하지 않는 것

SEC EDGAR에 공시 서류가 올라와 있다고 해서 SEC가 그 내용을 검증했다는 뜻은 아니다. SEC 기업금융국(Division of Corporation Finance)은 공시 서류를 선별적으로 심사하며, 자신의 심사 절차가 "is not a guarantee that the disclosure is complete and accurate", 곧 공시가 완전하고 정확하다는 보증은 아니라고 밝힌다. 완전하고 정확한 공시에 대한 책임은 기업과 서류 작성에 관여한 이들에게 있다.[10] 2002년 사베인스-옥슬리법(Sarbanes-Oxley Act of 2002)에 따라 각 보고 기업은 적어도 3년에 한 번은 어떤 수준으로든 기업금융국의 심사를 받는다. 기업금융국은 또한 거래의 타당성을 평가하거나 특정 투자가 투자자에게 적합한지 판단하지 않는다고 덧붙인다.[10]

EDGAR 공시 서류는 등록이나 승인의 증거도 아니다. SEC의 투자자 교육 사이트 Investor.gov는 개인이나 회사가 SEC에 서류를 제출했다고 해서 SEC에 등록된 것은 아니며, SEC는 등록 증명서를 발급하지 않는다고 설명한다.[12] 같은 페이지는 Form D 제출이 개인이나 회사의 SEC 등록 또는 인가 여부와는 아무 관련이 없다고 밝힌다.[12]

EDGAR의 공개 도구에는 수록 범위의 한계도 있다. 전문 검색(Full-Text Search)은 2001년 이후 전자적으로 제출된 공시 서류만 대상으로 하며, 첨부 서류(exhibit) 같은 부속 문서도 검색 범위에 포함된다.[6] 일부 서류는 지금도 종이로 제출되어 EDGAR에서 볼 수 없다. 또한 SEC 직원은 제출인의 요청에 따라 접수 후에도 서류를 삭제하거나 정정할 수 있는데, 다른 제출인 명의로 잘못 제출되었거나 앞서 제출한 서류와 중복되는 경우가 그 예다.[3]

## 자주 묻는 질문

### CIK 번호란 무엇인가요?

중앙 색인 키(Central Index Key, CIK)는 제출인이 SEC에 서류를 제출하기 위해 등록할 때 EDGAR가 부여하는 고유한 숫자 식별자입니다. CIK 번호는 재사용되지 않으며, data.sec.gov API에서는 앞자리를 0으로 채운 10자리로 표기합니다. [3][2]

### SEC EDGAR API를 쓰려면 API 키가 필요한가요?

필요하지 않습니다. 2026-11-21 기준으로 SEC는 data.sec.gov API에 인증이나 API 키가 필요 없다고 밝히고 있습니다. 다만 자동화된 요청은 초당 10건으로 제한되며, SEC는 요청 헤더에 사용자 에이전트를 밝히도록 요청합니다. [2][3]

### SEC는 EDGAR에 올라온 공시 서류의 정확성을 검증하나요?

SEC 기업금융국은 공시 서류를 선별적으로 심사하며, 이 심사 절차가 공시의 완전성과 정확성을 보증하지는 않는다고 밝히고 있습니다. 완전하고 정확한 공시에 대한 책임은 기업과 서류 작성에 관여한 이들에게 있습니다. [10]

### EDGAR에는 언제부터의 공시 서류가 있나요?

SEC는 EDGAR가 1994/1995년에 시작되었다고 설명하며, 색인 파일에는 1994년 3분기 이후의 공개 공시 서류가 수록되어 있습니다. 전문 검색은 2001년 이후 전자적으로 제출된 서류를 대상으로 합니다. [3][6]

### EDGAR Next란 무엇인가요?

EDGAR Next는 SEC가 2024년 9월 27일 채택한 제출인 접근 및 계정 관리에 관한 규칙·서식 개정입니다. 개정 사항은 2025년 3월 24일 발효되었고 준수 기한은 2025년 9월 15일이었습니다. 현재 EDGAR에 로그인하려면 Login.gov 개인 계정 자격 증명과 다중 요소 인증이 필요합니다. [8][7]

### Form 10-K, 10-Q, 8-K는 어떻게 다른가요?

Form 10-K는 감사받은 재무제표가 포함된 연차보고서이고, Form 10-Q는 감사받지 않은 재무제표가 포함된 분기보고서입니다. Form 8-K는 중요한 사건이나 정보를 다음 분기보고서나 연차보고서가 나오기 전에 공개하는 수시보고서입니다. [5]

## 인용 문장

- EDGAR는 Electronic Data Gathering, Analysis, and Retrieval의 약자다. [1]
- EDGAR가 부여한 CIK 번호는 해당 제출인에게만 쓰이며 재사용되지 않는다. [3]
- 2026-11-21 기준으로 SEC의 data.sec.gov API는 인증이나 API 키가 필요 없다. [2]
- 2026-11-21 기준으로 EDGAR에 대한 자동화된 접근의 최대 요청 속도는 초당 10건이다. [3]
- EDGAR 전문 검색은 2001년 이후 전자적으로 제출된 공시 서류를 대상으로 한다. [6]
- SEC는 2024년 9월 27일 EDGAR Next 규칙·서식 개정을 채택했다. [8]
- SEC 기업금융국은 자신의 공시 서류 심사 절차가 공시의 완전성과 정확성을 보증하지 않는다고 밝힌다. [10]
- Form D는 증권을 처음 판매한 날부터 15일 안에 제출해야 한다. [11]

## 연표

- 1992-07-15: 실제 운영되는 EDGAR 시스템이 자발적으로 참여하는 제출인에게 개방되었다. [9]
- 1993-02-23: SEC가 전자 제출을 의무화하는 잠정 규칙을 채택하는 공표문을 냈다. [9]
- 1993-04-26: 제출인을 EDGAR 시스템으로 옮기는 단계적 도입이 시작되었다. [9]
- 1994-12-19: SEC 공표문 제33-7122호로 EDGAR 잠정 규칙이 확정되어 모든 미국 내 등록 기업에 적용되었다. [9]
- 1999-06-28: EDGAR가 HTML 형식의 정식 공시 서류를 접수하기 시작했다. [9]
- 2002-11-04: 외국 발행인에게 EDGAR를 통한 SEC 서류 제출을 의무화한 규칙이 발효되었다. [9]
- 2024-09-27: SEC가 제출인 접근 및 계정 관리에 관한 EDGAR Next 규칙·서식 개정을 채택했다. [8]
- 2025-03-24: EDGAR Next 개정 사항이 발효되었고 개정된 Form ID의 준수가 의무화되었다. [8]
- 2025-09-15: EDGAR Next 규칙·서식 개정 사항 전체의 준수 기한이 도래했다. [8]

## 출처

1. SEC.gov | About EDGAR. U.S. Securities and Exchange Commission. https://www.sec.gov/submit-filings/about-edgar (확인일 2026-11-21; tier 1: government or public registry)
2. SEC.gov | EDGAR Application Programming Interfaces (APIs). U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-application-programming-interfaces (확인일 2026-11-21; tier 1: government or public registry)
3. SEC.gov | Accessing EDGAR Data. U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data (확인일 2026-11-21; tier 1: government or public registry)
4. SEC.gov | Developer Resources. U.S. Securities and Exchange Commission. https://www.sec.gov/about/developer-resources (확인일 2026-11-21; tier 1: government or public registry)
5. SEC.gov | Using EDGAR to Research Investments. U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-search-assistance/using-edgar-research-investments (확인일 2026-11-21; tier 1: government or public registry)
6. SEC.gov | EDGAR Full Text Search FAQ. U.S. Securities and Exchange Commission. https://www.sec.gov/edgar/search/efts-faq.html (확인일 2026-11-21; tier 1: government or public registry)
7. SEC.gov | EDGAR Next: Improving Filer Access and Account Management. U.S. Securities and Exchange Commission. https://www.sec.gov/submit-filings/improving-edgar/edgar-next-improving-filer-access-account-management (확인일 2026-11-21; tier 1: government or public registry)
8. SEC.gov | SEC Adopts Improvements to EDGAR System to Enhance Security, Filer Access, and Account Management. U.S. Securities and Exchange Commission. 게시일 2024-09-27. https://www.sec.gov/newsroom/press-releases/2024-155 (확인일 2026-11-21; tier 1: government or public registry)
9. Electronic Filing and EDGAR (October 2006). U.S. Securities and Exchange Commission. 게시일 2006-10-03. https://www.sec.gov/info/edgar/regoverview.htm (확인일 2026-11-21; tier 1: government or public registry)
10. SEC.gov | Filing Review Process. U.S. Securities and Exchange Commission. https://www.sec.gov/divisions/corpfin/cffilingreview.htm (확인일 2026-11-21; tier 1: government or public registry)
11. SEC.gov | What is Form D?. U.S. Securities and Exchange Commission. https://www.sec.gov/resources-small-businesses/capital-raising-building-blocks/what-form-d (확인일 2026-11-21; tier 1: government or public registry)
12. False Claims of SEC Registration | Investor.gov. U.S. Securities and Exchange Commission, Investor.gov. https://www.investor.gov/protect-your-investments/fraud/types-fraud/false-claims-sec-registration (확인일 2026-11-21; tier 1: government or public registry)

## 이 문서 인용하기

Mimirwiki. "SEC EDGAR." 버전 3c257dcb, 2026-11-21. https://mimirwiki.com/ko/wiki/sec-edgar
