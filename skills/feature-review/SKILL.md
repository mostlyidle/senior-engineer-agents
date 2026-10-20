---
name: feature-review
description: Review a feature, bug fix, branch, or working-tree diff against its requirements and applicable project standards. Use after a feature implementation or for an explicit code review request.
---

# Feature review

1. Establish the review boundary: the relevant base commit, branch comparison, or working-tree changes. Read the originating request and applicable project instructions. If the boundary is ambiguous, state a safe assumption or ask when it changes the review materially.
2. Read the full diff and surrounding contracts, callers, and tests. Trace the behavior across affected boundaries; review evidence rather than relying on commit messages or summaries.
3. Check requirements: observable behavior, failure cases, compatibility, migrations, user-visible states, and verification that can detect a regression.
4. Check project standards and risks: maintainability, demonstrated reuse, security and authorization, sensitive data, concurrency, resource lifetime, and relevant operational behavior. Scale the review to the change.
5. Report actionable findings with file/line references, the concrete trigger, impact, and a focused remedy. Distinguish verified defects from hypotheses and unrelated pre-existing issues. Avoid speculative redesigns and style preferences already settled by project conventions.
6. When implementation and repair are authorized, fix findings introduced by the feature, rerun affected checks, and review the new diff. When asked only for a review, report findings without silently editing the implementation.

Done when the scoped diff has been checked against both the request and project standards. Report unresolved findings, verification limits, and checks actually run. If there are no findings, say so without implying that the review proves absence of defects.
