---
agent: 'agent'
description: 'Perform a weekly evidence-based review of Copilot instructions and learnings'
---

Review [the current instructions](../copilot-instructions.md), [the learning candidates](../copilot-learnings.md), and recent sessions related to this repository.

Perform these checks:

1. Identify obsolete entries.
2. Merge entries with the same meaning.
3. Identify patterns confirmed across multiple sessions.
4. Remove candidates now obvious from the repository itself.
5. Identify rules already enforced by lint, formatting, tests, or CI.
6. Convert P0 and P1 learnings into short, specific, reviewable rules.
7. Separate repository-wide rules from path-specific rules.
8. Keep one-off observations in the learnings file.

For each proposed promotion to repository instructions, state:

- supporting session count;
- representative correction or failure;
- problem prevented;
- why repository-wide instructions are the correct destination;
- any overlap or conflict with an existing rule.

Return:

1. a cleanup diff for `.github/copilot-learnings.md`;
2. an improvement diff for `.github/copilot-instructions.md`;
3. proposed `.github/instructions/*.instructions.md` files where appropriate;
4. candidates better handled by documentation or automated checks.

Do not modify files until the user approves specific changes.

