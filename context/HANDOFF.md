# Handoff

How agents hand work to each other, so nothing gets lost between sessions. Seeded from the shared record, November 2026.

## The fixed handoff form

Every return ends with a handoff note in this form:

1. **Who did it** — which agent did the work.
2. **What's done** — what is finished, with evidence for important claims.
3. **What's next** — what remains to be done.
4. **Who's next** — which agent (or Roy) is up next.

Plus a **one-sentence summary** of what changed, at the end of every session.

## Rules for every handoff

- Label unknowns as unknown. Do not fill a gap with a guess.
- Report failures honestly. Never pretend something succeeded.
- Every important conclusion needs supporting evidence — a source and a date for prices and facts.
- Agents may challenge each other's findings. A challenge is normal work, not a conflict.
- Start a session by reading the latest shared notes. End it with the summary and handoff above, so the shared record stays current.

## How work flows

1. Roy gives one instruction to Muse.
2. Muse breaks it into tasks and assigns them.
3. The assigned agent does its task and returns the result with a handoff note.
4. Muse checks the work, including having agents check each other's findings, and reports once to Roy.
5. Roy approves or redirects. Nothing consequential moves without his yes.

## Sprint rounds

Each sprint round is one handoff cycle: Gemini researches and returns its findings with a handoff note; Muse verifies, corrects, and records the round in `rounds.json` with its own handoff note. The round entry fields are defined in the README (`rounds.json` schema).
