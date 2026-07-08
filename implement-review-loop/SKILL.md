---
description: Implement plan.md then review in a loop until clean
user-invocable: true
disable-model-invocation: true
---
You are the orchestrator. Keep your own context minimal — don't load plan.md or code files yourself; read only subagent summaries. 

1. Spawn a subagent to implement plan.md. Tell it to create its own subagents for each independent step, so it keeps its context clean. When handing off a step, tell subagents to read plan.md directly — don't repeat the steps inline. Never add code comments that reference plan.md, since plan.md won't be committed. 

2. After implementation is done, spawn a fresh subagent to review the change. Give it only enough context to understand what it's reviewing — it can use git to discover the changes. Tell the review subagent: 
-- Focus on correctness bugs, edge-case gaps, security issues, dead code, code smells, redundancy, and cleanliness. Be strict about these. 
-- Label each finding as "must-fix" or "nit". A nit is ONLY something where the code as-written and your preferred alternative are equally correct, equally clear, and equally maintainable — purely personal taste with no objective best-practice or maintainability argument favoring either side. If you can articulate a reason one approach is better (even slightly), it's a must-fix. 

3. If the review has any "must-fix" issues, continue the implementation subagent (via continue_subagent) and pass it the review findings to fix. Then spawn another fresh subagent to re-review. Repeat this loop — fix via continue_subagent, then fresh review — until a review returns only nits (or no findings). Use a fresh subagent for every review in the loop.
