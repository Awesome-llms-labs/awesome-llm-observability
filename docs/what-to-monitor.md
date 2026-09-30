# What to monitor

The four golden signals for LLM applications, and what to emit on every call.

## The golden signals

1. **Latency** — end-to-end ms, plus time-to-first-token (TTFT) for streaming. Break down by model, provider, and step (retrieval vs. generation vs. tools).
2. **Cost** — input/output/cached/reasoning tokens converted to $ per request, attributed to tenant, feature, and prompt version. A single request can cost $0.001 or $0.40; HTTP status tells you nothing about this.
3. **Quality** — eval scores sampled from production: task success, faithfulness, judge scores, user feedback (thumbs up/down). Track drift over time, not just point values.
4. **Safety** — guardrail trigger rates: prompt-injection attempts blocked, PII redactions, moderation flags. A spike here is an incident.

## The must-have span

Every LLM call should emit: `trace_id`, `request_id`, `tenant_id`, `feature_id`, `model`, `model_version`, `provider`, `input_tokens`, `cached_input_tokens`, `output_tokens`, `reasoning_tokens`, `cost_usd`, `latency_ms`, `ttft_ms`, `cache_hit`, `tool_calls[]`, `retry_count`, `prompt_version`, `outcome`.

If your logging is missing any of these, that is the highest-leverage item in your backlog.

## SLOs that actually work

- p95 latency per feature (not global — a slow summarizer hides behind a fast classifier).
- Cost per successful task completion, with budget alerts per tenant.
- Eval regression gates in CI (see [eval-ops-workflow.md](eval-ops-workflow.md)) rather than production-only monitoring.
- Guardrail block rate with an on-call runbook: a sudden 10x spike means you're under attack, not that users got ruder.

## Standards note

Prefer OpenTelemetry with the GenAI semantic conventions so traces stay portable across backends — but note the `gen_ai.*` conventions are still experimental (see Status notes in the README).
