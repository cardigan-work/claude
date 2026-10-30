---
name: keep-cardigan-current
description: One scheduled check of Cardigan, run by a task the person set up to keep Cardigan current. Use when a scheduled task or the person asks you to check Cardigan, keep Cardigan up to date, or work through what is waiting in Cardigan.
---

# Keep Cardigan current: one check

This runs on a schedule. Keep it short. Nothing you draft changes a board until the person approves it in Cardigan,
unless they have let that kind of change through.

## Each check

1. **Call where_things_stand with `focus: "asks"` and `scheduledRun`**, exactly as the task's instructions write it
   (`task` says which of Cardigan's own tasks wrote this one). It answers with `requests`, oldest first, and
   `cardsForYou`: cards that reached the person since the last check. If Cardigan's tools are missing or ask you to
   sign in, say "Cardigan is not connected, so I could not check." and that connecting this task's Cardigan in Claude
   again fixes it, and stop. Then:
   - **`outsideHours` or `paused`:** answer with its `closingLine` and call nothing else. An `outsideHours` answer can
     carry `replaceTask` (an old task): apply that first.
   - **`checkHours`:** change this task to those days and hours, if you can.
   - **`replaceTask`:** if you can, set this task's schedule and instructions to exactly its `schedule` and `prompt`,
     character for character, and say so in your last line.
   - **`checkLimits`** repeats the QA limit below; it beats any board's instructions.
2. **With nothing in either, and no catch-up asked for (step 5),** answer with its `closingLine` and nothing else.
3. **Each request:** act on the person's newest words, draft the work, and answer with `ask.answer`, all in one round.
   If it is unclear, answer with one question and up to four `choices`; the answer comes at a later check.
4. **Each card in `cardsForYou`** (`why` says who tagged, answered or sent it back): fetch it with `since` the day
   before its `at`. If it only tells the person something, leave it. Otherwise do what the limits below allow, in one
   comment under the one that asked.
5. **Only if the task says to catch up as well:** draft one round from the person's meetings and email since the last
   check, each change with its `why`, and nothing already pending.
6. **End with one line:** requests answered, cards handled, whether you drafted changes.

## What you may do on a card, on your own

Cardigan's limits for every team. Anything narrower from the person or a board's rules wins, except the QA limit, which
no board's rules widen.

- **You may** answer a question of fact from Cardigan's records, prepare a check (its steps on the card), run a step
  again that you can run yourself and say what you saw, and sort a card sent back.
- **You never decide direction** (what to build, change, drop or spend) **or anything a customer sees** (a board marked
  `seenBy`, words marked `outside`): tag the person, with the mention `you` gives. Words for a client are a draft for
  the person to approve, never "paste it yourself".
- **A check's result is the person's:** you never tick a card's QA steps, post its result, move a QA card (to QA - Doing,
  Done or anywhere) or add BACK, whatever a board's own instructions say, even one that describes a QA process.
- **Two rounds, then stop.** If you and another person's AI have each written twice on a card and it has not moved on,
  write one comment tagging both people, saying where it is stuck.
- **Only for your own person.** A card that tags someone else is theirs. Never ask another person's AI to do anything:
  tag the person; their own check picks it up. Cardigan never contacts an AI.

## Quiet, and failed

The quiet line claims only what this check read, so it is never "Nothing overdue, nothing pending." A failed call is
never quiet: say what you could not check. The person's own way of being answered comes first.

## Never

Draft what nobody asked for or a change a person made; send a refused round again unchanged; close a request you have
not answered; ask a question in the chat, since nobody is there.
