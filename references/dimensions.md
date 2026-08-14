# Ten Insight Dimensions and Canonical Sources

Output in this exact order. Links are canonical entry points; prefer a model-specific page when one is found during the workflow.

## 1. Model fact sheet & architecture (模型本体与技术档案)
Architecture (dense / MoE, total vs active params), context length, modalities, training-data cutoff, license, training stack.
- Hugging Face: https://huggingface.co
- ModelScope (魔搭): https://modelscope.cn
- arXiv technical report: https://arxiv.org
- Papers with Code: https://paperswithcode.com
- Vendor official site / GitHub repository

## 2. Capability benchmarks (能力评测)
Report as model-plus-harness evidence; note contamination and saturation.
- Hugging Face Open LLM Leaderboard: https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard
- LMArena (Chatbot Arena): https://lmarena.ai
- Artificial Analysis: https://artificialanalysis.ai
- OpenCompass (司南): https://opencompass.org.cn
- SWE-bench: https://www.swebench.com
- LiveCodeBench: https://livecodebench.github.io
- Chinese: SuperCLUE https://superclue.ai · C-Eval https://cevalbenchmark.com · FlagEval https://flageval.baai.ac.cn

## 3. Inference & deployment (推理与部署特性)
Memory footprint, quantization, acceleration optimizations, framework support, TTFT/TPOT, throughput, minimum hardware, and local cost assumptions. Check FP8/INT8/INT4 or GPTQ/AWQ, FlashAttention/PagedAttention, fused kernels/CUDA graphs, speculative decoding, continuous batching, prefix/KV-cache reuse, tensor/pipeline parallelism, and CPU/NVMe offload. Report baseline versus optimized settings and any quality regression.
- vLLM: https://docs.vllm.ai
- SGLang: https://sglang.ai
- TensorRT-LLM: https://github.com/NVIDIA/TensorRT-LLM
- llama.cpp: https://github.com/ggml-org/llama.cpp
- Ollama: https://ollama.com
- LMDeploy: https://github.com/InternLM/lmdeploy

## 4. Cloud availability & cost (云上可得性与成本)
Which clouds host it, serverless vs dedicated, regions, per-1M-token input/output pricing, batch discount, and how the cloud option compares with self-hosting. Keep local hardware, power, utilization, amortization, and operations assumptions separate from token pricing.
- AWS Bedrock: https://aws.amazon.com/bedrock/
- Azure AI Foundry: https://azure.microsoft.com/products/ai-foundry
- Google Vertex AI: https://cloud.google.com/vertex-ai
- Alibaba Cloud Bailian (阿里云百炼): https://bailian.console.aliyun.com
- Tencent Cloud Hunyuan / TI (腾讯云混元): https://cloud.tencent.com/product/hunyuan
- Huawei Cloud ModelArts (华为云): https://www.huaweicloud.com/product/modelarts.html
- Baidu Qianfan (百度千帆): https://cloud.baidu.com/product/wenxinworkshop
- Volcano Engine Doubao (火山引擎): https://www.volcengine.com/product/doubao

## 5. API & developer experience (API 与开发者体验)
OpenAI compatibility, function calling, structured output, streaming, batch, rate limits, SDKs.
- Official API documentation (vendor)
- OpenRouter: https://openrouter.ai

## 6. Safety & compliance (安全与合规)
Data residency/training policy, content moderation, alignment and red-teaming, prompt-injection resistance, certifications.
- Model card / responsible AI section (vendor)
- MLCommons AI Safety: https://mlcommons.org/ai-safety/
- NIST AI RMF: https://www.nist.gov/itl/ai-risk-management-framework

## 7. Ecosystem & community (生态与社区)
Downloads, GitHub issues/PRs, framework adaptation speed, real user feedback.
- Hugging Face forums: https://discuss.huggingface.co
- Reddit r/LocalLLaMA: https://www.reddit.com/r/LocalLLaMA/
- Hacker News: https://news.ycombinator.com
- GitHub repository Discussions / Issues
- Chinese: 知乎 (AI topic), 即刻, 微博

## 8. Fine-tuning & customization (微调与定制)
LoRA/SFT/preference alignment support, toolchain maturity, cost and data requirements.
- Axolotl: https://github.com/axolotl-ai-cloud/axolotl
- LLaMA-Factory: https://github.com/hiyouga/LLaMA-Factory
- Unsloth: https://unsloth.ai
- TRL: https://github.com/huggingface/trl
- PEFT: https://github.com/huggingface/peft

## 9. Real-scenario validation (真实业务场景验证)
Run your own harness on RAG/agent/coding/multilingual chains; record badcases, hallucination, latency, cost.
- lm-evaluation-harness: https://github.com/EleutherAI/lm-evaluation-harness
- Stanford HELM: https://crfm.stanford.edu/helm/
- promptfoo: https://promptfoo.dev
- Ragas: https://docs.ragas.io
- DeepEval: https://github.com/confident-ai/deepeval
- LangSmith: https://www.langchain.com/langsmith
- Braintrust: https://www.braintrust.dev
- Weave (W&B): https://weave-docs.wandb.ai

## 10. Independent price/performance cross-check (价格-性能-可用性独立交叉验证)
Cross-check vendor claims against independent measurement, including local acceleration, throughput, latency, and total cost of ownership under matched hardware, precision, context, and concurrency settings.
- Artificial Analysis: https://artificialanalysis.ai
- OpenRouter: https://openrouter.ai
- Together AI: https://www.together.ai
- Fireworks: https://fireworks.ai
- Groq: https://groq.com
- Replicate: https://replicate.com
- MLCommons Inference: https://mlcommons.org/benchmarks/inference/
