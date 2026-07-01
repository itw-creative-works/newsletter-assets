# When AI writes code, review must get smarter

_Why benchmarks, routing, and harness design matter more than ever_

AI coding changed the shape of the bottleneck. The hard part is no longer getting a draft out of a model, it is filtering the draft, routing the right checks, and preventing token spend from spiraling out of control.

---

## Benchmarks need to measure merge-worthiness

![A technical illustration of a code benchmark dashboard showing merge checks, maintainability scores, and a pull request ready for review in a clean modern style.](https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/main/optiic/-OupU3cAlN0T76Xg76uF/section-1.png)

If a coding model can produce something that looks plausible, the benchmark has to ask a better question: would this actually ship? That means grading for maintainability, correctness, and the kind of edge cases that block a pull request in real life. Pure pass or fail tests are too forgiving when a model can optimize for surface-level success. The better approach is to measure whether a change would survive code review and land in main without hidden cleanup work. In practice, that pushes evaluation from flashy demos toward the boring details that teams live with every day.

[Read the full article →](https://optiic.dev/blog/the-benchmark-question-that-matters-would-this-merge)

---

## Static review pipelines are already obsolete

![An isometric scene of a pull request being routed through multiple specialized review stations labeled security, schema, and behavior, with a planner node at the center.](https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/main/optiic/-OupU3cAlN0T76Xg76uF/section-2.png)

Once AI is writing the first draft, review cannot stay one-size-fits-all. A schema migration needs different scrutiny than an auth change, and a refactor needs different checks than a bug fix. The new pattern is to inspect the PR first, then assemble a review plan around it. That can mean security-focused checks for sensitive paths, behavioral checks for logic changes, and schema checks for database edits. This is less about replacing reviewers and more about routing attention where it matters. A generic pipeline wastes time on irrelevant checks and misses the ones that actually prevent incidents.

---

**Sponsored**

---

## Token spend is a systems problem

![A diagram-style illustration of an LLM agent loop with token counters, model tiers, and a routing switch that reduces cost as tasks progress.](https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/main/optiic/-OupU3cAlN0T76Xg76uF/section-3.png)

Agent loops can quietly become the most expensive part of the stack. The usual failure mode is simple: resend the full context every step, keep the model in a loop, and reach for the most expensive model by default. That is how a single task starts consuming far more tokens than anyone expected. The fix is not just picking a cheaper model. It is designing the loop so it remembers only what it needs, choosing models based on task difficulty, and avoiding repeated work. When teams get this right, they can keep costs predictable even as usage scales.

---

## The harness is part of the product

![A software engineering workstation showing an agent harness blueprint with prompts, tools, retries, and guardrails arranged like infrastructure architecture plans.](https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/main/optiic/-OupU3cAlN0T76Xg76uF/section-4.png)

A lot of agent failures do not come from the model at all. They come from the harness around it: the prompt structure, the tool interface, the retry logic, the context windows, and the guardrails that determine whether the agent can actually finish the job. If that setup is brittle, even a strong model will behave badly. The teams shipping reliable coding agents are treating harness engineering like core infrastructure, not scaffolding. That is the difference between a demo that looks impressive and a system that can produce useful output all day without constant babysitting.

---

## Human review still matters, but it has to be sharper

![A developer comparing a code diff against a chatbot response under a magnifying glass, with subtle warning signs around concurrency and security issues.](https://raw.githubusercontent.com/itw-creative-works/newsletter-assets/main/optiic/-OupU3cAlN0T76Xg76uF/section-5.png)

The easy mistake is to assume AI review can rubber-stamp AI code. It cannot. In one familiar failure mode, a reviewer trusts a chatbot's quick answer over the actual diff and ships a race condition. The right response is not more ceremony, but better judgment. Human reviewers should focus on the places models are still weakest: concurrency, integration boundaries, security-sensitive changes, and hidden behavior changes. If AI is accelerating code creation, human review has to become more selective and more skeptical, not less involved.

---

Best,  
The Optiic Team

---

## Notes

1. LLM agents can burn millions of tokens on a single task — _Industry engineering practice, 2026_

2. A senior dev approved a PR by pasting the diff into a chatbot and shipped a race condition — _Shared engineering example, 2026_

3. Open models can bring code review costs down to cents per review — _Vendor implementation notes, 2026_

_Tags: #code-quality #llm-agents #developer-tools #model-routing_

---
_You're receiving this because you subscribed to [Optiic](https://optiic.dev)._
