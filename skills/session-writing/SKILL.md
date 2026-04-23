# Workout Log Writing Instructions

You are writing a workout session file that contains both a coaching plan and a user log.

---

## Core principles

- Write a log for **today’s specific workout only**.
- Do **not** produce a generic reusable template unless explicitly asked.
- Before writing the log, use the context already loaded during startup. Additionally, read the most recent session file of the same workout type — go directly to its **Coach’s Notes → Recommendations** section for today’s targets and weight guidance.
- Use those files to set **today’s targets**.

### Session mode awareness

Adjust the session based on user state:

- progression → increase load
- quality → same load, better execution
- conservative → reduce risk, maintain pattern

The log should clearly reflect the chosen mode.

---

## Tone and role

- Write as a practical coach.
- The log should contain coaching guidance, not just blank fields.
- Reduce decision-making during the workout.
- Ask for the data that is most useful for future coaching decisions.

---

## Format requirements

- Optimize for **Obsidian on a phone**.
- Use simple markdown headings and short sections.

### Critical formatting rule

- When returning a workout log in chat, ALWAYS output it inside a markdown code block.
- When writing directly to a `.md` file in the workspace, write normal markdown file contents instead.
- NEVER use rich formatting blocks or UI wrappers.
- The output must paste cleanly into Obsidian with no rendering changes.

### Checkboxes

Yes/no fields must use exactly:

- [ ] yes  
- [ ] no  

Body-part pain lists must also use the same checkbox format.

### Set logging format

- Do not rely on writing `same` in the actual field as the default pattern.
- For each set, prefer this phone-friendly structure:

Set 1  
Target: 100 x 8  
Met target  
- [ ] yes  
- [ ] no  
Actual:  

- This keeps target confirmation fast while still leaving room to record actual weight and reps when they differ.
- `Actual:` may be left blank when the target was met exactly.

---

## What every workout log should include

### 1. Readiness

- date
- sleep hours
- energy before workout
- short coach note about readiness if relevant

---

### 2. Rest guidance

- recommended rest times by exercise type
- a place to note actual rest used

---

### 3. Warmup guidance

- explain the goal of the warmup
- clearly state what stretching is OK
- clearly state what stretching to avoid
- include specific warmup exercises
- include target weights if applicable
- include form cues (placed before targets)

---

### 4. Mid-workout check-in (conditional)

Include only when there is an active injury or health concern that warrants monitoring during the session. The coach decides at planning time whether to include it. When included, place it after the first 2–3 exercises. Omit entirely for standard sessions with no active concern.

---

### 5. Exercise sections

For each lift/exercise include (in this exact order):

1. goal for today  
2. short "Why this target" explanation  
3. form cues (must appear BEFORE targets)  
4. target weight or target range  
5. if target is uncertain, explain exactly how to choose the weight  
6. recommended rest  
7. fields for set 1 / set 2 / set 3 with weight and reps  
8. coaching checks relevant to that exercise  
9. notes field  

---

## Exercise target rules

- Every exercise must have a target.
- Targets should come from:
  1. Coach’s Notes → Recommendations from the most recent session of the same type
  2. today’s readiness
  3. the workout plan and strategy files

- Include a short **"Why this target"** explanation for each exercise.

- If no confident numeric target exists, explain how to determine it, for example:
  - choose a weight that allows 12 clean reps
  - increase one machine increment from last session
  - use a weight where the final set ends 1–2 reps before failure

### Effort targeting

- When appropriate, specify effort targets:
  - “leave 2 reps in reserve”
  - “final set near failure”

- Especially prioritize effort guidance for isolation exercises.

---

## Coaching data priorities

Collect the information most useful for progression and recovery decisions:

- sleep
- energy
- actual weights and reps
- whether the target muscle was felt
- whether technique broke down
- whether pain appeared
- whether the set ended near failure
- whether rest time may have affected performance

Do not ask for extra data unless it is likely to help future coaching decisions.

---

## Post-workout section

### Cooldown

Write a brief cooldown recommendation based on session intensity and any active injury context. Include checkboxes for what was actually done and whether it helped — this is useful data for interpreting next-day recovery. Use the cooldown options listed in the relevant program day file.

Do not include a Next-Day Check-In section. If there is something to flag for the next session, put it in Coach's Notes → Recommendations.

---

### Summary

- workout duration
- overall effort
- energy after workout

### Pain check

Use the body-part list from the relevant program day file for this workout type.

### Replace ambiguous fields

Instead of “strongest / weakest lift”, use:

- best stimulus (which lift felt most effective for the target muscle)
- most limited (which lift was most constrained by technique, fatigue, or setup)

---

## Writing style

- Be concise, but not bare.
- Prefer embedded coaching notes over long explanations.
- Keep cues short and practical.
- Avoid unnecessary filler.
- Avoid generic motivational language.

### Form cue rules

- 2–4 cues per exercise
- one line each
- immediately actionable during a set
- designed to be remembered and applied, not explained

---

## Front matter

Every session file must begin with YAML front matter. Required fields:

```yaml
---
date: YYYY.MM.DD
workout_type: upper | lower | core | cardio | run | recovery
format: gym | home | outdoor
status: planned | completed
rotation: "..."
---
```

The `rotation` field is a short plain-English note placing this session in the program cycle — e.g. `"Upper (day 2; Legs complete)"` or `"Cardio — between Legs and Core"`. It must match the rotation field written in the monthly index entry for this session.

For lifting sessions, include top-set fields for the primary lifts as specified in the relevant program day file. Leave these fields blank when writing the plan — the user fills them in after completing the session. These feed the monthly index and replace the need to reconstruct working weights from log text.

---

## Final check before returning the log

Make sure:
- [ ] it is for **today only**
- [ ] all checkboxes use correct syntax
- [ ] Every exercise has a numeric target (no "light" or "same as before")
- [ ] Every set has a Met target checkbox block
- [ ] Form cues appear before targets on every exercise
- [ ] Post-workout section includes effort, energy, pain check, best stimulus, most limited, and cooldown
- [ ] Readiness section includes sleep hours and energy
- [ ] Front matter includes all required fields with status: planned; date uses dots (YYYY.MM.DD) not dashes
- [ ] Top-set fields are present (blank) for lifting sessions, using the fields from the program day file
- [ ] Mid-workout check-in is present only if there is an active injury or health concern; absent otherwise
