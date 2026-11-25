---
title: "Java4Shell (CVE-2026-114938)"
subtitle: "Critical heap buffer overflow in the OpenJDK HotSpot C2 JIT x86-64 AVX-512 VBMI Base64 decoder intrinsic"
canonical_url: https://mimirwiki.com/wiki/java4shell
language: en
page_class: concept
revision_sha256: c4188de0c9b6c463ac7dd61811de4607c909195453780bf5d254e340c4a3be78
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 7
alternates:
  md: https://mimirwiki.com/wiki/java4shell.md
  txt: https://mimirwiki.com/wiki/java4shell.txt
  json: https://mimirwiki.com/wiki/java4shell.json
  jsonld: https://mimirwiki.com/wiki/java4shell.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/java4shell
  ja: https://mimirwiki.com/ja/wiki/java4shell
  zh: https://mimirwiki.com/zh/wiki/java4shell
  es: https://mimirwiki.com/es/wiki/java4shell
---

# Java4Shell (CVE-2026-114938)

> Reported to Oracle by Quang Luong of Calif.io (who analyzed the flaw using AI-assisted 'centaur hacking') and Albert Yang, and assigned CVSS v4.0 9.2 (Critical) and CVSS v3.1 8.1 (High), CVE-2026-114938 occurs when the C2 JIT AVX-512 Base64 decode block intrinsic encounters an unexpected '=' padding byte inside a 64-byte SIMD block, causing the remaining length calculation to underflow to -1 and generating an all-ones 64-bit write mask (0xFFFFFFFFFFFFFFFF) for the evmovdqub (VMOVDQU8) instruction. For a 65-character input ('A' * 64 + '='), this writes 64 bytes starting at offset 48 of a 50-byte destination buffer (a 62-byte heap overflow past the end of the array). It affects OpenJDK and Oracle Java SE 17.0.6+, 21, 25, and 27 (plus Oracle GraalVM 8u511b33-perf) on Intel Ice Lake+ and AMD Zen 4+ CPUs, and is patched in OpenJDK 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3, and 27.0.1.0.3.

Java4Shell (tracked as CVE-2026-114938) is a critical heap-based buffer overflow vulnerability in the OpenJDK HotSpot Virtual Machine's C2 Just-In-Time (JIT) compiler intrinsic for java.util.Base64.Decoder on x86-64 processors supporting the AVX-512 VBMI instruction set. Disclosed on November 17, 2026 via an out-of-band OpenJDK Vulnerability Advisory and an Oracle Critical Security Patch Update, the flaw allows unauthenticated remote attackers to corrupt adjacent Java heap objects - leading to Denial of Service (DoS), authentication bypass, or pre-authentication Remote Code Execution (RCE) - by sending a specially crafted Base64 payload containing a misplaced padding character ('=').

**Also known as:** CVE-2026-114938, Java4Shell, OpenJDK AVX-512 Base64 Heap Overflow, RHSB-2026-018

## Key facts

- **CVE Identifier & Scores:** CVE-2026-114938 (CVSS v4.0: 9.2 Critical / CVSS v3.1: 8.1 High) (as of 2026-11-17) [3]
- **Affected Component:** OpenJDK HotSpot VM C2 JIT x86-64 AVX-512 VBMI Base64.Decoder intrinsic [1]
- **Hardware Prerequisite:** x86-64 CPUs with AVX-512 VBMI (Intel Ice Lake+ / AMD Zen 4+); ARM64 unaffected [4]
- **Patched OpenJDK Versions:** 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3, and 27.0.1.0.3 (released Nov 17, 2026) (as of 2026-11-17) [1]

## Basic facts

- **CVE ID:** CVE-2026-114938 [3]
- **Common Name:** Java4Shell [4]
- **Disclosure Date:** November 17, 2026 [1]
- **Discoverer:** Quang Luong (Calif.io) and Albert Yang (credited by Oracle) [2]
- **CVSS Severity:** CVSS v4.0: 9.2 (Critical) / CVSS v3.1: 8.1 (High) [3]
- **Weakness Type:** CWE-122 (Heap-based Buffer Overflow) / Integer Underflow in SIMD Write Mask [3]
- **Affected Java Releases:** OpenJDK / Oracle JDK 17 (since 17.0.6), 21, 25, 27; Oracle JDK 8u511b33-perf [2]
- **JVM Flag Workaround:** -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics (or -XX:UseAVX=2) [5]

## Overview and Discovery via 'Centaur Hacking'

**Java4Shell** (`CVE-2026-114938`) is a critical memory-safety vulnerability in the Java Virtual Machine's hardware-accelerated Base64 decoding routine [1][3][4]. Because Java is a memory-safe, garbage-collected language, application developers routinely pass untrusted HTTP headers (such as `Authorization: Basic` or `Bearer` JWT tokens), cookies, SAML assertions, and JSON fields directly to `java.util.Base64.getDecoder().decode()` before performing authentication or schema validation [4][5]. However, when a hot Java method is compiled by the HotSpot C2 Just-In-Time (JIT) compiler, the JVM replaces the bytecode implementation of `Base64.Decoder.decodeBlock` with hand-written assembly intrinsics tailored to the host CPU architecture [1][4].

In its November 2026 Critical Security Patch Update (CSPU) advisory, Oracle credits **Quang Luong of Calif.io** and **Albert Yang** for reporting `CVE-2026-114938`, which was coordinated with Oracle and the OpenJDK Vulnerability Group for public disclosure on **November 17, 2026** [1][2][4][7]. In Calif.io's technical disclosure, Luong detailed finding the bug through a workflow he termed **'centaur hacking'** - combining human reverse-engineering hypotheses with large language model agents to audit complex hand-coded x86-64 SIMD assembly stub generators inside OpenJDK's `stubGenerator_x86_64.cpp` [4].

## Technical Mechanism: AVX-512 VBMI Mask Underflow

The root cause of `CVE-2026-114938` resides in the x86-64 **AVX-512 VBMI** (Vector Byte Manipulation Instructions) fast-path inside OpenJDK's C2 JIT Base64 decoder intrinsic (`decodeBlock`) [1][4]. In standard Base64 decoding, every 4 encoded ASCII bytes produce 3 decoded output bytes, so a 64-byte AVX-512 register (`ZMM`) of Base64 input yields up to 48 bytes of decoded output [4]. When the intrinsic encounters a non-Base64 character or an `'='` padding character (`0x3d`) inside a 64-byte SIMD chunk, it is supposed to exit the vectorized loop and hand off the remaining tail bytes to the scalar Java loop [4].

However, due to a signed/unsigned length calculation bug when computing the remaining `output_len` for the final masked SIMD store instruction `evmovdqub` (`VMOVDQU8` with writemask register `k`), a misplaced `'='` character at specific offsets causes the calculated remaining byte count to underflow to `-1` (`0xFFFFFFFFFFFFFFFF` in 64-bit two's complement) [4]. When that value is shifted or loaded into the 64-bit AVX-512 opmask register, the mask becomes all ones (`-1u64`), instructing the CPU's `evmovdqub` instruction to write a full **64 bytes** of register data into the destination Java `byte[]` array [4].

Calif.io demonstrated two minimal deterministic triggers depending on the JDK release's intrinsic threshold [4]: - **OpenJDK 21, 25, and 27**: Decoding the 65-byte string `'A' * 64 + '='` allocates a 50-byte destination `byte[]` array (which occupies a 72-byte 8-byte-aligned object on the HotSpot heap, including the 16-byte array object header). After the first 64 characters decode to 48 bytes, the masked `evmovdqub` writes 64 bytes starting at offset 48 of the 50-byte payload buffer (with bytes 48..63 of the write equal to `0x9a`) - **overflowing 62 bytes past the end of the array into the header and fields of the immediately adjacent Java heap object** [4]. - **OpenJDK 17 (17.0.6 through 17.0.21)**: Due to a larger minimum buffer size check before entering the AVX-512 loop in JDK 17, the minimal trigger is the 129-byte string `'A' * 128 + '='` [4].

## Affected Java Versions, CPU Architectures, and Enterprise Impact

Exploitation of `CVE-2026-114938` requires two simultaneous conditions: an affected JVM build and an x86-64 processor that supports **AVX-512 VBMI** [1][2][4]:

| Dimension | Vulnerable Configurations | Unaffected Configurations |
| --- | --- | --- |
| **Java / OpenJDK Versions** | OpenJDK & Oracle Java SE **17.0.6 - 17.0.21**, **21.0.0 - 21.0.13**, **25.0.0 - 25.0.5**, **27.0.0 - 27.0.1**; Oracle GraalVM / JDK **8u511b33-perf** [1][2] | Standard OpenJDK 8 and OpenJDK 11 (lack the AVX-512 VBMI Base64 intrinsic); OpenJDK 17.0.1 - 17.0.5 [1][4][5] |
| **CPU Architectures** | **x86-64 with AVX-512 VBMI**: Intel Ice Lake, Tiger Lake, Sapphire Rapids, Emerald Rapids, Granite Rapids; AMD Zen 4 (EPYC Genoa/Bergamo) and Zen 5 (EPYC Turin) [4][5] | **ARM64 / AArch64** (AWS Graviton, Apple Silicon, Ampere); older x86-64 CPUs without AVX-512 VBMI (e.g., Intel Skylake-SP, AMD Zen 2/Zen 3) [4][5] |

Because the 62-byte heap overflow overwrites the mark word, compressed klass pointer (`_klass`), array length field, or boolean/reference fields of the next object in the Thread-Local Allocation Buffer (TLAB), an attacker can corrupt adjacent security tokens or inflate an adjacent `byte[]` array's length field to construct arbitrary read/write primitives inside the JVM process [4]. Calif.io and enterprise vendors demonstrated or confirmed pre-authentication impact across major Java middleware and applications, including **Keycloak**, **Atlassian Jira and Confluence**, **JFrog Artifactory**, **Jenkins**, and **PingFederate** [4][7].

## Patched Releases, JVM Flag Workarounds, and CISA Guidance

On November 17, 2026, the OpenJDK Project, Oracle, Red Hat (`RHSB-2026-018`), Amazon Corretto, Eclipse Temurin, and Azul released emergency out-of-band builds disabling or bounds-fixing the faulty AVX-512 VBMI mask generation [1][2][5]: - **OpenJDK 17.0.21.0.3** - **OpenJDK 21.0.13.0.3** - **OpenJDK 25.0.5.0.3** - **OpenJDK 27.0.1.0.3**

**JVM Command-Line Workarounds**: For production systems that cannot immediately upgrade the JDK binary, administrators can disable the Base64 C2 intrinsic or restrict AVX-512 execution by adding one of the following flags to `JAVA_OPTS` and restarting the JVM [4][5]: ```text -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics ``` or alternatively cap AVX level below AVX-512: ```text -XX:UseAVX=2 ```

**CISA Alert and Boundary Mitigations**: On November 17, 2026, the U.S. Cybersecurity and Infrastructure Security Agency (CISA), with contributions from the Canadian Centre for Cyber Security, issued an alert urging organizations to inventory JDKs and Java runtimes (including those bundled in third-party applications, container images, and appliances) and prioritize patching internet-facing systems [6]. Where immediate patching is not feasible, CISA recommends temporary compensating controls such as restricting and validating Base64 input at the application boundary, enforcing input-size limits, and limiting unauthenticated access, while monitoring for rogue runtimes, unexpected JVM crashes, and suspicious Java processes [6].

## Frequently asked questions

### What is Java4Shell (CVE-2026-114938)?

Java4Shell (CVE-2026-114938) is a critical heap buffer overflow vulnerability (CVSS v4.0 9.2 / CVSS v3.1 8.1) in the OpenJDK HotSpot C2 JIT compiler's x86-64 AVX-512 VBMI intrinsic for java.util.Base64.Decoder. Disclosed on November 17, 2026, it allows remote attackers to corrupt adjacent objects on the Java heap by submitting malformed Base64 strings containing misplaced '=' padding characters. [1][3][4]

### Which Java versions and CPUs are vulnerable to CVE-2026-114938?

The flaw affects OpenJDK and Oracle Java SE 17 (versions 17.0.6 through 17.0.21), 21 (through 21.0.13), 25 (through 25.0.5), and 27 (through 27.0.1), as well as Oracle JDK 8u511b33-perf, but only when running on x86-64 CPUs that support AVX-512 VBMI (such as Intel Ice Lake and newer or AMD Zen 4 and newer). ARM64 servers and standard OpenJDK 8 and 11 builds are not affected. [1][2][4][5]

### How does a 65-byte Base64 string trigger a heap buffer overflow in Java?

When the AVX-512 VBMI Base64 decodeBlock intrinsic processes a 64-byte SIMD chunk (which decodes to 48 output bytes) and then encounters an unexpected '=' padding byte (such as 'A' repeated 64 times followed by '='), a length calculation underflows to -1. This turns the 64-bit AVX-512 write mask into all ones (0xFFFFFFFFFFFFFFFF), causing the evmovdqub instruction to write 64 bytes starting at offset 48 of a 50-byte buffer and overwrite 62 bytes past the end of the array into the adjacent Java heap object. [4]

### Which patched OpenJDK versions fix Java4Shell?

The vulnerability is patched in the November 17, 2026 out-of-band OpenJDK releases 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3, and 27.0.1.0.3, as well as the corresponding November 2026 Oracle Critical Security Patch Update and Red Hat OpenJDK builds. [1][2][5]

### How can I mitigate CVE-2026-114938 with JVM flags without upgrading Java?

Administrators can completely disable the vulnerable assembly intrinsic by passing '-XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics' (or '-XX:UseAVX=2') to the JVM startup arguments and restarting the Java process. [4][5]

## Quotable sentences

- CVE-2026-114938 (Java4Shell) was disclosed on November 17, 2026 with a CVSS v4.0 score of 9.2 (Critical) and CVSS v3.1 score of 8.1 (High). [1][2][3]
- CVE-2026-114938 is caused by an integer underflow to -1 in the AVX-512 VBMI write mask for the evmovdqub instruction inside OpenJDK's C2 JIT Base64.Decoder intrinsic, resulting in a 64-byte write starting at offset 48 of a 50-byte buffer (a 62-byte heap overflow). [4]
- Oracle's November 2026 Critical Security Patch Update advisory credits Quang Luong of Calif.io and Albert Yang for reporting CVE-2026-114938, which affects OpenJDK 17.0.6+, 21, 25, and 27 on x86-64 CPUs supporting AVX-512 VBMI while ARM64 and standard OpenJDK 8/11 are unaffected. [1][2][4][5][7]
- OpenJDK patched CVE-2026-114938 in emergency releases 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3, and 27.0.1.0.3, and it can be mitigated via -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics. [1][5]

## Timeline

- 2023-01: OpenJDK 17.0.6 backports the AVX-512 VBMI Base64 decoder C2 JIT intrinsic containing the latent mask underflow bug. [1][4]
- 2026-11-17: OpenJDK publishes Vulnerability Advisory 2026/11/17, Oracle releases an out-of-band Critical Security Patch Update, and CISA issues an alert urging immediate patching for CVE-2026-114938; OpenJDK 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3, and 27.0.1.0.3 are released. [1][2][6]
- 2026-11-18: Quang Luong of Calif.io publishes the technical root-cause analysis ('Java4Shell'), and Red Hat issues Security Bulletin RHSB-2026-018. [4][5]

## Sources

1. OpenJDK Vulnerability Advisory: 2026/11/17 (CVE-2026-114938 in Hotspot Base64 Intrinsic). OpenJDK Vulnerability Group. published 2026-11-17. https://openjdk.org/groups/vulnerability/advisories/2026-11-17 (checked 2026-11-23; tier 3: official site)
2. Oracle Critical Security Patch Update Advisory - November 2026. Oracle Corporation. published 2026-11-17. https://www.oracle.com/security-alerts/cspunov2026.html (checked 2026-11-23; tier 3: official site)
3. NVD Detail for CVE-2026-114938: OpenJDK HotSpot VM AVX-512 Base64 Decoder Heap-Based Buffer Overflow. National Vulnerability Database (NIST). published 2026-11-17. https://nvd.nist.gov/vuln/detail/CVE-2026-114938 (checked 2026-11-23; tier 1: government or public registry)
4. Java4Shell: Write once, RCE everywhere. Calif.io (Quang Luong). published 2026-11-18. https://calif.io/java4shell (checked 2026-11-23; tier 3: official site)
5. Red Hat Security Bulletin RHSB-2026-018: OpenJDK AVX-512 Base64 Heap Overflow (CVE-2026-114938). Red Hat, Inc.. published 2026-11-18. https://access.redhat.com/security/vulnerabilities/RHSB-2026-018 (checked 2026-11-23; tier 3: official site)
6. Critical Java Vulnerability Requires Immediate Patching | CISA. Cybersecurity and Infrastructure Security Agency (CISA). published 2026-11-17. https://www.cisa.gov/news-events/alerts/2026/11/17/critical-java-vulnerability-requires-immediate-patching (checked 2026-11-24; tier 1: government or public registry)
7. Java4Shell (CVE-2026-114938): OpenJDK RCE Vulnerability FAQ. Tenable Research. published 2026-11-17. https://www.tenable.com/blog/java4shell-cve-2026-114938-frequently-asked-questions-about-openjdk-rce-vulnerability (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "Java4Shell (CVE-2026-114938)." Version c4188de0, 2026-11-24. https://mimirwiki.com/wiki/java4shell
