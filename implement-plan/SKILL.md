---
description: Implement plan.md step by step
user-invocable: true
disable-model-invocation: true
---
Implement plan.md. Ask me questions if there is anything not clear. Use subagent to implement each step if needed, so that you keep your context window clean for large changes and can supervise the overall correctness.When use subagent to implement, let it refer to the doc instead of repeat the steps to it.Never make any comments in the code to refer to plan.md, since plan.md will not be commited to the repo at the end.

Make sure the finished code is clean and doesn't have dead code. Only use necessary comments: only comment things that the user cannot refer from the code. Describe what the code does in the comment makes it duplicate and easy to be outdated. Do not add any discussion and implementation noise in the comment: it should be a consistent final state instead of "how did we get here": those things belongs more to git commit messages.
