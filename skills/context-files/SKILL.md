# Context Files: Writing and Maintenance

Context is maintained across two file types:

- `sessions/chart.md` — rolling status snapshot; rewritten after every debrief
- `sessions/YYYY.MM/index.md` — session-level lookup table; updated after every debrief

---

## index.md

### Purpose

A quick-lookup record of every session in the month. Used to find "the last upper day" or check top-set weights without reading full session files.

### Format

One section per session, in chronological order. Use a `##` heading with the date and type, then front matter fields as key: value pairs, then a file path.

```markdown
## 2026.04.16 Upper

date: 2026.04.16  
workout_type: upper  
format: gym  
status: completed  
bench_top: 55x8  
lat_pulldown_top: 105x10  
shoulder_press_top: 25x8  
row_top: 95x10  

File: sessions/2026.04/2026.04.16 upper.md

---
```

- If the session is not yet completed, top-set fields may be blank or omitted.
- If a field is not applicable to the session type, omit it.
- Do not use a table or grid format.

### When to update

After every debrief, add or update the entry for the debriefed session. If the month's index file doesn't exist yet, create it.

---

## chart.md

### Purpose

A rolling snapshot of current status. Reading `sessions/chart.md` gives enough foundation to interact with the user without reading individual session files. It is rewritten (not appended) after each debrief so it stays current. It has no time boundary — it reflects the present state of injuries, weights, and patterns regardless of month.

### Format

```markdown
# Chart

_Last updated: YYYY.MM.DD_

## Injury and health status
[What's active, what resolved, what to watch. One paragraph.]

## Current weights

**Upper:** [Current top-set weights for each lift.]

**Lower:** [Current top-set weights for each lift.]

**Core / cardio:** [Current format and benchmarks.]

## Patterns and concerns
[Anything flagged across multiple sessions — fatigue accumulation, technique breakdown, missed sessions, etc. Omit if nothing notable.]
```

### When to update

Rewrite the entire file after every debrief. Do not append — a clean rewrite keeps it readable and concise. Pull facts from the session just debriefed and from the existing chart; do not re-read all session files unless a discrepancy requires it.
