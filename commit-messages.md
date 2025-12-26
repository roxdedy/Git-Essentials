# Git Commit Messages Reference

Professional reference for clear, consistent commit messages.

## Commit Message Structure

- **Subject line**: Imperative mood, ≤50 characters, no trailing period.
  Capitalization is team-dependent.
- **Body** (optional): Wrap at 72 characters. Explain _why_ and _what_, including trade-offs if relevant.
- **Footer** (optional): References (e.g., `Closes #123`).

Typed prefixes (e.g., `feat:`, `fix:`) are optional unless enforced by the team.

Example:

```text
feat: add user authentication

Implement JWT-based authentication for API endpoints.
Resolves security vulnerability in session management.

Closes #123
`````


Trade-off: Short subjects improve log scanning; detailed bodies add context but increase overhead.

## Essential Commit Patterns

Conventional Commits types are optional but widely adopted for tool integration (e.g., changelog generation). Plain descriptive subjects are acceptable if the team prefers simplicity.

| Type     | Description                             | When to Use                         | Example Subject                     |
| -------- | --------------------------------------- | ----------------------------------- | ----------------------------------- |
| feat     | New feature or enhancement              | Adding functionality                | feat: add search filtering          |
| fix      | Bug fix                                 | Correcting errors                   | fix: resolve null pointer in loader |
| refactor | Code restructuring (no behavior change) | Improving structure/readability     | refactor: extract validation logic  |
| docs     | Documentation changes                   | Updating README, comments, API docs | docs: clarify configuration options |
| chore    | Miscellaneous maintenance               | Dependency updates, config, tooling | chore: update lodash to v4.17       |

Optional scopes: `feat(api): add user endpoint` (team-dependent).

Optional additional types: `test`, `style`, `perf`, `ci`.

## Good vs Bad Examples

| Scenario         | Good Example                               | Bad Example     | Why Good/Bad                               |
| ---------------- | ------------------------------------------ | --------------- | ------------------------------------------ |
| Feature addition | feat: implement email notifications        | added emails    | Good: imperative, typed, clear. Bad: vague |
| Bug fix          | fix: handle division by zero in calculator | fixed a bug     | Good: specific. Bad: no context            |
| Refactor         | refactor: simplify payment processing      | cleaned up code | Good: intent clear. Bad: ambiguous         |
| Docs update      | docs: add deployment instructions          | updated readme  | Good: precise. Bad: uninformative          |
| Chore            | chore: upgrade Node.js to 20               | minor changes   | Good: actionable. Bad: meaningless         |

## References

- [Conventional Commits](https://www.conventionalcommits.org/) (optional standard)
- Official Git documentation

Opinionated toward brevity and optional typing; adapt to team needs.