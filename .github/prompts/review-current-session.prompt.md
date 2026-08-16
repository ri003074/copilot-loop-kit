---
agent: 'agent'
description: 'Extract reusable learnings from the current Copilot session'
---

Review the current session and extract only:

- explicit user corrections;
- causes of rework;
- approaches that worked well;
- failures caused by proceeding without inspecting relevant evidence;
- project knowledge worth preserving;
- possible instruction gaps.

Compare the observations with [the current learnings](../copilot-learnings.md) and merge duplicate meanings.

For each observation, include:

- date;
- a concise description;
- whether it is new or repeated;
- the number of known supporting sessions;
- the recommended destination.

Put one-off observations under `Candidates requiring more evidence`. Do not treat them as confirmed rules.

Present a proposed diff for `.github/copilot-learnings.md`. Do not change `.github/copilot-instructions.md`, and do not modify files until the user approves the diff.

