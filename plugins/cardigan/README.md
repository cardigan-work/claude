# Cardigan for Claude and Grok

Cardigan keeps your boards current from your own work. Your AI drafts the changes, you approve them, and the people
you share with see where things stand. This package teaches it how to work with Cardigan well.

## What it does

- **Sets up your first boards from your own work.** In a new chat, say *Set up my Cardigan*. Claude offers to read your
  email and calendar from the last two weeks, your calendar only, or what you tell it. It shows you what it found,
  asks a few questions about the gaps, and lays out a board for each client or line of work for you to approve.
- **Works with your connection to Cardigan.** Connect *Cardigan* under Claude's Connectors and sign in to your Cardigan
  account. There is no key or password to copy.
- **Teaches Claude how Cardigan works.** It learns to catch you up, draft changes for your approval, answer your
  requests, take a card and do its work, and share a board or add a file. Each guide loads only for its own job, so it
  uses little of your plan.
- **Keeps your boards current on its own, if you want.** Ask your AI to *keep Cardigan up to date*, or say yes when it
  offers, and it sets up a task that checks Cardigan every hour on weekdays from 8:00 to 18:00, so what you
  ask there is picked up within the hour. You change the days and hours in Cardigan, on Settings › AI. Claude runs it
  as a scheduled task, which needs a paid plan. Grok runs it as an Automation in a chat or a routine in a Grok Bot.
- **Ready-made requests**, in the **/** menu of a chat and of Claude Code: *Set up my Cardigan*, *Catch me up*,
  *Update my boards from today* and *Tidy a board*.

## Set up in one chat

Say *Set up my Cardigan* to Claude. It runs one chat of about five minutes, asks one round of questions, and sends Cardigan everything at once for you to approve in one visit.

## In Grok

Grok reads the same guides through the connection, so there is nothing to install. To keep them in Grok anyway, the
steps to add the skill file `one-file/cardigan/SKILL.md` are in the [repository's README](../../README.md#in-grok).

## Nothing changes without you

Drafts from your AI are pending in Cardigan for your approval, unless you have let that kind of change go through. You can
take them back later.

## What it sends

Your AI reads your boards and sends its drafts to Cardigan at `app.getcardigan.com`, as you, through the connector you
signed in with. Cardigan doesn't read your email, meetings or documents. It reads them through its own connections, and Cardigan receives only the changes it drafts, with a short note on where each came from. This package contains only instructions and the connector's address. It runs nothing on your computer.

## Keep it current

With **Sync automatically** on, new versions arrive on their own, and Claude Code gets them at its next session.
Without it, in the Claude desktop app, open **Customize**, then **Plugins**, and click **Cardigan**. Press **Update**,
then start a new chat. A grayed-out **Update** that says **On latest version** means you have the newest one.

In a terminal, Claude Code keeps the copy of this package you first installed. If a command such as `/cardigan:catch-me-up` isn't
there, type `claude plugin update cardigan@cardigan` in a terminal, then start a new session. To get each new version
from then on, type `/plugin`, open **Marketplaces**, choose **cardigan**, then **Enable auto-update**.

## Help

Everything you can ask: <https://app.getcardigan.com/help/your-ai-and-cardigan>. Connecting:
<https://app.getcardigan.com/help/connect-your-ai>
