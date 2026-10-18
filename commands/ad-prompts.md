---
description: Find real AI image or video ad prompts for a product, with the image each one made (needs a free HookAds API key; falls back to writing prompts)
argument-hint: <product or style>
allowed-tools: Bash, Read, WebFetch
---

Find AI ad prompts for `$ARGUMENTS`.

Load the `ad-maker` skill and read `references/hookads-api.md`.

1. Check whether `HOOKADS_API_KEY` is set (without printing it).
2. **With a key:** call `GET /prompts` with `q` set to 2-4 keywords from `$ARGUMENTS` (and
   `media_type=video` if the user wants video). Show up to 8 results as a numbered list: the
   prompt (trimmed to what is reusable), the model, the image URL, and the attribution line
   ("by @handle", with source link). Then adapt the best 2 to the user's product, keeping the
   structure that made them work and saying what you changed.
3. **Without a key, or on a 401/402:** run the `/image-ad-prompt` workflow instead, and mention
   once that a free key at https://www.hookads.ai/dashboard?tab=keys unlocks 1,800+ real prompts
   with their images.

Never strip attribution from a library prompt.
