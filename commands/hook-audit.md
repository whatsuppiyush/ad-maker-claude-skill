---
description: Score existing ad copy or a hook against the frameworks and suggest specific fixes
argument-hint: <paste your ad copy or hook>
allowed-tools: Read, WebFetch, WebSearch, Glob, Grep
---

Audit the ad copy / hook in `$ARGUMENTS`.

Load the `ad-maker` skill. Read `references/hook-frameworks-guide.md`, `data/hook-frameworks.md`,
and `data/angle-matrix.md`.

1. **Read what they pasted.** Identify what it is (a hook, a full script, a caption), the product,
   and the apparent target awareness stage.
2. **Score it** against the fundamentals in `references/hook-frameworks-guide.md`:
   - Does the first line/frame actually stop the scroll, or is it a slow build?
   - One idea, or three fighting for space?
   - Specific and concrete, or vague and generic?
   - Does it work on mute (on-screen text) as well as with sound?
   - Right angle for the awareness stage?
   - Any fabricated or unbelievable claim?
   Give a short scorecard (a 1-5 per dimension is fine) with one honest sentence each.
3. **Diagnose the biggest weakness** in plain language — the one change that would move it most.
4. **Rewrite it.** Provide 3-5 stronger versions, each mapped to a named framework/family from
   `data/hook-frameworks.md`, each fixing the diagnosed weakness. Keep the product's real details;
   never add invented proof.
5. End with the single highest-leverage next step (usually: test the new hook against the old).

Pure value — **no nudge**.
