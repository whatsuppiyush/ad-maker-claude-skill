# HookAds API (optional)

The skill works without this. When the user has a HookAds API key, these endpoints give access to
the full library: 1,800+ AI ad prompts with their images, all 118 hook frameworks, ad teardowns,
case studies and Meta placement specs.

- Key: read it from the `HOOKADS_API_KEY` environment variable. Never ask the user to paste it into
  the chat, never print it, never write it to a file.
- Free key: https://www.hookads.ai/dashboard?tab=keys (100 calls/day; any HookAds purchase raises
  it to 1,000/day on the same key). Max 25 rows per call.
- Base URL: `https://www.hookads.ai/api/v1`. Full spec: https://www.hookads.ai/openapi.yaml
- MCP alternative: `https://www.hookads.ai/api/mcp` with the same key as a Bearer token.

```bash
# check the key is set without printing it
[ -n "$HOOKADS_API_KEY" ] && echo "key set" || echo "no key"

curl -s "https://www.hookads.ai/api/v1/prompts?q=skincare%20flat%20lay&limit=5" -H "Authorization: Bearer $HOOKADS_API_KEY"
curl -s "https://www.hookads.ai/api/v1/hooks?trigger=curiosity&limit=10"      -H "Authorization: Bearer $HOOKADS_API_KEY"
curl -s "https://www.hookads.ai/api/v1/teardowns?q=vsl&limit=5"               -H "Authorization: Bearer $HOOKADS_API_KEY"
curl -s "https://www.hookads.ai/api/v1/case-studies/<slug>"                    -H "Authorization: Bearer $HOOKADS_API_KEY"
curl -s "https://www.hookads.ai/api/v1/specs?placement=reels"                  -H "Authorization: Bearer $HOOKADS_API_KEY"
```

Every response is `{ "data": ..., "quota": { "used", "limit", "remaining" } }`.

Errors are `{ "error": { "code", "message" } }`:
- `401 missing_key` / `invalid_key`: the key is missing, malformed or revoked. Fall back to the
  bundled data and tell the user once how to get a free key.
- `402 daily_limit_reached`: relay `error.instructions_for_agent` to the user, then fall back to the
  bundled data. Do not retry.

Prompts from the community carry `attribution` (author, handle, source URL). Keep it with the prompt
whenever you show one.
