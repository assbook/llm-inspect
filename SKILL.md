---
name: llm-launch-insight
description: Scan a newly launched large language model (LLM) and produce a capability insight ordered by ten dimensions — model fact sheet, benchmarks, inference/deployment, cloud availability and pricing, API/DX, safety/compliance, ecosystem, fine-tuning, real-scenario validation, and independent price/performance cross-check — each with web links to official sources, leaderboards, tools, and communities. Use when the user names a just-released, new, or latest model (for example "洞察这个新模型", "这个刚上市的大模型能力怎么样", "评估/扫描新模型", or any fresh model name plus a request for capability analysis with sources).
---

# LLM Launch Insight

Produce a capability insight for a newly launched model. For each of the ten dimensions in `references/dimensions.md`, output the dimension label followed by web links, in the fixed order given there.

For any self-hosted or local-deployment claim, treat acceleration and cost as one coupled question: name the optimization, show the before/after measurement or label it as unverified, and expose the assumptions behind the estimate.

## Workflow

1. Pin down the exact model identifier (vendor + version + release tag). Disambiguate release dates and forks before searching; never substitute a similar-looking model name.
2. Search for official primary sources first: model card, launch blog, technical report, and weights page. Prefer Hugging Face, ModelScope, arXiv, and the vendor's own site or GitHub.
3. Read `references/dimensions.md` to load the ten dimensions and their canonical source URLs.
4. For each dimension in order, emit the dimension number + name, then the model-specific links found in step 2 and the canonical sources, each with a short caveat (official vs third-party, harness + sampling setup, region/account needed).
5. End with a "verify before committing" note marking live/volatile items (leaderboard rank, price, region availability) versus stable items (framework docs, tool URLs).

## Output format

- Use the exact ten-dimension order from `references/dimensions.md`.
- Use Markdown links for every URL.
- One compact line or short list per dimension; do not dump unrelated generic content.

## Rules

- Report benchmark numbers as model-plus-harness evidence: name the eval framework, sampling settings, and contamination caveats; never present a bare score as intrinsic ability.
- Separate vendor claims from independent measurement; cross-check price, throughput, and latency with Artificial Analysis, OpenRouter, or your own run rather than trusting a launch blog.
- Label each link official vs third-party. Never fabricate a model-specific URL; if a per-model page is not found, link the canonical entry point and state that the per-model page still needs the user's account or region.
- Before recommending any cloud deployment, verify account, region, GPU/model/API availability, data residency, compliance, and live pricing.
- If a dimension has no model-specific information yet, say so explicitly instead of filling it with generic defaults.

## Local deployment and acceleration contract

- In dimension 3, inventory applicable acceleration techniques instead of treating quantization as the only optimization: FP8/INT8/INT4 or GPTQ/AWQ quantization, FlashAttention/PagedAttention, fused kernels and CUDA graphs, speculative decoding, continuous batching/prefix or KV-cache reuse, tensor/pipeline parallelism, and CPU/NVMe offload. Mark each as vendor-supported, framework-supported, independently measured, or unverified for the exact model.
- Report a reproducible baseline and optimized configuration when performance or cost is claimed: model revision, precision/quantization, framework and version, GPU(s), tensor/pipeline parallel degree, context length, input/output token lengths, concurrency or batch size, and sampling settings. Include quality/regression checks for quantization or decoding changes.
- Separate one-time and running local costs. State hardware purchase or rental price, amortization period and utilization, electricity draw, local electricity rate, storage/network/operations overhead, and currency/date. A useful estimate is `hourly_total = hardware_hourly + (watts / 1000 * electricity_rate) + other_hourly`; show sensitivity when an input is unknown rather than inventing a value.
- In dimension 10, cross-check local cost and throughput against an independent benchmark or a documented own run. Keep vendor claims separate from measured values and do not compare optimized local results with an unoptimized cloud result without calling out the configuration mismatch.
