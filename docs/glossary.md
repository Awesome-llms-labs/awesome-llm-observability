# Glossary

- **Trace** — the full tree of everything that happened for one request: the user prompt, retrieval calls, model calls, tool calls, and the final response.
- **Span** — one node in a trace: a single model call, retrieval step, or tool invocation, with timing and token attributes.
- **Eval** — an offline test of model/app behavior against a dataset, scored by rules, embeddings, or a judge model.
- **Eval-ops** — running evals as continuous operations: versioned datasets, CI gates, judge calibration, production sampling.
- **LLM-as-judge** — using a (different, pinned) model to score outputs against a rubric. Calibrate against humans or it's theater.
- **Golden dataset** — a versioned set of inputs with human-verified expected outputs; the ground truth your evals run against.
- **Guardrail** — runtime check on inputs and/or outputs: blocks or rewrites content matching safety, topical, or security policies.
- **Red-teaming** — adversarially probing a model/app for jailbreaks, injections, and unsafe behavior before attackers do.
- **Prompt injection** — malicious instructions smuggled into the model via user input, retrieved documents, or tool output.
- **Drift** — silent degradation over time: data drift (inputs change), model drift (provider updates the model), or judge drift (your scorer goes stale).
- **TTFT** — time to first token; the streaming-latency metric users actually feel.
- **Hallucination** — fluent, confident output that is wrong or ungrounded. Returns HTTP 200 — only evals and guardrails catch it.
- **Canary tokens** — honeypot strings planted in prompts/data; if they appear in output, something leaked or got injected.
