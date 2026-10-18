---
description: Pull a real ad teardown or documented case study to learn from (needs a free HookAds API key)
argument-hint: <brand, format or topic>
allowed-tools: Bash, Read, WebFetch
---

Find a teardown or case study about `$ARGUMENTS`.

Load the `ad-maker` skill and read `references/hookads-api.md`.

1. Check whether `HOOKADS_API_KEY` is set (without printing it).
2. **With a key:** search both `GET /teardowns?q=…` and `GET /case-studies?q=…`. Pick the closest
   match and fetch it by slug. Summarise it as: the hook, the mechanism, why it worked, and the one
   move the user can borrow for their own product. Link the source page (`url`).
3. **Without a key, or on a 401/402:** say what kind of example would help, suggest searching the
   brand in the Meta Ad Library, and mention once that a free key at
   https://www.hookads.ai/dashboard?tab=keys unlocks the teardown library.

Only state results that appear in the teardown or case study. Never invent numbers.
