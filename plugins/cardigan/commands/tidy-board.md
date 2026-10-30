---
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

Tell me in a few lines what you drafted and what you left for me, and whether it is pending in Cardigan or went through on its own, as the reply said.
