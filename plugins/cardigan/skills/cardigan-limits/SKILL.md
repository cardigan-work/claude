---
name: cardigan-limits
description: "What one import to Cardigan can hold, what Cardigan refuses, and the form the import takes. Read it before sending a new person's setup to Cardigan."
---

<!-- Written by npm run plugin:build from app/lib/mcp/guides/cardigan-limits.ts. Edit the guide there. -->

# Cardigan's limits, and the form of the import

## Limits

- A person can have at most 10 workspaces.
- A workspace can take at most 20 boards in one import.
- One import can hold at most 5,000 cards.
- People on a card must already be members. You cannot invite anyone.
- You cannot share a board, make a dashboard or make a rule in what you send now. Do not promise them in the chat. Offer one at a later update, when it fits.
- Nothing is on a board until the person approves it in Cardigan. They cannot approve a new workspace from the chat.
- A board's custom AI instructions are four short lines, and the person's own instructions are two. Together a board's lines hold at most 350 words.
- The hourly check runs every hour inside the days and hours the person chooses. Shorter hours give fewer checks.
- Team only hides a card from people outside the workspace, such as a guest. It hides nothing from a teammate. Which teammates can open a board is set for each board, by the person, after they approve.

## What a board can hold

Projects, columns, cards, due dates, labels, custom fields, milestones, checklists, links, Team-only cards, and cost and budget.

## The form

Send what you built with propose_additions, in this order. Leave out what you do not use.

1. **Each workspace:** `workspace.create`, alone in its draft, with its `name` and a `from`: what you read, in a few words ("14 emails and 6 meetings"). Put your one line on who this is set up for in the draft's `summary`. The answer gives back the new `workspaceId`. The workspaces of one send are approved together, in one approval.
2. **Each board:** `board.from_file`, one board a draft, with that `workspaceId` and a `file` in the shape below. Send the boards straight after their workspace, without waiting for a go-ahead. The person approves a workspace and its boards together, in Cardigan.
3. **The person's own part:** `person` on the first `workspace.create`, with `howIWork`, `askFirst` ("Nothing yet" when they gave none), `approval` (`review`, `big` or `full`) and `hourlyCheck` (`{ "days": "weekdays", "from": "08:00", "to": "18:00" }`; leave it out when you cannot run it). Each line holds at most 300 characters. They are saved when the person approves.

```json
{
  "board": { "name": "", "modules": "budget", "instructions": { "card": "", "columns": "", "done": "", "contact": "" } },
  "people": [{ "ref": "p1", "name": "", "userId": "" }],
  "fields": [{ "ref": "f1", "name": "", "type": "TEXT | NUMBER | CURRENCY | RATING | SELECT", "options": [{ "name": "" }], "onCardFace": false }],
  "labels": [{ "ref": "l1", "name": "" }],
  "milestones": [{ "ref": "m1", "title": "", "endDate": "YYYY-MM-DD" }],
  "projects": [
    {
      "ref": "pr1",
      "name": "",
      "baseBudget": 0,
      "columns": [{ "key": "todo", "label": "To do" }, { "key": "doing", "label": "In progress" }, { "key": "done", "label": "Done", "isDone": true }],
      "cards": [
        { "ref": "c1", "title": "", "column": "todo", "why": "where it came from", "dueDate": "YYYY-MM-DD", "cost": 0, "teamOnly": false, "assignees": ["p1"], "labels": ["l1"], "fieldValues": [{ "field": "f1", "text": "" }], "milestone": "m1", "checklists": [{ "title": "", "items": [{ "text": "" }] }], "links": [{ "url": "", "title": "" }] }
      ]
    }
  ],
  "cardLinks": [{ "from": "c1", "to": "c2", "kind": "WAIT" }]
}
```

- A `ref` is a name you choose, used only inside the file. A card's `column` is a column's `key`. Its `assignees` are `people` refs, its `labels` are label refs, its `milestone` is a milestone's ref, and a value's `field` is a field's ref.
- A person in `people` needs their `userId`, from search.
- `modules: "budget"` tracks cost and budget on the board. A card's `cost` and a project's `baseBudget` are whole numbers.
- `options` is for a SELECT field only. A value goes in `text` for a TEXT or SELECT field, and in `num` for a NUMBER, CURRENCY or RATING field.
- A card's `why` holds at most 160 characters.
- `instructions` is the board's custom AI instructions, four lines: `card` is what one card is, `columns` what each column means, `done` what Done means, and `contact` who to ask about this board. Each holds at most 300 characters and no rule: no "ask", "never" or "always". An Admin approves them with the board.
- `cardLinks` holds the cards that wait on other cards of the same board: `from` waits on `to`.

For a person who joined a workspace someone else runs, send no workspaces. Send only `person.set_up` with `person`, as in step 3, alone in its draft and, with their yes, one propose_changes draft that puts them on the cards that are theirs and adds the work of theirs that is on no board yet. For each card that is theirs: `card.assign` with the `cardId` and `userIds: ["me"]`. For each piece of work that is on no board yet: `card.create` with the `boardId`, the `title`, the `column` and the `dueDate`, if it has one. Each change has a `why`. Say that these wait for their yes in Cardigan. Make no board there. The boards are for whoever runs the workspace to lay out.

For a person who already has boards in Cardigan, make nothing twice. Send changes to what is there, beside or in place of new workspaces: one propose_changes draft for each workspace, each change with a `why`. fetch "kinds:<board id>" lists every kind of change with its fields.

<!-- guide version 7288b39bc3 -->
