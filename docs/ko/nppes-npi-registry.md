---
title: "NPPES와 국가 의료 제공자 식별번호(NPI)"
subtitle: "미국 의료 제공자에게 10자리 식별번호를 부여하고 NPI 레지스트리로 공개하는 연방 시스템"
canonical_url: https://mimirwiki.com/ko/wiki/nppes-npi-registry
language: ko
page_class: anchor
revision_sha256: 6c8e222bc8a4e4a80aca52782a6b680e985b227d3339fcec3fd4d3b1ed76e7f1
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/ko/wiki/nppes-npi-registry.md
  txt: https://mimirwiki.com/ko/wiki/nppes-npi-registry.txt
  json: https://mimirwiki.com/ko/wiki/nppes-npi-registry.json
  jsonld: https://mimirwiki.com/ko/wiki/nppes-npi-registry.jsonld
translations:
  en: https://mimirwiki.com/wiki/nppes-npi-registry
---

# NPPES와 국가 의료 제공자 식별번호(NPI)

> NPPES는 미국 메디케어·메디케이드 서비스 센터(CMS)가 의료 제공자에게 국가 의료 제공자 식별번호(NPI)를 부여하는 시스템이며, NPI는 HIPAA에 따른 10자리 표준 식별자다. 공개 데이터는 NPI 레지스트리에서 검색하거나 읽기 전용 API로 조회할 수 있고, 월간 및 주간 파일로 내려받을 수도 있다. NPI가 있다고 해서 의료 제공자의 면허나 자격이 확인되는 것은 아니다.

NPPES(National Plan and Provider Enumeration System)는 미국 메디케어·메디케이드 서비스 센터(Centers for Medicare & Medicaid Services, CMS)가 의료 제공자에게 국가 의료 제공자 식별번호(National Provider Identifier, NPI)를 부여하는 시스템이다. NPI는 1996년 건강보험 이동성 및 책임에 관한 법률(Health Insurance Portability and Accountability Act, HIPAA)에 따라 채택된 의료 제공자 표준 고유 식별자로, 열 번째 자리가 검증 숫자(check digit)인 10자리 숫자이며 번호 자체에는 의료 제공자에 관한 정보가 담기지 않는다. CMS는 NPPES 기록 가운데 공개 대상인 부분을 NPI 레지스트리 검색 사이트, 읽기 전용 API, 다운로드용 파일로 공개한다. CMS는 NPI 발급이 의료 제공자의 면허나 자격을 보장하거나 확인해 주지 않는다고 밝힌다.

**다른 이름:** NPPES, National Plan and Provider Enumeration System, NPI, National Provider Identifier, NPI Registry, NPI 레지스트리, 국가 의료 제공자 식별번호

## 핵심 정보

- **식별자 형식:** 숫자 10자리, 마지막 자리는 룬(Luhn) 검증 숫자 [4]
- **운영 기관:** 메디케어·메디케이드 서비스 센터(CMS) [6]
- **공개 API 버전:** 2.1(버전 1.0과 2.0은 폐기) (기준 2026-11-21) [5]
- **API 결과 한도:** 요청당 200건, skip 사용 시 검색당 1,200건 (기준 2026-11-21) [5]
- **대량 파일 제공 주기:** 전체 교체 파일은 매월, 증분 파일은 매주 (기준 2026-11-21) [8]

## 기본 정보

- **정식 명칭:** National Plan and Provider Enumeration System [6]
- **운영 기관:** 메디케어·메디케이드 서비스 센터(CMS) [6]
- **발급 식별자:** 국가 의료 제공자 식별번호(NPI) [1]
- **식별자 형식:** 숫자 10자리, 열 번째 자리는 검증 숫자 [3]
- **검증 숫자 알고리즘:** 룬(Luhn) 공식(모듈러스 10 "double-add-double") [4]
- **법적 근거:** HIPAA 행정 간소화 규정, 45 CFR Part 162 Subpart D [2]
- **최종 규칙:** 69 FR 3434, 2004-01-23 게재 [2]
- **개체 유형:** 유형 1(개인), 유형 2(기관) [10]
- **공개 조회:** NPI 레지스트리, npiregistry.cms.hhs.gov [6]
- **API:** 읽기 전용 JSON API, 버전 2.1(2026-11-21 기준) [5]
- **대량 데이터:** 월간 전체 교체 파일, 주간 증분 파일, 월간 비활성화 파일, 모두 버전 2(2026-11-21 기준) [7]
- **전문 분야 코드 집합:** 의료 제공자 분류 코드(Health Care Provider Taxonomy), 전미 통일 청구 위원회(NUCC) 관리 [11]

## 국가 의료 제공자 식별번호(NPI)의 형식과 검증 숫자

NPPES가 부여하는 국가 의료 제공자 식별번호(NPI)는 연방 규정에서 10자리 숫자 식별자로 정의된다. 열 번째 자리는 검증 숫자(check digit)이고, 번호 자체에는 의료 제공자에 관한 정보가 담기지 않는다.[3] CMS는 NPI를 정보를 담지 않는(intelligence-free) 번호라고 설명하는데, 의료 제공자가 거주하는 주나 전문 진료 분야 같은 정보가 숫자에 반영되지 않는다는 뜻이다.[1]

2004년 1월 23일자 CMS 요건 문서에 따르면 NPI는 숫자 9자리 뒤에 검증 숫자 1자리가 붙는 구조이며, 다른 카드 발급자 식별자와 겹치지 않도록 처음에는 첫 자리가 1 또는 2인 번호만 발급한다.[4] 검증 숫자는 모듈러스 10 "double-add-double" 방식의 룬(Luhn) 공식으로 계산한다. NPI를 표준 건강 식별 카드의 카드 발급자 식별자로 쓸 때는 앞에 접두 번호 80840이 붙는데, 80은 보건 분야를, 840은 미국을 뜻한다. 검증 숫자는 언제나 이 접두 번호가 있다고 가정하고 계산하며, 접두 번호 없이 NPI만 쓸 때는 룬 합계에 상수 24를 더해 같은 결과를 얻는다.[4] CMS 문서의 계산 예시에서 9자리 식별자 123456789의 검증 숫자는 3이고, 완성된 NPI는 1234567893이다.[4]

CMS 문서에 나온 형식 규칙을 정리하면 다음과 같다.[4]

| 항목 | 값 |
| --- | --- |
| 길이 | 숫자 10자리 |
| 구조 | 식별자 9자리 뒤에 검증 숫자 1자리 |
| 최초 발급 시 첫 자리 | 1 또는 2 |
| 검증 숫자 알고리즘 | 룬(Luhn) 공식(모듈러스 10 "double-add-double") |
| 카드 발급자 접두 번호 | 80840 |
| 접두 번호가 없을 때 더하는 상수 | 24 |

## 국가 의료 제공자 식별번호(NPI)를 발급받고 사용해야 하는 대상

국가 의료 제공자 식별번호(NPI)는 모든 적용 대상 의료 제공자(covered health care provider)가 발급받아야 한다. NPI 최종 규칙(Final Rule)은 보건복지부 장관이 표준을 채택한 거래와 관련해 건강 정보를 전자적으로 전송하는 의료 제공자를 적용 대상 의료 제공자로 규정한다.[2] 45 CFR 162.410에 따라 적용 대상 의료 제공자는 표준 거래(standard transaction)에서 자신을 식별할 때 NPI를 사용해야 하고, 표준 거래에 NPI가 필요한 기관이 요청하면 NPI를 알려야 하며, 필수 기재 정보가 바뀌면 30일 안에 변경 사실을 알려야 한다.[3] 건강보험자(health plan)와 의료 정보 중계 기관(health care clearinghouse)은 NPI를 부여받은 의료 제공자를 표준 거래에서 그 NPI로 식별해야 하며, 건강보험자는 이미 NPI가 있는 의료 제공자에게 NPI를 추가로 발급받으라고 요구할 수 없다.[3]

적용 대상이 아닌 의료 제공자도 NPI를 발급받을 수 있다.[3] 또한 이 규정은 적용 대상 의료 제공자인 기관에 대해, 소속 구성원이거나 고용 또는 계약 관계에 있는 처방자가 스스로는 적용 대상이 아니더라도 NPPES에서 NPI를 발급받게 하도록 요구한다.[3] 최종 규칙 전문(preamble)은 등록 간호사, 치과위생사, 기사(technician)를 예로 들어, 의료 서비스를 제공하지만 적용 대상 거래를 반드시 수행하지는 않는 사람도 NPI를 받을 자격이 있다고 설명한다.[2]

NPI 최종 규칙은 2004년 1월 23일 연방 관보(Federal Register)에 게재되어 2005년 5월 23일 발효되었고, 의료 제공자는 이 발효일부터 NPI를 신청할 수 있었다. 적용 대상 의료 제공자와 의료 정보 중계 기관, 그리고 소규모 건강보험자를 제외한 건강보험자의 준수 기한은 2007년 5월 23일이었고, 소규모 건강보험자의 기한은 2008년 5월 23일이었다.[2] 최종 규칙 전문은 NPI를 한번 부여되면 계속 유지되는 식별자로 설명한다. 개인에게는 영구적인 번호로 부여하며, 기관은 소유권, 명칭, 주소, 분류 코드가 바뀌어도 새 NPI를 받을 필요가 없다.[2] 비활성화된 NPI는 다른 의료 제공자에게 다시 부여되지 않는다.[3]

## NPPES의 개체 유형: 유형 1 NPI와 유형 2 NPI

NPPES는 모든 국가 의료 제공자 식별번호(NPI)를 두 가지 개체 유형(entity type) 가운데 하나로 부여하며, 유형은 NPI 신청서에서 선택한다. 유형 1(Entity Type 1)은 의사, 치과의사, 간호사, 카이로프랙터, 약사, 물리치료사처럼 의료 서비스를 제공하는 개인에게 해당한다. 유형 2(Entity Type 2)는 병원, 가정간호 기관, 구급차 회사, 그룹 진료소, 건강유지기구(health maintenance organization), 내구성 의료 장비 공급업체, 약국처럼 의료 서비스를 제공하거나 의료 용품을 공급하는 기관에 해당한다.[10]

CMS-10114 신청서는 개인사업자(sole proprietorship)가 유형 1 개인에 해당하며 NPI를 하나만 받을 수 있다고 명시한다. 반면 법인을 설립한 개인은 본인 명의로 유형 1 NPI를, 법인 명의로 유형 2 NPI를 각각 받을 수 있다.[10] 기관은 하위 조직(subpart)별로 NPI를 따로 받을 수도 있다. 신청서는 하위 조직을 기관 의료 제공자의 구성 단위로 설명하며, 소재지가 다르거나 제공하는 의료 서비스의 종류가 다를 수 있다고 덧붙인다.[3][10] NPI 레지스트리 API에서는 두 유형이 `NPI-1`과 `NPI-2`라는 값으로 표시된다.[5]

의료 제공자가 NPI를 신청하는 방법은 세 가지다. NPPES에서 온라인으로 신청하거나, 의료 제공자의 동의를 받아 신청 자료를 일괄 제출하는 전자 파일 교환(Electronic File Interchange, EFI) 기관을 통하거나, 종이 양식 CMS-10114를 NPI 등록 담당 기관(NPI Enumerator)에 우편으로 보내면 된다.[12] 주된 의료 제공자 분류 코드(Healthcare Provider Taxonomy code)는 필수 항목이며, 분류 코드는 최대 15개까지 기재할 수 있다.[9] 이 분류 코드 집합은 전미 통일 청구 위원회(National Uniform Claim Committee, NUCC)가 관리한다. 각 코드는 영문자와 숫자로 이루어진 10자리 값이며, 제공자 그룹, 분류, 세부 전문 분야의 세 단계로 구성된다.[11]

## NPI 레지스트리 검색과 NPPES API(버전 2.1)

npiregistry.cms.hhs.gov의 NPI 레지스트리(NPI Registry)는 CMS의 설명에 따르면 활성 상태인 모든 국가 의료 제공자 식별번호(NPI) 기록을 무료로 조회할 수 있는 디렉터리다. NPI 기록 가운데 CMS가 공개할 필요가 있다고 보는 부분, 곧 의료 제공자의 이름, 전문 분야(분류 코드), 진료 장소 주소 등이 표시된다.[6] NPI 번호, NPI 유형, 분류 코드 설명, 의료 제공자 이름 또는 기관명, 권한 있는 담당자(Authorized Official) 이름, 시, 주, 국가, 우편번호로 검색할 수 있다. 검색 결과는 조건에 맞는 기록 가운데 처음 2,100건까지만 표시된다. NPPES는 2024년 6월 25일부터 시간당 처리할 수 있는 레지스트리 조회 횟수를 제한하고 있으나 검색 페이지에 구체적인 횟수는 나와 있지 않으며, 같은 페이지는 대량 조회에는 데이터 배포 파일을 사용해야 한다고 안내한다.[6]

NPPES API는 레지스트리 데이터를 JSON으로 돌려주는 읽기 전용 인터페이스이며, NPPES에서 매일 데이터를 가져온다.[5] 2026-11-21 기준으로 지원되는 버전은 2.1뿐이다. CMS는 버전 1.0과 2.0이 폐기되었고 버전 표시가 없는 요청도 더 이상 작동하지 않는다고 밝히고 있으며, 버전 2.1의 폐기 예정일은 "TBD"(미정)로 표기한다. 엔드포인트는 `https://npiregistry.cms.hhs.gov/api/?version=2.1`이다.[5] API 도움말 페이지에 나온 요청 한도는 다음과 같다.[5]

| 항목 | 2026-11-21 기준 값 |
| --- | --- |
| 지원 버전 | 2.1 |
| `limit` 기본값 | 10 |
| `limit` 최댓값 | 요청당 결과 200건 |
| `skip` 최댓값 | 기록 1,000건 |
| 한 가지 검색 조건으로 받을 수 있는 최대 기록 수 | 요청 6회에 걸쳐 1,200건 |
| 응답 형식 | JSON |

버전 2.1 문서에 나온 검색 매개변수로는 `number`, `enumeration_type`, `taxonomy_description`, `first_name`, `last_name`, `organization_name`, `city`, `state`, `postal_code`, `country_code`, `limit`, `skip` 등이 있으며, 이 목록에 API 키나 인증용 매개변수는 없다. 이름과 우편번호 항목은 두 글자 이상을 입력한 뒤 끝에 와일드카드를 붙일 수 있다.[5] JSON 응답에는 주소 배열, 분류 코드 배열, 기타 식별자 배열이 들어 있다. 주소 배열의 첫 번째 항목은 주된 진료 장소이고 두 번째 항목은 우편 주소이며, 분류 코드 배열은 최대 15개, 기타 식별자 배열은 최대 50개 항목을 담는다. 이 밖에 다른 이름, 엔드포인트, 추가 진료 장소를 담는 배열도 있다.[5]

## NPPES 다운로드용 데이터 배포 파일

NPPES 데이터는 다운로드용 파일로도 공개된다. CMS는 2007년 9월부터 정보공개법(Freedom of Information Act, FOIA)에 따라 공개할 수 있는 NPPES 의료 제공자 데이터를 두 가지 형태로 공개해 왔다. 하나는 매일 갱신되는 조회 전용 데이터베이스인 NPI 레지스트리이고, 다른 하나는 다운로드용 파일이다. 데이터 열람과 다운로드에는 비용이 들지 않는다.[8] 파일은 월간 전체 교체 NPI 파일, 주간 증분 NPI 파일, 전체 교체 NPI 비활성화 파일의 세 종류다. 주간 파일에는 해당 주에 새로 부여된 NPI, 변경된 정보, 새로 비활성화된 NPI 등 그 주의 데이터만 들어 있으며, 가장 최근의 월간 파일과 함께 쓰도록 만들어졌다.[8]

월간 다운로드 파일은 ZIP 압축 파일로, 안내 문서(readme), 코드 값 문서, 헤더 파일, 그리고 모든 값을 큰따옴표로 감싼 쉼표 구분 데이터 파일이 들어 있다. CMS는 데이터 파일의 크기가 4 GB를 넘으며, 파일을 내려받거나 사용하는 데 대한 헬프데스크나 기술 지원은 제공하지 않는다고 밝힌다.[8] 2018년 6월 18일부터는 압축 파일마다 기타 명칭(Other Name), 진료 장소(Practice Location), 엔드포인트(Endpoint)의 세 가지 참조 파일도 함께 들어 있다.[8] 비활성화된 NPI는 번호와 비활성화 날짜만 공개된다.[8]

2026-11-21 기준으로 NPI 파일 페이지는 버전 2 파일만 제공한다. NPPES는 2026년 3월 3일부로 월간 및 주간 파일의 버전 1 지원을 종료했으며, 버전 2에서는 이름(First Name)과 법적 상호(Legal Business Name) 항목의 글자 수 한도가 늘어났다.[7] 2026-11-21에 이 페이지에는 2026년 11월 9일자 월간 파일(1,079.11 MB ZIP), 같은 날짜의 월간 비활성화 갱신 파일, 그리고 2026년 11월 2일부터 8일까지와 11월 9일부터 15일까지를 다루는 주간 갱신 파일이 올라와 있었다.[7]

## NPPES와 NPI 레지스트리가 검증하지 않는 것

NPPES와 NPI 레지스트리는 의료 제공자의 면허나 자격을 검증하지 않는다. 레지스트리 검색 페이지, API 도움말 페이지, NPI 파일 페이지에는 모두 같은 CMS 안내문이 실려 있다. "Issuance of an NPI does not ensure or validate that the Health Care Provider is Licensed or Credentialed." NPI 발급은 해당 의료 제공자가 면허나 자격을 갖추었음을 보장하거나 확인해 주지 않는다는 뜻이다.[5][6][7] 레지스트리와 다운로드용 파일의 데이터는 의료 제공자 본인이나 대리인, 또는 기관의 권한 있는 담당자가 NPPES에 신고한 내용이며, CMS는 잘못된 정보가 있으면 의료 제공자가 바로잡도록 요청한다.[8]

NPPES 항목 가운데 자격 증명처럼 보이는 것들도 의료 제공자가 직접 기재한 내용이다. 개인 의료 제공자에 대해 공개되는 데이터 항목에는 면허 번호와 면허 발급 주 코드가 포함된다.[9] 분류 코드는 의료 제공자가 스스로 선택하며, NUCC는 면허의 범위가 분류 코드 집합이 다루는 사항이 아니라고 밝힌다.[11] NPI 번호 자체에도 전문 분야나 소재지에 관한 정보는 담겨 있지 않다.[1]

NPPES 데이터 가운데 일부는 공개되지 않는다. 사회보장번호(SSN), 국세청 개인 납세자 식별번호(ITIN), 생년월일은 FOIA에 따른 공개 대상이 아니라고 판단되어 공개되지 않는다.[9] 반대로 활성 NPI를 가진 의료 제공자는 자기 기록의 공개를 거부하거나 기록을 숨길 수 없다.[8] 2004년 최종 규칙 전문은 또한 여러 NPI 유형 사이의 연결 관계를 식별번호 부여 시스템에서 관리하지 않으며, 소유권과 법인 설립에 관한 정보도 이 시스템에 담지 않는다고 밝혔다.[2]

## 자주 묻는 질문

### NPI 번호란 무엇인가요?

국가 의료 제공자 식별번호(NPI)는 HIPAA에 따라 미국 의료 제공자에게 부여하는 표준 고유 식별자입니다. 마지막 자리가 검증 숫자인 10자리 숫자이며, 의료 제공자에 관한 정보는 번호에 담기지 않습니다. 메디케어·메디케이드 서비스 센터(CMS)의 식별번호 부여 시스템인 NPPES를 통해 발급됩니다. [1][3][6]

### NPI가 있으면 면허가 있는 의료 제공자라는 뜻인가요?

아닙니다. CMS는 NPI 레지스트리에서 NPI 발급이 의료 제공자의 면허나 자격을 보장하거나 확인해 주지 않는다고 밝히고 있습니다. NPPES 데이터는 의료 제공자가 직접 신고한 내용이고, 분류 코드도 의료 제공자가 스스로 선택한 것입니다. [6][8][11]

### NPI 검증 숫자는 어떻게 계산하나요?

열 번째 자리는 번호 앞에 접두 번호 80840이 붙어 있다고 가정하고 룬(Luhn) 공식(모듈러스 10 "double-add-double")으로 계산한 검증 숫자입니다. 접두 번호를 쓰지 않을 때는 룬 합계에 상수 24를 더합니다. CMS 예시에서 123456789의 검증 숫자는 3이므로 NPI는 1234567893이 됩니다. [4]

### 유형 1 NPI와 유형 2 NPI는 어떻게 다른가요?

유형 1 NPI는 의료 서비스를 제공하는 개인에게 발급됩니다. 개인사업자도 여기에 해당하며 NPI를 하나만 받을 수 있습니다. 유형 2 NPI는 병원, 그룹 진료소, 약국 같은 기관과 그 하위 조직에 발급됩니다. [10]

### NPI 레지스트리 API에는 어떤 한도가 있나요?

2026-11-21 기준으로 API는 버전 2.1만 지원하며, 요청 한 번에 최대 200건을 돌려줍니다. skip 매개변수로 최대 1,000건까지 건너뛸 수 있어, 한 가지 검색 조건으로 받을 수 있는 기록은 최대 1,200건입니다. CMS는 대량 조회가 필요한 이용자에게 다운로드용 데이터 배포 파일을 쓰도록 안내합니다. [5][6]

### NPPES 공개 데이터는 얼마나 자주 갱신되나요?

CMS는 NPI 레지스트리가 매일 갱신된다고 설명하며, API도 NPPES에서 매일 데이터를 가져옵니다. 전체 교체 다운로드 파일은 매월, 증분 파일은 매주 제공됩니다. [5][8]

## 인용 문장

- 국가 의료 제공자 식별번호(NPI)는 열 번째 자리가 검증 숫자인 10자리 숫자 식별자다. [3]
- NPI 검증 숫자는 번호 앞에 접두 번호 80840이 있다고 가정하고 룬(Luhn) 공식으로 계산한다. [4]
- CMS는 NPI 발급이 의료 제공자의 면허나 자격을 보장하거나 확인해 주지 않는다고 밝힌다. [6]
- 2026-11-21 기준으로 NPPES NPI 레지스트리 API는 버전 2.1만 지원한다. [5]
- 2026-11-21 기준으로 NPPES NPI 레지스트리 API는 요청 한 번에 최대 200건의 결과를 돌려준다. [5]
- NPPES는 전체 교체 NPI 파일을 매월, 증분 NPI 파일을 매주 공개한다. [8]
- NPI 최종 규칙은 2004년 1월 23일 연방 관보 69 FR 3434에 게재되었다. [2]
- NPPES가 보유한 사회보장번호, 국세청 개인 납세자 식별번호, 생년월일은 일반에 공개되지 않는다. [9]

## 연표

- 2004-01-23: 미국 보건복지부가 NPI 최종 규칙(69 FR 3434)을 연방 관보에 게재해 국가 의료 제공자 식별번호를 의료 제공자 표준 고유 식별자로 채택했다. [2]
- 2005-05-23: NPI 최종 규칙이 발효되어 의료 제공자가 NPI를 신청할 수 있게 되었다. [2]
- 2006-05-01: 일괄 등록을 위한 전자 파일 교환(EFI) 절차가 도입되었다. [9]
- 2007-05-23: 적용 대상 의료 제공자, 의료 정보 중계 기관, 소규모 건강보험자를 제외한 건강보험자의 준수 기한이 도래했다. [2]
- 2007-05-30: CMS가 NPPES 데이터 배포 고시(CMS-6060-N)를 연방 관보에 게재했다. [9]
- 2008-05-23: 소규모 건강보험자의 준수 기한이 도래했다. [2]
- 2018-06-18: NPPES 다운로드용 압축 파일에 기타 명칭, 진료 장소, 엔드포인트 참조 파일이 포함되기 시작했다. [8]
- 2024-06-25: NPPES가 시간당 처리할 수 있는 NPI 레지스트리 조회 횟수를 제한하기 시작했다. [6]
- 2026-03-03: NPPES가 월간 및 주간 다운로드용 파일의 버전 1 지원을 종료했다. [7]

## 출처

1. National Provider Identifier Standard (NPI) | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/regulations-and-guidance/administrative-simplification/nationalprovidentstand (확인일 2026-11-21; tier 1: government or public registry)
2. HIPAA Administrative Simplification: Standard Unique Health Identifier for Health Care Providers. Federal Register, Department of Health and Human Services. 게시일 2004-01-23. https://www.federalregister.gov/documents/2004/01/23/04-1149/hipaa-administrative-simplification-standard-unique-health-identifier-for-health-care-providers (확인일 2026-11-21; tier 1: government or public registry)
3. 45 CFR Part 162 Subpart D: Standard Unique Health Identifier for Health Care Providers. Electronic Code of Federal Regulations (eCFR). https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-C/part-162/subpart-D (확인일 2026-11-21; tier 1: government or public registry)
4. Requirements for National Provider Identifier (NPI) and NPI Check Digit. Centers for Medicare & Medicaid Services. 게시일 2004-01-23. https://www.cms.gov/Regulations-and-Guidance/Administrative-Simplification/NationalProvIdentStand/Downloads/NPIcheckdigit.pdf (확인일 2026-11-21; tier 1: government or public registry)
5. NPPES NPI Registry: NPPES API Help. Centers for Medicare & Medicaid Services. https://npiregistry.cms.hhs.gov/api-page (확인일 2026-11-21; tier 1: government or public registry)
6. NPPES NPI Registry: Search NPI Records. Centers for Medicare & Medicaid Services. https://npiregistry.cms.hhs.gov/search (확인일 2026-11-21; tier 1: government or public registry)
7. NPI Files. Centers for Medicare & Medicaid Services. https://download.cms.gov/nppes/NPI_Files.html (확인일 2026-11-21; tier 1: government or public registry)
8. Data Dissemination | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/medicare/regulations-guidance/administrative-simplification/data-dissemination (확인일 2026-11-21; tier 1: government or public registry)
9. HIPAA Administrative Simplification: National Plan and Provider Enumeration System Data Dissemination. Federal Register, Centers for Medicare & Medicaid Services. 게시일 2007-05-30. https://www.federalregister.gov/documents/2007/05/30/07-2651/hipaa-administrative-simplification-national-plan-and-provider-enumeration-system-data-dissemination (확인일 2026-11-21; tier 1: government or public registry)
10. CMS-10114 National Provider Identifier (NPI) Application/Update Form. Centers for Medicare & Medicaid Services. https://www.cms.gov/Medicare/CMS-Forms/CMS-Forms/downloads/CMS10114.pdf (확인일 2026-11-21; tier 1: government or public registry)
11. National Uniform Claim Committee - Provider Taxonomy. National Uniform Claim Committee. https://www.nucc.org/index.php/code-sets-mainmenu-41/provider-taxonomy-mainmenu-40 (확인일 2026-11-21; tier 1: government or public registry)
12. How to Apply | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/medicare/regulations-guidance/administrative-simplification/how-apply (확인일 2026-11-21; tier 1: government or public registry)

## 이 문서 인용하기

Mimirwiki. "NPPES와 국가 의료 제공자 식별번호(NPI)." 버전 6c8e222b, 2026-11-21. https://mimirwiki.com/ko/wiki/nppes-npi-registry
