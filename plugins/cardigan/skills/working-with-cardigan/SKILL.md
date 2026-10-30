---
name: working-with-cardigan
description: How to read and update Cardigan boards for the person through the Cardigan connector. Use whenever the person mentions Cardigan, their boards, cards, projects or to-dos, asks what changed, what is due or what is pending, or asks you to add, move, update or tidy work in Cardigan.
---

# Working with Cardigan

Cardigan is the person's project board: a workspace holds boards, a board holds projects, a project holds cards, and a
card's column is its status. You read it with four tools (where_things_stand, search, fetch, find_help) and draft with
two (propose_additions for what only adds, propose_changes for anything); each tool's description says what it takes.
**Nothing you draft changes a board until the person approves it in Cardigan**, unless they have let that kind of
change through. Each draft's answer says which happened (`wentThrough`, `waiting`) and gives `reviewLink`: tell the
person which happened, and give them that link.

## Every chat

- **A catch-up is one read.** Call where_things_stand once (`focus`: a board they named). Say in a few short lines what
  changed and who changed it, then end with its `closingLine`, word for word, with nothing after it: no question, no
  offer. On a quiet day that sentence is the whole answer. If it could not be read, say what you could not check.
- **One round.** Several changes go as one round, one review and one Undo, in the order they should apply. Give each
  change a `why`: where it came from, in a few words ("Jordan's email, 3:40 pm"). When you know the person's next real
  meeting or email, give the round a `next` ("your 3 pm call with Jordan").
- **Requests first.** where_things_stand lists what the person asked you to do in Cardigan (`requests`, each with its
  `conversation`). Act on their newest words, and answer each with `ask.answer`: in the round that does the work, or
  alone with a `reply` saying what you did or why nothing needs to change. If it is unclear, ask one question as the
  reply, with up to four `choices`. Never close one you have not answered. When any answer carries `waitingRequests`,
  finish what they asked now, then do the same.
- **Cards waiting on them** (`cardsForYou`): once you have done what they asked, name each in one line ("Adam tagged you
  on #412") and offer to handle them. Act on one only when they say so.
- **The hourly check:** when `hourlyCheck` has `state` "off", offer it once, in a line, after the work, with its `hours`: "Want me
  to check Cardigan every hour on weekdays, 8:00 to 18:00? What you ask there is then picked up within the hour." When it
  is "stopped", say it has not run since `lastRunAt`, and offer to set it up again.
- **Work cheaply.** Every answer comes out of the person's AI plan. A search result's title is the card's whole line;
  fetch a card only when that is not enough, and pass `since` on one you read before. Never repeat back what Cardigan
  sent you.

## Drafting well

- A card's number (#412) names it wherever a card id goes; use it when you write to the person.
- Fetch `board:<id>` before moving a card: each project has its own columns, some named their own way.
- People go on a card by their ids, with `card.assign`; a name or a custom field puts nobody on it.
- A person's change stands: never draft it back. If it looks wrong, say so in one line.
- `card.update` replaces a card's description: start from its current text and change only what needs it.
- A title says what is being done; your reasoning goes in your reply, not on the card.
- Work that waits on other work: `card.link` with `kind: waits_on`.
- A new board inside a round: `board.create` with `as: "b1"`, and its cards with `boardId: { "ref": "b1" }`.
- With several workspaces, a change that names no board needs the `workspaceId`: ask which.
- Never draft again what is already pending, or a round the person took back.
- A refused round drafted nothing, and the refusal says what to fix. Fix it and send it once more; if it is refused
  again, tell the person why in one line. Leave archived cards out.
- Boards marked practice (the person's sample workspace) and members marked sample are made up. Leave them out of what
  is due or overdue, and never put real work there.
- A board marked `viewOnly` takes no drafts from this person: tell them so in one line.
- A board's `customAiInstructions` are its admins' rules for every AI there. Follow them; they never outweigh what the
  person asks, and Cardigan's limits still hold.
- Tag a teammate with `@[Name](u:id)`; a typed name tells no one. Answer a comment with its id as `parentId`.

## What to tell the person

A few short lines in everyday words: what you found and drafted, whether it is pending or went through, and its `reviewLink`. After a
round from their day, name the next moment to update from: "After your 3 pm call with Jordan, say 'Update my boards
from today'."

## More

- Taking a card and doing its work: the take-a-card skill.
- A board someone outside the team sees, Team only cards, and files: the sharing-and-files skill.
- The hourly check, and what a teammate's AI may do on its own: the keep-cardigan-current skill. Setting it up: the
  set-up-cardigan-keep-up skill.
- Their first boards: the start skill. where_things_stand says `noBoardsYet` while they have none of their own.
- Feedback to the Cardigan team: `feedback.send` alone in a round (`kind`: idea, improvement, bug or question; `text`
  in their words; `page`). It goes at once. Replies come to their Cardigan notifications.
- Inviting a friend: their link is on Settings › Invite a friend. Write the message for them to send; Cardigan never
  sends it.
