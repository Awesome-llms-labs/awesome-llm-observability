# Awesome LLM Observability [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated directory of **LLM observability and eval-ops**: tracing/monitoring platforms, evaluation harnesses and eval-ops tooling, guardrails and safety monitoring, gateways with cost tracking, prompt management for production, and the benchmarks that keep everyone honest — as of **September 2026**.

Standard APM sees HTTP 200; it can't see a hallucination. This list covers the tooling that closes that gap: per-request traces with token costs, offline eval gates, runtime guardrails, and the gateway layer that meters it all.

**Verification confidence:** every link below was checked live on ✅ **2026-09-30** (official site or repo resolves). **Specs and prices are never guessed** — this list links tools, it doesn't quote their marketing. Machine-readable records live in [`data/llm-observability.json`](data/llm-observability.json) with a `verified` boolean per entry.

## Contents
- [Tracing & Observability Platforms](#tracing--observability-platforms)
- [Evaluation Harnesses & Eval-Ops](#evaluation-harnesses--eval-ops)
- [Guardrails & Safety Monitoring](#guardrails--safety-monitoring)
- [Gateways, Cost Tracking & Prompt Management](#gateways-cost-tracking--prompt-management)
- [Benchmarks & Datasets](#benchmarks--datasets)
- [Status notes](#status-notes)
- [Guides](#guides)
- [Related](#related)
- [Contributing](#contributing)
- [License](#license)

---

## Tracing & Observability Platforms

*The production eyes: per-request traces with prompts, tokens, cost, latency, and tool calls.*

- [Langfuse](https://langfuse.com) — Open-source LLM engineering platform: tracing, prompt management, evaluations, and datasets; self-hostable. `✅ verified 2026-09-30`
- [LangSmith](https://www.langchain.com/langsmith) — LangChain's platform for tracing, debugging, and evaluating LLM and agent applications. `✅ verified 2026-09-30`
- [Helicone](https://helicone.ai) — Proxy-based LLM observability: drop-in request logging, cost tracking, caching, and rate limits. `✅ verified 2026-09-30`
- [Braintrust](https://www.braintrust.dev) — Evaluation-first platform tying production traces to datasets and prompt experiments. `✅ verified 2026-09-30`
- [Arize Phoenix](https://github.com/Arize-AI/phoenix) — Open-source, OpenTelemetry-native tracing and evaluation for LLM apps; self-hostable. `✅ verified 2026-09-30`
- [Arize AX](https://arize.com) — Arize's commercial platform for LLM tracing, evaluation, and drift monitoring in production. `✅ verified 2026-09-30`
- [W&B Weave](https://wandb.ai) — Weights & Biases' toolkit for tracing, evaluating, and iterating on LLM applications. `✅ verified 2026-09-30`
- [MLflow](https://mlflow.org) — Open-source ML platform with GenAI tracing, prompt tracking, and LLM-as-judge evaluation. `✅ verified 2026-09-30`
- [Datadog LLM Observability](https://www.datadoghq.com/product/llm-observability/) — LLM traces correlated with Datadog APM infrastructure monitoring and incident workflows. `✅ verified 2026-09-30`
- [New Relic AI Monitoring](https://newrelic.com/platform/ai-monitoring) — AI response monitoring integrated into New Relic's APM agent and dashboards. `✅ verified 2026-09-30`
- [Honeycomb](https://www.honeycomb.io) — Observability platform with OpenTelemetry-based LLM instrumentation and trace analysis. `✅ verified 2026-09-30`
- [OpenLLMetry](https://www.traceloop.com/openllmetry) — Traceloop's open-source OpenTelemetry extensions and SDKs for LLM observability. `✅ verified 2026-09-30`
- [OpenLIT](https://github.com/openlit/openlit) — Open-source, OpenTelemetry-native LLM observability SDK with GPU monitoring. `✅ verified 2026-09-30`
- [Opik](https://github.com/comet-ml/opik) — Comet's open-source platform for LLM evaluation, tracing, and monitoring. `✅ verified 2026-09-30`
- [Literal AI](https://github.com/Chainlit/literalai-python) — Observability and evaluation SDK/platform from the Chainlit team. `✅ verified 2026-09-30`
- [AgentOps](https://github.com/AgentOps-AI/agentops) — Agent monitoring with session replays plus cost and latency tracking across frameworks. `✅ verified 2026-09-30`
- [Pydantic Logfire](https://github.com/pydantic/logfire) — OpenTelemetry-based observability for LLM and agent apps from the Pydantic team. `✅ verified 2026-09-30`
- [OpenTelemetry GenAI Semantic Conventions](https://github.com/open-telemetry/semantic-conventions-genai) — The (still experimental) standard attribute names for GenAI spans: gen_ai.* conventions. `✅ verified 2026-09-30`

## Evaluation Harnesses & Eval-Ops

*Offline quality gates: harnesses, metrics libraries, and managed eval platforms that stop regressions before they ship.*

- [Promptfoo](https://promptfoo.dev) — CLI-first open-source tool for testing prompts and models side by side; red-teaming built in. `✅ verified 2026-09-30`
- [DeepEval](https://www.deepeval.com) — Pytest-style Python framework with LLM-evaluated metrics for RAG pipelines and agents. `✅ verified 2026-09-30`
- [Ragas](https://www.ragas.io) — RAG-focused evaluation metrics (faithfulness, context precision/recall); standard reference for RAG scoring. `✅ verified 2026-09-30` — ⚠️ **status: maintenance** (see notes)
- [Inspect AI](https://github.com/UKGovernmentBEIS/inspect_ai) — UK AISI's framework for large-scale model and agentic evaluations with sandboxing. `✅ verified 2026-09-30`
- [lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness) — The harness for reproducing academic benchmark numbers across hundreds of tasks; HF leaderboard backend. `✅ verified 2026-09-30`
- [HELM](https://github.com/stanford-crfm/helm) — Stanford's holistic, multi-metric evaluation across many scenarios. `✅ verified 2026-09-30`
- [OpenCompass](https://github.com/open-compass/opencompass) — Open-source model benchmarking platform with strong multilingual coverage. `✅ verified 2026-09-30`
- [LightEval](https://github.com/huggingface/lighteval) — Hugging Face's lightweight evaluation library wired into the HF Hub. `✅ verified 2026-09-30`
- [TruLens](https://www.trulens.org) — Systematic tracking and evaluation of LLM app quality, from prototype to production. `✅ verified 2026-09-30`
- [Giskard](https://www.giskard.ai) — Open-source testing framework for ML/LLM models: robustness, bias, and hallucination scans. `✅ verified 2026-09-30`
- [Evidently AI](https://www.evidentlyai.com) — Open-source ML monitoring with LLM-specific evaluations and drift reports. `✅ verified 2026-09-30`
- [Confident AI](https://www.confident-ai.com) — Managed evaluation platform behind DeepEval: datasets, experiments, and regression tracking. `✅ verified 2026-09-30`
- [Cleanlab](https://cleanlab.ai) — Data-centric AI tools including Trustworthy Language Model (TLM) hallucination detection. `✅ verified 2026-09-30`
- [Kolena](https://www.kolena.com) — Testing and validation platform for ML models with LLM evaluation workflows. `✅ verified 2026-09-30`
- [openai/evals](https://github.com/openai/evals) — OpenAI's eval registry format and framework; a community reference implementation. `✅ verified 2026-09-30` — ⚠️ **status: maintenance** (see notes)
- [OpenAI simple-evals](https://github.com/openai/simple-evals) — Transparent reference implementations of common evals (MMLU, MATH, GPQA) to read and copy. `✅ verified 2026-09-30`
- [PromptBench](https://github.com/microsoft/promptbench) — Toolkit for stress-testing prompt robustness and adversarial perturbations. `✅ verified 2026-09-30`
- [MTEB](https://github.com/embeddings-benchmark/mteb) — Massive Text Embedding Benchmark: the standard suite for evaluating embedding models. `✅ verified 2026-09-30`
- [Maxim AI](https://www.getmaxim.ai) — End-to-end platform for prompt management, simulation testing, and production monitoring. `✅ verified 2026-09-30`
- [Galileo](https://www.galileo.ai) — Evaluation intelligence platform for GenAI teams: guardrails, evals, and observability. `✅ verified 2026-09-30`
- [Patronus AI](https://www.patronus.ai) — Enterprise evaluation and monitoring for LLMs, aimed at regulated industries. `✅ verified 2026-09-30`
- [Humanloop](https://humanloop.com) — Prompt management and evaluation platform for iterating on prompts with whole teams. `✅ verified 2026-09-30`
- [Vellum](https://www.vellum.ai) — Development platform for building, testing, and deploying AI workflows and agents. `✅ verified 2026-09-30`
- [UpTrain](https://github.com/upTrain-ai/uptrain) — Open-source framework for evaluating and monitoring LLM applications. `✅ verified 2026-09-30`
- [HoneyHive](https://honeyhive.ai) — Evaluation and observability platform for LLM apps, from experimentation to production. `✅ verified 2026-09-30`

## Guardrails & Safety Monitoring

*Runtime protection: input/output filtering, prompt-injection detection, and content-safety classifiers.*

- [NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) — Open-source toolkit for programmable guardrails in conversational AI, defined in Colang. `✅ verified 2026-09-30`
- [Guardrails AI](https://github.com/guardrails-ai/guardrails) — Framework adding structural, type, and quality guarantees to LLM outputs; Guardrails Hub validators. `✅ verified 2026-09-30`
- [Llama Guard](https://github.com/meta-llama/PurpleLlama) — Meta's safety classifier models for filtering unsafe LLM inputs and outputs (PurpleLlama suite). `✅ verified 2026-09-30`
- [LLM Guard](https://github.com/protectai/llm-guard) — Open-source input/output scanners: toxicity, PII, prompt injection, secrets, invisible text. `✅ verified 2026-09-30`
- [Rebuff](https://github.com/protectai/rebuff) — Prompt-injection detection combining heuristics, LLM analysis, vector DB, and canary tokens. `✅ verified 2026-09-30`
- [Lakera Guard](https://www.lakera.ai/) — Real-time API detecting prompt injection, data leakage, and toxic content. `✅ verified 2026-09-30`
- [Arthur Shield](https://www.arthur.ai/product/shield) — Firewall for LLMs: hallucination, toxicity, PII, and prompt-injection detection in real time. `✅ verified 2026-09-30`
- [Vigil](https://github.com/deadbits/vigil-llm) — Open-source LLM security scanner for prompt injection via embeddings and heuristics. `✅ verified 2026-09-30`
- [Invariant Guardrails](https://github.com/invariantlabs-ai/invariant) — Policy-as-code guardrails engine for agentic applications with trace analysis. `✅ verified 2026-09-30`
- [OpenAI Moderation API](https://platform.openai.com/docs/guides/moderation) — Hosted content classification across hate, harassment, self-harm, sexual, and violence categories. `✅ verified 2026-09-30`
- [Perspective API](https://perspectiveapi.com) — Jigsaw's API scoring toxicity and related attributes of text. `✅ verified 2026-09-30`
- [Azure AI Content Safety](https://azure.microsoft.com/en-us/products/ai-services/ai-content-safety) — Managed service for harmful-content detection, including prompt-injection (Prompt Shields). `✅ verified 2026-09-30`
- [AWS Bedrock Guardrails](https://aws.amazon.com/bedrock/guardrails/) — Configurable safeguards for Bedrock apps: content filters, denied topics, PII redaction. `✅ verified 2026-09-30`
- [Detoxify](https://github.com/unitaryai/detoxify) — Open-source trained models for toxic-comment classification. `✅ verified 2026-09-30`
- [Granite Guardian](https://github.com/ibm-granite/granite-guardian) — IBM's open guardrail models for detecting risks in prompts and responses. `✅ verified 2026-09-30`
- [Hyperion](https://github.com/Salesforce/hyperion) — Framework for evaluating and hardening LLM agents against adversarial attacks. `✅ verified 2026-09-30`

## Gateways, Cost Tracking & Prompt Management

*The control plane: unified gateways with spend tracking, caching, fallbacks, and versioned prompts.*

- [Portkey](https://portkey.ai) — AI gateway with observability, caching, fallbacks, budgets, and guardrails; open-source core. `✅ verified 2026-09-30`
- [LiteLLM](https://github.com/BerriAI/litellm) — Open-source proxy unifying 100+ LLM APIs with spend tracking, virtual keys, and budgets. `✅ verified 2026-09-30`
- [Cloudflare AI Gateway](https://developers.cloudflare.com/ai-gateway/) — Edge gateway with caching, rate limiting, and analytics; generous free tier. `✅ verified 2026-09-30`
- [Kong AI Gateway](https://konghq.com/products/kong-ai-gateway) — Kong's AI plugins for governance: PII sanitization, rate limiting, and prompt guardrails. `✅ verified 2026-09-30`
- [Bifrost](https://github.com/maximhq/bifrost) — High-throughput Go-based open-source LLM gateway from the Maxim team. `✅ verified 2026-09-30`
- [PromptLayer](https://promptlayer.com/) — Prompt management, versioning, and evaluation middleware with production usage tracking. `✅ verified 2026-09-30`
- [Agenta](https://agenta.ai) — Open-source platform for prompt management, evaluation, and observability. `✅ verified 2026-09-30`
- [OpenRouter](https://openrouter.ai) — Unified model marketplace and router with usage-based billing and per-request cost visibility. `✅ verified 2026-09-30`
- [Vercel AI Gateway](https://vercel.com/docs/ai-gateway) — Vercel's gateway for the AI SDK with routing and spend controls. `✅ verified 2026-09-30`

## Benchmarks & Datasets

*Reference measurements: standard benchmarks and datasets for comparing models and tracking progress.*

- [MMLU](https://github.com/hendrycks/test) — Massive Multitask Language Understanding: 57-subject multiple-choice benchmark. `✅ verified 2026-09-30`
- [BIG-bench](https://github.com/google/BIG-bench) — Collaborative 200+ task suite probing LLM capabilities beyond the reach of scaling. `✅ verified 2026-09-30`
- [LMArena](https://lmarena.ai) — Crowdsourced human-preference arena ranking models by blind pairwise votes. `✅ verified 2026-09-30`
- [LiveBench](https://livebench.ai) — Contamination-resistant benchmark with objectively verifiable, regularly refreshed questions. `✅ verified 2026-09-30`
- [SWE-bench](https://www.swebench.com) — Real-world GitHub issues testing models' software-engineering ability. `✅ verified 2026-09-30`
- [AgentBench](https://github.com/THUDM/AgentBench) — Multi-environment benchmark for LLM-as-agent capabilities. `✅ verified 2026-09-30`
- [GAIA](https://huggingface.co/datasets/gaia-benchmark/GAIA) — Benchmark of general AI assistants on real-world tasks requiring tool use. `✅ verified 2026-09-30`
- [tau-bench](https://github.com/sierra-research/tau-bench) — Benchmark for tool-augmented agents in realistic conversational settings. `✅ verified 2026-09-30`
- [MT-Bench](https://github.com/lm-sys/FastChat) — Multi-turn conversation benchmark scored by strong LLM judges. `✅ verified 2026-09-30`
- [AlpacaEval](https://github.com/tatsu-lab/alpaca_eval) — Automated pairwise evaluation of instruction-following against a reference model. `✅ verified 2026-09-30`
- [Arena-Hard-Auto](https://github.com/lmarena/arena-hard-auto) — Hard-prompt automatic benchmark aligned with human preference rankings. `✅ verified 2026-09-30`
- [WildBench](https://github.com/allenai/WildBench) — Benchmark built on real-world challenging user queries. `✅ verified 2026-09-30`

---

## Status notes

Honest caveats, with dates — correct them via PR if they go stale:

- **Ragas** (eval): no release since Jan 2026 — roughly 8 months of quiet as of an Aug 2026 ecosystem survey. Treat it as a conceptual reference for RAG metrics, not a CI dependency; pin the version if you use it. Marked `maintenance` in the data file.
- **openai/evals** (eval): no releases and last push Apr 2026 (reported Aug 2026) — effectively stalled. Marked `maintenance`; prefer Inspect AI or lm-evaluation-harness for new work.
- **Lunary** (tracing): the open-source repo was deleted (~Dec 2025) and self-hosting is now paywalled — **excluded from this list** rather than linked dead.
- **OpenTelemetry GenAI semantic conventions**: the whole `gen_ai.*` surface is still `Development`/experimental as of mid-2026 — don't pin instrumentation to span names expecting stability.
- **Promptfoo**: reportedly acquired by OpenAI (Mar 2026, third-party reports). Assess provider neutrality if you use it to compare rival models.
- **Helicone / Portkey**: a Sept 2026 third-party gateway roundup reports both were acquired — unconfirmed; linked as independent until verified otherwise.
- **Eval ≠ observability.** Evals run offline before deploy; observability watches production. You need both — see [docs/eval-ops-workflow.md](docs/eval-ops-workflow.md).

## Guides

- [What to monitor](docs/what-to-monitor.md) — the golden signals for LLM apps and the must-have span fields.
- [Eval-ops workflow](docs/eval-ops-workflow.md) — from golden datasets to CI gates to production sampling.
- [Glossary](docs/glossary.md) — trace, span, judge, guardrail, red-teaming, and friends.

## Related

More from [Awesome-llms-labs](https://github.com/awesome-llms-labs):

- [awesome-decisions-llms](https://github.com/awesome-llms-labs/awesome-decisions-llms)
- [awesome-fast-llms](https://github.com/awesome-llms-labs/awesome-fast-llms)
- [awesome-flagship-llms](https://github.com/awesome-llms-labs/awesome-flagship-llms)
- [awesome-flash-llms](https://github.com/awesome-llms-labs/awesome-flash-llms)
- [awesome-free-llms](https://github.com/awesome-llms-labs/awesome-free-llms)
- [awesome-ai-agents](https://github.com/awesome-llms-labs/awesome-ai-agents)
- [awesome-ai-sandboxes](https://github.com/awesome-llms-labs/awesome-ai-sandboxes)
- [awesome-jev](https://github.com/awesome-llms-labs/awesome-jev)
- [awesome-microVM](https://github.com/awesome-llms-labs/awesome-microVM)

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) — entries need an official source link and an honest verification flag.

## License

MIT — see [LICENSE](LICENSE).
