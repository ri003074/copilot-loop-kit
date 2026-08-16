---
agent: 'agent'
description: 'Analyze past Copilot sessions and propose evidence-based instruction improvements'
---

Analyze the past GitHub Copilot sessions started by me that are related to this repository.

Compare the findings with [the current repository instructions](../copilot-instructions.md) and [the learning candidates](../copilot-learnings.md).

Look specifically for:

- explicit user corrections;
- requests repeated across multiple sessions;
- decisions made by Copilot and then reversed by the user;
- signs of possible frustration, without asserting the user's emotion as fact;
- work based on assumptions instead of inspected files or data;
- repeated tool calls spent locating files;
- project knowledge rediscovered in multiple sessions;
- missing tests or verification later requested by the user.

Classify findings as:

- P0: repeated across sessions with explicit corrections or reversals;
- P1: repeated across multiple sessions;
- P2: potentially useful but supported by only one occurrence.

For every finding, report:

| Priority | Pattern | Session count | Concise evidence | Already covered? | Recommended destination |
|---|---|---:|---|---|---|

Use only sessions demonstrably related to this repository. Explain how that relationship was determined. Do not expose secrets, personal data, or unnecessary source content.

Recommend one of these destinations for each finding:

- `.github/copilot-instructions.md` for broadly applicable, always-on rules;
- `.github/instructions/*.instructions.md` for path-specific rules;
- `.github/copilot-learnings.md` when more evidence is required;
- repository documentation for project knowledge;
- lint, formatter, tests, or CI for mechanically enforceable rules;
- no change.

Propose repository-wide instructions only for P0 and P1 findings that are short, specific, broadly applicable, and reviewable. Merge overlapping rules.

End with proposed diffs. Do not modify any files.

If synced session history is unavailable, say so explicitly and recommend running `/chronicle improve` in Copilot CLI or using the local-log prompt. Do not invent history.

