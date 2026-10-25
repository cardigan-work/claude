---
name: set-up-cardigan-keep-up
description: Set up a scheduled task that keeps the person's Cardigan up to date on its own, checking every hour on their days and hours. Use when the person asks you to keep Cardigan up to date, check Cardigan regularly or every hour, work on Cardigan without being reminded, or keep up on its own, or says yes when you offer the hourly check.
---

# Set up Cardigan to keep up on its own

The person wants what they ask in Cardigan picked up without having to remind you. Set up one scheduled task for it.
With it on, anything they ask in Cardigan during their hours is done within the hour, and Cardigan tells them when to
expect it.

## Tell them first, in four short lines

- You will check Cardigan every hour on their days and hours, do what they asked, and stop straight away when nothing
  is waiting.
- You will also pick up cards where a teammate tagged them or sent one back: answer questions of fact from Cardigan,
  prepare checks, and sort what came back. Anything about direction, or that a customer sees, you tag to them.
- Nothing changes on a board until they approve it in Cardigan, unless they have let that kind of change through. So
  it is safe to let the task keep working without stopping to ask.
- Each check uses a little of their Claude plan. Scheduled tasks need a paid Claude plan.

## Get the task from Cardigan, and copy it

Cardigan makes the task itself, so you make none of it. Call `list_asks` with `setUp` true (or `where_things_stand` with
the focus "hourly check"). The answer's `setUpCheck.task` is the whole task: its `name`, its `schedule` and its `prompt`.
It is built from the person's days and hours on Settings › AI, in their own time zone (weekdays from 8:00 to 18:00 unless
they chose otherwise). If they want other days or hours now, tell them to change them in Settings › AI first, then fetch
the task again.

Set the task to exactly these days, hours and time zone, not to those of an old task, your memory or past chats.

If a Keep Cardigan current task already exists, replace its schedule and instructions with Cardigan’s instead of switching it
back on as it was.

- **Name:** the task's `name`
- **When:** the schedule's `cron` line, in the schedule's `timeZone` if the scheduler has a time zone, so it does not move an
  hour when the clocks change. If the scheduler takes only its own form, enter the schedule's `words`.
- **Instructions for the task:** the task's `prompt`, character for character. Do not shorten it, reword it or add to it,
  and do not write instructions from a board's own rules, even ones that describe a QA process. The only addition allowed
  is "Also catch up from my meetings and email once a day", and only if they chose the daily catch-up. Ask whether they
  want it; the default is no.
- **Model:** if the schedule lets you choose, a lighter one than the most capable: each check reads a little and
  drafts small changes
- **Permissions:** keep working without stopping (auto), because Cardigan holds every change for their approval
- **Connectors:** Cardigan, plus their email and calendar only if they chose the daily catch-up. Claude can list
  Cardigan twice, once from the address they added and once from this package. Choose the one that is connected,
  the one this chat is using. If both are listed and one is not connected, tell them to connect it too (it joins the
  same Cardigan connection), so the task works whichever one it reaches for.

Show them the task to confirm before it is saved. Then say the task's `say` sentence, word for word: it gives their days
and hours and points to Settings › AI in Cardigan.

## If a schedule cannot be set up here

For example on a free plan, or where scheduled tasks are not offered: say so plainly. Suggest they say "Update my
boards from today" after a meeting or email, or ask "catch me up on Cardigan" whenever they like, and that what they
ask in Cardigan waits for them until then.
