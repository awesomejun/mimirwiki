---
title: "생성형 엔진 최적화"
subtitle: "생성형 AI 검색 응답에서 웹 콘텐츠의 가시성과 인용 가능성을 높이기 위한 기법과 평가 지표"
canonical_url: https://mimirwiki.com/ko/wiki/generative-engine-optimization
language: ko
page_class: concept
revision_sha256: 6df7d51e09510a3defdac1bb8aba9e37ff819e39838e24838f25465c564700fb
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/ko/wiki/generative-engine-optimization.md
  txt: https://mimirwiki.com/ko/wiki/generative-engine-optimization.txt
  json: https://mimirwiki.com/ko/wiki/generative-engine-optimization.json
  jsonld: https://mimirwiki.com/ko/wiki/generative-engine-optimization.jsonld
translations:
  en: https://mimirwiki.com/wiki/generative-engine-optimization
  ja: https://mimirwiki.com/ja/wiki/generative-engine-optimization
  zh: https://mimirwiki.com/zh/wiki/generative-engine-optimization
  es: https://mimirwiki.com/es/wiki/generative-engine-optimization
---

# 생성형 엔진 최적화

> 생성형 엔진 최적화(Generative Engine Optimization, GEO)는 AI 검색 시스템이 생성하는 답변에서 웹 출처의 가시성과 인용 빈도를 높이기 위한 콘텐츠 및 구조 조정 기법이다. 2023년 11월 아가르왈(Aggarwal) 등의 연구진이 GEO-bench 벤치마크와 함께 용어를 제안했으며, 다단계 검색 및 생성 파이프라인에서 작동하므로 측정 효과는 사전 검색 여부와 도메인에 따라 달라진다.

생성형 엔진 최적화(Generative Engine Optimization, GEO)는 생성형 검색 엔진(generative engine)이 합성하는 답변에서 웹 문서의 노출, 인용 가능성, 비중을 높이기 위한 웹 콘텐츠 최적화 패러다임이다. 프란잘 아가르왈(Pranjal Aggarwal), 비슈박 무라하리(Vishvak Murahari), 탄마이 라즈푸로히트(Tanmay Rajpurohit), 아슈윈 칼얀(Ashwin Kalyan), 카르틱 나라심한(Karthik Narasimhan), 아미트 데시판데(Ameet Deshpande)는 2023년 11월 16일 arXiv:2311.09735에서 이 용어를 공식 제안했으며, 해당 논문은 제30회 ACM SIGKDD 학회(KDD 2024)에 채택됐다. 기존 검색 엔진은 순위화된 링크 목록을 반환하고, 생성형 엔진은 검색 백엔드로 웹 문서를 조회한 뒤 대규모 언어 모델(LLM)로 인용이 포함된 자연어 답변을 생성한다. 2026년 7월의 비판적 서베이는 GEO를 크롤링과 색인, 검색, 재순위화, 인용, 충실도에 걸친 확률적이고 부분 관측 가능한 파이프라인으로 설명하며, 2026년 11월 23일 기준 Google 검색 센터 문서는 자사 AI 기능에 별도의 최적화 없이 기존 검색 기술 요건과 SEO 기본 원칙이 적용된다고 밝힌다.

**다른 이름:** GEO, Generative Engine Optimization, 답변 엔진 최적화, 대화형 SEO

## 핵심 정보

- **최초 제안일:** 2023-11-16(arXiv:2311.09735, KDD 2024 채택) [1]
- **제안 연구진:** Aggarwal, Murahari, Rajpurohit, Kalyan, Narasimhan, Deshpande [1]
- **초기 벤치마크:** GEO-bench(다양한 도메인의 질의 10,000건) [2]
- **초기 논문 보고 수치:** 벤치마크 평가 최대 40%, Perplexity.ai 최대 37% 가시성 향상 (기준 2024-06-28) [2]
- **Google 검색 요건:** 검색 기술 요건 외 추가 기술 요건이나 별도 최적화 없음 (기준 2026-11-23) [7]

## 기본 정보

- **유형:** 정보 검색 및 웹 콘텐츠 최적화 패러다임 [1]
- **약어:** GEO [1]
- **최초 제안일:** 2023-11-16(arXiv:2311.09735 v1) [1]
- **학회 발표:** 제30회 ACM SIGKDD 학회(KDD '24), 2024년 8월 25~29일 [2]
- **최초 제안 저자:** Pranjal Aggarwal, Vishvak Murahari, Tanmay Rajpurohit, Ashwin Kalyan, Karthik Narasimhan, Ameet Deshpande [1]
- **저자 소속 기관:** 인도 공과대학교 델리(IIT Delhi), 프린스턴 대학교(Princeton University), 독립 연구자 [2]
- **초기 벤치마크:** GEO-bench(다중 도메인 사용자 질의 10,000건) [2]
- **검토 문헌 규모:** 2023년 11월~2026년 7월 연구 45편(Martinez, 2026) (기준 2026-07-15) [5]
- **구조 최적화 실증 결과:** 6개 엔진에서 인용률 17.3%, 주관적 품질 18.5% 향상(GEO-SFE) (기준 2026-03-31) [4]
- **Google 검색 지침:** AI 개요와 AI 모드에 기존 SEO 기본 원칙과 스니펫 자격 요건 적용 (기준 2026-11-23) [7]

## 생성형 엔진 최적화의 개념과 등장 배경

생성형 엔진 최적화(Generative Engine Optimization, GEO)는 생성형 검색 엔진이 합성하는 답변 안에서 웹 콘텐츠의 노출과 출처 인용을 개선하기 위한 프레임워크다.[1][2] 프란잘 아가르왈(Pranjal Aggarwal), 비슈박 무라하리(Vishvak Murahari), 탄마이 라즈푸로히트(Tanmay Rajpurohit), 아슈윈 칼얀(Ashwin Kalyan), 카르틱 나라심한(Karthik Narasimhan), 아미트 데시판데(Ameet Deshpande)는 2023년 11월 16일 프리프린트 `arXiv:2311.09735` 첫 판에서 이 용어를 처음 제시했고, 2024년 6월 28일 개정판(v3)을 공개한 뒤 2024년 8월 25~29일 바르셀로나에서 열린 제30회 ACM SIGKDD 학회(KDD '24) 논문집에 발표했다.[1][2] 저자들은 인도 공과대학교 델리(Indian Institute of Technology Delhi), 프린스턴 대학교(Princeton University) 및 시애틀의 독립 연구자 소속이었다.[2]

논문은 생성형 엔진(generative engine, GE)을 검색 엔진 백엔드와 여러 대규모 언어 모델(LLM)을 결합한 검색 시스템으로 정식화하며, 배포 사례로 BingChat, Google의 SGE, [Perplexity](https://mimirwiki.com/ko/wiki/perplexity)(Perplexity.ai)를 든다.[2] 정식화된 구조에서 생성형 엔진은 사용자 질의와 선택적 개인화 정보를 입력받아 모듈화된 단계를 거쳐 자연어 응답을 만든다. 질의 재구성 모델이 입력 질의를 하위 질의로 분할하면 검색 엔진이 순위화된 웹 출처를 조회하고, 요약 모델이 각 출처를 요약한 뒤 응답 생성 모델이 본문 내 인용(inline citation)을 포함한 구조화된 답변을 작성한다.[2] 본문 인용은 사용자가 진술을 검증할 수 있게 하고 LLM의 환각(hallucination)을 완화하는 역할을 하며, 답변의 모든 진술이 관련 출처로 뒷받침되는지를 보는 인용 재현율(citation recall)과 각 인용이 해당 진술을 정확히 지지하는지를 보는 인용 정밀도(citation precision)로 평가된다.[2]

생성형 엔진 최적화는 웹사이트 운영자와 콘텐츠 제작자가 직면한 구조적 변화에서 출발했다.[1][2] 생성형 엔진이 포괄적인 답변을 직접 제시하면 사용자가 원본 웹사이트로 이동할 필요가 줄어 자연 유입 트래픽이 감소할 수 있고, 독점적인 블랙박스 생성 구조 때문에 제작자가 콘텐츠의 수집과 표시 방식을 통제하기 어렵다.[2] 마르티네즈의 2026년 서베이는 답변 엔진 최적화(answer engine optimization), 대화형 SEO(conversational SEO), AI 검색 가시성(AI search visibility), 인용 흡수(citation absorption) 등의 검색어로 문헌을 찾았다.[6]

## 생성형 엔진 최적화 프레임워크, 가시성 지표와 GEO-bench

생성형 엔진 최적화(GEO)는 아가르왈 등의 초기 연구에서 원본 웹 페이지를 입력받아 표현 방식, 문체, 내용을 조정한 최적화 버전을 출력하는 블랙박스 최적화 프레임워크로 정의됐다.[1][2] 이 정식화에서 웹사이트 운영자는 생성된 응답 안에서 자기 출처 인용의 가시성(노출도) 함수를 최대화하려 하고, 생성형 엔진은 내부의 비공개 알고리즘을 통해 질의에 대한 출처 관련성과 인용 가시성의 균형을 맞춘다.[2]

생성형 엔진에서의 가시성은 링크가 일렬로 나열되는 기존 검색 결과의 평균 순위와 성질이 다르다.[2] 생성형 응답은 구조화된 문장 속에 여러 출처 인용을 서로 다른 길이, 위치, 서식으로 섞어 배치한다.[2] 이에 따라 GEO 프레임워크는 질의에 대한 인용의 관련성과 영향력을 객관적 지표와 주관적 지표로 함께 측정할 수 있는 맞춤형 가시성 지표 체계를 제안한다.[2]

아가르왈 등은 GEO 기법을 체계적으로 평가하기 위해 다양한 도메인과 관련 웹 출처에서 구성한 10,000건의 사용자 질의로 이루어진 GEO-bench 벤치마크를 공개했다.[1][2] GEO-bench 평가에서 저자들은 제안한 GEO 기법이 다양한 질의에 걸쳐 출처 가시성을 최대 40%까지 높일 수 있다고 보고했다.[1][2] 특히 출처 인용, 관련 출처의 직접 인용문, 통계 수치를 포함하면 여러 질의에서 가시성이 40% 이상 증가했으며, 각 전략의 효과는 도메인마다 다르게 나타나 도메인별 최적화의 필요성이 확인됐다.[1][2] 연구진은 실제 운영 중인 생성형 엔진인 [Perplexity](https://mimirwiki.com/ko/wiki/perplexity)(Perplexity.ai)에서도 실험을 수행해 최대 37%의 가시성 향상을 보고했다.[2]

## 2025~2026년 생성형 엔진 최적화 후속 연구

생성형 엔진 최적화에 관한 학술 연구는 2025년과 2026년에 상용 AI 검색 플랫폼 비교, 문서 구조 공학, 방법론적 비판 검토로 폭넓게 확장됐다.[3][4][5] 2025년 9월부터 2026년 7월 사이에 공개된 세 편의 arXiv 논문은 단일 벤치마크의 텍스트 수정에서 다중 엔진 비교, 구조적 특성 설계, 파이프라인 단위 검증으로 연구가 전개된 흐름을 보여 준다.[3][4][5]

| 연구 | 공개일 | 연구 범위 | 주요 보고 결과 |
| --- | --- | --- | --- |
| Aggarwal 등 (arXiv:2311.09735 / KDD '24) | 2023-11-16 (v3: 2024-06-28) | 10,000건 질의 GEO-bench 및 Perplexity.ai | 벤치마크 평가 최대 40% 가시성 향상, 인용·인용문·통계 추가 시 40% 초과 향상, Perplexity.ai 최대 37% 향상.[1][2] |
| Chen 등 (arXiv:2509.08919) | 2025-09-10 | ChatGPT, Perplexity, Gemini와 Google 검색의 산업·언어·바꿔쓰기 비교 | 브랜드 자체·소셜 콘텐츠 대비 제3자 획득 미디어로의 체계적 편향, 엔진 간 다양성·최신성·표현 민감도의 큰 차이 확인.[3] |
| Yu 등 (arXiv:2603.29979) | 2026-03-31 | 6개 생성형 엔진 대상 구조적 특성 공학(GEO-SFE) | 거시·중간·미시 구조 최적화로 의미를 유지하면서 인용률 17.3%, 주관적 품질 18.5% 향상.[4] |
| Martinez (arXiv:2607.14035) | 2026-07-15 | 2023년 11월~2026년 7월 연구 45편의 비판적 서베이 | GEO를 다단계 확률 파이프라인으로 정식화, 기존 근거가 이미 검색된 문서에 집중되어 있으며 자연 노출·트래픽에 대한 안정적 교차 플랫폼 인과 효과는 미입증.[5][6] |

2025년 9월 천마허(Mahe Chen), 왕샤오쉬안(Xiaoxuan Wang), 천카이원(Kaiwen Chen), 닉 쿠다스(Nick Koudas)는 여러 산업 분야, 언어, 질의 바꿔쓰기 조건에서 [ChatGPT](https://mimirwiki.com/ko/wiki/chatgpt), [Perplexity](https://mimirwiki.com/ko/wiki/perplexity), [Google Gemini](https://mimirwiki.com/ko/wiki/google-gemini)를 기존 Google 웹 검색과 비교하는 대규모 통제 실험을 수행했다.[3] 실험 결과 AI 검색 시스템은 Google 검색이 상대적으로 균형 잡힌 구성을 보이는 것과 대조적으로, 브랜드 자체 사이트나 소셜 미디어보다 공신력 있는 제3자 출처인 획득 미디어(earned media)에 체계적이고 강한 편향을 보였다.[3] 또한 AI 검색 서비스들 사이에서도 도메인 다양성, 최신성, 언어 간 안정성, 질의 표현 변화에 대한 민감도가 크게 달랐다.[3] 이를 바탕으로 저자들은 기계 가독성과 근거 제시를 고려한 콘텐츠 구성, 획득 미디어 확보, 엔진별·언어별 전략 채택, 소규모·틈새 사이트의 대형 브랜드 편향 극복이라는 네 가지 실무 과제를 제시했다.[3]

2026년 3월 위쥔웨이(Junwei Yu), 양무펑(Mufeng Yang), 딩예펑(Yepeng Ding), 사토 히로유키(Hiroyuki Sato)는 의미 내용 수정에 치중했던 기존 접근에 더해 문서 구조의 역할을 분석하는 GEO-SFE(Structural Feature Engineering) 프레임워크를 제안했다.[4] GEO-SFE는 콘텐츠 구조를 거시 구조(문서 아키텍처), 중간 구조(정보 청킹), 미시 구조(시각적 강조)의 세 계층으로 분해하고, 생성형 엔진 아키텍처별로 구조 특성이 인용 확률에 미치는 영향을 모델링한다.[4] 6개 생성형 엔진에서 수행한 실험에서 GEO-SFE는 의미를 보존하면서도 인용률 17.3% 향상과 주관적 품질 18.5% 향상을 일관되게 기록했다.[4]

2026년 7월 올리비에 마르티네즈(Olivier Martinez)는 2023년 11월 16일부터 2026년 7월 14일 사이에 공개되거나 채택된 45편의 GEO 연구와 2023년 12월 EMNLP에 발표된 선행 인용 충실도 연구 및 관련 검색 증강 생성(RAG) 평가 문헌을 검토한 비판적 서베이를 발표했다.[5][6] 이 서베이는 GEO를 검색 활성화, 크롤링과 색인, 검색, 재순위화와 컨텍스트 할당, 인용, 비중, 사실 흡수, 충실도, 사용자 행동으로 이어지는 다단계 파이프라인으로 정식화하고, 노출 가능성, 인용, 내용 흡수, 경제적 성과를 분리하는 가시성 벡터를 제안했다.[5]

## 생성형 엔진 최적화와 SEO, RAG, robots.txt, llms.txt의 관계

생성형 엔진 최적화(GEO)는 검색 엔진 최적화(SEO), 검색 증강 생성(RAG), 크롤러 접근 제어, 기계 판독용 게시 관례와 밀접하게 연결되어 있다.[2][5][7][9] 기존 SEO가 링크 목록의 순위 상승에 초점을 맞춘다면, GEO는 언어 모델이 검색된 문서를 이해하고 요약해 인용하는 과정에 초점을 맞춘다.[2] 생성형 검색 엔진은 기반 검색 색인과 검색 모델에 의존하므로 상위 단계의 SEO 요소가 하위 단계의 인용 결과와 계속 맞물린다.[5][7] 마르티네즈의 2026년 서베이는 한 단계를 개선하는 개입이 다른 단계를 저해할 수 있으며, 특히 인용만을 겨냥한 문장 재작성이 상위 검색 단계의 조회 성능을 떨어뜨릴 수 있다고 지적한다.[5][6]

크롤러 접근 규칙은 웹 콘텐츠가 생성형 검색 색인에 들어갈 수 있는지를 결정한다.[7][9] [robots.txt](https://mimirwiki.com/ko/wiki/robots-txt) 규약은 검색 색인 봇을 비롯한 자동화 도구가 사이트에 어떤 방식으로 접근할 수 있는지 명시하는 수단이다.[9] Google 검색 센터는 AI 검색 기능 노출을 위해 `robots.txt`와 콘텐츠 전송 네트워크(CDN) 또는 호스팅 인프라에서 크롤링을 허용해야 한다고 밝힌다.[7] [OpenAI](https://mimirwiki.com/ko/wiki/openai)는 자사 웹 크롤러를 안내하는 별도의 개발자 문서를 운영한다.[10] 네트워크 인프라 차원에서는 [Cloudflare](https://mimirwiki.com/ko/wiki/cloudflare)가 2026년 7월 1일 모든 고객을 대상으로 AI 트래픽을 검색(Search), 에이전트(Agent), 학습(Training) 세 범주로 구분해 관리할 수 있는 제어 옵션을 발표했다.[11]

게시자 생태계에서는 제러미 하워드(Jeremy Howard)가 2024년 9월 3일 제안하고 2026년 8월 10일 v2로 개정한 [llms.txt](https://mimirwiki.com/ko/wiki/llms-txt) 관례도 함께 논의된다.[9] 이 제안은 사이트 루트(`/llms.txt`)나 하위 경로(`/docs/llms.txt`)에 선별된 마크다운(Markdown) 개요 파일을 두고, 개별 페이지의 `.md` 버전을 HTML `<link>` 요소나 HTTP `Link` 헤더의 `alternate`(`type="text/markdown"`) 및 `describedby` 링크 관계로 탐색할 수 있게 한다.[9] 제안은 크롤러 권한을 지정하는 `robots.txt` 및 색인 가능한 사람용 페이지를 모두 나열해 전체 분량이 LLM 컨텍스트 윈도에 담기기 어려운 사이트맵(`sitemap.xml`)과 `llms.txt`의 역할을 구분한다.[9] 또한 공유 호스트에서 하위 경로만 관리하는 작성자도 게시할 수 있도록 오리진 루트에만 적용되는 RFC 8615의 `/.well-known/` 경로를 사용하지 않는다.[9] 2026년 8월 기준 v2 문서는 `llms.txt`가 주로 추론 시점에 활용돼 왔으며 Mintlify와 GitBook 같은 문서 플랫폼이 자동 생성을 지원하고, [OpenAI](https://mimirwiki.com/ko/wiki/openai), [Anthropic](https://mimirwiki.com/ko/wiki/anthropic), Google의 Gemini가 개발자 문서용 `llms.txt`를 게시한다고 밝힌다. 실제로 OpenAI의 크롤러 문서 상단에서도 전체 문서 색인인 `llms.txt`와 `.md` 마크다운 페이지 제공을 안내한다.[9][10]

## 생성형 엔진 최적화에 대한 플랫폼 공식 지침

생성형 엔진 최적화(GEO)와 관련해 Google 검색 센터는 Google 검색의 AI 개요(AI Overviews)와 AI 모드(AI Mode)에 대한 공식 지침을 제공하고 있다.[7][8] 2026년 11월 23일 기준 Google 공식 문서는 기존 SEO 기본 원칙이 Google 검색의 AI 기능에도 그대로 유효하며, AI 개요나 AI 모드에 노출되기 위해 추가적인 기술 요건이나 별도의 특별한 최적화가 필요하지 않다고 명시한다.[7] 두 기능에서 참고 링크로 표시될 자격을 얻으려면 페이지가 Google 검색의 기술 요건을 충족해 색인되고 스니펫(snippet) 표시 자격을 갖추면 되며, 요건을 충족하더라도 크롤링, 색인, 노출 자체가 보장되지는 않는다.[7]

Google은 AI 개요가 기존 검색 결과에 부가 가치를 더할 수 있다고 판단되는 질의에서만 표시되어 자주 작동하지 않을 수 있다고 설명하며, AI 모드는 추가 탐색, 추론, 복잡한 비교가 필요한 질의에 적합하다고 안내한다.[7] 두 기능은 모두 답변을 구성하는 과정에서 하위 주제와 여러 데이터 출처에 대해 다수의 관련 검색을 동시에 발행하는 "쿼리 팬아웃(query fan-out)" 기법을 사용할 수 있으며, 이를 통해 기존 웹 검색보다 더 다양하고 폭넓은 참고 웹 페이지를 식별한다.[7] AI 개요와 AI 모드는 서로 다른 모델과 기법을 사용할 수 있어 표시되는 응답과 링크 구성이 달라질 수 있다.[7]

Google 검색 센터가 AI 검색 기능에도 계속 유효하다고 열거한 SEO 기본 사항은 다음과 같다.[7]

- `robots.txt` 및 CDN·호스팅 인프라에서 크롤링 허용 유지
- 웹사이트 내부 링크를 통한 콘텐츠 탐색 가능성 확보
- 양호한 페이지 경험 제공과 핵심 콘텐츠의 텍스트 형태 게시
- 필요한 경우 고품질 이미지와 동영상으로 텍스트 콘텐츠 보강
- 페이지에 표시되는 텍스트와 일치하는 구조화 데이터(structured data) 유지
- 판매자 센터(Merchant Center)와 비즈니스 프로필(Business Profile) 정보의 최신 상태 유지

Google 검색 센터 블로그는 2025년 5월 Google의 AI 검색 환경에서 콘텐츠 성과를 높이는 방법에 관한 안내를 게시했고, 2026년 5월에는 Google 검색의 생성형 AI 최적화를 위한 새 리소스를, 2026년 6월에는 Search Console의 검색 생성형 AI 실적 보고서 도입을 발표했다.[8]

## 생성형 엔진 최적화의 방법론적 한계와 근거 범위

생성형 엔진 최적화(GEO)는 2025년과 2026년의 실증 감사와 문헌 검토에서 방법론적 한계와 근거 범위의 제약이 분명하게 지적되고 있다.[3][5][6] 올리비에 마르티네즈는 2026년 7월 45편의 연구를 검토한 비판적 서베이에서, 아가르왈 등의 최대 40% 가시성 향상 수치가 상업적 홍보에서 ChatGPT에서 높은 순위에 오른다는 일반적인 약속으로 바뀌어 쓰이는 경우가 많지만 실제로는 5개 문서가 이미 모델 컨텍스트에 투입된 시뮬레이터 환경의 상대적 가시성 증가를 측정한 결과라고 짚었다.[5][6] 검토된 문헌 전반에서 확인되는 근거의 범위는 좁다. 이미 검색된 문서의 내용을 수정해 답변 내 인용이나 활용을 인과적으로 바꿀 수 있다는 증거는 존재하지만, 자연 검색 노출(organic discoverability)이나 트래픽·전환 같은 후속 사용자 행동에 대해 플랫폼 전반에서 장기적으로 안정적인 인과 효과를 보인 기법은 검토 대상 중 없었다.[5][6]

기존 실증 결과는 실험 환경과 경쟁 구도에 크게 좌우된다.[5][6] 문헌 종합 결과 주제 관련성과 컨텍스트 내 위치가 가장 재현성 높은 요인으로 확인된 반면, 일반적인 경험 법칙(heuristic)은 도메인과 모델이 바뀌면 전이 성능이 낮았다.[5] 또한 여러 게시자가 동시에 최적화를 적용하는 다중 행위자 경쟁 환경에서는 개별 사이트의 이득이 상쇄될 수 있으며, 이는 푸에르토(Puerto) 등(2025)의 상반된 결과를 단일 행위자 실험과 조화롭게 설명하는 요인이 된다.[5][6] 상용 생성형 엔진 감사에서도 플랫폼 간 출처 중복률이 낮고 실행별 변동성과 질의 바꿔쓰기 민감도가 크며, 출처가 진술을 뒷받침하지 않은 채 인용되거나 링크 없이 바꿔쓰기되는 충실도 격차가 지속되는 것으로 보고됐다.[3][5][6]

유익한 문구 재작성, 적대적 텍스트 삽입, 간접 프롬프트 주입(indirect prompt injection)은 모두 엔진이 소비하는 동일한 텍스트 경로를 수정한다.[6] 마르티네즈는 최적화와 조작이 같은 기술적 경로를 공유하므로 허용 가능한 GEO와 조작의 규범적 경계는 사실성, 의미 보존, 공개 여부, 숨겨진 지시문의 부재에 두어야 한다고 제안했다.[6] 아울러 2023~2026년 GEO 문헌에는 동료 심사를 거친 학회 논문, 채택 예정 논문, 워크숍 논문, 프리프린트가 혼재되어 있으므로, 향후 평가는 반복 측정, 질의 바꿔쓰기, 대조군 설정, 인간 검증, 다중 행위자 간섭 시험을 포함한 재현 가능한 프로토콜에 따라 수행해야 한다고 제시했다.[5][6]

## 자주 묻는 질문

### 생성형 엔진 최적화(GEO)란 무엇인가요?

생성형 엔진 최적화(GEO)는 생성형 검색 엔진이 만드는 답변에서 웹 출처의 가시성과 인용 가능성을 높이기 위해 콘텐츠의 표현, 문체, 구조를 조정하는 블랙박스 최적화 프레임워크입니다. 아가르왈(Aggarwal) 등의 연구진이 2023년 11월 16일 arXiv:2311.09735에서 용어를 제안했고, 이 논문은 KDD 2024에 채택됐습니다. [1][2]

### 생성형 엔진 최적화는 기존 SEO와 어떻게 다른가요?

기존 검색 엔진 최적화(SEO)는 순위화된 링크 목록에서의 평균 순위를 목표로 합니다. 생성형 엔진 최적화는 다단계 검색과 생성 파이프라인 전반에서 다중 문서 합성, 본문 인용 배치, 답변 내 비중, 출처 충실도를 다룹니다. [2][5]

### 최초의 GEO-bench 연구에서는 어떤 결과가 나왔나요?

아가르왈 등은 10,000개 질의로 구성된 GEO-bench 평가에서 다양한 질의에 대해 최대 40%, 인용과 인용문 및 통계 추가 시 40%를 넘는 가시성 향상을 보고했으며 Perplexity.ai에서는 최대 37%의 향상을 기록했습니다. 2026년 7월 올리비에 마르티네즈의 서베이는 이 수치가 이미 5개 문서가 컨텍스트에 배치된 시뮬레이터에서 측정된 상대적 향상이어서 자연 검색 노출이나 지속적 트래픽 효과를 입증하지는 않는다고 지적합니다. [2][5][6]

### 2025년과 2026년 후속 학술 연구는 GEO의 효과에 대해 무엇을 보여 주나요?

2025년 9월 천(Chen) 등의 연구는 ChatGPT, Perplexity, Gemini가 브랜드 자체 콘텐츠나 소셜 콘텐츠보다 제3자 획득 미디어를 강하게 선호하며 엔진별로 다양성, 최신성, 표현 민감도가 크게 다름을 보였습니다. 2026년 3월 위(Yu) 등의 연구는 구조적 특성 공학으로 6개 엔진에서 인용률 17.3%, 주관적 품질 18.5% 향상을 보고했고, 마르티네즈의 2026년 7월 45편 검토에서는 주제 관련성과 컨텍스트 내 위치가 가장 재현성 높은 요인으로 나타났습니다. [3][4][5]

### Google의 AI 개요와 AI 모드에 노출되려면 별도의 GEO 기법이 필요한가요?

아닙니다. 2026년 11월 23일 기준 Google 검색 센터 문서는 Google 검색에 색인되고 스니펫 표시 자격을 충족하는 페이지라면 AI 개요나 AI 모드의 참고 링크로 표시되기 위해 추가 기술 요건이나 별도의 최적화가 필요하지 않다고 밝힙니다. [7]

### robots.txt와 llms.txt는 생성형 엔진 최적화와 어떤 관계가 있나요?

robots.txt는 자동 크롤러의 접근 허용 범위를 지정하며, Google은 AI 기능 노출 자격을 위해 robots.txt와 호스팅 인프라에서 크롤링을 허용할 것을 요구합니다. Cloudflare 역시 2026년 7월부터 검색, 에이전트, 학습 AI 트래픽을 구분해 제어하는 기능을 제공하며, llms.txt는 언어 모델과 에이전트가 추론 시점에 참조하도록 선별된 마크다운 개요를 제공하는 별도의 웹 관례 제안입니다. [7][9][11]

## 인용 문장

- 프란잘 아가르왈, 비슈박 무라하리, 탄마이 라즈푸로히트, 아슈윈 칼얀, 카르틱 나라심한, 아미트 데시판데는 2023년 11월 16일 arXiv:2311.09735에서 생성형 엔진 최적화 용어를 처음 제안했으며, 이 논문은 KDD 2024에 채택됐다. [1][2]
- GEO-bench 벤치마크는 생성형 엔진 가시성 기법을 평가하기 위해 다양한 도메인과 웹 출처에서 구성한 10,000개의 질의로 이루어진다. [2]
- 아가르왈 등은 벤치마크 평가에서 최대 40%, Perplexity.ai에서 최대 37%의 가시성 향상을 보고했으며, 출처 인용, 관련 출처 직접 인용문, 통계 추가 시 40%를 넘는 가시성 증가가 나타났다. [2]
- 2025년 9월 천(Chen) 등의 실증 연구는 ChatGPT, Perplexity, Gemini가 Google 웹 검색과 비교해 브랜드 자체 콘텐츠나 소셜 콘텐츠보다 제3자 획득 미디어(earned media)를 체계적으로 편향 인용한다는 결과를 보고했다. [3]
- 2026년 3월 발표된 구조적 특성 공학 프레임워크 GEO-SFE는 6개 생성형 엔진 평가에서 인용률 17.3%, 주관적 품질 18.5% 향상을 보고했다. [4]
- 올리비에 마르티네즈(Olivier Martinez)가 2026년 7월 45편의 연구를 검토한 비판적 서베이는 이미 검색된 콘텐츠가 인용이나 활용을 인과적으로 바꿀 수 있으나, 자연 검색 노출이나 후속 사용자 행동에 대해 플랫폼 전반에서 장기적으로 안정적인 인과 효과를 입증한 기법은 검토 대상 중 없었다고 결론지었다. [5]
- 2026년 11월 23일 기준 Google 검색 센터 문서는 Google 검색에 색인되고 스니펫 표시 자격을 갖춘 페이지라면 AI 개요(AI Overviews)와 AI 모드(AI Mode) 노출을 위해 추가 기술 요건이나 별도의 최적화가 필요하지 않다고 밝힌다. [7]
- Cloudflare는 2026년 7월 1일 웹사이트 소유자가 AI 트래픽을 검색, 에이전트, 학습 범주로 구분해 관리할 수 있는 제어 옵션을 발표했다. [11]

## 연표

- 2023-11-16: 프란잘 아가르왈, 비슈박 무라하리, 탄마이 라즈푸로히트, 아슈윈 칼얀, 카르틱 나라심한, 아미트 데시판데가 arXiv에 "GEO: Generative Engine Optimization" 첫 판을 제출하며 GEO 용어와 GEO-bench 벤치마크를 제안한다. [1]
- 2024-06-28: 아가르왈 등이 2024년 8월 25~29일 바르셀로나 KDD 2024 발표에 앞서 GEO 논문 개정판 v3을 arXiv에 공개한다. [1][2]
- 2024-09-03: 제러미 하워드가 언어 모델과 AI 에이전트에게 선별된 마크다운 사이트 개요를 제공하는 /llms.txt 제안을 공개한다. [9]
- 2025-05: Google 검색 센터 블로그가 Google의 AI 검색 환경에서 콘텐츠 성과를 높이는 방법에 관한 안내를 게시한다. [8]
- 2025-09-10: 천(Chen) 등이 ChatGPT, Perplexity, Gemini와 Google 검색을 비교한 실증 연구(arXiv:2509.08919)를 제출해 획득 미디어 편향과 엔진 간 차이를 보고한다. [3]
- 2026-03-31: 위(Yu) 등이 구조적 특성 공학 프레임워크 GEO-SFE 연구(arXiv:2603.29979)를 제출해 6개 생성형 엔진에서의 인용률 및 주관적 품질 향상을 보고한다. [4]
- 2026-06: Google 검색 센터 블로그가 2026년 5월 생성형 AI 최적화 리소스 공개에 이어 Search Console의 검색 생성형 AI 실적 보고서 도입을 발표한다. [8]
- 2026-07-01: Cloudflare가 웹사이트 소유자에게 AI 트래픽을 검색, 에이전트, 학습 범주로 구분해 관리하는 제어 옵션을 도입한다. [11]
- 2026-07-15: 올리비에 마르티네즈가 2023년 11월~2026년 7월 GEO 연구 45편을 검토한 비판적 서베이(arXiv:2607.14035)를 공개하며 다단계 파이프라인 모델과 재현 가능한 평가 프로토콜을 제시한다. [5][6]
- 2026-08-10: 제러미 하워드가 /llms.txt 제안을 v2로 갱신한다. v2는 파일을 하위 경로에 두는 방법과 alternate·describedby 링크 관계로 파일을 찾는 방법을 설명한다. [9]

## 출처

1. [2311.09735] GEO: Generative Engine Optimization. arXiv. 게시일 2023-11-16. https://arxiv.org/abs/2311.09735 (확인일 2026-11-23; tier 2: academic or news)
2. GEO: Generative Engine Optimization. arXiv. 게시일 2024-06-28. https://arxiv.org/html/2311.09735v3 (확인일 2026-11-23; tier 2: academic or news)
3. [2509.08919] Generative Engine Optimization: How to Dominate AI Search. arXiv. 게시일 2025-09-10. https://arxiv.org/abs/2509.08919 (확인일 2026-11-23; tier 2: academic or news)
4. [2603.29979] Structural Feature Engineering for Generative Engine Optimization: How Content Structure Shapes Citation Behavior. arXiv. 게시일 2026-03-31. https://arxiv.org/abs/2603.29979 (확인일 2026-11-23; tier 2: academic or news)
5. [2607.14035] Optimizing Visibility in Generative Engines: A Critical Survey of Generative Engine Optimization (2023-2026). arXiv. 게시일 2026-07-15. https://arxiv.org/abs/2607.14035 (확인일 2026-11-23; tier 2: academic or news)
6. Optimizing Visibility in Generative Engines: A Critical Survey of Generative Engine Optimization (2023–2026). arXiv. 게시일 2026-07-15. https://arxiv.org/html/2607.14035v1 (확인일 2026-11-23; tier 2: academic or news)
7. AI Features and Your Website | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/ai-features (확인일 2026-11-23; tier 3: official site)
8. Top ways to ensure your content performs well in Google's AI experiences on Search | Google Search Central Blog | Google for Developers. Google Search Central Blog. 게시일 2025-05. https://developers.google.com/search/blog/2025/05/succeeding-in-ai-search (확인일 2026-11-23; tier 3: official site)
9. The /llms.txt file, v2 – llms-txt. llmstxt.org. 게시일 2024-09-03. https://llmstxt.org/ (확인일 2026-11-23; tier 3: official site)
10. Overview of OpenAI Crawlers. OpenAI. https://developers.openai.com/api/docs/bots (확인일 2026-11-23; tier 3: official site)
11. Your site, your rules: new AI traffic options for all customers | Cloudflare Blog. The Cloudflare Blog. 게시일 2026-07-01. https://blog.cloudflare.com/content-independence-day-ai-options/ (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "생성형 엔진 최적화." 버전 6df7d51e, 2026-11-25. https://mimirwiki.com/ko/wiki/generative-engine-optimization
