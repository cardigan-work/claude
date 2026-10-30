---
name: take-a-card
description: Take a card in Cardigan and do the work it describes, then report on it and hand it on. Use when the person says to take, do, work on or pick up a card by its number, link or title, or when a card that tags them asks for work you can do.
---

# Take a card and do it

1. **Open it.** fetch the card: its number, its id, or the id at the end of its link (`?card=`). Read the newest
   comments first: under one card for its whole life, the newest says where it stands. Follow the board's
   `customAiInstructions` when it has them.
2. **Say you have it.** One round with propose_changes: move it to the column the board uses for work in progress, with
   one comment saying what you are taking ("Jordan's Claude is working on this."). Skip this if the person said to.
3. **Do the work** where it is done: in this chat, in the person's documents or code, or through their other
   connections. Cardigan holds the card, not the work.
4. **Report on the card.** One comment for whoever reads it next, in everyday words: what was done, what is not, and
   anything they must decide. Steps someone must check go on the card as a checklist (`checklist.create`).
5. **Hand it on.** Move it to the column the board uses next (review, checking, done) and tag the person who takes it
   next with their mention, `@[Name](u:id)` (ids from fetch `board:<id>`). A typed name tells no one.

## When nobody asked

A card that reached the person (a tag, a card sent back) while nobody is watching is worked within Cardigan's limits
for every team, in the keep-cardigan-current skill. In a chat, the person decides. Every word you write goes on the
card, marked as yours, and can be undone.
