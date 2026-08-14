---
name: llm-launch-insight
description: Scan a newly launched large language model (LLM) and produce a capability insight ordered by ten dimensions — model fact sheet, benchmarks, inference/deployment, cloud availability and pricing, API/DX, safety/compliance, ecosystem, fine-tuning, real-scenario validation, and independent price/performance cross-check — each with web links to official sources, leaderboards, tools, and communities. Use when the user names a just-released, new, or latest model (for example "洞察这个新模型", "这个刚上市的大模型能力怎么样", "评估/扫描新模型", or any fresh model name plus a request for capability analysis with sources).
---

# LLM Launch Insight

Produce a capability insight for a newly launched model. For each of the ten dimensions in `references/dimensions.md`, output the dimension label followed by web links, in the fixed order given there.

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
