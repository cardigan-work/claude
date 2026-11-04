---
name: tidy-board
description: "Tidy a board: your AI drafts changes for overdue cards, unassigned cards and stalled work."
argument-hint: "[board name]"
---

Tidy my Cardigan board "$ARGUMENTS".

If I named no board, ask me which one, and list my boards.

Call where_things_stand with focus "$ARGUMENTS" and since two weeks ago: it lists cards that changed, only the newest when it says more did. search with board:"$ARGUMENTS" lists its open cards, each with its column, people and due date.

Look for cards past their due date, cards with nobody on them, cards that have not moved in two weeks, and likely duplicates. Never call a card stalled because it is missing from the changed list: only when told it has not moved (fetch it with since set to that day: "Nothing new since").

Send ONE draft with propose_changes for what is clear-cut, and list what needs my judgment instead of guessing. Give each change a why, in a few words ("overdue since Sep 30"). Never archive or delete anything; suggest it instead.

Before moving a card, fetch "board:<id>" for its columns: each project has its own, and some are named their own way (Working, Backlog). Move a card only to a column its project has, and map my words to the closest one.

Work cheaply: every answer comes out of my own AI plan, so read only what you need and open a card only when a line needs explaining.

Setting up boards the way a good project manager would

Board or project. Make a board for each group of people who should see the same work: a client, a strand of the business, a team. A board can be shared on its own; a project cannot. Inside a board, make a project for each phase, workstream or kind of deliverable those same people follow.

Columns. One column for each point where work changes hands or waits. Most boards need four to six: To do, In progress and Done, with a review column if someone checks the work. Add a waiting column if work stops on someone outside: a client, a vendor, an approval. A person is an assignee and a priority is a field; neither is a column.

Field or label. A field when every card has a value and people sort or filter by it: a size, a priority, a client, a cost, a date, a link to the record in another system. A label when it is true of some cards and should catch the eye: a bug, a blocker, a rush. Show at most three fields on the card's face.

Checklist or cards. A checklist when one person does the steps in one go and nobody tracks them apart. Separate cards when a step has its own person, date or wait. Work that repeats gets a checklist the team starts from each time.

Dates. A due date only where a real date exists: the client's, an event's, a filing deadline. A board full of made-up dates teaches people to ignore them.

The board's instructions. Write what a new teammate's AI must know to work here. Say what one card is, who moves cards where and what Done means. Say what to ask a person about, and what never to do. Write them as rules to follow. Under 350 words; one of the three examples is a good start.

Systems outside Cardigan. When the work lives partly in a CRM, an inbox or a shared drive, give the board a link field to the record there, so each card points at it. On setting up, ask once which of those systems you are connected to.

Rules that run themselves. When a pattern shows, offer the ready-made rule that fits, once: cards that sit too long in a column, a card whose waits are all done, a due date arriving.

Someone outside needs to see it. When a client or a boss asks where things stand, offer a dashboard or a shared board, once, and share nothing until your person approves it.

Fewer parts. Every column, field and label is something a person reads on every card. Leave one out when you are unsure, and add it when the work asks for it.

Looking over a board. Look for columns nobody uses, fields nobody fills, labels doing a field's job, cards stuck in one place for two weeks, cards with nobody on them, and likely duplicates. Draft what is clear together, each change with its why. List what needs your person's judgment. Leave alone what a person set up on purpose; suggest a change to it instead of making it. Archive or delete nothing; suggest it.

Tell me in a few lines what you drafted and what you left for me, and whether it is pending in Cardigan or went through on its own, as the reply said.
