---
title: "Cloudflare Workers"
subtitle: "V8 아이솔레이트와 오픈소스 workerd 런타임으로 JavaScript, TypeScript, Python, Rust, WebAssembly를 실행하는 Cloudflare의 서버리스 컴퓨팅 플랫폼"
canonical_url: https://mimirwiki.com/ko/wiki/cloudflare-workers
language: ko
page_class: entity
revision_sha256: 22d620d888fbe34a2abf686717e4eba49c4392c177141e19bbf6bf547027d312
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/ko/wiki/cloudflare-workers.md
  txt: https://mimirwiki.com/ko/wiki/cloudflare-workers.txt
  json: https://mimirwiki.com/ko/wiki/cloudflare-workers.json
  jsonld: https://mimirwiki.com/ko/wiki/cloudflare-workers.jsonld
translations:
  en: https://mimirwiki.com/wiki/cloudflare-workers
---

# Cloudflare Workers

> Cloudflare Workers는 Cloudflare가 운영하는 서버리스(serverless) 컴퓨팅 플랫폼으로, V8 아이솔레이트(isolate)와 workerd 런타임을 사용해 전 세계 네트워크에서 JavaScript, TypeScript, Python, Rust, WebAssembly 코드를 실행한다. 2017년에 발표되었으며 웹 표준 API, Node.js 호환성, 스토리지 바인딩을 지원한다. 2026-11-23 기준 Workers Free 요금제와 월 최소 5달러의 Workers Paid 요금제로 제공된다.

Cloudflare Workers는 Cloudflare, Inc.가 운영하는 서버리스(serverless) 컴퓨팅 플랫폼으로, V8 아이솔레이트(isolate)와 오픈소스 workerd 런타임을 이용해 전 세계 Cloudflare 네트워크에서 개발자 애플리케이션을 실행한다. 2017년 9월 29일에 발표된 이 플랫폼은 웹 플랫폼 API와 런타임 내장 Node.js API 일부를 바탕으로 JavaScript, TypeScript, Python, Rust, 웹어셈블리(WebAssembly, Wasm) 워크로드를 구동한다. Cloudflare는 2022년 9월 27일 Cloudflare Workers의 기반이 되는 JavaScript 및 WebAssembly 서버 런타임 workerd를 Apache-2.0 라이선스로 공개했다. 2026-11-23 기준 Cloudflare는 하루 요청 100,000건 한도의 Workers Free 요금제와 Standard 사용량 모델 기준 계정당 월 최소 5달러이며 이그레스(egress) 및 대역폭 요금이 없는 Workers Paid 요금제를 제공한다.

**다른 이름:** Workers, 클라우드플레어 워커스, CF Workers, workerd

## 핵심 정보

- **개발사:** Cloudflare, Inc. [2]
- **실행 구조:** 전 세계 Cloudflare 네트워크상의 V8 아이솔레이트 [6]
- **오픈소스 런타임:** workerd (Apache-2.0 라이선스) [10]
- **Workers Free 한도:** 하루 요청 100,000건, 호출당 CPU 시간 10ms (기준 2026-11-23) [4]
- **Workers Paid 가격:** 월 최소 5달러 (월 1,000만 요청, 3,000만 CPU ms 포함) (기준 2026-11-23) [4]

## 기본 정보

- **개발사:** Cloudflare, Inc. (SEC CIK 0001477333) [2]
- **최초 발표일:** 2017년 9월 29일 [12]
- **실행 엔진:** V8 자바스크립트 엔진(아이솔레이트) [6]
- **오픈소스 런타임:** workerd (Apache-2.0 라이선스, 2022년 9월 27일 베타 발표) [11]
- **1급 지원 언어:** JavaScript, TypeScript, Python, Rust (기준 2026-11-23) [7]
- **WebAssembly 지원 언어:** C, C++, Kotlin, Go 등 Wasm 컴파일 대상 언어 (기준 2026-11-23) [7]
- **Node.js 호환성:** 호환성 날짜 2026-08-04 이후 기본 활성화 (기준 2026-11-23) [9]
- **Workers Free 요금제:** 하루 요청 100,000건, 호출당 CPU 시간 10ms (기준 2026-11-23) [4]
- **Workers Paid 요금제:** 월 최소 5달러, 월 1,000만 요청 및 3,000만 CPU ms 포함, 이그레스 요금 없음 (기준 2026-11-23) [4]
- **아이솔레이트당 메모리:** 128MB (JavaScript 힙 및 WebAssembly 할당 포함) (기준 2026-11-23) [5]
- **Worker 크기 및 시작 한도:** 비압축 번들 64MiB, 시작 시간 1초 (기준 2026-11-23) [5]
- **최대 CPU 시간 (Paid):** HTTP 요청당 5분(기본값 30초), 1시간 이상 주기 Cron Trigger당 15분 (기준 2026-11-23) [5]

## Cloudflare Workers의 V8 아이솔레이트 아키텍처와 workerd 런타임

Cloudflare Workers는 전 세계에 분산된 [Cloudflare](https://mimirwiki.com/ko/wiki/cloudflare) 네트워크 서버에서 V8 자바스크립트 엔진으로 사용자 애플리케이션을 실행한다.[6] 각 서버는 Workers 런타임 인스턴스를 구동하며, 하나의 런타임 인스턴스가 메모리가 독립적으로 격리된 경량 실행 컨텍스트인 V8 아이솔레이트(isolate) 수백에서 수천 개를 실행하고 전환한다.[6] Workers 런타임은 컨테이너 시작 시 단일 V8 호스트 프로세스를 한 번 초기화한 뒤 그 안에서 여러 사용자 스크립트를 아이솔레이트로 실행하며, 컨테이너 기반 서버리스 아키텍처는 함수마다 별도의 언어 런타임 프로세스나 가상 머신을 실행한다.[6] Cloudflare 문서는 아이솔레이트가 컨테이너나 가상 머신의 Node.js 프로세스보다 시작 속도가 약 100배 빠르고 시작 시 메모리 사용량이 한 자릿수 이상 적다고 밝힌다.[6]

`*.workers.dev` 하위 도메인이나 Cloudflare 관리 도메인으로 들어온 요청은 ES 모듈 문법으로 작성된 Worker의 `fetch(request, env, ctx)` 핸들러를 호출하고 `Response` 객체를 반환받는다.[6] 단일 Worker 인스턴스는 비동기 I/O를 대기하는 동안 들어오는 동시 요청을 포함해 여러 요청을 단일 스레드 이벤트 루프에서 처리한다.[6] 아이솔레이트는 서버 리소스 제약, 개별 리소스 한도 초과, 또는 샌드박스 탈출 시도처럼 보이는 의심스러운 스크립트 감지 시 종료되어 제거될 수 있다.[6] 같은 사용자의 연속 요청이 동일한 아이솔레이트로 전달된다는 보장이 없으므로 Cloudflare는 전역 스코프에 변경 가능한 상태를 저장하지 않도록 안내한다.[6]

Cloudflare Workers를 구동하는 오픈소스 서버 런타임은 `workerd`(발음: 워커디)이며, GitHub에 Apache-2.0 라이선스로 공개되어 있다.[10][11] 개발자는 `workerd`를 Workers용 애플리케이션 자체 호스팅 서버, 로컬 개발 및 테스트 도구, 또는 네트워크 요청을 가로채고 수정해 라우팅하는 프로그래머블 HTTP 포워드·리버스 프록시로 사용할 수 있다.[10] Cloudflare는 `workerd`의 여섯 가지 설계 원칙을 제시한다.[10]

- 서버 우선(Server-first) 설계로 CLI와 GUI 대상을 제외하고 서버 워크로드에 집중한다.[10]
- `fetch()` 등 웹 플랫폼 표준에 기반한 내장 API를 제공한다.[10]
- 나노서비스(nanoservices) 구조를 채택해 독립적으로 배포 가능한 구성 요소가 호출 시 같은 스레드와 프로세스 안에서 실행된다.[10]
- 클러스터의 모든 서버에 전체 나노서비스를 동일하게 배포하는 균일 배포(homogeneous deployment)로 로드 밸런싱을 단순화한다.[10]
- 전역 네임스페이스 대신 명시적 권한 참조인 기능 바인딩(capability bindings)으로 서비스와 외부 리소스를 연결해 서버 측 요청 위조(SSRF) 노출을 줄인다.[10]
- 날짜 기반 하위 호환성을 유지해 `workerd` 버전 번호가 지원하는 최대 호환성 날짜(compatibility date)를 나타내며, 과거 날짜로 설정된 Worker에 해당 시점의 API 동작을 그대로 에뮬레이션한다.[10]

`workerd`는 Bazel로 빌드되며 Linux와 macOS(`x86-64`, `arm64`) 및 Windows(`x86-64`) 환경에서 테스트된다.[10] 기본 설정은 Cap'n Proto 텍스트 형식을 사용하고, `workerd serve wrangler.jsonc` 명령으로 `esbuild` 번들링이 포함된 Wrangler 설정 파일도 읽을 수 있다.[10] 2026-11-23 기준 `cloudflare/workerd` GitHub 저장소는 스타 9.2k개, 포크 843개, 커밋 13,908건을 기록했다.[10] Cloudflare는 단독 `workerd`가 구현 결함에 대비한 강화 샌드박스는 아니므로 악성 가능성이 있는 코드를 실행할 때는 가상 머신 같은 별도 보안 샌드박스 내부에서 구동해야 하며, 호스팅형 Cloudflare Workers 서비스에는 추가 심층 방어 계층이 적용된다고 경고한다.[10]

## Cloudflare Workers의 런타임 API, 웹 표준, Node.js 호환성

Cloudflare Workers는 브라우저와 서버 런타임 전반에서 코드를 재사용할 수 있도록 웹 플랫폼 API와 JavaScript 표준을 따른다.[8] 내장 런타임 API에는 Fetch, Request, Response, Headers, Cache, Streams(`ReadableStream`, `WritableStream`, `TransformStream`), Web Crypto, WebSockets, TCP 소켓, Encoding, EventSource, MessageChannel, 성능 및 타이머, Scheduler, HTMLRewriter, 원격 프로시저 호출(Remote Procedure Call, RPC), 컨텍스트(`ctx`), 바인딩(`env`), 그리고 Fetch, Scheduled, Queue, Email, Alarm, Tail, Connect 이벤트 핸들러가 포함된다.[8]

Cloudflare 런타임 API 문서는 Workers가 WinterCG 자바스크립트 런타임 전반에서 상호운용될 수 있도록 웹 플랫폼 API를 채택한다고 설명한다.[8] 표준화 측면에서 Ecma International의 기술위원회 TC55인 WinterTC(Technical Committee on Web-interoperable Server Runtimes)는 서버 측 JavaScript 런타임 간 API 상호운용성을 높이기 위해 웹과 공통된 최소 공통 API를 표준화하고, WHATWG 및 W3C 같은 웹 표준 기구와 협력하며, 상호운용 가능한 새 서버 측 API 표준을 제정한다.[1]

Node.js 라이브러리에 의존하는 npm 패키지를 실행하기 위해 Cloudflare Workers는 두 가지 방식으로 Node.js API 일부를 제공한다.[9] 첫째는 현재(Current) Node.js 릴리스 구현에 맞춘 런타임 기본 내장 API이고, 둘째는 Wrangler가 `unenv`를 통해 주입하는 폴리필(polyfill) 심(shim)으로, 미구현 메서드를 호출하면 아무 동작을 하지 않거나 오류를 발생시킨다.[9] 런타임 동작은 Worker의 호환성 날짜와 호환성 플래그로 제어한다.[8][9] 호환성 날짜가 2026-08-04 이후이면 `nodejs_compat`과 `nodejs_compat_v2`가 기본으로 활성화되며, 이를 완전히 끄려면 `no_nodejs_compat`과 `no_nodejs_compat_v2`를 추가해야 한다.[9] 2024-09-23부터 2026-08-03 사이의 호환성 날짜에서는 `nodejs_compat` 플래그를 설정해 활성화하고 자동 `unenv` 폴리필 주입을 사용하며, `AsyncLocalStorage`만 필요한 경우 `nodejs_als` 플래그를 단독 사용할 수 있다.[9]

2026-11-23 기준 Cloudflare 문서가 밝힌 Node.js 호환성 지원 범위는 다음과 같다.[9]

- 네이티브 지원 모듈: `assert`, `AsyncLocalStorage`, `Buffer`, `crypto`, Debugger(Chrome DevTools 연동), Diagnostics Channel, Errors, `EventEmitter`, `fs`, Globals, `http`, `https`, `net`, `path`, `process`, Punycode(지원 중단 예정), Query strings, `stream`, `StringDecoder`, `timers`, `url`, `util`, Web Crypto API, Web Streams API, `zlib`.[9]
- 부분 지원 모듈: Console, `dns`, Module, OS, Performance hooks, Test runner, `tls`(TLS/SSL).[9]
- 호환성 날짜별로 `nodejs_compat`과 함께 자동 활성화되는 가져오기 전용 비기능 스텁(stub) 모듈: `node:http2`(2025-09-01), `node:vm`(2025-10-01), `node:cluster`·`node:domain`·`node:trace_events`·`node:wasi`(2025-12-04), `node:_stream_wrap`·`node:dgram`·`node:inspector`·`node:sqlite`(2026-01-29), `node:child_process`·`node:readline`·`node:repl`·`node:tty`·`node:v8`·`node:worker_threads`(2026-03-17).[9]

## Cloudflare Workers의 지원 언어, 개발 도구, 플랫폼 바인딩

Cloudflare Workers는 여러 프로그래밍 언어, 로컬 개발 도구, 웹 프레임워크, 그리고 Cloudflare 플랫폼 서비스와의 바인딩(binding)을 지원한다.[3][7] 2026-11-23 기준 1급 지원 언어는 JavaScript, TypeScript, Python(Python Workers), Rust(문서 내비게이션 기준 Beta 표기) 네 가지다.[3][7] 웹어셈블리(WebAssembly, Wasm) 바이너리 형식도 지원하므로 C, C++, Kotlin, Go 등으로 작성해 Wasm으로 컴파일한 Worker도 배포할 수 있다.[7]

개발자는 Wrangler CLI, Cloudflare Vite Plugin, Miniflare, Vitest 연동 도구를 사용해 로컬에서 개발하고 테스트할 수 있으며, GitHub과 GitLab을 연동하는 Workers Builds나 GitHub Actions, GitLab CI/CD 같은 외부 CI/CD 파이프라인으로 배포한다.[3] 공식 프레임워크 가이드는 React, Vue, SvelteKit, Next.js(OpenNext 어댑터 사용), Astro, React Router, Remix 3, Nuxt, Angular, Hono, TanStack Start, Qwik, Solid, FastAPI, Flask 등을 다룬다.[3] 프런트엔드 정적 에셋은 Worker 코드와 함께 Cloudflare의 [콘텐츠 전송 네트워크](https://mimirwiki.com/ko/wiki/content-delivery-network)(CDN)와 캐시를 통해 제공되며, 백엔드 애플리케이션은 Smart Placement를 통해 외부 데이터 저장소와 지연 시간을 최적화해 연결할 수 있다.[3] 2026-11-23 기준 Cloudflare Workers 문서는 [llms.txt](https://mimirwiki.com/ko/wiki/llms-txt) 색인, `llms-full.txt`, 페이지별 [Markdown](https://mimirwiki.com/ko/wiki/markdown) 보기, 그리고 Cloudflare의 [Model Context Protocol](https://mimirwiki.com/ko/wiki/model-context-protocol)(MCP) 서버 링크도 함께 제공한다.[3]

[SEC EDGAR](https://mimirwiki.com/ko/wiki/sec-edgar)에 제출된 Cloudflare의 2025 회계연도 공시는 개발자용 컴퓨팅(Compute) 제품군으로 Cloudflare Workers, 멀티테넌트 플랫폼 고객이 최종 사용자 코드를 배포·실행할 수 있는 관리형 실행 환경인 Cloudflare Workers for Platforms, 그리고 프런트엔드 웹사이트 배포 서비스인 Cloudflare Pages를 분류한다.[2] Workers는 명시적 `env` 바인딩을 통해 플랫폼의 스토리지, 컴퓨팅, AI, 미디어 서비스에 연결된다.[2][3]

- 스토리지 및 데이터베이스: Durable Objects(실시간 상태 조정용 스토리지), D1(서버리스 SQL 데이터베이스), Workers KV(엣지 캐시 읽기를 지원하는 전역 키-값 스토리지), Queues(이그레스 요금 없는 비동기 메시지 큐), Hyperdrive(외부 데이터베이스용 연결 풀링·라우팅 최적화·쿼리 캐싱), R2(이그레스 요금 없는 오브젝트 스토리지).[2][3]
- 컴퓨팅 및 AI: Workers AI(서버리스 GPU 기반 머신러닝 추론), Workflows(자동 재시도를 갖춘 장기 지속 실행 워크플로), Vectorize(임베딩 및 시맨틱 검색용 벡터 데이터베이스), Browser Run(프로그래밍 방식 서버리스 브라우저), Service 바인딩(Worker 간 HTTP 및 `WorkerEntrypoint` RPC 호출), Dynamic Worker Loaders, Workers for Platforms용 Dispatcher.[2][3]
- 미디어 및 운영 바인딩: Cache, Images, Stream, Media Transformations, Assets, Analytics Engine, Rate Limiting, Secrets, Secrets Store(Beta), mTLS 인증서, 환경 변수.[3]

## Cloudflare Workers 요금제와 가격

Cloudflare Workers는 기본 제공되는 Workers Free 요금제, 계정당 월 최소 5달러인 Workers Paid 요금제, 계약 기반의 Workers Enterprise 계정으로 나뉜다.[4] 모든 계정은 기본적으로 Workers Free를 사용할 수 있으며, 여기에는 Workers, Pages Functions, Workers KV, Hyperdrive의 일일 제한 사용량이 포함된다.[4] Workers Paid는 Standard 사용량 모델을 따르며 Workers, Pages Functions, Workers KV, Hyperdrive, Durable Objects의 월간 기본 제공량을 포함하고 데이터 전송(egress)이나 대역폭에 대한 추가 요금을 부과하지 않는다.[4] 모든 Pages Functions는 Workers와 동일한 기준과 요율로 과금된다.[4] 일부 기존 구성에는 레거시 사용량 모델인 Workers Unbound와 Workers Bundled가 남아 있으며, 2024년 3월 1일 Standard 가격제로 전환되면서 기존 Bundled Worker에는 50밀리초 CPU 한도가 자동 적용되었다.[4]

2026-11-23 기준 Cloudflare 문서에 기재된 Workers Free와 Workers Paid(Standard) 컴퓨팅 가격은 다음과 같다.[4]

| 항목 | Workers Free | Workers Paid (Standard) |
| --- | --- | --- |
| 기본 구독료 | 0달러 | 월 최소 5달러 |
| 인바운드 요청 | 하루 100,000건 | 월 1,000만 건 포함, 초과 100만 건당 0.30달러 |
| 실행 지속 시간(Duration) | 요금 없음 | 요금 및 한도 없음 |
| CPU 시간 | 호출당 10ms | 월 3,000만 CPU ms 포함, 초과 100만 CPU ms당 0.02달러 |
| 호출당 최대 CPU 시간 | 10ms | HTTP 5분(기본값 30초), 1시간 이상 주기 Cron Trigger 15분 |
| 정적 에셋 요청 | 무료·무제한 | 무료·무제한 |

Worker 내부에서 외부로 보내는 서브리퀘스트(subrequest)에는 요금이 청구되지 않는다.[4] WebSocket 연결은 초기 Upgrade 연결 수립 시 요청 1건으로 집계되며, 이후 전달되는 WebSocket 메시지는 요청 수에 포함되지 않는다.[4] Workers Caching을 활성화하면 캐시에서 응답하는 요청(정적 에셋과 Worker 간 호출 포함)에도 일반 요청과 동일한 요청당 요율이 적용되며, CPU 시간은 캐시 미스나 우회로 Worker가 실제 실행될 때만 과금된다.[4] 사용자는 기본 제공량 초과분 요청 및 CPU 요금 기준(월 5달러 구독료 제외)으로 새 호출을 차단하는 Workers 지출 한도(spending limit)를 설정하거나, 차단 없이 알림만 받는 이메일 경고를 구성할 수 있다.[4]

2026-11-23 기준 Workers 가격 페이지에는 연계 개발자 서비스의 제공량과 초과 요율도 함께 게시되어 있다.[4]

| 서비스 및 지표 | Workers Free | Workers Paid |
| --- | --- | --- |
| Workers Logs 로그 이벤트 기록 | 하루 200,000건 (3일 보관) | 월 2,000만 건 포함, 초과 100만 건당 0.60달러 (7일 보관) |
| Workers Trace Events Logpush | 미제공 | 월 1,000만 요청 포함, 초과 100만 건당 0.05달러 |
| Workers KV 키 읽기 | 하루 100,000건 | 월 1,000만 건 포함, 초과 100만 건당 0.50달러 |
| Workers KV 키 쓰기·삭제·목록 조회 | 각 하루 1,000건 | 각 월 100만 건 포함, 초과 100만 건당 5.00달러 |
| Workers KV 저장 용량 및 네임스페이스 | 1GB, 1,000개 | 1GB(초과 GB-월당 0.50달러), 1,000개 포함(추가 개당 월 0.10달러) |
| Hyperdrive 데이터베이스 쿼리 | 하루 100,000건 | 무제한 |
| Queues 표준 작업 (메시지 64KB 청크 기준) | 하루 10,000건 (24시간 보관, 큐 10,000개) | 월 100만 건 포함(초과 100만 건당 0.40달러, 기본 4일·최대 14일 보관, 큐 10,000개 포함 후 추가 개당 월 0.10달러) |
| Workflows 단계 및 스토리지 | 하루 3,000단계, 1GB-월 (요청은 Workers와 공유) | 월 500,000단계 포함(추가 100,000단계당 0.80달러), 1GB-월 포함(초과 GB-월당 0.20달러) |
| D1 읽은 행 수 | 하루 500만 행 | 월 250억 행 포함, 초과 100만 행당 0.001달러 |
| D1 기록한 행 수 | 하루 100,000행 | 월 5,000만 행 포함, 초과 100만 행당 1.00달러 |
| D1 저장 용량 및 데이터베이스 수 | 총 5GB, 10개 | 5GB 포함(초과 GB-월당 0.75달러), 100,000개 포함(추가 개당 월 0.10달러) |

Cloudflare는 2026년 12월 1일부터 Workers Logs에 Cloudflare Observability 요금 체계가 적용되며, Workflows의 단계 및 스토리지 과금은 Workflows 과금 변경 로그에 공지된 시작일 이후 개시된다고 명시한다.[4] Queues는 개별 메시지마다 64KB(1KB=1,000바이트, 내부 메타데이터 약 100바이트 포함) 단위로 쓰기·읽기·삭제 작업을 계산하므로 일반적인 메시지 전달 1건은 작업 3건으로 집계되며 이그레스 요금은 없다.[4]

## Cloudflare Workers 운영 및 리소스 한도

Cloudflare Workers는 Workers Free와 Workers Paid 요금제 전반에 걸쳐 계정, 실행 시간, 메모리, 네트워크, 배포 관련 한도를 적용한다.[5] 2026-11-23 기준 Cloudflare 문서에 명시된 핵심 계정 및 플랫폼 한도는 다음과 같다.[5]

| 한도 항목 | Workers Free | Workers Paid |
| --- | --- | --- |
| 일일 요청 수 | 하루 100,000건 (UTC 00:00 초기화) | 제한 없음 |
| HTTP 요청당 CPU 시간 | 10ms | 5분 (기본값 30초) |
| Cron Trigger당 CPU 시간 | 10ms | 1시간 미만 주기 5분, 1시간 이상 주기 15분 |
| 아이솔레이트당 메모리 | 128MB | 128MB |
| 호출당 서브리퀘스트 | 50건 (내부 서비스 1,000건) | 10,000건 (최대 1,000만 건 설정 가능) |
| 응답 헤더 대기 동시 외부 연결 | 6개 | 6개 |
| Worker당 환경 변수 (시크릿+텍스트) | 64개 (각 5KB) | 128개 (각 5KB) |
| Worker 번들 크기 (비압축) | 64MiB | 64MiB |
| Worker 시작 시간 (전역 스코프) | 1초 | 1초 |
| 계정당 Worker 수 | 100개 | 500개 |
| 버전 보관 기간 | 30일 (최근 100개 항상 유지) | 30일 (최근 100개 항상 유지) |
| 계정당 Cron Trigger 수 | 5개 | 1,000개 |
| Worker 버전당 정적 에셋 파일 수 | 20,000개 (파일당 25MiB) | 100,000개 (파일당 25MiB) |

CPU 시간은 실제 스크립트 연산 시간만 측정하며 `fetch()` 호출, KV 읽기, 데이터베이스 쿼리 같은 네트워크 대기 시간은 포함하지 않는다.[5] Cloudflare는 평균적인 Worker가 요청당 약 2.2ms의 CPU 시간을 소비하며, 인증·서버 측 렌더링·대용량 페이로드 파싱 같은 무거운 작업은 보통 10-20ms를 사용한다고 설명한다.[5] Workers Free의 일일 요청 한도를 초과하면 Error 1027이 반환되며, 라우트 설정에 따라 Worker를 건너뛰는 Fail open 모드나 오류 페이지를 반환하는 Fail closed 모드를 선택할 수 있다.[5] CPU 시간이나 메모리 한도를 초과하면 클라이언트에 Error 1102(`exceededCpu` 또는 `exceededMemory`)가 반환되고, 전역 스코프 파싱·실행이 1초를 넘으면 오류 코드 10021로 배포가 거부된다.[5]

128MB 메모리 한도는 JavaScript 힙과 WebAssembly 할당을 모두 포함해 아이솔레이트 전체에 적용되며, 하나의 아이솔레이트가 동시에 처리하는 여러 요청이 이 한도를 공유한다.[5] 아이솔레이트가 128MB를 초과하면 런타임은 처리 중인 요청을 완료시킨 뒤 후속 요청용 새 아이솔레이트를 생성하며, 극심한 부하 상황에서만 일부 신규 요청을 취소한다.[5] HTTP 요청으로 실행된 Worker는 클라이언트가 연결을 유지하는 한 실제 경과 시간(wall-clock time) 제한이 없고, 응답 완료나 연결 종료 후에도 `ctx.waitUntil()`로 최대 30초까지 후속 작업을 이어갈 수 있다.[5] Cron Trigger, Durable Object Alarm, Queue Consumer의 경과 시간 한도는 각각 15분이며, 정기 런타임 업데이트 중 이전 버전 프로세스는 스트리밍 HTTP 응답과 WebSocket 연결이 종료될 수 있도록 최대 20분의 유예 기간을 제공한다.[5]

최상위 요청 단위(Service 바인딩으로 호출된 Worker 포함)에서는 `fetch()`, KV, Cache, R2, Queues, TCP `connect()`, 외부 WebSocket 연결 중 응답 헤더를 기다리는 동시 연결이 최대 6개로 제한되며, 헤더를 수신하면 집계에서 해제되고 7번째 연결은 대기열에 들어간다.[5] 요청 및 응답 한도는 URL 16KB, 요청 헤더 총합 128KB, 응답 헤더 총합 128KB이며 응답 본문 크기에는 별도 강제 한도가 없다(단, CDN 캐시 한도는 Free·Pro·Business 512MB, Enterprise 5GB).[5] 도메인으로 들어오는 요청 본문 크기 한도는 해당 도메인의 Cloudflare 요금제에 따라 Free·Pro 100MB, Business 200MB, Enterprise 셀프서비스 최대 5GB(초과 시 HTTP 413 반환)로 정해지며, Durable Object나 Container 아웃바운드 핸들러의 외부 HTTP 요청 본문 기본 한도는 100MiB이다.[5] 라우팅 한도는 존당 라우트 1,000개(`wrangler dev --remote` 및 Quick Editor는 50개), 존당 커스텀 도메인 100개, Worker당 라우팅 존 1,000개이다.[5] 계정당 500개를 넘는 사용자 Worker가 필요한 멀티테넌트 플랫폼은 사용자 Worker 수 제한이 없는 Workers for Platforms를 사용할 수 있다.[5]

## Cloudflare Workers 연혁과 운영 공시

Cloudflare Workers는 2017년 9월 29일 Cloudflare 블로그의 Birthday Week 발표로 처음 공개되었으며, Cloudflare 네트워크 엣지에서 JavaScript Service Workers를 실행하는 방식으로 소개되었다.[12] 이후 해당 발표 게시물에는 2018년 3월 13일 자로 서비스 가용성을 기록한 업데이트가 추가되었다.[12] 최초 공개로부터 5년 뒤인 2022년 9월 27일 Cloudflare는 `workerd`의 첫 베타 버전을 발표하며 Cloudflare Workers를 구동하는 JavaScript 및 WebAssembly 런타임 코드를 Apache-2.0 라이선스의 오픈소스 소프트웨어로 공개했다.[11]

이후 과금 체계와 Node.js 호환성 확장이 이어졌다. 2024년 3월 1일 Cloudflare는 기존 Bundled 과금 계정을 Standard 사용량 모델로 전환했다.[4] 호환성 날짜 2024-09-23부터는 `nodejs_compat` 플래그 활성화 시 Wrangler가 `unenv` 폴리필을 자동 주입하기 시작했다.[9] 2025년 9월부터 2026년 3월 사이에는 `node:http2`, `node:vm`, `node:sqlite`, `node:child_process`, `node:worker_threads` 같은 비서버리스 Node.js 모듈용 가져오기 스텁이 호환성 날짜 기준으로 순차 추가되었고, 2026년 8월 4일 호환성 날짜부터는 `nodejs_compat`과 `nodejs_compat_v2`가 기본으로 활성화되었다.[9] 또한 Cloudflare는 2026년 12월 1일부터 Workers Logs를 Cloudflare Observability 요금 체계로 전환할 예정이다.[4]

[SEC EDGAR](https://mimirwiki.com/ko/wiki/sec-edgar)에 제출된 [Cloudflare](https://mimirwiki.com/ko/wiki/cloudflare)의 2025 회계연도 공시는 Cloudflare Workers를 포함한 개발자 솔루션 채택이 회사를 스토리지 및 컴퓨팅 시장으로 확장시켰으며, 이 영역에서 퍼블릭 클라우드 사업자들과 경쟁하고 있다고 서술한다.[2] 같은 공시의 위험 요인 항목에서 Cloudflare는 2025년 6월 Workers KV 서비스가 사용하는 기반 제3자 스토리지 인프라에 장애가 발생해 수 시간 동안 일부 서비스와 고객에게 영향을 미친 중단 사고가 있었다고 공시했다.[2] Cloudflare는 해당 2025년 6월 사고가 사업, 영업 실적, 재무 상태에 중대한 영향을 미치지 않았다고 밝혔다.[2]

## 자주 묻는 질문

### Cloudflare Workers는 V8 아이솔레이트로 코드를 어떻게 실행하나요?

Cloudflare Workers는 공유 운영체제 프로세스 안에서 V8 자바스크립트 엔진을 구동하고, 각 사용자 애플리케이션에 메모리가 격리된 경량 V8 아이솔레이트(isolate)를 할당합니다. 단일 런타임 인스턴스가 수백에서 수천 개의 아이솔레이트를 실행하고 전환하므로 컨테이너 시작 시 런타임 프로세스 오버헤드를 한 번만 부담합니다. Cloudflare 문서는 아이솔레이트가 컨테이너나 가상 머신의 Node.js 프로세스보다 시작 속도가 약 100배 빠르고 시작 시 메모리 소비가 한 자릿수 이상 적다고 설명합니다. [6]

### workerd는 무엇이며 어떤 라이선스로 배포되나요?

workerd(발음: 워커디)는 Cloudflare Workers를 구동하는 코드에 기반한 오픈소스 JavaScript 및 WebAssembly 서버 런타임이며, Apache-2.0 라이선스로 배포됩니다. Cloudflare는 로컬 개발, Workers 애플리케이션 자체 호스팅, 프로그래머블 HTTP 프록시 용도로 2022년 9월 27일 첫 베타 버전을 공개했습니다. Cloudflare는 신뢰할 수 없는 코드를 단독 workerd에서 실행할 때는 가상 머신 같은 별도의 보안 샌드박스 안에서 구동해야 한다고 안내합니다. [10][11]

### Cloudflare Workers의 요금은 얼마인가요?

2026-11-23 기준 Cloudflare는 하루 요청 100,000건과 호출당 CPU 시간 10밀리초를 제공하는 무료 Workers Free 요금제와 계정당 월 최소 5달러인 Workers Paid 요금제를 운영합니다. Standard 사용량 모델을 쓰는 Workers Paid에는 월 1,000만 건의 요청과 3,000만 CPU 밀리초가 포함되며, 초과분은 요청 100만 건당 0.30달러, CPU 시간 100만 밀리초당 0.02달러가 청구되고 실행 지속 시간이나 이그레스 대역폭 요금은 없습니다. 정적 에셋 요청과 Worker가 보내는 서브리퀘스트(subrequest)는 무료입니다. [4]

### Cloudflare Workers Free와 Paid 요금제의 주요 리소스 한도는 어떻게 되나요?

2026-11-23 기준 Workers Free와 Workers Paid 모두 아이솔레이트당 메모리 128MB, 비압축 Worker 번들 크기 64MiB, 시작 시간 1초, 응답 헤더를 대기하는 동시 외부 연결 6개 한도가 적용됩니다. Workers Free는 하루 요청 100,000건, HTTP 요청당 CPU 시간 10ms, 요청당 서브리퀘스트 50건, 계정당 Worker 100개와 Cron Trigger 5개로 제한됩니다. Workers Paid는 일일 요청 수 제한이 없으며 HTTP CPU 시간 최대 5분(기본값 30초), 서브리퀘스트 10,000건(최대 1,000만 건 설정 가능), 계정당 Worker 500개, Cron Trigger 1,000개를 지원합니다. [5]

### Cloudflare Workers는 어떤 프로그래밍 언어를 지원하나요?

2026-11-23 기준 Cloudflare Workers는 JavaScript, TypeScript, Python(Python Workers), Rust 네 가지 언어를 1급 언어로 지원합니다. 또한 웹어셈블리(WebAssembly, Wasm) 바이너리 실행을 지원하므로 C, C++, Kotlin, Go 등으로 작성해 Wasm으로 컴파일한 코드도 Workers에서 실행할 수 있습니다. [7]

### Cloudflare Workers는 Node.js API를 지원하나요?

네, 지원합니다. 2026-11-23 기준 Cloudflare Workers는 Buffer, crypto, fs, http, https, net, path, process, stream, timers, url, util, zlib, AsyncLocalStorage를 포함한 Node.js API 일부를 런타임에 기본 내장하고 있으며, Wrangler의 unenv 폴리필(polyfill)과 가져오기 전용 스텁(stub) 모듈을 함께 제공합니다. 호환성 날짜가 2026-08-04 이후이면 추가 플래그 없이 nodejs_compat과 nodejs_compat_v2가 기본으로 활성화됩니다. [9]

## 인용 문장

- Cloudflare는 2017년 9월 29일 Cloudflare 블로그를 통해 Cloudflare Workers를 발표했다. [12]
- Cloudflare Workers는 전 세계 Cloudflare 네트워크의 공유 런타임 프로세스 내부에 배치된 V8 아이솔레이트(isolate)에서 사용자 코드를 실행한다. [6]
- Cloudflare는 2022년 9월 27일 Cloudflare Workers를 구동하는 JavaScript 및 WebAssembly 런타임 workerd의 첫 베타 버전을 Apache-2.0 라이선스로 공개했다. [10][11]
- 2026-11-23 기준 Cloudflare Workers는 JavaScript, TypeScript, Python, Rust를 1급 언어로 지원하며 C, C++, Kotlin, Go 등을 컴파일하는 WebAssembly(Wasm)도 지원한다. [7]
- 호환성 날짜(compatibility date)가 2026-08-04 이후인 경우 Cloudflare Workers는 nodejs_compat과 nodejs_compat_v2를 기본값으로 활성화한다. [9]
- 2026-11-23 기준 Workers Free 요금제는 하루 요청 100,000건과 호출당 CPU 시간 10밀리초를 허용하며, Workers Paid 요금제는 월 최소 5달러에 월 1,000만 건의 요청과 3,000만 CPU 밀리초를 포함하고 이그레스(egress) 요금을 부과하지 않는다. [4]
- 2026-11-23 기준 Cloudflare Workers는 Free와 Paid 요금제 모두에서 아이솔레이트당 메모리 128MB, 비압축 Worker 크기 64MiB, 시작 시간 1초 한도를 적용한다. [5]
- Cloudflare의 2025 회계연도 SEC 공시는 2025년 6월 Workers KV가 사용하는 제3자 스토리지 인프라 장애로 수 시간 동안 서비스 중단이 발생했으나 재무적 중대 영향은 없었다고 밝힌다. [2]

## 연표

- 2017-09-29: Cloudflare가 Cloudflare 블로그에서 엣지 환경의 JavaScript Service Workers 실행 플랫폼인 Cloudflare Workers를 발표했다. [12]
- 2018-03-13: Cloudflare가 2017년 9월 Cloudflare Workers 발표 게시물에 서비스 가용성을 알리는 업데이트를 추가했다. [12]
- 2022-09-27: Cloudflare가 Cloudflare Workers의 JavaScript 및 WebAssembly 런타임 workerd의 첫 베타 버전을 Apache-2.0 라이선스로 공개했다. [11]
- 2024-03-01: Cloudflare가 기존 Bundled 과금 모델의 Workers 계정을 Standard 사용량 모델로 전환하고, 기존 Bundled Worker에 50밀리초 CPU 한도를 자동 적용했다. [4]
- 2024-09-23: Cloudflare Workers가 이 호환성 날짜 이후 nodejs_compat 플래그를 활성화한 프로젝트에 Wrangler unenv 폴리필을 자동 주입하기 시작했다. [9]
- 2025-06: Workers KV가 사용하는 기반 제3자 스토리지 인프라 장애로 수 시간 동안 서비스 중단이 발생했으며, 이는 Cloudflare의 2025 회계연도 SEC 공시에 기재되었다. [2]
- 2026-08-04: Cloudflare Workers가 이 호환성 날짜 이후 설정된 Worker에서 nodejs_compat과 nodejs_compat_v2를 기본값으로 활성화했다. [9]

## 출처

1. WinterTC. Ecma International (WinterTC). https://wintertc.org/ (확인일 2026-11-23; tier 1: government or public registry)
2. cloud-20251231. U.S. Securities and Exchange Commission (EDGAR). https://www.sec.gov/Archives/edgar/data/1477333/000147733326000016/cloud-20251231.htm (확인일 2026-11-23; tier 1: government or public registry)
3. Overview · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/ (확인일 2026-11-23; tier 3: official site)
4. Pricing · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/platform/pricing/ (확인일 2026-11-23; tier 3: official site)
5. Limits · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/platform/limits/ (확인일 2026-11-23; tier 3: official site)
6. How Workers works · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/reference/how-workers-works/ (확인일 2026-11-23; tier 3: official site)
7. Languages · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/languages/ (확인일 2026-11-23; tier 3: official site)
8. Runtime APIs · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/runtime-apis/ (확인일 2026-11-23; tier 3: official site)
9. Node.js compatibility · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/runtime-apis/nodejs/ (확인일 2026-11-23; tier 3: official site)
10. GitHub - cloudflare/workerd: The JavaScript / Wasm runtime that powers Cloudflare Workers · GitHub. Cloudflare (GitHub). https://github.com/cloudflare/workerd (확인일 2026-11-23; tier 3: official site)
11. Introducing workerd: the Open Source Workers runtime | Cloudflare Blog. The Cloudflare Blog. 게시일 2022-09-27. https://blog.cloudflare.com/workerd-open-source-workers-runtime/ (확인일 2026-11-23; tier 3: official site)
12. Introducing Cloudflare Workers: Run JavaScript Service Workers at the Edge | Cloudflare Blog. The Cloudflare Blog. 게시일 2017-09-29. https://blog.cloudflare.com/introducing-cloudflare-workers/ (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "Cloudflare Workers." 버전 22d620d8, 2026-11-23. https://mimirwiki.com/ko/wiki/cloudflare-workers
