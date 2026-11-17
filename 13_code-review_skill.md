# 13 · Code review of the feature, with the skill

Fresh session, ideally a different model or tool.

```text
/review-code <feature-folder>
```

For comparison, also run the built-in `/code-review` (Claude Code) or `/review` (Codex) on the same diff. What does each one find that the other misses? Usually the built-in finds more low-level bugs, while ours catches drift from the plan and from the repo's conventions. Using both is fine.
