---
name: take-a-card
description: Take a card in Cardigan and do the work it describes, then report on it and hand it on. Use when the person says to take, do, work on or pick up a card by its number, link or title, when where_things_stand lists cards handed to your AI, or when a card that tags them asks for work you can do.
---

# Take a card and do it

1. **Open it.** fetch the card: its number, its id, or the id at the end of its link (`?card=`). Read the newest
   comments first: under one card for its whole life, the newest says where it stands. Follow the board's
   `customAiInstructions` when it has them.
2. **Take it.** One round with propose_additions: the kind `card.ai_claim` with the cardId. It goes through at once and
   answers a lease; send that lease in every later `card.ai_*` kind. One AI holds a card at a time, and when another
   holds it the answer says who. A card the person handed to their AI is listed first in where_things_stand
   (`handedToYourAi`): take each of those this way, never with a comment. A comment does not take a card.
3. **Do the work** where it is done: in this chat, in the person's documents or code, or through their other
   connections. Cardigan holds the card, not the work. Say what you are doing now with `card.ai_progress`, and add a line
   with `card.ai_log` for each thing worth keeping. A change you made outside Cardigan goes in with `card.ai_outside`.
4. **Report on the card.** One comment for whoever reads it next, in everyday words: what was done, what is not, and
   anything they must decide. Steps someone must check go on the card as a checklist (`checklist.create`).
5. **End the visit.** Write `card.ai_handoff` (done, open, next, learned): it parks the card until your next visit and
   is what you read first then. A card with nothing written to it for the board's quiet time (30 minutes unless the
   board says otherwise) goes back to the person, and they are told. A card the person took back is theirs; do not take
   it again until they hand it over again.
6. **Hand it on.** Move it to the column the board uses next (review, checking, done) and tag the person who takes it
   next with their mention, `@[Name](u:id)` (ids from fetch `board:<id>`). A typed name tells no one.

## When nobody asked

A card that reached the person (a tag, a card sent back) while nobody is watching is worked within Cardigan's limits
for every team, in the keep-cardigan-current skill. In a chat, the person decides. Every word you write goes on the
card, marked as yours, and can be undone.
