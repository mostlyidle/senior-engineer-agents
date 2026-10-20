---
name: systematic-debugging
description: Diagnose bugs, regressions, intermittent failures, or performance problems by reproducing the symptom and testing falsifiable hypotheses. Use when a failure needs investigation before a fix.
---

# Systematic debugging

1. Record the expected and observed behavior, the relevant environment, and the exact failure. Inspect affected code and callers. Use synthetic or redacted inputs for evidence.
2. Establish the smallest reliable reproduction. For intermittent failures, record frequency and conditions; for performance problems, establish a comparable measurement. State the limits when reproduction is unavailable.
3. Rank plausible causes and identify a probe that could disprove each one. Change one variable per experiment and record the result. Use focused instrumentation without exposing credentials or personal data.
4. Trace the confirmed cause through the relevant boundaries. Check whether the failure comes from inputs, configuration, contracts, state, concurrency, resources, or dependencies before choosing the smallest complete fix.
5. Add or update a meaningful regression check when feasible. Verify that the case can detect the original failure rather than merely confirming the implementation's current shape.
6. Apply the fix and rerun the reproduction plus affected checks. If evidence contradicts the diagnosis, return to the hypotheses instead of stacking speculative fixes.
7. Review the full fix for regressions and security issues. Remove temporary instrumentation introduced by the investigation when it is no longer needed. Review any resulting changes again.

Done when the original behavior is corrected, relevant checks support the fix, and introduced review findings are resolved. Report the cause, evidence, checks actually run, and remaining uncertainty. If blocked, identify the missing access, decision, or evidence needed to proceed.
