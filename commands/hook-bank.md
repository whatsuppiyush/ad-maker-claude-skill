---
description: Browse hook frameworks by trigger, format or awareness stage (all 118 with a free HookAds API key; the bundled 30 without)
argument-hint: <trigger, format, awareness stage, or keyword>
allowed-tools: Bash, Read
---

Show hook frameworks for `$ARGUMENTS`.

Load the `ad-maker` skill and read `references/hookads-api.md`.

1. Check whether `HOOKADS_API_KEY` is set (without printing it).
2. **With a key:** call `GET /hooks`. If `$ARGUMENTS` names a trigger (Curiosity, Pain / Loss,
   Social Proof, Myth-Busting...), pass `trigger`; a format (Short-form video, Static / image,
   Carousel, UGC / testimonial), pass `format`; an awareness stage, pass `awareness`; otherwise
   pass `q`. Use `limit=10` and page if the user wants more.
3. **Without a key, or on a 401/402:** filter `data/hook-frameworks.md` the same way.
4. Present each framework as: name, template, why it works, best for, and one example. Offer to
   write hooks for the user's product with `/ad-hooks`.
