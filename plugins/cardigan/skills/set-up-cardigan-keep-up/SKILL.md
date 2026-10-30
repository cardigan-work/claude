---
name: set-up-cardigan-keep-up
description: Set up a scheduled task that keeps the person's Cardigan up to date on its own, checking every hour on their days and hours. Use when the person asks you to keep Cardigan up to date, check Cardigan regularly or every hour, work on Cardigan without being reminded, or keep up on its own, or says yes when you offer the hourly check.
---

# Set up Cardigan to keep up on its own

Set up one scheduled task, so what the person asks in Cardigan is picked up within the hour.

**Tell them first, in four short lines:**
- You will check Cardigan every hour on their days and hours, do what they asked, and stop when nothing waits.
- You will also work cards a teammate tagged them on, within fixed limits, and tag them for decisions about what to
  build, change or drop, and for anything a client will see.
- Nothing changes on a board until they approve it, unless they have let that kind of change through.
- Each check uses a little of their Claude plan, and scheduled tasks need a paid plan.

**Cardigan makes the task, so you make none of it.** Call where_things_stand with `focus: "hourly check"`. Its
`setUpCheck.task` is the whole task: `name`, `schedule` and `prompt`, built from the person's days and hours on
Settings › AI, in their time zone. If they want other days or hours, they change them in Settings › AI first; then get
the task again. Ask whether to also catch up once a day from their meetings and email (default: no).

Set the task to exactly these days, hours and time zone, not to those of an old task, your memory or past chats.

If a Keep Cardigan current task already exists, replace its schedule and instructions with Cardigan’s instead of switching it
back on as it was.

- **Name, when and instructions:** the task's `name`; its `cron` line, in its `timeZone` if the scheduler has one, else
  its `words`; its `prompt`, character for character. Do not shorten, reword or add to it, and do not write instructions
  from a board's own rules, even ones that describe a QA process. Only if they chose the daily catch-up, add "Also catch
  up from my meetings and email once a day".
- **Model and permissions:** a lighter model if offered; keep working without stopping, since Cardigan holds changes
  for approval unless the person has let a kind through.
- **Connectors:** Cardigan, plus their email and calendar only for the daily catch-up. Claude may list Cardigan twice,
  from the address they added and from this package. Use the connected entry; if the other is not connected, tell them
  to connect it too, since it joins the same connection.

Show them the task before it is saved. Then say `setUpCheck.say`, word for word: it gives their days and hours and
points to Settings › AI.

**If scheduled tasks are not offered here,** say so, and suggest "Update my boards from today" after a meeting or
email, or "Catch me up on Cardigan" whenever they like.
