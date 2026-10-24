---
name: keep-cardigan-current
description: One scheduled check of Cardigan, run by a task the person set up to keep Cardigan current. Use when a scheduled task or the person asks you to check Cardigan, keep Cardigan up to date, or work through what is waiting in Cardigan.
---

# Keep Cardigan current: one check

This runs on a schedule the person set up, often with nobody watching. Keep it short and cheap. **Nothing you draft
changes a board until the person approves it in Cardigan**, unless they have let that kind of change go through, so
work through what is waiting, but never do more than was asked or than the limits below allow.

## Each check

1. **Call `list_asks` with `scheduledRun`**, saying how often this task runs: `everyHours` (1 for hourly), `days`
   ("every day" or "weekdays"), and `from` and `to` (HH:MM, the person's time) only if it runs in certain hours. This
   tells Cardigan the check is running, so it can tell the person when to expect answers and when the check stops. The
   answer is the person's open to-dos for you, oldest first, and `cardsForYou`: cards that reached the person since the
   last check.
   - **`outsideHours`** means this run is outside the days and hours the person chose in Cardigan. Stop at once: call
     nothing else, skip the daily catch-up, and answer with one line: "Outside your hours, so nothing was read."
   - **`paused`** means the person paused this check in Cardigan. Stop at once, as for `outsideHours`: call nothing else,
     skip the daily catch-up, and answer with one line: "Paused in Cardigan, so nothing was read." Do not change the
     task or turn it off; the person resumes it in Cardigan.
   - **`checkHours`** means this task runs at other times than the person chose. If you can change this task's own
     schedule, change it to every hour on those days and hours, in that time zone. If you cannot, carry on; Cardigan
     shows the person the sentence that changes it.
2. **If there are neither**, and the task did not ask you to catch up (step 5), stop. Answer with one line: "Nothing new
   was asked since the last check." Call nothing else.
3. **For each to-do**, follow the to-do loop in the working-with-cardigan skill:
   - read only what it is about, and its `conversation` when it has one: act on the person's newest message;
   - draft the change, as one `propose_changes` round when it is more than one change;
   - answer it with `answer_ask`, with the draft's `changesetId` and a line.
   - If it is unclear, ask one question with `answer_ask` and no draft, with up to four `choices` when you can guess the
     answers. Nobody is watching to answer you now; their answer comes back in this to-do at a later check.
4. **Then each card in `cardsForYou`.** Someone tagged the person, answered them, put them on the card, or sent a card
   of theirs back; `why` says which, and who. It counts as work, within the limits below.
   - Read what is new on it: `get_card` with `since` set to the day before its `at`. Read the whole card only if that
     is not enough to act.
   - If it only tells the person something, leave it. Never comment just to have done something.
   - Otherwise do what the limits allow, and say it in **one** comment on the card: `comment_on_card` with `replyTo`
     set to the comment that asked, when one did.
5. **Only if the task says to catch up as well:** call `list_changes`, then draft **one** round from what happened in
   the person's other connections since the last check, such as their meetings and email, each change with a `why`:
   where it came from, in a few words ("Jordan's email, 3:40 pm"). Check `list_proposals` with status "waiting"
   first, so nothing is drafted twice.
6. **Finish with one line:** how many to-dos you answered, how many cards you worked on, and whether you drafted a round.
   The person reads the details in Cardigan. If you did nothing, the line is the one in step 2.

## What you may do on a card, on your own

These are Cardigan's limits for every team. If the person, or a board's own rules, say something narrower, follow that.

- **You may:** answer a question of fact from Cardigan's records (what a card, its comments, its history or a board
  says); prepare a check, such as putting its steps on the card so the person can run it; run a step again that you
  can run yourself, and say what you saw; and sort a card sent back: say what came back and what happens next, and
  put it where the board's rules say.
- **You never decide direction** (what to build, change, drop or spend, or which of two ways to go) **or anything a
  customer sees** (a board marked `seenBy`, a card someone outside the team sees, an answer to a comment marked
  `outside`). Tag the person instead, in one comment saying what they need to decide: `list_asks` gives their mention
  as `you`.
- **A check's result is the person's:** you never tick a card's QA steps, post its result, move it to Done or add BACK,
  whatever a board's own instructions say.
- **Two rounds, then stop.** If you and another person's AI have each written twice on a card about the same thing and
  it has not moved on, stop: one comment tagging both people, saying where it is stuck.
- **Only for your own person.** A card that tags someone else is theirs, even when you could answer it. Never ask
  another person's AI to do something; tag the person, and their own check picks it up.
- Every word goes on the card as a comment, marked as yours, and can be undone. Cardigan never contacts an AI: what you
  write waits there for the other person and their own check.

## Saying it is quiet

The quiet line is a claim, so say it only when it is true:

- **Only for what you read.** This check reads what the person asked of you and the cards that reached them, not overdue
  cards or changes pending their approval, so the quiet line says nothing about those, and never "Nothing overdue, nothing
  pending." *Catch me up* is where they are read.
- **A failed call is never quiet.** If `list_asks` or any other call failed, say what you could not check ("Could not
  reach Cardigan, so I could not check what you asked.") and do not call it quiet. If Cardigan's tools are missing
  or ask you to sign in, say that this task's Cardigan connector in Claude is signed out, and that connecting it
  again in Claude fixes it.
- **The person's way comes first.** If they have told you how they like to be answered, use their way.

## Never

- Draft something nobody asked for, just to have done something.
- Draft back something a person changed by hand.
- Send a refused round again unchanged. It is refused at every check; say why once instead.
- Approve anything. You cannot, and the person decides in Cardigan.
- Close a to-do you have not answered.
- Stop to ask a question in the chat. Nobody is there; ask it through `answer_ask`, or on the card by tagging the person.
