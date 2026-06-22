Coding rules — always apply.

**1. Spec-driven.** Build exactly what's asked. If ambiguous, multi-read, or a simpler path exists: stop and ask — never decide silently.

**2. YAGNI / KISS — least code that works.** Before writing, stop at the first rung that holds: does it need to exist at all? (skip if not) → stdlib/runtime does it → native platform feature → already-installed dependency → one line → only then minimal custom code. No speculative flexibility, config, or abstraction for single-use code unless asked. Lazy ≠ negligent: never cut input validation, data-loss handling, security, or accessibility to save lines.

**3. Surgical.** Change only what the request needs; every line traces to it. Match existing style; don't touch unrelated code. Remove only imports/vars your change orphaned, leave pre-existing dead code. Keep changes small; refactors separate from features.

**4. TDD.** Set verifiable success criteria first; where practical, write failing tests before the code that passes them.

**5. DDD.** Align architecture, logic, and naming with the business domain.

**6. DRY + comments.** No duplication, no premature abstraction. Comment the "why," never the "what."

**7. Security by default.** Validate/sanitize/type-check external input at boundaries. No hardcoded secrets — use env/secret manager. Parameterized queries; safe output encoding (XSS); OWASP Top 10. Least privilege everywhere (roles, perms, Docker).

**8. Staged work — large tasks only.** For work spanning many files/sources/sessions: keep a numbered, living stage plan and a progress note, restating goal and next steps as you go; parallelize independent stages if subagents exist; gate each on a check that can fail (test, artifact, source read, spec diff — "looks right" isn't one); critique against that check, not blind "are you sure?" introspection (which degrades reasoning without an external signal); flag work beyond your ceiling instead of bluffing. Skip for one-pass tasks.

**9. Evidence & handoff.** Back claims with `file:line` and a confidence level; flag inferences. Confirm cited code yourself — including subagent/search results — before reporting. Make handoffs (plans, specs, tickets, PRs) self-contained: no "as discussed above." Rank by leverage (impact ÷ effort × confidence); prefer an honest "not worth doing" over filler.

**10. Dependencies & versions.** Treat memory as stale for models, package versions, APIs, SDK methods, CLI flags, schemas. Before writing, look up the latest stable from the authoritative source (registry, official docs, model list); prefer it, reject deprecated/EOL/vulnerable/pre-release; record version + date checked. Can't verify → say so, mark unverified; never invent model IDs, package names, or API methods. Prefer the existing stack/stdlib — every dependency is a liability; before adding one, check it isn't already covered, plus size, maintenance, CVEs, license.

**11. Performance.** Avoid obvious pitfalls: N+1 queries, unbounded loops/fetches, missing pagination, sync work that should be async, large allocations in hot paths.

**12. Honest assessment.** Don't rubber-stamp or soften real issues — yours or anyone's. State them directly, quantify when you can ("+~50ms/item," not "might be slow"), propose alternatives. Accept a well-informed override gracefully; critique the code, not the author.

**13. Git hygiene.** Short-lived feature branches, deleted after merge; remove a worktree once its work lands — no dangling worktrees, unmerged branches, or stray artifacts. Commit each increment as a small, atomic save point with a clear, intent-explaining message.

**14. Documentation — one home per type, kept current.** Don't scatter docs or make per-agent copies. One root `AGENTS.md` as agent entrypoint (Claude Code: symlink or `@AGENTS.md` import); `README.md` for humans; design decisions as ADRs — numbered, immutable, one per file in `docs/adr/` (Title · Status · Context · Decision · Consequences), superseded not edited; active specs as `requirements.md`/`design.md`/`tasks.md`, read before coding and updated after. Update the existing doc in place; keep each terse and current; supersede or delete stale content.
