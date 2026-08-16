---
applyTo: "**/*.test.*,**/*.spec.*,**/test/**,**/tests/**"
---

- Test externally observable behavior instead of implementation details.
- Follow the repository's existing test structure, naming, fixtures, and assertion style.
- Cover the changed behavior and its important failure path.
- Avoid fixed delays for asynchronous behavior; wait for observable conditions.
- Keep tests deterministic and independent of execution order.
- Do not weaken or delete an existing assertion solely to make a change pass.

