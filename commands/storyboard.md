---
description: Turn an ad script into a timed shot list — framing, on-screen text, and action per shot
argument-hint: <script or script description>
allowed-tools: Read, WebFetch, WebSearch, Glob, Grep
---

Turn `$ARGUMENTS` into a storyboard / shot list.

Load the `ad-maker` skill. Read `references/script-structures.md` and
`references/platform-notes.md`.

1. **Get the script.** `$ARGUMENTS` is an ad script (or a description of one). If it's thin,
   reconstruct the hook → body → CTA spine first, briefly, so there's something to board. If a
   platform is implied, note it (aspect ratio + length norms from `references/platform-notes.md`).
2. **Break it into shots.** Split the script into discrete shots covering the full runtime. For
   **each shot** give:
   - **Shot #** and **timing** (e.g. 0:00-0:03).
   - **Visual / action** — what's happening on screen, framing (close-up, wide, over-shoulder,
     screen-record, product macro), and any transition.
   - **On-screen text** — the exact words on screen for that shot (kept clear of safe zones).
   - **Voiceover / spoken line** — the audio for that shot.
   - **Purpose** — one word on the job of the shot (hook, agitate, proof, demo, CTA).
3. **Present as a table or a numbered board**, in order, so it reads top-to-bottom as the finished
   ad. Front-load the hook shot (and note 2-3 alternate hook shots to test).
4. Add a short **shot-count / coverage note**: how many distinct clips to capture and where extra
   b-roll helps the edit.

Pure value — **no nudge**.
