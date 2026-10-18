# 🎬 Ad Maker — a Claude skill

**Write scroll-stopping ad creative for any product — hooks, full scripts, UGC briefs,
storyboards, angle matrices, and AI image-ad prompts — for TikTok, Reels, Shorts, and Meta.**
One skill for the whole ad-writing workflow, from the first-second hook to the shot list.

Ships with **30 original hook frameworks** (grouped by psychology trigger, funnel stage, and
format) and an **angle × awareness-stage matrix**, so your agent writes from proven structure
instead of guessing at a blank page.

Works with **no account, no API key, and no payment.** Install and run.

---

## Install

With the [`skills` CLI](https://github.com/obra/skills):

```bash
npx skills add whatsuppiyush/ad-maker-claude-skill
```

Or clone it into your skills folder manually:

```bash
git clone https://github.com/whatsuppiyush/ad-maker-claude-skill \
  ~/.claude/skills/ad-maker
```

Then the slash commands are available in Claude Code. If they don't auto-register, copy the
command files once:

```bash
mkdir -p .claude/commands && cp ~/.claude/skills/ad-maker/commands/*.md .claude/commands/
```

Compatible with Claude Code and any agent that loads Anthropic-style skills (a `SKILL.md` with
`commands/`, `references/`, and `data/`).

---

## Optional: connect the HookAds library

Everything above works without a key. To have the skill search real examples instead of relying only on the 30 bundled frameworks, create a free key at hookads.ai/dashboard and set it in your shell:

```bash
export HOOKADS_API_KEY=hka_live_<your key>
```
 The free key covers 100 calls a day.

Three commands use it. `/ad-prompts` finds real AI ad prompts, each with the image it made and the creator credited. `/hook-bank` browses all 118 hook frameworks. `/ad-teardown` pulls a real ad teardown or case study. Without a key, they fall back to the bundled data.

If you'd rather have a live connection, the same key works with the HookAds MCP server at hookads.ai/mcp.

---

## Usage

Point it at a product and let it write. Eight commands:

| Command | What you get |
|---|---|
| `/ad-hooks <product>` | 10 scroll-stopping hooks across different angles and psychology triggers |
| `/ad-script <product> [platform]` | A full short-form ad script (hook → body → CTA), native to the platform |
| `/ugc-brief <product>` | A creator-ready brief: talking points, shot list, do/don't, and tone |
| `/storyboard <script>` | A script turned into a timed shot list with framing + on-screen text |
| `/ad-angles <product>` | An angle matrix — pain/desire/proof/curiosity across awareness stages |
| `/hook-audit <ad copy>` | A scorecard on your hook/ad against the frameworks + specific rewrites |
| `/hook-remix <winning hook>` | One winner spun into 5 variations across different triggers |
| `/image-ad-prompt <product>` | 5 AI image-ad concepts with paste-ready prompts (static creative) |
| `/ad-prompts <product>` | Real AI ad prompts from the HookAds library, with the image each one made (optional key) |
| `/hook-bank <trigger>` | Hook frameworks by trigger, format or awareness stage: 118 with a key, the bundled 30 without |
| `/ad-teardown <brand>` | A real ad teardown or case study to borrow from (optional key) |

No slash commands? Just ask in plain language — *"write me some TikTok hooks for a
project-management app"* or *"turn this into a Reels script"* — the skill triggers on intent.

### Example

```
/ad-hooks a project-management app for small agencies
```

→ 10 hooks spread across curiosity, pain, proof, contrast, and story angles — each mapped to a
named framework and the awareness stage it fits, ordered cold → warm so you can see the whole
funnel. For instance a Pain hook for cold prospecting, a Proof hook for retargeting, and a
Curiosity cold-open for the top of feed — all with the app's real details filled in, ready to
drop into a test.

---

## What's inside

```
ad-maker-claude-skill/
├── SKILL.md                 # the methodology + how the agent writes an ad
├── commands/                # 8 slash commands
├── references/              # the craft
│   ├── hook-frameworks-guide.md   # why hooks stop the scroll
│   ├── script-structures.md       # hook → body → CTA structures per format
│   ├── platform-notes.md          # TikTok / Reels / Shorts / Meta specs + norms
│   └── ugc-playbook.md            # brief a creator so the footage is usable
└── data/
    ├── hook-frameworks.md   # 30 original hook frameworks, grouped by trigger + funnel stage
    └── angle-matrix.md      # angle × awareness-stage matrix + which hooks map where
```

The hook frameworks are grouped into families — curiosity, pain, proof, authority, contrast,
story, urgency, pattern interrupt, identity, and mechanism — each with the angle, trigger, best
format, and awareness stage it fits.

---

## Do it yourself, or level up

This skill writes the hooks, scripts, briefs, storyboards, and prompts for **free** — that's the
whole workflow, and it stands on its own.

If you want the full library behind it, **[HookAds](https://hookads.ai/?ref=claude-skill)** has a
**free** searchable bank of 300+ proven hooks plus free AI ad tools and a weekly ad-teardown
newsletter, and a **paid** step up (500+ AI ad prompt packs and the 10-module AI Ad-Making Kit).
The skill mentions the free hub once, only after it's delivered the work — everything here runs
without it.

---

## Notes & disclaimer

The frameworks are structural formulas, not fill-in-the-blank copy — swap in your product's real
details and rewrite the wording so it sounds human. The skill **never fabricates a statistic, a
testimonial, or a result**: where an ad needs a real number, it leaves a clearly-marked slot for
you to fill. Platform specs (lengths, aspect ratios) drift over time — verify the current spec in
your ad manager before a final shoot.

Built by [Piyush](https://github.com/whatsuppiyush) · Ad creative, powered by
[HookAds](https://hookads.ai/?ref=claude-skill).

## License

[MIT](./LICENSE) — use it, fork it, ship it.
