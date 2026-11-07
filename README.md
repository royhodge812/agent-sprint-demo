# agent-sprint-demo

A public demo of two AI agents working together in rounds, where anyone can watch the work happen.

## What this repo is

- **The demo:** Muse (lead coordinator) and Gemini (research and verification) improve the Hotel Brendle lobby display loop, round by round, in public.
- **The shared agent context:** the `context/` folder holds the team roster, the approval gates, and the handoff format the agents work from. It is seeded from the real shared record (repo `royhodge812/agent-shared-context`), not invented for this demo.
- **The sprint board:** `index.html` is the front page. It explains the demo, lists the team and the gates, and renders the rounds table from `rounds.json`.

Repo name is proposed (`agent-sprint-demo`), not yet confirmed. Nothing here has been pushed or published yet.

## How the sprint works

- **2 hours, 8 rounds, one round every 15 minutes, then it stops.**
- Each round does one real unit of work: Gemini researches one new item for the lobby loop, Muse checks every fact against real sources and corrects what is wrong, and the loop gains one new verified addition.
- **No fake changes.** If a round cannot verify something, it reports that instead of inventing an update. A round that finds nothing verifiable is recorded as such — the table shows it, the loop does not change.
- After the sprint, the loop returns to a weekly rhythm. Lobby content does not naturally change every 15 minutes; the fast pace exists so people can watch the machine work.

## The lobby loop

The Hotel Brendle lobby loop is a rotating display for the hotel lobby in Robstown, Texas — general information and videos only. It currently has 11 slides: a welcome message, a Community Board, Being Good Neighbors, a landmark slide (designated 1984, Marker No. 2571), Around Robstown (including Church of Grace and Route 27 / Stop 1266), two reserved slots for the "Fixing the Brendle" video series, and the sign-off "Be careful kids, have fun."

**Guardrail: the loop never shows tenant names, rent amounts, or any private data.** It is general information only.

Putting the loop on the actual lobby TV needs Dane's yes — he owns the building. This repo and the preview are the plan and the demo, not an install.

The hardware half of the lobby display (screen, player, and mount prices) is a separate approved task, LOBBY-01. It is not part of this repo.

## The team

- **Roy** — owner. Sets goals, makes decisions, gives the final yes on anything consequential.
- **Muse** — lead coordinator. Breaks goals into tasks, hands them out, checks the work, reports back once.
- **Copilot** — planning and quality checking.
- **Gemini** — research and verification.
- **ChatGPT** — strategy, drafting, and analysis.
- **Grok** — stress-testing.

## Approval gates (short version)

Nothing consequential moves without Roy's explicit yes on that specific item: no spending, sending, posting, publishing, filing, provisioning, deleting, sharing publicly, changing an account, or signing. Silence is never a yes. Items that time out are held, not approved. Muse may approve internal, reversible steps only (Medium after 72 hours' notice, Low after 24 hours), and every such approval is logged so Roy can review or reverse it. Full policy in `context/APPROVALS.md`.

## rounds.json schema

`rounds.json` holds one object: `{"rounds": [...]}`. Each entry in the `rounds` array has these fields:

| Field | Meaning |
|---|---|
| `round` | Round number, 1–8. |
| `time` | Time the round finished, in Central Time (e.g. `"2026-11-07 09:45 CT"`). |
| `gemini_found` | What Gemini's research returned this round, in plain words, with its source. |
| `muse_verified_or_corrected` | What Muse checked, what was confirmed, and what was corrected — including anything Gemini got wrong. |
| `change_made` | What actually changed in the lobby loop this round. If nothing could be verified, this says so and no change is recorded. |
| `status` | One of: `complete`, `no-verified-change`, `failed` (with the reason in `change_made`). |

The front page (`index.html`) reads this file and renders one table row per round. Rounds that have not happened yet show as placeholders.

## Why this demo works

This exact loop has already run once for real: on 2026-11-07, Gemini researched camera prices through the API and Muse's verification caught real errors (a substituted kit model, connectors priced per piece instead of per pack, an unconfirmed price) before anything was recorded as verified. The sprint applies the same loop to the lobby loop, in public, every 15 minutes.
