<!-- sm80-a100-banner:start -->
> ## ⚠️ You are on the `sm80-a100` branch
>
> This branch adds **DeepSeek-V4.1-Flash support and optimizations for NVIDIA A100
> (SM80)**. It is a community branch maintained on a fork, **not** part of upstream
> SGLang, and it is not intended to be merged into `main`.
>
> 👉 **[Jump to the A100 / SM80 usage guide](#deepseek-v41-flash-on-nvidia-a100-sm80)**
>
> Everything below the guide is the unmodified upstream SGLang README.
<!-- sm80-a100-banner:end -->

# SGLang: Fast inference for LLMs and multimodal models

<p align="center" id="sglangtop">
<img src="https://raw.githubusercontent.com/sgl-project/sglang/main/assets/logo.png" alt="SGLang" width="400">
</p>

<p align="center">
  <a href="https://pypi.org/project/sglang/"><img src="https://img.shields.io/pypi/v/sglang?style=flat&amp;label=PyPI&amp;labelColor=555555&amp;color=orange" alt="PyPI version"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-Apache%202.0-green?style=flat&amp;labelColor=555555" alt="License: Apache 2.0"></a>
  <a href="https://pypistats.org/packages/sglang"><img src="https://img.shields.io/pypi/dm/sglang?style=flat&amp;label=Downloads&amp;labelColor=555555&amp;color=blue" alt="PyPI downloads per month"></a>
</p>

<p align="center">
  <a href="https://docs.sglang.io/">Docs</a> |
  <a href="https://cookbook.sglang.io/">Cookbook</a> |
  <a href="https://www.sglang.io/">Website</a> |
  <a href="https://lmsys.org/blog/">Blog</a> |
  <a href="https://slack.sglang.io/">Slack</a>
</p>

SGLang is an open-source inference framework for large language, vision-language, and diffusion models, optimized for agentic workloads, large-scale serving, and RL rollouts. [SGLang Diffusion](https://docs.sglang.io/docs/sglang-diffusion) is its built-in image and video generation engine, included in this repository and the `sglang` Python package.

👋 Get started below, or meet the community at [SGLang Events](https://www.sglang.io/events), including meetups, developer meetings, workshops, and office hours.

## Get Started

Pull the Docker image, which includes SGLang and its dependencies:

```bash
docker pull lmsysorg/sglang:latest
```

Alternatively, install SGLang in an activated Python environment with uv:

```bash
uv pip install --prerelease=allow sglang
```

Next, launch your model:

- [Quickstart](https://docs.sglang.io/docs/get-started/quickstart): Run your first model and send a request.
- [Cookbook](https://cookbook.sglang.io/): Choose your model and hardware to get a ready-to-run launch command.

## Supported Hardware

SGLang supports a wide range of GPUs, TPUs, NPUs, CPUs, and Apple Silicon platforms.

| Platform | Representative hardware |
| --- | --- |
| [NVIDIA](https://docs.sglang.io/docs/hardware-platforms/nvidia-gpus) | B200/B300/GB200/GB300; H100/H200/H800/H20; A100; RTX 30/40/50 series, RTX 6000 Ada / PRO 6000; DGX Spark, Jetson Orin |
| [AMD](https://docs.sglang.io/docs/hardware-platforms/amd_gpu) | Instinct MI300X, MI325X, MI350X, MI355X |
| [Google TPU](https://docs.sglang.io/docs/hardware-platforms/tpu) | v6e, v7; [SGL-JAX](https://github.com/sgl-project/sglang-jax) / [SGL-torchtpu](https://lmsys.org/blog/2026-07-30-sglang-google-tpu/) |
| Intel ([GPU](https://docs.sglang.io/docs/hardware-platforms/xpu) / [CPU](https://docs.sglang.io/docs/hardware-platforms/cpu_server)) | Arc / Arc Pro B-Series GPUs, Xeon CPUs |
| [Apple Silicon](https://docs.sglang.io/docs/hardware-platforms/apple_metal) | Macs via Metal / MLX |
| [Huawei Ascend](https://docs.sglang.io/docs/hardware-platforms/ascend-npus/getting-started/installation) | A2, A3, 950PR/DT NPUs |
| [Moore Threads](https://docs.sglang.io/docs/hardware-platforms/mthreads_gpu) | MTT S5000 GPUs |

Integrations in progress: AWS Trainium, [Alibaba T-Head PPU](https://github.com/sgl-project/sglang/issues/37519), [Cambricon MLU](https://github.com/sgl-project/sglang/pull/26898), Qualcomm QAIC, MetaX, Hygon HCU/DCU, Iluvatar CoreX, and more.

See the [Cookbook](https://cookbook.sglang.io/) and platform guides for model compatibility and setup.

## SGL Ecosystem

| Area | Projects | Purpose |
| --- | --- | --- |
| Diffusion | [SGLang Diffusion](https://docs.sglang.io/docs/sglang-diffusion/installation) | Built into SGLang for image and video generation with diffusion models. |
| Audio | [SGLang Omni](https://github.com/sgl-project/sglang-omni) | Audio model serving for text-to-speech (TTS) and automatic speech recognition (ASR). |
| Speculative Decoding | [SpecForge](https://github.com/sgl-project/SpecForge) | Train draft models for speculative decoding and deploy them with SGLang. |
| RL and Post-Training | [Miles](https://github.com/radixark/miles), [slime](https://github.com/THUDM/slime), [AReaL](https://github.com/inclusionAI/AReaL), [Tunix](https://github.com/google/tunix), [verl](https://github.com/volcengine/verl) | Training frameworks that integrate SGLang for rollout generation. |
| Deployment and Orchestration | [SMG](https://github.com/smg-project/smg), [RBG](https://github.com/sgl-project/rbg), [llm-d](https://llm-d.ai/docs/dev/operations/disaggregation/sglang), [Ray Serve](https://docs.ray.io/en/latest/serve/llm/user-guides/sglang.html), [NVIDIA Dynamo](https://docs.nvidia.com/dynamo/backends/sg-lang/reference-guide) | Deploy and scale SGLang inference services with routing, load balancing, and cluster orchestration. |
| Education | [Mini-SGLang](https://github.com/sgl-project/mini-sglang), [zero-to-sglang](https://github.com/datawhalechina/zero-to-sglang), [DeepLearning.AI course](https://www.deeplearning.ai/short-courses/efficient-inference-with-sglang-text-and-image-generation/) | Learn inference engine design and efficient text and image generation through code and hands-on courses. |

## Development and Contributing

Contributions are welcome, from bug fixes and documentation to model support and performance improvements.

### Development setup

Start from the `lmsysorg/sglang:dev` Docker image, which provides development tools and most dependencies. Clone or mount your SGLang checkout inside the container, then install it in editable mode from the repository root so tests use your local Python changes:

```bash
pip install -e "python"
```

In an activated virtual environment, you can use `uv pip install --prerelease=allow -e "python"` instead. See the [development guide](https://docs.sglang.io/docs/developer_guide/development_guide_using_docker) for container setup and testing.

### Contribute

1. Fork the repository and create a branch for your changes. For larger changes, discuss your proposal in a [GitHub issue](https://github.com/sgl-project/sglang/issues) or on [Slack](https://slack.sglang.io/).
2. Make your changes, run the relevant tests, and add regression coverage for fixes or new behavior. Run `pre-commit run --all-files` before submitting.
3. Open a pull request describing the change and how you tested it. Include benchmarks or accuracy evaluations when relevant.

See the [contributor guide](https://docs.sglang.io/docs/developer_guide/contribution_guide) for formatting, testing, and pull request instructions. Documentation contributors can start with the [docs guide](docs/README.md).

## Community and Sponsorship

SGLang is hosted by [LMSYS](https://lmsys.org/about/), a non-profit open-source organization.

- **Community discussions:** Join [Slack](https://slack.sglang.io/) for technical questions and development discussions.
- **Events:** Find meetups, workshops, and office hours on [SGLang Events](https://www.sglang.io/events).
- **Updates:** Follow [X](https://x.com/lmsysorg) and [LinkedIn](https://www.linkedin.com/company/sgl-project/) for project updates, and the [LMSYS Blog](https://lmsys.org/blog/) for release announcements and technical articles.
- **Project resources:** Explore the [documentation](https://docs.sglang.io/), [Cookbook](https://cookbook.sglang.io/), [roadmap](https://roadmap.sglang.io/), [release notes](https://github.com/sgl-project/sglang/releases), [issue tracker](https://github.com/sgl-project/sglang/issues), and [contributor guide](https://docs.sglang.io/docs/developer_guide/contribution_guide).
- **Contact Us:** For enterprise adoption and deployment, technical consulting, sponsorship, or partnership inquiries, please contact [sglang@lmsys.org](mailto:sglang@lmsys.org).
- **Contributor sponsorship:** Long-term active SGLang contributors are eligible for coding agent sponsorship, including Cursor, Claude Code, or OpenAI Codex. To apply, email [sglang@lmsys.org](mailto:sglang@lmsys.org) with links to your key commits or pull requests.

## Trusted by Industry and Research

SGLang serves production workloads across AI labs, cloud platforms, enterprises, and universities.

<img src="https://raw.githubusercontent.com/sgl-project/sgl-learning-materials/refs/heads/main/slides/adoption.png" alt="Organizations adopting SGLang" width="800">

## Acknowledgment
We learned the design and reused code from the following projects: [Guidance](https://github.com/guidance-ai/guidance), [vLLM](https://github.com/vllm-project/vllm), [LightLLM](https://github.com/ModelTC/lightllm), [FlashInfer](https://github.com/flashinfer-ai/flashinfer), [Outlines](https://github.com/outlines-dev/outlines), and [LMQL](https://github.com/eth-sri/lmql).

---

<a id="deepseek-v41-flash-on-nvidia-a100-sm80"></a>

# DeepSeek-V4.1-Flash on NVIDIA A100 (SM80)

This branch makes **DeepSeek-V4.1-Flash** serve correctly and quickly on
**8 × A100-SXM4-80GB** (compute capability **exactly `(8, 0)`**), which upstream
SGLang does not support out of the box.

Every optimization here is **opt-in and off by default**. With no environment
variables set, this branch behaves like upstream SGLang. Nothing outside the
SM80 path is affected.

> **Branch status.** Community fork branch, not upstream. It is not intended to
> be merged into `main`. Pin the commit you deploy — see [Reproducibility](#reproducibility).

---

## 1. Requirements

| Item | Requirement |
|---|---|
| GPU | 8 × NVIDIA A100-SXM4-80GB |
| Compute capability | **exactly `(8, 0)`** on every visible device |
| Python | ≥ 3.11 |
| CUDA | CUDA build of PyTorch with `torch.version.hip is None` |
| Platform | Linux (the template uses `numactl`, optional) |

The launcher performs an explicit capability check and refuses to start on
anything else. It is not a soft warning: `(8, 6)`, `(8, 9)`, `(9, 0)`, and
`(10, 0)` devices are all rejected.

**There is no AOT kernel build step.** The SM80 kernels are TileLang JIT
kernels, compiled on first use. This means:

- `pip install -e python/` is enough — no extra `sgl-kernel` build required
- the **first launch is slow** (allow roughly 9–10 minutes: weight load plus
  CUDA graph capture), because TileLang compiles each kernel shape on demand
- keep the resulting JIT cache warm across restarts if you can

## 2. Installation

```bash
git clone -b sm80-a100 https://github.com/Ruijie-Ysp/sglang.git
cd sglang
pip install -e python/
```

Verify the runtime sees the expected hardware:

```bash
python3 - <<'PY'
import torch
assert torch.version.hip is None, "this branch needs the CUDA build of PyTorch"
assert torch.cuda.device_count() == 8, "expected exactly 8 visible GPUs"
assert all(torch.cuda.get_device_capability(i) == (8, 0) for i in range(8)), \
    "every visible GPU must be compute capability (8, 0)"
print("OK: 8 x A100 (SM80)")
PY
```

## 3. Quick start

Set `MODEL_PATH` to your **original DeepSeek-V4.1-Flash checkpoint directory**
(the unquantized release checkpoint — the FP8/MXFP4 handling lives in this
branch, do not pre-convert it).

```bash
export MODEL_PATH=/path/to/deepseek-v4.1-flash

# Required: turns the SM80 path on at all.
export SGLANG_DSV41_SM80_EXPERIMENTAL=1

python -m sglang.launch_server \
  --model-path "$MODEL_PATH" \
  --host 127.0.0.1 --port 31080 \
  --device cuda --language-model-only \
  --attention-backend dsv4 \
  --dsv4-attn-backend flashmla \
  --dsv4-prefill-backend flashmla_sparse \
  --kv-cache-dtype fp8_e4m3 \
  --tp-size 8 --max-running-requests 1 \
  --context-length 65536 --max-total-tokens 66048 \
  --chunked-prefill-size 256 \
  --mem-fraction-static 0.95 \
  --moe-runner-backend marlin \
  --dtype bfloat16 --trust-remote-code
```

Then:

```bash
curl -s -o /dev/null -w '%{http_code}\n' http://127.0.0.1:31080/health   # -> 200
curl -s http://127.0.0.1:31080/v1/models                                  # -> list of models
```

A minimal smoke test:

```bash
curl -s http://127.0.0.1:31080/v1/chat/completions \
  -H 'Content-Type: application/json' \
  -d '{"model":"'"$MODEL_PATH"'","messages":[{"role":"user","content":"17*19=?"}],"max_tokens":32}'
```

## 4. Recommended configurations

Two configurations are validated in production. Both are 1M-capable; the
difference is concurrency.

### 4.1 Single-request (lowest latency, most optimizations)

Use `--max-running-requests 1` with a batch-1 CUDA graph. This is the fastest
path for one request at a time and enables the full set of tuning switches:

```bash
export SGLANG_DSV41_SM80_EXPERIMENTAL=1
export SGLANG_DSV41_SM80_FULL_GRAPH=1
export SGLANG_DSV41_SM80_GRAPH_VARIANTS=1
export SGLANG_DSV41_SM80_MARLIN_N64=1
export SGLANG_DSV41_SM80_DENSE_TILE=n64
export SGLANG_DSV41_SM80_MHC_FUSED_STATS=1
export SGLANG_DSV41_SM80_MHC_SIMT_STATS=1
export SGLANG_DSV41_SM80_MHC_COMBINE_NORM=1
export SGLANG_DSV41_SM80_MHC_POST_SPLIT_H=1
export SGLANG_DSV41_SM80_MHC_REDUCE_TILE=1
export SGLANG_DSV41_SM80_INDEXER_FINISH=1
export SGLANG_DSV41_SM80_MERGE_DTILE=1
export SGLANG_DSV41_SM80_PARTIAL_SIDE_STREAM=1
export SGLANG_DSV41_SM80_PARTIAL_WORD_LOADS=1
export SGLANG_DSV4_KV_LAYOUT=v41
export SGLANG_AUTO_NUMA_BIND=0
```

Launch flags:

```
--cuda-graph-config '{"decode":{"backend":"full","bs":[1],"max_bs":1},"prefill":{"backend":"disabled"}}'
--tp-size 8 --max-running-requests 1
--context-length 65536    # use 1000000 for the 1M configuration
--max-total-tokens 66048  # use 1000512 for the 1M configuration
--chunked-prefill-size 256   # use 1024 for the 1M configuration
```

### 4.2 Concurrent (up to 8 requests)

Concurrency needs two extra switches. Without them, batches of 2–8 fall back to
the serial sparse-attention kernel, and CUDA graphs must be disabled entirely
(see [§7](#7-how-the-concurrency-fix-works) for why):

```bash
export SGLANG_DSV41_SM80_FULL_GRAPH_MULTI_BS=1
export SGLANG_DSV41_SM80_TILED_MULTIROW_MAX_TOKENS=32
```

Launch flags (note the widened graph batch list and request cap):

```
--cuda-graph-config '{"decode":{"backend":"full","bs":[1,2,4,8],"max_bs":8},"prefill":{"backend":"disabled"}}'
--tp-size 8 --max-running-requests 8
--context-length 1000000 --max-total-tokens 1000512 --chunked-prefill-size 1024
```

Optional, for multimodal and reasoning behaviour:

```bash
export SGLANG_DSV41_SM80_ALLOW_VISION=1   # relaxes the SM80 multimodal fence
export SGLANG_DSV41_REASONING_EFFORT=high
```

`SGLANG_DSV41_SM80_ALLOW_VISION=1` was verified against a rendered test image
(427 image tokens, exact text read back).

## 5. Measured performance

8 × A100-SXM4-80GB, TP8, 1M configuration, 256 output tokens, cold prefix.
These are **steady-state decode** measurements, not end-to-end throughput.

| Workload | Result |
|---|---|
| Single request | ~125 tokens/s |
| 8-way aggregate | ~535 tokens/s |
| 16-way aggregate | ~699 tokens/s |

Historically, on the same deployment, 8-way aggregate went from 118 to 535
tokens/s once the two concurrency gates were fixed. Batch correctness was
verified 8/8 and 16/16 with a unique secret per request — no cross-talk, exact
token counts.

Long-context single-request decode (equal-condition, 64K capacity, three cold
trials per length, exactly 256 output tokens, 15/15 marker retrievals passed):

| Input tokens | Median decode |
|---|---|
| 64 | 126.78 tokens/s |
| 4K | 111.52 tokens/s |
| 16K | 104.97 tokens/s |
| 32K | 104.59 tokens/s |
| 65K | 103.54 tokens/s |

Roughly **+23%** over the earlier same-capacity baseline.

> **A note on the 200 tokens/s goal:** it was **not reached**. Treat ~105–127
> tokens/s as the realistic single-request range. Do not plan capacity around a
> 200 tokens/s figure.

## 6. Environment variables

Legend: **R** = required for the SM80 path · **T** = tuning (validated, safe to
enable) · **N** = measured neutral or negative — **leave it off**.

| Variable | Default | Class | Effect |
|---|---|---|---|
| `SGLANG_DSV41_SM80_EXPERIMENTAL` | `0` | **R** | Master gate. Nothing else activates without it. |
| `SGLANG_DSV41_SM80_FULL_GRAPH` | unset | T | Batch-1 full decode CUDA graph. |
| `SGLANG_DSV41_SM80_FULL_GRAPH_MULTI_BS` | unset | T | Lets the graph capture a `bs` list > 1. Needed for concurrency. |
| `SGLANG_DSV41_SM80_GRAPH_VARIANTS` | unset | T | CPU-length-selected indexer graph variants. |
| `SGLANG_DSV41_SM80_MARLIN_N64` | unset | T | Narrow-N Marlin MoE tile. Read via `getenv` in the CUDA source, **not** declared in `environ.py`. |
| `SGLANG_DSV41_SM80_DENSE_TILE` | unset | T | Dense-shape tile override (e.g. `n64`). |
| `SGLANG_DSV41_SM80_MHC_FUSED_STATS` | unset | T | Fuse the mHC stats reduction. |
| `SGLANG_DSV41_SM80_MHC_SIMT_STATS` | unset | T | SIMT mHC stats path. |
| `SGLANG_DSV41_SM80_MHC_COMBINE_NORM` | unset | T | Fuse mHC combine + norm. |
| `SGLANG_DSV41_SM80_MHC_POST_SPLIT_H` | unset | T | Split-H post-mix; used for narrow-batch decode. |
| `SGLANG_DSV41_SM80_MHC_REDUCE_TILE` | unset | T | Tile the mHC reduce+sinkhorn kernel. |
| `SGLANG_DSV41_SM80_INDEXER_FINISH` | unset | T | SM80 indexer finish path. |
| `SGLANG_DSV41_SM80_MERGE_DTILE` | unset | T | Tile the sparse-attention merge over the output axis. |
| `SGLANG_DSV41_SM80_PARTIAL_SIDE_STREAM` | unset | T | Overlap the two sparse-attention pool launches. |
| `SGLANG_DSV41_SM80_PARTIAL_WORD_LOADS` | unset | T | Load partial-kernel KV bytes as words. |
| `SGLANG_DSV41_SM80_TILED_MULTIROW_MAX_TOKENS` | unset | T | Token threshold for routing 2..N-row decode to tiled split-K attention. `32` is the validated value. |
| `SGLANG_DSV41_SM80_ALLOW_VISION` | unset | T | Relax the SM80 multimodal fence. Verified with a 427-token image. |
| `SGLANG_DSV41_SM80_FFN_GRAPH` | unset | **N** | FFN segment graph. Measured not to pay off. |
| `SGLANG_DSV41_SM80_M1_GEMV` | unset | **N** | Dense M1 FP8 GEMV fast path. |
| `SGLANG_DSV41_SM80_LOW_RATIO_MULTISTREAM` | unset | **N** | Extended multi-stream prepare. Measured neutral. |
| `SGLANG_DSV41_SM80_DENSE_TILE_SMALL` | unset | N | Rejected alternative; leave unset. |
| `SGLANG_DSV41_SM80_MOE_DOWN_BLOCKS` | unset | N | Rejected alternative; leave unset. |

`_use_tiled_decode` treats **unset, malformed, and non-positive** values of
`TILED_MULTIROW_MAX_TOKENS` as "serial", so a typo degrades safely rather than
routing every batch to the wrong kernel.

Two non-SM80 variables are also relevant:

| Variable | Value | Why |
|---|---|---|
| `SGLANG_DSV4_KV_LAYOUT` | `v41` | The SM80 adapter reads only V4.1 packed layouts. |
| `SGLANG_AUTO_NUMA_BIND` | `0` | Leave NUMA binding to the operator. |

## 7. How the concurrency fix works

Two independent `bs=1`-only gates made concurrency slow. Both are addressed:

1. **`flash_mla_sm80.py`** routed tiled split-K attention only when
   `tokens == 1`. But during decode `tokens` is the *running batch size*, so
   batches of 2..8 fell back to the serial sparse-attention kernel — that
   fallback was 15.5 ms/step at `bs=8`, i.e. 82% of the whole `bs=8` step-time
   increase over `bs=1`.

   The gate exists to keep multi-token **prefill** on the serial kernel, and
   that is preserved: only decode-sized counts up to
   `SGLANG_DSV41_SM80_TILED_MULTIROW_MAX_TOKENS` opt in.

2. **`deepseek_v4_hook.py`** required `max_running_requests=1` and decode
   `bs=[1]`/`max_bs=1` for the full-graph experiment, so concurrency meant
   disabling CUDA graphs entirely. The graph runner already accepted a `bs`
   list, so the batch pin is now bypassable with
   `SGLANG_DSV41_SM80_FULL_GRAPH_MULTI_BS=1`. **Every other activation guard
   still runs.**

## 8. Reproducibility

This branch is a **moving target** in the sense that its base tracks upstream
`main`. For a reproducible deployment, pin the exact commit:

```bash
git clone https://github.com/Ruijie-Ysp/sglang.git
cd sglang
git checkout <commit-sha>
pip install -e python/
```

Record the commit SHA alongside your server configuration. Upstream `main`
moves quickly; a floating branch can pick up unrelated upstream changes
between deployments.

## 9. Scope, limitations, and honest caveats

Read this before making claims about this branch.

**What is verified**

- The deployment was live-checked: `/health` and `/v1/models` returned HTTP 200
  with a 1,000,000-token limit, and a minimal chat request returned `323` for
  `17 × 19` (HTTP 200, normal stop, ~0.212 s).
- 46 CPU AST/policy tests pass; syntax and whitespace checks pass.
- Registered test suites cover the routing helper and both concurrency gates at
  their boundaries.

**What is NOT verified — do not overstate**

- **The deployed container's exact revision cannot be proven.** Its disk-source
  hashes do not fully match the submitted revision (two match a previous local
  baseline, two match neither compared revision), and the production container
  has no Git. This verifies the *deployment's availability*, not full GPU
  certification of every change in the source tree.
- **SM80 GPU numerical and graph tests for the exact submitted revision** are
  still outstanding.
- **The mHC multi-row extension is not numerically validated** and is **not part
  of this branch** as a supported feature.
- There is a known strict **mHC T=2049 / no-norm precision boundary**. Do not
  broaden validation claims or relax thresholds to hide it.
- Multi-concurrency is verified for the **8-way and 16-way** batches above.
  Higher concurrency, other topologies, and comprehensive model-quality
  certification are **not** claimed.

**Shared-code caveat (matters for review, not for SM80 users)**

Two changes touch files shared with other architectures:

- `python/sglang/kernels/jit/csrc/gemm/marlin/gptq_marlin.cuh` adds
  `GROUP32_GET_IF_*` macro instantiations for FP8 block-32 (`group_blocks=2`).
  These are **compile-time and not arch-guarded**, so they affect the kernel
  instantiation set on other architectures too.
- `moe_wna16_marlin.cuh` adds narrow-N tile instantiations; this part **is**
  guarded by `#if SGL_CUDA_ARCH == 800`.

If you only care about A100, you can ignore this. If you are reviewing for
upstream, these two files need cross-architecture review.

## 10. Troubleshooting

| Symptom | Cause / fix |
|---|---|
| Launcher exits: *"requires exactly eight visible NVIDIA A100 GPUs"* | The template enforces 8 GPUs. Set `CUDA_VISIBLE_DEVICES` to exactly 8 A100s, or adapt the template. |
| Launcher exits: *"Every visible GPU must have exact CUDA capability (8, 0)"* | A non-A100 device is visible. This branch targets SM80 only. |
| Server starts but is slow / no speedup | `SGLANG_DSV41_SM80_EXPERIMENTAL=1` is missing, or the tuning switches were dropped. Verify the environment **inside** the server process — in containers, `-e` flags are easy to lose. |
| Concurrency falls off a cliff at `bs=2` | `FULL_GRAPH_MULTI_BS=1` and `TILED_MULTIROW_MAX_TOKENS` are not both set. See [§7](#7-how-the-concurrency-fix-works). |
| First startup takes ~10 minutes | Expected. TileLang JIT compilation plus CUDA graph capture. Keep the JIT cache. |
| Different outputs across restarts with graphs enabled | Report it — that is a correctness issue, not a tuning issue. |

## 11. Tests

CPU-only, no GPU or checkpoint required:

```bash
python -m pytest test/registered/unit/test_dsv41_sm80_runtime.py
python -m pytest test/registered/unit/test_dsv41_sm80_graph_variants.py
python -m pytest test/registered/unit/server_args/test_deepseek_v41_sm80_experimental.py
```

The GPU-dependent tests under `test/registered/kernels/` require actual SM80
hardware; upstream CI has no A100 runner, so **skipped H100 tests are not SM80
coverage**.

## 12. Getting help

Please include, at minimum:

- the commit SHA you are on
- the full environment variable list **as seen by the server process**
- the complete launch command
- GPU model and count, driver version, CUDA version, Python version
- the `/health` and `/v1/models` responses

## 13. AI-assisted development disclosure

Core code development was completed with assistance from **GPT-6.1** and
**DeepSeek-V4.1-Flash**. The human contributor supplied reference material,
optimization suggestions, and real-server deployment validation. This disclosure
describes the development process — it is **not** proof of numerical
correctness.

## License

Unchanged from upstream SGLang: Apache 2.0. See [LICENSE](LICENSE).
