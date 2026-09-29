---
name: keep-cardigan-current
description: One scheduled check of Cardigan, run by a task the person set up to keep Cardigan current. Use when a scheduled task or the person asks you to check Cardigan, keep Cardigan up to date, or work through what is waiting in Cardigan.
---

# Keep Cardigan current: one check

This runs on a schedule the person set up, often with nobody watching. Keep it short and cheap. **Nothing you draft
changes a board until the person approves it in Cardigan**, so work through what is waiting, but never do more than
was asked.

## Each check

1. **Call `list_asks`.** These are the person's open to-dos for you, oldest first.
2. **If there are none**, and the task did not ask you to catch up (step 4), stop. Answer with one line: "Nothing
   waiting in Cardigan." Call nothing else.
3. **For each to-do**, follow the to-do loop in the working-with-cardigan skill:
   - read only what it is about;
   - draft the change, as one `propose_changes` round when it is more than one change;
   - close it with `answer_ask`, with the draft's `changesetId` and one line.
   - If it is unclear, close it with a one-line question and no draft. Nobody is watching to answer you now.
4. **Only if the task says to catch up as well:** call `list_changes`, then draft **one** round from what happened in
   the person's other connections since the last check, such as their meetings and email. Check `list_proposals`
   with status "waiting" first, so nothing is drafted twice.
5. **Finish with one line:** how many to-dos you answered and whether you drafted a round. The person reads the
   details in Cardigan.

## Never

- Draft something nobody asked for, just to have done something.
- Approve anything. You cannot, and the person decides in Cardigan.
- Close a to-do you have not answered.
- Stop to ask a question in the chat. Nobody is there; ask it through `answer_ask` instead.
