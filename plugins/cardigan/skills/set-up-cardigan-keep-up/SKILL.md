---
name: set-up-cardigan-keep-up
description: Set up a scheduled task that keeps the person's Cardigan up to date on its own, checking every hour. Use when the person asks you to keep Cardigan up to date, check Cardigan regularly or every hour, work on Cardigan without being reminded, or keep up on its own, or says yes when you offer the hourly check.
---

# Set up Cardigan to keep up on its own

The person wants what they ask in Cardigan picked up without having to remind you. Set up one scheduled task for it.
With it on, anything they ask in Cardigan is done within the hour, and Cardigan tells them when to expect it.

## Tell them first, in three short lines

- You will check Cardigan every hour, do what they asked, and stop straight away when nothing is waiting.
- Nothing changes on a board until they approve it in Cardigan, unless they have let that kind of change through. So
  it is safe to let the task keep working without stopping to ask.
- Each check uses a little of their Claude plan. Scheduled tasks need a paid Claude plan.

The default is every hour, every day. If they want something else (only on weekdays, only working hours, every two
hours), use the closest schedule offered here. The shortest a scheduled task allows is hourly.
Ask whether to also catch up once a day from their meetings and email; the default is no.

## Then set up the task

- **Name:** Keep Cardigan current
- **When:** every hour, every day, or what they chose
- **Permissions:** keep working without stopping (auto), because Cardigan holds every change for their approval
- **Connectors:** Cardigan, plus their email and calendar only if they chose the daily catch-up
- **Instructions for the task:** "Use the keep-cardigan-current skill. Call list_asks with scheduledRun saying how
  often this task runs (for example everyHours 1, days "every day"). Work through my open Cardigan to-dos, draft each
  one, and close each with answer_ask. Stop when nothing is waiting." Add "Also catch up from my meetings and email
  once a day" only if they chose it. If they chose other days or hours, put them in scheduledRun too (days
  "weekdays", from and to as HH:MM in their time).

Show them the task to confirm before it is saved. Then say one line: "Done. I'll check every hour. Tell me any time to
change that."

## If a schedule cannot be set up here

For example on a free plan, or where scheduled tasks are not offered: say so plainly. Suggest they ask "catch me up
on Cardigan" whenever they like, and that what they ask in Cardigan waits for them until then.
