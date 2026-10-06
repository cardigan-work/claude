# Cardigan for Claude

Cardigan is a project board — workspaces, boards, projects and cards — where the work your AI does is seen,
approved and shown to other people. This package connects Claude to your Cardigan account and teaches Claude how to
work with it well.

## What it does

- **Sets up your first boards from your own work.** In a new chat, say *Set up my Cardigan*. Claude offers to read your
  email and calendar from the last two weeks, your calendar only, or what you tell it. It shows you what it found,
  asks a few questions about the gaps, and lays out a board for each client or strand of work for you to approve.
- **Connects Claude to Cardigan.** Already connected with Cardigan's address? Keep that connection: these guides use
  it, and the package's own *Cardigan* entry needs no connecting. Otherwise, connect *Cardigan* on the package's
  Connectors tab and sign in to your Cardigan account. There is no key or password to copy.
- **Teaches Claude how Cardigan works:** how to catch up cheaply on what changed, how to draft updates as one round,
  each change saying where it came from, and how to work through the to-dos you give it in Cardigan and close each one.
- **Keeps your boards current on its own, if you want.** Ask Claude to *keep Cardigan up to date*, or say yes when it
  offers, and it sets up a scheduled task that checks Cardigan every hour, so what you ask there is done within the
  hour. Scheduled tasks need a paid Claude plan.
- **Ready-made requests:** *Set up my Cardigan*, *Catch me up*, *Update my boards from today*, *Tidy a board* and
  *Keep up*.

## Start from something specific

Say one of these to Claude, or your own. The ones that read your email or calendar need Claude connected to them.

<!-- Examples: written by npm run plugin:build from app/lib/mcp/startGuide.ts. Edit them there. -->
- **For a consultant**
  - *A board for each client from my last two weeks of email* (reads your email)
  - *Set up my week from my calendar* (reads your calendar)
  - *Pull the to-dos out of this call transcript*
  - *Make a board from this proposal: every deliverable with its date*
  - *Track what each client is waiting on from me* (reads your email)
- **For a founder**
  - *My fundraise from investor emails: who’s at which stage* (reads your email)
  - *A launch plan from this product doc*
  - *Bring over my Trello export and tidy it*
  - *What my cofounder and I agreed this week, from email and our calendar* (reads your email)
  - *What I promised investors in last month’s update, as cards* (reads your email)
  - *Hiring from my calendar invites and the recruiter’s emails* (reads your email)
  - *A board from these meeting notes*
  - *Everything due before our board meeting, from my calendar* (reads your calendar)
- **For anyone**
  - *Turn the plan we made in this chat into a board*
<!-- End of the examples. -->

## Nothing changes without you

Everything Claude drafts waits in Cardigan for your approval, unless you have let that kind of change go through on
its own. You can take a whole round back later.

## What it sends

Claude reads your boards and sends its drafts to Cardigan at `app.getcardigan.com`, as you, through the connector you
signed in with. Cardigan never sees your email, meetings or documents. Your AI reads those through its own
connections. This package contains only instructions and the connector's address. It runs nothing on your computer.

## Help

<https://app.getcardigan.com/help/connect-your-ai>
