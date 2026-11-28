---
title: "llama.cpp"
subtitle: "Open-source C/C++ inference engine maintained by ggml-org for running large language models locally across CPU and GPU hardware"
canonical_url: https://mimirwiki.com/wiki/llama-cpp
language: en
page_class: entity
revision_sha256: 2dac9379be7159953e034d92fe6e26c3dc07ad821274246c2bf8df32f8a2a5ba
date_modified: 2026-11-28
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 6
alternates:
  md: https://mimirwiki.com/wiki/llama-cpp.md
  txt: https://mimirwiki.com/wiki/llama-cpp.txt
  json: https://mimirwiki.com/wiki/llama-cpp.json
  jsonld: https://mimirwiki.com/wiki/llama-cpp.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/llama-cpp
---

# llama.cpp

> llama.cpp is an open-source C/C++ inference engine maintained by ggml-org for running large language models locally on consumer and workstation hardware. On November 26, 2026, ggml-org released an AMD Ryzen and Radeon benchmark dashboard on Hugging Face measuring PP512 prompt processing and TG128 token generation separately from zero context depth across models, builds, and quantizations.

llama.cpp is an open-source C and C++ inference engine developed under ggml-org for executing large language models locally on personal computers, workstations, and GPUs. It includes the `llama-bench` utility for standardized throughput measurement and powers prebuilt local installations distributed via `llama-install.sh` and the separate Llama desktop application. On November 26, 2026, ggml-org launched a public AMD Ryzen and Radeon benchmark dashboard on Hugging Face that tracks prompt processing (PP512) and token generation (TG128) throughput separately across models, builds, and quantizations.

**Also known as:** llama.cpp, 라마닷시피피

## Key facts

- **Maintainer / repository:** ggml-org (github.com/ggml-org/llama.cpp) (as of 2026-11-28) [3]
- **Implementation language:** C / C++ (as of 2026-11-28) [3]
- **AMD benchmark dashboard launch:** November 26, 2026 (Radeon 8060S gfx1151 and Radeon AI Pro R9700S gfx1201) (as of 2026-11-26) [1]
- **Core benchmark metrics:** PP512 (512 input tokens, no generation) and TG128 (128 output tokens, depth 0) (as of 2026-11-26) [1]

## Basic facts

- **Software type:** Open-source local LLM inference engine [3]
- **Organization:** ggml-org [3]
- **Programming languages:** C and C++ [3]
- **Benchmarking tool:** llama-bench [4]
- **AMD dashboard hardware (Nov 2026):** Radeon 8060S (gfx1151) and Radeon AI Pro R9700S (gfx1201) [1]
- **Related desktop app:** Llama app (distributed via llama-install.sh) [6]

## llama.cpp architecture and local inference ecosystem

llama.cpp is an open-source C/C++ project hosted under `ggml-org` that enables large language model inference on local hardware without relying on cloud APIs.[3] Alongside the core inference engine, the repository maintains `llama-bench` for reproducible command-line benchmarking across quantization formats and hardware backends.[4] Prebuilt binaries are packaged through `llama-install.sh`, which also underpins the separate `llama.app` local desktop application.[1][6]

## How PP512 prompt processing and TG128 token generation are measured separately

On November 26, 2026, ggml-org released the llama.cpp x AMD Benchmark dashboard on Hugging Face Spaces to track local inference performance over time on AMD Ryzen and Radeon hardware, initially featuring Radeon 8060S (`gfx1151`) and Radeon AI Pro R9700S (`gfx1201`).[1][2] Rather than collapsing performance into a single score, the dashboard reports two distinct workloads in tokens per second (mean throughput, `avg_ts`), both starting at context depth zero (`n_depth=0`):[1]

| Benchmark Metric | Workload Measured | Starting Context Depth | What It Indicates |
| --- | --- | --- | --- |
| PP512 | Processing 512 input tokens without text generation | 0 (`n_depth=0`) | Prompt ingestion / prefill speed |
| TG128 | Generating 128 output tokens without pre-existing context | 0 (`n_depth=0`) | Autoregressive decoding speed |
| Context scaling tab | Token generation throughput as context length increases | Growing context | Memory-bandwidth impact at longer contexts |

Users can filter results by hardware, model, llama.cpp build, and quantization format.[1][2]

## Public weekly benchmark workflows

ggml-org publishes both the underlying benchmark results and the automated GitHub Actions workflows (such as `bench-gfx1151.yml` in `llama-install.sh`) that run weekly against prebuilt binaries using `llama-bench`.[1][5] Making the workflows public lets developers verify how kernel, build, and model updates affect AMD local inference throughput over time.[1]

## Limits of benchmark numbers as of November 2026

As of November 28, 2026, throughput figures on the AMD dashboard reflect controlled zero-depth and context-scaling test configurations on specific reference hardware rather than guaranteed speed on any individual user's device or real-world application setup.[1] Moreover, tokens-per-second throughput measures execution speed only and cannot evaluate the accuracy or quality of a model's answers.[1][4]

## Frequently asked questions

### What is llama.cpp?

llama.cpp is an open-source C/C++ inference engine maintained by ggml-org for running large language models locally on consumer and workstation CPUs and GPUs. [3]

### How are prompt processing and response generation speeds measured separately?

In ggml-org's November 26, 2026 AMD benchmark dashboard, PP512 measures processing 512 input tokens without generation, while TG128 measures generating 128 output tokens without prior context. Both start at context depth zero and report mean tokens per second, while a separate Context scaling tab tracks generation speed as context grows. [1][2]

### Which AMD GPUs were included at the launch of the benchmark dashboard?

The initial hardware selections on the Hugging Face dashboard are the AMD Radeon 8060S (gfx1151) and Radeon AI Pro R9700S (gfx1201), tested weekly via public GitHub workflows. [1][5]

### Do higher tokens-per-second scores mean better answer quality?

No. PP512 and TG128 measure execution throughput under specific hardware, build, and quantization settings; they do not measure model reasoning accuracy or output quality. [1][4]

## Quotable sentences

- On November 26, 2026, ggml-org launched the llama.cpp x AMD Benchmark dashboard on Hugging Face covering Radeon 8060S (gfx1151) and Radeon AI Pro R9700S (gfx1201). [1][2]
- The AMD benchmark dashboard separates PP512 (processing 512 input tokens with no generation) and TG128 (generating 128 tokens with no prior context), both starting at context depth zero. [1]
- ggml-org runs weekly public benchmark workflows on prebuilt binaries distributed through llama-install.sh, the installation project behind llama.app. [1][5][6]
- llama.cpp is maintained in C and C++ under ggml-org and includes the llama-bench benchmarking utility. [3][4]

## Timeline

- 2026-11-26: ggml-org launches the public llama.cpp x AMD Benchmark dashboard on Hugging Face for AMD Ryzen and Radeon hardware. [1][2]

## Sources

1. Introducing the llama.cpp benchmark dashboard for AMD Ryzen and Radeon hardware. ggml-org (Hugging Face Blog). published 2026-11-26. https://huggingface.co/blog/ggml-org/llamacpp-amd-bench (checked 2026-11-28; tier 2: academic or news)
2. llama.cpp x AMD Performance Explorer. ggml-org (Hugging Face Spaces). https://ggml-org-llamacpp-amd-bench.static.hf.space/index.html (checked 2026-11-28; tier 2: academic or news)
3. ggml-org/llama.cpp: LLM inference in C/C++. GitHub (ggml-org). https://github.com/ggml-org/llama.cpp (checked 2026-11-28; tier 2: academic or news)
4. llama-bench README. ggml-org (GitHub). https://raw.githubusercontent.com/ggml-org/llama.cpp/master/tools/llama-bench/README.md (checked 2026-11-28; tier 2: academic or news)
5. bench-gfx1151.yml Benchmark Workflow. ggml-org (GitHub). https://github.com/ggml-org/llama-install.sh/blob/master/.github/workflows/bench-gfx1151.yml (checked 2026-11-28; tier 2: academic or news)
6. Llama - Your AI, on your computer. ggml-org / Llama. https://llama.app/ (checked 2026-11-28; tier 3: official site)

## Cite this page

Mimirwiki. "llama.cpp." Version 2dac9379, 2026-11-28. https://mimirwiki.com/wiki/llama-cpp
