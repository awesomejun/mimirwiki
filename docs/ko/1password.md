---
title: "1패스워드 (1Password)"
subtitle: "이중 키 암호화 금고 구조를 사용하는 캐나다 기반 비밀번호 관리 서비스"
canonical_url: https://mimirwiki.com/ko/wiki/1password
language: ko
page_class: entity
revision_sha256: 7398370e9d144c6e9d149d269b00d479aad880c4c00ccf4e29d61b8b3b92b8e4
date_modified: 2026-11-26
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 6
alternates:
  md: https://mimirwiki.com/ko/wiki/1password.md
  txt: https://mimirwiki.com/ko/wiki/1password.txt
  json: https://mimirwiki.com/ko/wiki/1password.json
  jsonld: https://mimirwiki.com/ko/wiki/1password.jsonld
translations:
  en: https://mimirwiki.com/wiki/1password
---

# 1패스워드 (1Password)

> 1패스워드는 이중 키 암호화 방식의 비밀번호 관리 서비스다. 2026년 11월 19일 직원 GitHub 계정 침해로 탐지된 사고에 대해 회사는 11월 25일 일부 고객의 이름·로그인 이메일·식별자·공개키 등이 복사됐지만 암호화 금고 내용과 복호화 키는 안전하다고 설명했다.

1패스워드(1Password)는 캐나다 토론토에 본사를 둔 비밀번호 관리 서비스로, 사용자의 계정 비밀번호와 기기에서 생성되는 34자리 시크릿 키(Secret Key)를 결합한 이중 키 암호화 모델로 금고 데이터를 보호한다. 2026년 11월 25일 1패스워드는 11월 19일 탐지한 백엔드 보안 사고로 일부 고객의 제한된 계정 정보가 복사됐으나, 암호화된 금고 데이터와 비밀번호·시크릿 키는 영향을 받지 않았다고 밝혔다.

**다른 이름:** 1Password, 원패스워드

## 핵심 정보

- **본사:** 캐나다 토론토 [4]
- **암호화 구조:** 계정 비밀번호 + 기기 생성 34자리 시크릿 키(Secret Key) 이중 키 모델 [2]
- **2026년 11월 사고 경과:** 2026년 11월 19일 침해 탐지, 11월 25일 공식 공개 (기준 2026-11-26) [4]
- **금고 영향 여부 (회사 발표):** 암호화 금고 데이터·항목·비밀번호·시크릿 키 미영향, 피싱 주의 권고 (기준 2026-11-26) [1]

## 기본 정보

- **서비스명:** 1패스워드 (1Password) [1]
- **거점:** 캐나다 토론토 [4]
- **보안 모델:** 이중 키 종단간 암호화 (계정 비밀번호 + 34자리 Secret Key) [3]
- **2026년 11월 침입 경로:** 침해된 직원 사내 GitHub 계정으로 백엔드 서비스에 악성 코드 배포 [4]
- **유출된 정보 범위:** 일부 고객의 이름, 로그인 이메일, 계정·사용자 ID, 생성·최종 로그인 시각, 공개키, SRP 매개변수 [5]
- **권장 사용자 조치:** 계정 변경 불필요, 1Password 사칭 피싱 이메일 주의 [1]

## 1패스워드 개요와 이중 키 암호화 구조

1패스워드는 캐나다 토론토 기반 기업이 운영하는 비밀번호 관리 서비스로, 오직 사용자 본인만 데이터를 복호화할 수 있도록 이중 키(dual-key) 보안 모델을 적용한다.[2][4] 각 계정은 사용자가 정한 계정 비밀번호와 사용자 기기에서 생성되어 긴급 키트(Emergency Kit)에 보관되는 고유한 34자리 시크릿 키(Secret Key)를 함께 사용한다.[3]

1패스워드 고객지원 문서에 따르면 회사는 사용자의 시크릿 키 기록을 보유하지 않으며 복구도 불가능하므로, 1패스워드 자체도 고객 금고 내부 항목을 열람할 수 없다.[1][3]

## 1패스워드 2026년 11월 백엔드 보안 사고

1패스워드는 2026년 11월 25일 공격자가 일부 백엔드 시스템에 접근해 일부 고객의 제한된 계정 정보를 복사했다고 공지했다.[1] TechCrunch와 MacRumors에 따르면 1패스워드는 2026년 11월 19일 직원의 사내 GitHub 계정이 침해된 정황을 탐지했으며, 공격자는 해당 권한으로 소스코드에 접근하고 백엔드 서비스에 악성 코드를 배포해 고객 데이터를 내려받았다.[4][5]

1패스워드 공지와 MacRumors 보도에 따르면 복사된 정보에는 일부 고객의 이름, 로그인 이메일 주소, 계정·사용자 식별자, 계정 생성 및 마지막 로그인 시각, 공개키, SRP(Secure Remote Password) 프로토콜 매개변수가 포함됐다.[1][5] 2026년 11월 26일 기준 영향을 받은 전체 고객 수와 독립 외부 검증 결과는 공개되지 않았다.[1][6]

## 1패스워드 금고 안전성, 대응 조치 및 피싱 주의

1패스워드는 11월 25일 공지에서 자사가 고객 비밀번호나 시크릿 키에 접근할 수 없는 구조이므로 고객의 금고 데이터, 저장 항목, 비밀번호, 시크릿 키는 안전하며 영향을 받지 않았다고 밝혔다.[1]

회사는 사고 격리 조치를 시행하고 영향받은 서비스를 정상 버전으로 복구했으며 내부 자격 증명을 교체했다고 설명했다.[1] 또한 고객이 계정에서 별도로 변경할 사항은 없으나, 초대장이나 계정 복구 요청을 사칭한 예상치 못한 1Password 관련 피싱 이메일에 주의하라고 권고했다.[1]

## 1패스워드 2026년 11월 사고 범위와 미확인 사항

1패스워드는 2026년 11월 백엔드 침입으로 제한된 계정 메타데이터가 복사된 대상이 전체가 아닌 일부 고객이며, SRP 매개변수만으로는 계정에 직접 접근할 수 없다고 밝혔다.[1][5] 다만 2026년 11월 26일 기준 영향을 받은 전체 고객 수와 독립 외부 보안 검증 결과는 아직 공개되지 않았다.[1][6]

## 자주 묻는 질문

### 2026년 11월 1패스워드 보안 사고로 금고에 저장된 비밀번호가 유출됐나요?

1패스워드는 2026년 11월 25일 공지에서 회사가 고객 비밀번호나 시크릿 키를 보유하지 않으므로 암호화된 금고 데이터와 저장 항목, 복호화 키는 영향을 받지 않았다고 밝혔습니다. [1][4]

### 이번 사고에서 어떤 계정 정보가 복사됐나요?

1패스워드와 MacRumors에 따르면 일부 고객의 이름, 로그인 이메일 주소, 계정·사용자 ID, 생성 및 마지막 로그인 시각, 공개키, SRP 프로토콜 매개변수가 포함됐습니다. [1][5]

### 공격자는 어떻게 1패스워드 백엔드 시스템에 침입했나요?

TechCrunch와 MacRumors에 따르면 2026년 11월 19일 탐지된 이번 사고는 침해된 직원의 사내 GitHub 계정을 통해 소스코드에 접근하고 백엔드 서비스에 악성 코드를 배포하는 방식으로 발생했습니다. [4][5]

### 1패스워드 이용자가 마스터 비밀번호를 즉시 변경해야 하나요?

1패스워드는 계정에서 별도 변경 조치가 필요하지 않다고 안내했으나, 초대장이나 계정 복구 요청으로 위장한 피싱 이메일에 주의할 것을 권고했습니다. [1]

## 인용 문장

- 1패스워드는 사용자 계정 비밀번호와 기기에서 생성되는 34자리 시크릿 키를 결합한 이중 키 암호화 모델을 사용하며 회사는 시크릿 키를 저장하지 않는다. [2][3]
- 2026년 11월 25일 1패스워드는 11월 19일 탐지한 백엔드 보안 사고를 공개했으며, 공격자가 직원 사내 GitHub 계정을 통해 악성 코드를 배포했다고 확인됐다. [1][4][5]
- 일부 고객의 이름·로그인 이메일·식별자·시각·공개키·SRP 매개변수가 복사됐으나 암호화 금고 데이터와 비밀번호·시크릿 키는 영향을 받지 않았다고 회사는 밝혔다. [1][5]
- 1패스워드는 내부 자격 증명 교체와 정상 서비스 복구를 완료했으며, 계정 변경은 불필요하나 피싱 이메일에 주의하라고 안내했다. [1]

## 출처

1. Update on a security incident involving 1Password's backend systems. 1Password Blog. 게시일 2026-11-25. https://1password.com/blog/update-on-nov-2026-security-incident (확인일 2026-11-26; tier 3: official site)
2. Password Security Manager: Key Principles. 1Password. https://1password.com/security (확인일 2026-11-26; tier 3: official site)
3. About your Secret Key. 1Password Support. https://support.1password.com/secret-key-security/ (확인일 2026-11-26; tier 3: official site)
4. 1Password said hackers broke into its internal systems, but customer passwords are safe. TechCrunch. 게시일 2026-11-25. https://techcrunch.com/2026/11/25/1password-said-hackers-broke-into-its-internal-systems-but-customer-passwords-are-safe/ (확인일 2026-11-26; tier 2: academic or news)
5. 1Password Security Breach: What Was Accessed and What Wasn't. MacRumors. 게시일 2026-11-25. https://www.macrumors.com/2026/11/25/1password-security-breach/ (확인일 2026-11-26; tier 2: academic or news)
6. 1Password Hacked, Customer Data and Source Code Stolen in GitHub Account Breach. The Hacker News. 게시일 2026-11-26. https://thehackernews.com/2026/11/1password-hacked-customer-data-and.html (확인일 2026-11-26; tier 2: academic or news)

## 이 문서 인용하기

Mimirwiki. "1패스워드 (1Password)." 버전 7398370e, 2026-11-26. https://mimirwiki.com/ko/wiki/1password
