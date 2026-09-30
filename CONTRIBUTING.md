# Contributing

Thanks for helping keep this the most current directory of LLM observability and eval-ops tooling!

## Adding an entry

1. **Check it fits:** an LLM tracing/monitoring platform, eval harness or eval-ops tool, guardrail/safety monitor, AI gateway with cost tracking, prompt/version management for production, or a benchmark/dataset used to evaluate LLMs. A PR must point at a primary source: the vendor's docs or the project's repo.
2. **Add to the right section** of `README.md`:
   - Tracing & Observability Platforms → per-request tracing, APM-style monitoring
   - Evaluation Harnesses & Eval-Ops → offline eval frameworks, managed eval platforms
   - Guardrails & Safety Monitoring → input/output filtering, injection detection, content safety
   - Gateways, Cost Tracking & Prompt Management → unified gateways, spend tracking, prompt versioning
   - Benchmarks & Datasets → standard benchmarks and eval datasets
   - Archived / discontinued → shut-down or deleted projects, with the date and what happened
3. **One entry = one bullet.** Format:
   `- [Name](https://official-site-or-docs) — ` one-line description. Stamp verification honestly: write `✅ verified 2026-09-30` only when you confirmed the official URL resolves yourself; otherwise mark it `⚠️ unverified`.
4. **Add the matching record** to `data/llm-observability.json` with these exact fields:

| field | type | values |
|---|---|---|
| `name` | string | tool / benchmark name |
| `vendor` | string | vendor / organization |
| `url` | string | official https:// URL |
| `description` | string | one sentence |
| `category` | string | `tracing` / `eval` / `guardrails` / `gateway` / `benchmark` |
| `status` | string | `active` / `maintenance` / `archived` |
| `verified` | bool | `true` only if you confirmed the official URL yourself |
| `verified_date` | string | `YYYY-MM-DD`, or `""` |
| `verified_source` | string | official URL you checked, or `""` |
| `note` | string | status caveat, or `""` |

5. **Never invent specs, prices, or claims.** If you can't verify a fact on an official source, flag the entry `unverified` rather than making it up. Stale-but-honest beats fresh-but-wrong.

## Style

- One sentence descriptions, no marketing superlatives ("best", "leading").
- Link the official docs or repo, not a blog post about it.
- Date-stamp every status claim (e.g. "no release since Jan 2026, reported Aug 2026") so it can age gracefully.
