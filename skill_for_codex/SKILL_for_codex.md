---
name: readable-code
description: Apply clear, readable, pragmatic design principles when generating, modifying, or reviewing code. Use for implementation, refactoring, and code review tasks.
---

# Readable Code

When generating, modifying, or reviewing code, prioritize clarity, simplicity, consistency, and practical correctness. Follow the user's requirements and the project's conventions. Avoid unsupported assumptions, hidden errors, and unnecessary complexity.

## Generate and modify code

### Clarity and readability

- Prefer familiar, idiomatic patterns used by the language and project over clever techniques.
- Use names that communicate the intent of variables, functions, types, and modules.
- Choose the simplest implementation that satisfies the requirements. Do not add abstractions merely to make the design appear elegant.
- When a problem is inherently complex, organize that complexity into functions or modules with clear responsibilities.
- Avoid unnecessary nesting and make the main flow easy to follow.
- Keep code easy to scan: use appropriate structure and avoid overly long functions, crowded expressions, and unrelated operations grouped together.
- Treat readability as part of correctness, not as a cosmetic preference.

### Consistency, practicality, and errors

- Do not introduce a separate rule or implementation merely because a case seems unusual. First check whether existing patterns already handle it.
- When an exception is necessary, keep it narrowly scoped and make its rationale clear.
- Prefer solutions that meet real functional, compatibility, performance, and maintenance needs over theoretical purity.
- Handle failures explicitly. Do not silently swallow errors or use defaults that conceal an unsuccessful operation.
- Ignore an error only when the requirements or caller explicitly permit it. Keep the ignored error category narrow and make the decision visible.
- Preserve useful diagnostic context without exposing sensitive information.

### Ambiguity and solution choice

- If ambiguity could change behavior, an interface, or the implementation direction, ask a specific clarifying question instead of guessing.
- If the ambiguity does not affect the result, follow project conventions and state any important assumption.
- Prefer an existing, applicable project pattern over introducing a second way to solve the same problem.
- Compare viable options using correctness, readability, compatibility, performance, and maintenance cost; choose the most direct option that fits the project.
- Do not assume a solution is obvious without checking the codebase, conventions, and requirements.

### Progress and care

- Once requirements and constraints are sufficiently clear, take concrete steps to complete the task rather than extending planning unnecessarily.
- Before changing code, understand the task's scope, relevant implementation, and constraints.
- Do not rush past compatibility, existing behavior, or likely side effects just to act quickly.
- Prefer implementations whose behavior and rationale can be explained clearly. If an implementation is difficult to explain, reconsider whether it contains avoidable complexity.
- Ease of explanation is not proof of correctness. Verify that the implementation meets the requirements.
- Keep changes within the task's scope. Do not expand the work without a reason grounded in the request.
- Do not omit necessary tests or checks merely to finish sooner.

### Namespaces and module boundaries

- Follow the project's existing namespace, package, and module structure.
- Use namespaces and module boundaries to clarify responsibilities and prevent naming conflicts or unintended coupling.
- Follow the language's and project's conventions. Avoid redundant prefixes, needless nesting, and excessive layers.
- Split code into modules when doing so reduces complexity, clarifies responsibilities, or enables meaningful reuse.
- Avoid splitting that only adds navigation, circular dependencies, or indirection.
- Follow explicit user requirements for directories, modules, naming, and architecture. Explain material tradeoffs rather than silently overriding those requirements.

## Review code

Review the implementation against the following:

- Is its purpose and main flow easy to understand?
- Are names and structure clear and consistent with the project?
- Is there avoidable complexity, nesting, duplication, or abstraction?
- Does the implementation rely on an unconfirmed assumption that could affect behavior?
- Does it handle failures explicitly, or could it hide errors and mislead callers?
- If errors are intentionally ignored, is that allowed and narrowly scoped?
- Are special cases necessary and consistent with existing patterns?
- Do module boundaries solve a real problem, or introduce needless indirection?
- Does the code satisfy the requirements, including relevant edge cases?
- Has it been appropriately tested or checked?

When raising a review concern, identify the relevant code, explain the concrete impact, and suggest a practical improvement. Do not request changes based only on personal style preferences or unfamiliarity with an approach. If multiple solutions are reasonable, describe the meaningful tradeoffs.

## Verify and report

- Run tests, checks, or builds relevant to the change when feasible.
- If verification cannot be performed, state what was not run and why.
- Explain important design choices, assumptions, and exceptions.
- Keep the report concise and distinguish verified results from unverified claims.