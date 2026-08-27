---
name: bughunt
description: One-time, read-only daily bug and staleness hunt. Invoke explicitly with $bughunt.
---

# $bughunt

Run a bounded pass on demand, suitable for a daily cleanup. Do not edit, stage, commit, push, or install anything. Inspect recent changes and high-signal code paths for reproducible bugs, stale references, dead configuration, misleading documentation, and tests that no longer match behavior. Limit exploration to a small set of likely-impactful findings; do not turn housekeeping into a repository-wide rewrite. Report each finding with severity, file/line, evidence, and a suggested next action, separating confirmed defects from hypotheses. This skill is read-only and never imposes a per-task gate.
