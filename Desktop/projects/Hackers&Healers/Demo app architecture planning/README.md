# Tide — Follow-up Operations Copilot

A clickable demo prototype for a primary-care follow-up copilot. Tide reads
EMR Ticklers (Gmail), post-visit scribe actions (Heidi), and past email threads,
then turns them into a reviewable, Ocean-delivered outreach queue — so routine
patient follow-ups stop falling through the cracks.

Built for the **AI in Healthcare Co-Design Event** (uOttawa DFM · TOH DFP ·
Bruyère Health Innovation). Aligns to the COMPASS priorities *"Follow-up & care
plan automation"* and *"Administrative coordination."*

## The demo flow

1. **Dirty inbox** — a physician's inbox buried under 130+ Tickler reminders.
2. **Connect** — link Gmail, Heidi, Ocean, and OSCAR EMR (read-only).
3. **Analyze** — the agent parses messages, clusters them into 6 care-gap
   cohorts, reconstructs stalled follow-ups, and scores confidence.
4. **Sunday review** — a spreadsheet-style board with a pinned urgent lane,
   per-ticket "why due" evidence trail, confidence, channel badges, an editable
   draft drawer, and batch approve-and-send.
5. **Live queue** — new follow-ups stream in async as visits wrap up.
6. **Backfill** — recovered stalled follow-ups the copilot can take over.

> All data is synthetic. No real patient information; nothing is actually sent.

## Running it

**Easiest — standalone file:** open `dist/tide-standalone.html` in any modern
browser. No server, no build, works offline.

**Source version:** serve the folder and open `Tide.dc.html`
(it loads `support.js` and `TideRow.dc.html` from the same directory):

```bash
npx serve .
# then open http://localhost:3000/Tide.dc.html
```

Opening `Tide.dc.html` directly via `file://` may be blocked by browser CORS
rules — use the standalone file or a local server.

## Files

| File | Purpose |
|------|---------|
| `Tide.dc.html` | Main app — all screens, state, and logic |
| `TideRow.dc.html` | Reusable patient-row component for the review board |
| `support.js` | Component runtime (do not edit) |
| `dist/tide-standalone.html` | Self-contained single-file build |

## Tech

Plain HTML + inline styles + a small React-class component runtime. No
dependencies to install for the standalone build.
