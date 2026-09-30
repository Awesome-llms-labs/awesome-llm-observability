# Eval-ops workflow

How to run evaluations like tests: from golden datasets to CI gates to production sampling.

## 1. Build a golden dataset

- 25–100 examples covering your real traffic: happy paths, edge cases, and known failures.
- Version it in git next to the prompt (`evals/*.jsonl`). The eval set is code: reviewed in PRs, tagged with releases.
- Include human-verified expected outputs or anchored rubrics — a judge without a rubric is a random number generator.

## 2. Pick the harness

- **CI-integrated**: Promptfoo (config-driven asserts) or DeepEval (`pytest` ergonomics) for gates that fail the build.
- **RAG-specific**: Ragas metrics as reference definitions.
- **Academic reproduction**: lm-evaluation-harness or HELM.
- **Agentic/safety**: Inspect AI with sandboxing.

## 3. Calibrate the judge

- Use a **different model family** for the judge than the generator (removes self-preference bias), pinned by exact model ID.
- Calibrate against 25–50 human-annotated examples; track judge–human agreement (correlation, MAE) over time — Langfuse, Braintrust, and DeepEval all support this.
- Prefer **pairwise comparisons with both orderings** for model selection; absolute scoring only against an anchored rubric for thresholds.

## 4. Gate deployments

- Run the eval suite in CI on every prompt/model change. Fail the build on regression beyond a threshold — treat evals like unit tests.
- Keep a **canary slice**: route 5% of production traffic to the candidate, compare live quality/cost before full rollout.

## 5. Sample production

- Log everything, **human-review a sample**: annotation queues in LangSmith/Braintrust/Langfuse turn production traces into new golden examples.
- Watch for drift: embedding drift, judge-score decay, cost-per-task creep. Re-calibrate judges quarterly — models update under you.

## The loop

```
production traces → sample & annotate → golden dataset → CI eval gate → deploy → production traces …
```

The teams that win are the ones where this loop runs weekly, not the ones with the fanciest dashboard.
