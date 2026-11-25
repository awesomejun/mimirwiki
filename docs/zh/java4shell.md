---
title: "Java4Shell (CVE-2026-114938)"
subtitle: "OpenJDK HotSpot C2 JIT 编译器 x86-64 AVX-512 VBMI Base64 解码器内联函数中的严重堆缓冲区溢出漏洞"
canonical_url: https://mimirwiki.com/zh/wiki/java4shell
language: zh
page_class: concept
revision_sha256: 9e6846d2c53dfa01d1e8f63fe1dff603033d1cd0455c5e21dafd5493b61d9863
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 7
alternates:
  md: https://mimirwiki.com/zh/wiki/java4shell.md
  txt: https://mimirwiki.com/zh/wiki/java4shell.txt
  json: https://mimirwiki.com/zh/wiki/java4shell.json
  jsonld: https://mimirwiki.com/zh/wiki/java4shell.jsonld
translations:
  en: https://mimirwiki.com/wiki/java4shell
  ko: https://mimirwiki.com/ko/wiki/java4shell
  ja: https://mimirwiki.com/ja/wiki/java4shell
  es: https://mimirwiki.com/es/wiki/java4shell
---

# Java4Shell (CVE-2026-114938)

> CVE-2026-114938 由 Calif.io 的 Quang Luong（借助 AI 辅助的“半人马黑客攻击”分析该缺陷）和 Albert Yang 向 Oracle 报告，获评 CVSS v4.0 9.2 分（严重）与 CVSS v3.1 8.1 分（高危）。当 C2 JIT 的 AVX-512 Base64 解码块内联函数在 64 字节 SIMD 块内遇到意外的 '=' 填充字节时，剩余长度计算会下溢至 -1，进而为 evmovdqub（VMOVDQU8）指令生成全 1 的 64 位写掩码（0xFFFFFFFFFFFFFFFF）。对于 65 字符输入（'A' * 64 + '='），该指令会从 50 字节目标缓冲区的偏移 48 处开始写入 64 字节（超出数组末尾 62 字节的堆溢出）。该漏洞影响运行在 Intel Ice Lake 及更新型号、AMD Zen 4 及更新型号 CPU 上的 OpenJDK 与 Oracle Java SE 17.0.6+、21、25 和 27（以及 Oracle GraalVM 8u511b33-perf），已在 OpenJDK 17.0.21.0.3、21.0.13.0.3、25.0.5.0.3 和 27.0.1.0.3 中修复。

Java4Shell（编号 CVE-2026-114938）是支持 AVX-512 VBMI 指令集的 x86-64 处理器上 OpenJDK HotSpot 虚拟机 C2 即时（JIT）编译器中 java.util.Base64.Decoder 内联函数（intrinsic）存在的一个严重堆缓冲区溢出漏洞。该漏洞于 2026 年 11 月 17 日通过 OpenJDK 带外安全公告与 Oracle 紧急安全补丁更新（Critical Security Patch Update）公开，允许未经身份验证的远程攻击者通过发送包含错位填充字符（'='）的特制 Base64 载荷来破坏相邻的 Java 堆对象，从而导致拒绝服务（DoS）、身份验证绕过或认证前远程代码执行（RCE）。

**别名:** CVE-2026-114938, Java4Shell, OpenJDK AVX-512 Base64 堆溢出, RHSB-2026-018

## 关键事实

- **CVE 编号与评分:** CVE-2026-114938（CVSS v4.0: 9.2 严重 / CVSS v3.1: 8.1 高危） (截至 2026-11-17) [3]
- **受影响组件:** OpenJDK HotSpot VM C2 JIT x86-64 AVX-512 VBMI Base64.Decoder 内联函数 [1]
- **硬件前提条件:** 支持 AVX-512 VBMI 的 x86-64 CPU（Intel Ice Lake+ / AMD Zen 4+）；ARM64 不受影响 [4]
- **已修复的 OpenJDK 版本:** 17.0.21.0.3、21.0.13.0.3、25.0.5.0.3 和 27.0.1.0.3（2026 年 11 月 17 日发布） (截至 2026-11-17) [1]

## 事实摘要

- **CVE 编号:** CVE-2026-114938 [3]
- **通称:** Java4Shell [4]
- **公开日期:** 2026 年 11 月 17 日 [1]
- **发现者:** Quang Luong（Calif.io）与 Albert Yang（获 Oracle 致谢） [2]
- **CVSS 严重程度:** CVSS v4.0: 9.2（严重）/ CVSS v3.1: 8.1（高危） [3]
- **漏洞类型:** CWE-122（堆缓冲区溢出）/ SIMD 写掩码整数下溢 [3]
- **受影响的 Java 版本:** OpenJDK / Oracle JDK 17（自 17.0.6 起）、21、25、27；Oracle JDK 8u511b33-perf [2]
- **JVM 参数缓解措施:** -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics（或 -XX:UseAVX=2） [5]

## Java4Shell 概述与通过“半人马黑客攻击”的发现过程

**Java4Shell**（`CVE-2026-114938`）是 Java 虚拟机硬件加速 Base64 解码例程中的一个严重内存安全漏洞。[1][3][4] 由于 Java 是一种具备垃圾回收机制的内存安全语言，应用程序开发者通常会在执行身份验证或模式校验之前，直接将不可信的 HTTP 标头（例如 `Authorization: Basic` 或 `Bearer` JWT 令牌）、Cookie、SAML 断言以及 JSON 字段传递给 `java.util.Base64.getDecoder().decode()`。[4][5] 然而，当热点 Java 方法被 HotSpot C2 即时（JIT）编译器编译时，JVM 会将 `Base64.Decoder.decodeBlock` 的字节码实现替换为针对宿主机 CPU 架构手工编写的汇编内联函数（intrinsic）。[1][4]

在 2026 年 11 月的紧急安全补丁更新（CSPU）公告中，Oracle 将 **Calif.io 的 Quang Luong** 和 **Albert Yang** 列为 `CVE-2026-114938` 的报告者；该漏洞在与 Oracle 及 OpenJDK 安全小组协调后，于 **2026 年 11 月 17 日**公开披露。[1][2][4][7] 在 Calif.io 的技术披露文章中，Luong 详细介绍了其通过他称为**“半人马黑客攻击”（centaur hacking）**的工作流发现该缺陷的过程：将人类逆向工程假设与大语言模型智能体相结合，以审计 OpenJDK `stubGenerator_x86_64.cpp` 中复杂的手工编写 x86-64 SIMD 汇编桩代码生成器。[4]

## Java4Shell 技术原理：AVX-512 VBMI 掩码下溢

`CVE-2026-114938` 的根本原因位于 OpenJDK C2 JIT Base64 解码器内联函数（`decodeBlock`）中的 x86-64 **AVX-512 VBMI**（向量字节操作指令）快速路径。[1][4] 在标准 Base64 解码中，每 4 个编码后的 ASCII 字节产生 3 个解码输出字节，因此一个 64 字节的 AVX-512 寄存器（`ZMM`）中的 Base64 输入最多产生 48 字节的解码输出。[4] 当内联函数在 64 字节 SIMD 块内遇到非 Base64 字符或 `'='` 填充字符（`0x3d`）时，其预期行为是退出向量化循环并将剩余的尾部字节交由标量 Java 循环处理。[4]

然而，在为最终带掩码的 SIMD 存储指令 `evmovdqub`（使用写掩码寄存器 `k` 的 `VMOVDQU8`）计算剩余 `output_len` 时，由于存在有符号/无符号长度计算错误，位于特定偏移处的错位 `'='` 字符会导致计算出的剩余字节数下溢为 `-1`（64 位二进制补码表示为 `0xFFFFFFFFFFFFFFFF`）。[4] 当该值被移位或加载到 64 位 AVX-512 操作掩码寄存器时，掩码变为全 1（`-1u64`），从而指示 CPU 的 `evmovdqub` 指令将完整的 **64 字节**寄存器数据写入目标 Java `byte[]` 数组。[4]

Calif.io 根据不同 JDK 版本的内联函数阈值演示了两种最小确定性触发载荷。[4] - **OpenJDK 21、25 和 27**：解码 65 字节字符串 `'A' * 64 + '='` 会分配一个 50 字节的目标 `byte[]` 数组（包括 16 字节数组对象头在内，在 HotSpot 堆上占用一个按 8 字节对齐的 72 字节对象）。前 64 个字符解码为 48 字节后，带掩码的 `evmovdqub` 会从 50 字节载荷缓冲区的偏移 48 处开始写入 64 字节（其中写入的第 48..63 字节等于 `0x9a`），从而**超出数组末尾 62 字节并溢出到紧邻的下一个 Java 堆对象的对象头和字段中**。[4] - **OpenJDK 17（17.0.6 至 17.0.21）**：由于 JDK 17 在进入 AVX-512 循环之前的最小缓冲区大小检查阈值更大，其最小触发载荷为 129 字节字符串 `'A' * 128 + '='`。[4]

## 受影响的 Java 版本、CPU 架构与企业级影响

利用 `CVE-2026-114938` 必须同时满足两个条件：受影响的 JVM 构建版本以及支持 **AVX-512 VBMI** 的 x86-64 处理器。[1][2][4]

| 维度 | 受影响的配置 | 不受影响的配置 |
| --- | --- | --- |
| **Java / OpenJDK 版本** | OpenJDK 与 Oracle Java SE **17.0.6 - 17.0.21**、**21.0.0 - 21.0.13**、**25.0.0 - 25.0.5**、**27.0.0 - 27.0.1**；Oracle GraalVM / JDK **8u511b33-perf** [1][2] | 标准 OpenJDK 8 与 OpenJDK 11（不包含 AVX-512 VBMI Base64 内联函数）；OpenJDK 17.0.1 - 17.0.5 [1][4][5] |
| **CPU 架构** | **支持 AVX-512 VBMI 的 x86-64**：Intel Ice Lake、Tiger Lake、Sapphire Rapids、Emerald Rapids、Granite Rapids；AMD Zen 4（EPYC Genoa/Bergamo）与 Zen 5（EPYC Turin） [4][5] | **ARM64 / AArch64**（AWS Graviton、Apple Silicon、Ampere）；不支持 AVX-512 VBMI 的较旧 x86-64 CPU（例如 Intel Skylake-SP、AMD Zen 2/Zen 3） [4][5] |

由于 62 字节的堆溢出可覆写线程本地分配缓冲区（TLAB）中下一个对象的标记字（mark word）、压缩类指针（`_klass`）、数组长度字段或布尔/引用字段，攻击者可以破坏相邻的安全令牌，或篡改并扩大相邻 `byte[]` 数组的长度字段，进而在 JVM 进程内构造任意读写原语。[4] Calif.io 与多家企业级厂商已在多款主流 Java 中间件和应用中演示或确认了认证前影响，包括 **Keycloak**、**Atlassian Jira 与 Confluence**、**JFrog Artifactory**、**Jenkins** 以及 **PingFederate**。[4][7]

## 补丁版本、JVM 启动参数缓解与 CISA 建议

2026 年 11 月 17 日，OpenJDK 项目、Oracle、Red Hat（`RHSB-2026-018`）、Amazon Corretto、Eclipse Temurin 和 Azul 发布了紧急带外版本，禁用了有缺陷的 AVX-512 VBMI 掩码生成或修复了边界计算。[1][2][5] - **OpenJDK 17.0.21.0.3** - **OpenJDK 21.0.13.0.3** - **OpenJDK 25.0.5.0.3** - **OpenJDK 27.0.1.0.3**

**JVM 命令行缓解措施**：对于无法立即升级 JDK 二进制文件的生产系统，管理员可在 `JAVA_OPTS` 中添加以下任一参数并重启 JVM，以禁用 Base64 C2 内联函数或限制 AVX-512 执行。[4][5] ```text -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics ``` 或者将 AVX 级别限制在 AVX-512 以下： ```text -XX:UseAVX=2 ```

**CISA 警报与边界缓解措施**：2026 年 11 月 17 日，美国网络安全和基础设施安全局（CISA）在加拿大网络安全中心（Canadian Centre for Cyber Security）协助下发布警报，敦促各机构清查 JDK 与 Java 运行时（包括捆绑在第三方应用、容器镜像和设备中的版本），并优先为面向互联网的系统打补丁。[6] 若无法立即打补丁，CISA 建议实施临时补偿性控制措施，例如在应用边界限制并校验 Base64 输入、强制执行输入大小限制、限制未经身份验证的访问，同时监控异常运行时、意外 JVM 崩溃及可疑 Java 进程。[6]

## 常见问题

### 什么是 Java4Shell（CVE-2026-114938）？

Java4Shell（CVE-2026-114938）是 OpenJDK HotSpot C2 JIT 编译器中 java.util.Base64.Decoder 的 x86-64 AVX-512 VBMI 内联函数存在的一个严重堆缓冲区溢出漏洞（CVSS v4.0 9.2 分 / CVSS v3.1 8.1 分）。该漏洞于 2026 年 11 月 17 日公开，允许远程攻击者通过提交包含错位 '=' 填充字符的畸形 Base64 字符串来破坏 Java 堆上的相邻对象。 [1][3][4]

### 哪些 Java 版本和 CPU 容易受到 CVE-2026-114938 的影响？

该漏洞影响 OpenJDK 和 Oracle Java SE 17（17.0.6 至 17.0.21 版本）、21（至 21.0.13）、25（至 25.0.5）和 27（至 27.0.1），以及 Oracle JDK 8u511b33-perf，但仅限运行在支持 AVX-512 VBMI 的 x86-64 CPU（例如 Intel Ice Lake 及更新型号或 AMD Zen 4 及更新型号）上的环境。ARM64 服务器以及标准 OpenJDK 8 和 11 构建版本不受影响。 [1][2][4][5]

### 65 字节的 Base64 字符串如何在 Java 中触发堆缓冲区溢出？

当 AVX-512 VBMI Base64 decodeBlock 内联函数处理完一个 64 字节 SIMD 块（解码为 48 字节输出）后遇到意外的 '=' 填充字节（例如 64 个 'A' 后接一个 '='）时，长度计算会下溢至 -1。这会使 64 位 AVX-512 写掩码变为全 1（0xFFFFFFFFFFFFFFFF），导致 evmovdqub 指令从 50 字节缓冲区的偏移 48 处开始写入 64 字节，超出数组末尾 62 字节并覆写相邻的 Java 堆对象。 [4]

### 哪些已修补的 OpenJDK 版本修复了 Java4Shell？

该漏洞已在 2026 年 11 月 17 日发布的 OpenJDK 带外版本 17.0.21.0.3、21.0.13.0.3、25.0.5.0.3 和 27.0.1.0.3，以及相应的 2026 年 11 月 Oracle 紧急安全补丁更新和 Red Hat OpenJDK 构建版本中得到修复。 [1][2][5]

### 如何在不升级 Java 的情况下通过 JVM 参数缓解 CVE-2026-114938？

管理员可以在 JVM 启动参数中传入 '-XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics'（或 '-XX:UseAVX=2'）并重启 Java 进程，从而完全禁用存在漏洞的汇编内联函数。 [4][5]

## 可引用的句子

- CVE-2026-114938（Java4Shell）于 2026 年 11 月 17 日公开披露，CVSS v4.0 评分为 9.2（严重），CVSS v3.1 评分为 8.1（高危）。 [1][2][3]
- CVE-2026-114938 由 OpenJDK C2 JIT Base64.Decoder 内联函数中 evmovdqub 指令的 AVX-512 VBMI 写掩码整数下溢至 -1 引起，导致从 50 字节缓冲区的偏移 48 处写入 64 字节（62 字节堆溢出）。 [4]
- Oracle 2026 年 11 月紧急安全补丁更新公告将 Calif.io 的 Quang Luong 和 Albert Yang 列为 CVE-2026-114938 的报告者；该漏洞影响支持 AVX-512 VBMI 的 x86-64 CPU 上的 OpenJDK 17.0.6+、21、25 和 27，而 ARM64 与标准 OpenJDK 8/11 不受影响。 [1][2][4][5][7]
- OpenJDK 在紧急版本 17.0.21.0.3、21.0.13.0.3、25.0.5.0.3 和 27.0.1.0.3 中修复了 CVE-2026-114938，且可通过 -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics 进行缓解。 [1][5]

## 时间线

- 2023-01: OpenJDK 17.0.6 反向移植了包含潜在掩码下溢缺陷的 AVX-512 VBMI Base64 解码器 C2 JIT 内联函数。 [1][4]
- 2026-11-17: OpenJDK 发布 2026/11/17 安全公告，Oracle 发布计划外关键安全补丁更新，CISA 发布警报敦促立即修复 CVE-2026-114938；OpenJDK 17.0.21.0.3、21.0.13.0.3、25.0.5.0.3 与 27.0.1.0.3 同步发布。 [1][2][6]
- 2026-11-18: Calif.io 的 Quang Luong 发布技术根因分析（“Java4Shell”），Red Hat 发布安全公告 RHSB-2026-018。 [4][5]

## 来源

1. OpenJDK Vulnerability Advisory: 2026/11/17 (CVE-2026-114938 in Hotspot Base64 Intrinsic). OpenJDK Vulnerability Group. 发布于 2026-11-17. https://openjdk.org/groups/vulnerability/advisories/2026-11-17 (访问于 2026-11-23; tier 3: official site)
2. Oracle Critical Security Patch Update Advisory - November 2026. Oracle Corporation. 发布于 2026-11-17. https://www.oracle.com/security-alerts/cspunov2026.html (访问于 2026-11-23; tier 3: official site)
3. NVD Detail for CVE-2026-114938: OpenJDK HotSpot VM AVX-512 Base64 Decoder Heap-Based Buffer Overflow. National Vulnerability Database (NIST). 发布于 2026-11-17. https://nvd.nist.gov/vuln/detail/CVE-2026-114938 (访问于 2026-11-23; tier 1: government or public registry)
4. Java4Shell: Write once, RCE everywhere. Calif.io (Quang Luong). 发布于 2026-11-18. https://calif.io/java4shell (访问于 2026-11-23; tier 3: official site)
5. Red Hat Security Bulletin RHSB-2026-018: OpenJDK AVX-512 Base64 Heap Overflow (CVE-2026-114938). Red Hat, Inc.. 发布于 2026-11-18. https://access.redhat.com/security/vulnerabilities/RHSB-2026-018 (访问于 2026-11-23; tier 3: official site)
6. Critical Java Vulnerability Requires Immediate Patching | CISA. Cybersecurity and Infrastructure Security Agency (CISA). 发布于 2026-11-17. https://www.cisa.gov/news-events/alerts/2026/11/17/critical-java-vulnerability-requires-immediate-patching (访问于 2026-11-24; tier 1: government or public registry)
7. Java4Shell (CVE-2026-114938): OpenJDK RCE Vulnerability FAQ. Tenable Research. 发布于 2026-11-17. https://www.tenable.com/blog/java4shell-cve-2026-114938-frequently-asked-questions-about-openjdk-rce-vulnerability (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "Java4Shell (CVE-2026-114938)." 版本 9e6846d2, 2026-11-24. https://mimirwiki.com/zh/wiki/java4shell
