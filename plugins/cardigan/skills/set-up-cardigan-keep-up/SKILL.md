---
name: set-up-cardigan-keep-up
description: Set up a scheduled task that keeps the person's Cardigan current on its own. Use when the person asks you to keep Cardigan up to date, check Cardigan regularly or every hour, work on Cardigan without being reminded, or keep up on its own.
---

# Set up Cardigan to keep up on its own

The person wants their to-dos in Cardigan picked up without having to remind you. Set up one scheduled task for it.

## Tell them first, in three short lines

- You will check Cardigan every hour on weekdays, do what they asked, and stop straight away when nothing is waiting.
- Nothing changes on a board until they approve it in Cardigan, unless they have let that kind of change through. So
  it is safe to let the task keep working without stopping to ask.
- Each check uses a little of their Claude plan. Scheduled tasks need a paid Claude plan.

Ask whether every hour on weekdays suits them, or another interval. The shortest a scheduled task allows is hourly.
Ask whether to also catch up once a day from their meetings and email; the default is no.

## Then set up the task

- **Name:** Keep Cardigan current
- **When:** every hour on weekdays, or what they chose
- **Permissions:** keep working without stopping (auto), because Cardigan holds every change for their approval
- **Connectors:** Cardigan, plus their email and calendar only if they chose the daily catch-up
- **Instructions for the task:** "Use the keep-cardigan-current skill. Work through my open Cardigan to-dos with
  list_asks, draft each one, and close each with answer_ask. Stop when nothing is waiting." Add "Also catch up from
  my meetings and email once a day" only if they chose it.

Show them the task to confirm before it is saved.

## If a schedule cannot be set up here

For example on a free plan, or where scheduled tasks are not offered: say so plainly. Suggest they ask "catch me up
on Cardigan" whenever they like, and that their to-dos wait for them until then.
