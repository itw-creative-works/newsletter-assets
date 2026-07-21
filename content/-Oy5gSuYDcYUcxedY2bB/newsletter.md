# Why your engineering dashboard is lying

_AI changed the work, so old productivity proxies are drifting off target._

Two very different parts of the stack are converging on the same lesson: raw output is not the same as useful signal. In engineering, dashboards can overrate activity while missing real progress. In AI, models can keep growing in size and still hit a ceiling if the underlying data does not carry enough information.

---

## Your dashboard is counting motion, not impact

![A modern engineering dashboard with glowing charts, but a developer standing in front of it looking skeptical, illustrated in clean editorial style.](https://cdn.itwcreativeworks.com/newsletters/optiic/content/-Oy5gSuYDcYUcxedY2bB/section-1.png)

A lot of teams still treat pull requests, commits, and ticket throughput as if they are direct measures of engineering quality. They are not. Once AI assistants enter the workflow, those numbers can move fast even when the underlying work is unchanged, duplicated, or partly automated. That makes the old scoreboard less useful and, in some cases, actively misleading.

The fix is not to throw metrics away. It is to split them into two buckets: activity and outcome. Activity tells you how work is flowing. Outcome tells you whether the work mattered. If your dashboard cannot connect the two, it is mostly telling a story about motion.

[Read the full article →](https://optiic.dev/blog/stop-treating-pr-counts-as-engineering-quality)

---

## AI did not break productivity, it exposed bad proxies

![A split-screen illustration showing a flurry of code activity on one side and a product dashboard with customer impact signals on the other.](https://cdn.itwcreativeworks.com/newsletters/optiic/content/-Oy5gSuYDcYUcxedY2bB/section-2.png)

The problem is not that teams became less productive overnight. The problem is that AI changed the shape of the work faster than the measurement system changed with it. A developer can now produce more code, more branches, and more review requests without a proportional increase in shipped value. That means the team that looks busiest may not be the team that is improving the product the fastest.

If you lead engineers, start asking different questions. Did cycle time improve for important work? Did defects go down? Did customer-facing outcomes move? Those questions are slower to measure, but they are closer to the truth. Productivity is now less about counting keystrokes and more about tracing impact.

---

**Sponsored**

---

## When the data runs out, scaling stops

![A technical illustration of a model scaling upward into a ceiling made of sparse data points, with richer data streams breaking through it.](https://cdn.itwcreativeworks.com/newsletters/optiic/content/-Oy5gSuYDcYUcxedY2bB/section-3.png)

The same trap shows up in model building. You can add parameters and compute for a while, but if the dataset does not contain enough useful signal, performance eventually flattens. That is especially obvious in tasks where the model needs to understand change, not just label static patterns. If the data does not encode the right causal structure, the model cannot invent it from size alone.

The practical lesson is that more data is not the same as better data. The winning move is to generate information-rich examples, not just collect more of the same. In other words, if you want the model to reason about what causes what, your data pipeline has to be designed for causality from the start.

---

## Formal verification is the opposite of vibe-based software

![A precise, minimalist scene of a programmer, a proof assistant interface, and a verified code pipeline rendered in crisp technical illustration style.](https://cdn.itwcreativeworks.com/newsletters/optiic/content/-Oy5gSuYDcYUcxedY2bB/section-4.png)

There is a useful counterweight to all this uncertainty: systems that prove what they do before they ship. Formal verification is still niche in day-to-day development, but it matters because it replaces intuition with machine-checked guarantees. Instead of trusting that the compiler or a critical component behaves correctly, you can narrow the space for hidden failures.

That mindset pairs well with the measurement and data problems above. Whether you are building models or software, the goal is the same: reduce guesswork where the cost of being wrong is high. Verification will not replace ordinary engineering judgment, but it is a strong reminder that the best systems do not rely on hope.

---

Stay sharp,  
The Optiic Team

---

## Notes

1. Engineers using a coding assistant opened about seven-tenths more pull requests than peers, and the gap kept growing — _Reported by an engineering leader, July 2026_

2. A model trained on richer experimental data was able to keep scaling with model size and compute after hitting a data bottleneck on a smaller dataset — _Per internal model development results, July 2026_

3. The richer dataset delivered roughly thirty times more informational value than the earlier setup — _Per internal data collection results, July 2026_

_Tags: #engineering-productivity #ai-workflows #data-quality #formal-methods_

---
_You're receiving this because you subscribed to [Optiic](https://optiic.dev)._
