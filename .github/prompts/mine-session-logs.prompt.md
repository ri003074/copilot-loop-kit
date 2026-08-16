---
agent: 'agent'
description: 'Mine local Copilot JSONL session logs for repeated workflow problems'
---

Inspect local Copilot session logs under `~/.copilot/session-state/*/events.jsonl` and select only sessions demonstrably related to this repository.

Do not copy logs into the repository, edit the logs, or reproduce secrets, personal data, or unnecessary source content.

First report:

- the log location searched;
- the number of candidate logs;
- the number of sessions judged relevant;
- the evidence used to associate sessions with this repository;
- any logs that could not be read.

Analyze up to 100 relevant sessions, largest first. Divide them into up to 10 groups. If parallel analysis is available, analyze groups independently; otherwise process them sequentially.

For each group, report only:

1. cases where work proceeded without inspecting relevant files or data;
2. unnecessary tool usage spent locating files;
3. project knowledge rediscovered in separate sessions;
4. explicit user corrections repeated within or across sessions;
5. validation repeatedly omitted and later requested.

Combine the group results and sort patterns by the number of groups and sessions in which they appeared.

Compare the results with [the current instructions](../copilot-instructions.md) and [the learning candidates](../copilot-learnings.md). Recommend one destination for each pattern:

- repository-wide instruction;
- path-specific instruction;
- learning candidate;
- repository documentation;
- automated check;
- no change.

End with evidence-based proposed diffs. Do not modify files.

If local JSONL logs are unavailable or inaccessible, stop after reporting the paths checked. Do not infer missing history.

