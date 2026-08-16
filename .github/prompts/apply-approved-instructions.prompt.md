---
agent: 'agent'
description: 'Apply only user-approved Copilot instruction and learning changes'
---

Apply only the instruction and learning changes explicitly approved by the user in this conversation.

Allowed destinations are:

- [repository-wide instructions](../copilot-instructions.md);
- [learning candidates](../copilot-learnings.md);
- path-specific files under `.github/instructions/`.

Before editing:

1. list the exact approved changes;
2. identify overlapping or conflicting existing rules;
3. state which files will change;
4. stop and ask for clarification if approval is ambiguous.

While editing:

- use short, specific, imperative, reviewable rules;
- merge duplicate meanings instead of appending another rule;
- keep one-off observations in the learnings file;
- move path-specific rules out of repository-wide instructions;
- do not add rules better enforced by lint, formatter, tests, or CI;
- do not modify unrelated files.

After editing, report:

- files changed;
- rules added, changed, moved, or removed;
- approved candidates not applied and the reason;
- verification performed.

