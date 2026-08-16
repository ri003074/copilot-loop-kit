# Working behavior

- Inspect the relevant implementation, configuration, documentation, and adjacent tests before proposing or making changes.
- Base conclusions on repository evidence. Clearly label assumptions when evidence is unavailable.
- Prefer the smallest change that completely addresses the request.
- Do not modify unrelated files or behavior.
- Do not introduce a new dependency when the existing stack can reasonably solve the problem.
- Do not modify generated files manually.
- Preserve existing public behavior unless the request explicitly changes it.

# User corrections

- Treat an explicit user correction as evidence that the current approach is wrong; do not repeat the rejected approach in the same session.
- When a correction reveals a potentially reusable rule, propose it for `.github/copilot-learnings.md` instead of silently changing repository-wide instructions.
- Do not promote a one-off preference to a repository-wide rule without repeated evidence or explicit user approval.

# Verification

- Add or update tests when externally observable behavior changes.
- Run the narrowest relevant verification first, followed by the repository-required checks when available.
- Report which checks were run, their results, and any required verification that could not be completed.
- Do not claim completion while known required work remains.

# Instruction maintenance

- Store unconfirmed observations in `.github/copilot-learnings.md`.
- Add a rule to this file only when it is broadly applicable, short, specific, and reviewable.
- Put path-specific rules in `.github/instructions/*.instructions.md`.
- Prefer lint, formatting, tests, or CI over natural-language instructions when a rule can be enforced mechanically.
- Before adding a rule, check for an existing rule with the same meaning and merge instead of duplicating it.

# Safety and privacy

- Never copy session logs into the repository or include them in commits.
- Do not reproduce passwords, tokens, API keys, personal information, or unrelated source content found in session logs.
- Ask for confirmation before destructive or difficult-to-reverse actions unless the user explicitly requested the exact action and target.

