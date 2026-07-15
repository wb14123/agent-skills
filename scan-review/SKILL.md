---
description: Review the whole project
user-invocable: true
disable-model-invocation: true
---

Review the code in the current directory. Focus on correctness, edge cases, potential bugs, security, code cleanliness, and dead code. Do not need to review things like built targets, releases or compiled files.

After it, create a markdown file under `reviews/` directory for each issue found:

1. High level description of the issue at the beginning.
2. Then the context and details. Make sure it includes everything that anyone without previous context can understand the issue.
3. Suggest fixes.

Also add an overview file `reviews/overview.md` for an overview of the issues.

Do not need to modify the code to fix the issues.
