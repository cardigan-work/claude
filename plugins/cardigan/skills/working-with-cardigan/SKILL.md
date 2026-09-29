---
name: working-with-cardigan
description: How to read and update Cardigan boards for the person through the Cardigan connector. Use whenever the person mentions Cardigan, their boards, cards, projects or to-dos, asks what changed, what is due or what is waiting on them, or asks you to add, move, update or tidy work in Cardigan.
---

# Working with Cardigan

Cardigan is the person's project board. You read it and draft changes through the Cardigan connector. **Nothing you
draft changes a board until the person approves it in Cardigan**, unless they have let that kind of change go through
on its own. Each draft's reply says which happened: tell the person that, "It waits for you in Cardigan" or "It
went through on its own; you can undo it from Changes".

## How Cardigan is organised

- A **workspace** holds **boards**; a board holds **projects**; a project holds **cards**.
- A card's **column** is its status (for example *To do*, *In Progress*, *Done*). `list_projects` gives a board's
  projects and their columns.
- Labels belong to one board. Custom fields belong to one board. People go on a card as **assignees**, by the ids
  `list_members` gives, never by name and never in a custom field.
- A person can be in several workspaces. `list_boards` gives every board with its `workspaceId`.

## Start with what the person asked you to do

Before anything else, call `list_asks`. It lists the person's open to-dos for you, oldest first, each with what it is
about: a draft of yours, its cards and boards, by id and by name.

For each to-do:

1. Read what it is about, and only as much of the board as you need.
2. Draft the change, as one `propose_changes` round when it is more than one change.
3. Close it with `answer_ask`: give the draft's `changesetId` as `proposalId`, and one line saying what you did.
4. If it is unclear, do not guess. Close it with a one-line question as `reply` and no draft. The person answers by
   asking again.
5. If nothing needs to change, close it with a one-line `reply` saying why.

Never close a to-do you have not answered.

## Work cheaply

Every answer comes out of the person's own AI plan.

- To catch up, call `list_changes`. It returns only what changed since you last asked.
- For where things stand, call `read_dashboard` with `dashboardId` "standard".
- Open a single card with `get_card` only when a line needs explaining, and use `omit` for the parts you do not need.
- Send changes as **one** `propose_changes` round with a one-line `summary`, not many small drafts.
- Before drafting, check `list_proposals` with status "waiting" so you never draft what is already waiting.

## Drafting well

- **One round, tied to what prompted it.** Each change should be something the person would recognise from their
  day, such as a meeting, an email or their own words.
- **New cards** need a `projectId` and a clear title. Add a due date or assignees only when you know them.
- **Assignees:** `update_card`'s `assigneeIds` is the exact list of who should be on the card. Only the difference is
  drafted, and an empty list takes everyone off.
- **A whole new board:** draft it with `propose_board`, from a Cardigan board file, the format Cardigan's Export
  writes.
- **A new workspace:** draft it with `propose_workspace`.
- **More than one workspace:** when a change names no board, such as a new board or a milestone, and the person has
  several workspaces, ask which one and pass its `workspaceId`.
- **A round the person took back** shows `undoneAt` in `list_proposals`. Do not draft it again unless they ask.
- **Never** archive or delete as a tidy-up. Suggest it instead.

## What to tell the person

Keep it short: what you drafted, in two or three lines, and whether it waits for them in Cardigan or already went
through, as the reply said. Do not paste what the tools returned.
