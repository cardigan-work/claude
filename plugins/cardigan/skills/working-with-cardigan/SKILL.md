---
name: working-with-cardigan
description: How to read and update Cardigan boards for the person through the Cardigan connector. Use whenever the person mentions Cardigan, their boards, cards, projects or to-dos, asks what changed, what is due or what is waiting on them, or asks you to add, move, update or tidy work in Cardigan.
---

# Working with Cardigan

Cardigan is the person's project board. You read it and draft changes through the Cardigan connector. **Nothing you
draft changes a board until the person approves it in Cardigan**, unless they have let that kind of change go through
on its own. Each draft's reply says which happened and ends with a link to that draft in Cardigan: tell the person
which happened and **always give them that link**, e.g. "It went through on its own. Review or undo it here: <link>".

## How Cardigan is organized

- A **workspace** holds **boards**; a board holds **projects**; a project holds **cards**.
- A card's **column** is its status (for example *To do*, *In Progress*, *Done*). `list_projects` gives a board's
  projects and their columns. Columns differ from project to project and some have their own names (*Working*,
  *Backlog*): read them before moving a card, never assume them.
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

**Requests waiting, whatever you came for.** When any Cardigan answer carries `waitingRequests`, the person has asked
you something in Cardigan that nobody has picked up yet. After finishing what they asked you now, call `list_asks` and
work through them the same way.

**Offer the hourly check when there is none.** When `list_asks` carries `hourlyCheck` with `state` "off", the person has
no scheduled check, so what they ask in Cardigan waits for a visit like this one. After finishing what they asked,
offer it once, in one or two lines: "Want me to check Cardigan every hour? Anything you ask there gets done within the
hour. Each check uses a little of your plan." If they say yes, use the set-up-cardigan-keep-up skill. If they say no,
drop it. When `state` is "stopped", tell them their hourly check has not run since `lastRunAt` and offer to look at
it or set it up again.

## Work cheaply

Every answer comes out of the person's own AI plan.

- To catch up, call `list_changes`. It returns one line per card for what changed since you last asked. Pass
  `full: true` only when you need each change on its own line.
- For where things stand, call `read_dashboard` with `dashboardId` "standard".
- Open a single card with `get_card` only when a line needs explaining, and use `omit` for the parts you do not need.
- Send changes as **one** `propose_changes` round with a one-line `summary`, not many small drafts.
- Before drafting, check `list_proposals` with status "waiting" so you never draft what is already waiting.

## Drafting well

- **One round, tied to what prompted it.** Each change should be something the person would recognize from their
  day, such as a meeting, an email or their own words.
- **New cards** need a `projectId` and a clear title. Add a due date or assignees only when you know them.
- **Assignees:** `update_card`'s `assigneeIds` is the exact list of who should be on the card. Only the difference is
  drafted, and an empty list takes everyone off.
- **Work that waits on other work:** when a meeting, an email or the person says one thing can't start until another
  is done, draft `card.link` with `kind: waits_on` (or `needed_for` from the other card) in the same round. The card is
  marked on the board, and its people hear when it is ready. Use `related` for context only. A WAITING label is for
  work held up by a person, never by another card. `get_card` shows a card's `linkedCards`; `list_cards` shows
  `waitingOn` on a card that waits on open work.
- **A whole new board:** draft it with `propose_board`, from a Cardigan board file, the format Cardigan's Export
  writes.
- **A new workspace:** draft it with `propose_workspace`.
- **More than one workspace:** when a change names no board, such as a new board or a milestone, and the person has
  several workspaces, ask which one and pass its `workspaceId`.
- **A round the person took back** shows `undoneAt` in `list_proposals`. Do not draft it again unless they ask.
- **Never** archive or delete as a tidy-up. Suggest it instead.

## What to tell the person

Keep it short: what you drafted, in two or three lines, whether it waits for them in Cardigan or already went
through, as the reply said, and the link from the reply's last sentence, as it is. Do not paste what the tools returned.
