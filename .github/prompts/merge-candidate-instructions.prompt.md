---
agent: 'agent'
description: 'Safely merge candidate Copilot instructions into existing repository instructions'
---

Compare the existing [repository instructions](../copilot-instructions.md) with the candidate file at `.github/copilot-instructions.candidate.md`.

The existing repository instructions are authoritative. Do not overwrite them wholesale.

Analyze the two files and classify every candidate rule as one of the following:

- duplicate: the existing file already contains the same meaning;
- conflict: the candidate contradicts or weakens an existing rule;
- new repository-wide rule: broadly applicable and not already covered;
- path-specific rule: should be placed under `.github/instructions/*.instructions.md`;
- automation candidate: better enforced by lint, formatting, tests, hooks, or CI;
- reject: abstract, unverifiable, obsolete, project-inappropriate, or unnecessary.

Follow these requirements:

- Preserve project-specific existing rules unless the user explicitly approves changing them.
- Compare meaning, not wording, when detecting duplicates.
- Merge overlapping rules instead of appending another version.
- Do not weaken a more specific existing rule.
- Keep repository-wide instructions short, imperative, specific, and reviewable.
- Do not add one-off preferences as permanent repository-wide rules.
- Do not modify unrelated files.
- Do not delete the candidate file.

First return this report:

| Candidate rule | Classification | Existing related rule | Recommendation | Reason |
|---|---|---|---|---|

Then provide:

1. duplicate rules;
2. conflicting rules;
3. recommended repository-wide additions or consolidations;
4. rules to move into path-specific instruction files;
5. rules better handled by automated checks;
6. rejected rules and reasons;
7. the proposed diff for every affected file.

Do not modify any files during this analysis step.

After presenting the report and diffs, ask the user to specify which proposed changes are approved. Apply only explicitly approved changes in a later step. If approval is ambiguous, ask for clarification before editing.

