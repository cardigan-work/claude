# Cardigan for Claude and Grok

The Cardigan package: the Cardigan connector together with Cardigan's own guides. It gives your AI your boards,
teaches it to draft updates for you to approve, and lets it keep your boards current on a schedule. It works in
Claude and in Grok.

## Add it

### In Claude

1. In Claude, open **Customize › Plugins › Add › Add marketplace**, paste this repository's address, and turn on
   **Sync automatically**, so each new version reaches you by itself.
2. Open **Discover**, find **Cardigan** under New plugins, and press **+** to install it.
3. Connect *Cardigan* under the package's Connectors and sign in. Already connected to Cardigan with its address?
   Connect this one as well: it joins the same connection, and a scheduled task may use either one.

In Claude Code: `/plugin marketplace add cardigan-work/claude`, then `/plugin install cardigan@cardigan`. The package's
connection asks you to sign in once: type `/mcp`, choose *cardigan*, then *Authenticate*.

Then, in a new chat, say *Set up my Cardigan*, or type `/cardigan:start`.

### In Grok

Grok reads the guides from one skill file instead of the package.

1. Download `one-file/cardigan/SKILL.md` from this repository. It holds every guide in one file.
2. In a Grok chat, add the file as a skill.
3. In a Grok Bot, ask the bot to save the file's text as a private skill.
4. Connect Cardigan to Grok: [Connect your AI, In Grok](https://app.getcardigan.com/help/connect-your-ai#in-grok).

Then say *Set up my Cardigan*.

To keep your boards current on a schedule, ask Grok to set up Cardigan's hourly check: an Automation in a chat, or a routine in a Bot. All your Grok Bots count as one AI to Cardigan, with one lead and one hourly check.

## Keep it current

With **Sync automatically** on, new versions arrive on their own, and Claude Code gets them at its next session.
Without it, in the Claude desktop app, open **Customize**, then **Plugins**, and click **Cardigan**. Press **Update**,
then start a new chat. A grayed-out **Update** that says **On latest version** means you have the newest one.

In a terminal, Claude Code keeps the copy of the package you first installed, and doesn't fetch a new one by itself. If a command
such as `/cardigan:catch-me-up` or `/cardigan:start` isn't there, or a request says its file was not found, get the
current package:

1. In a terminal, type `claude plugin update cardigan@cardigan`. Or, in Claude Code, type `/plugin`, open
   **Installed**, choose **cardigan**, then **Update now**.
2. Start a new Claude Code session, or type `/reload-plugins` in the one you have open.
3. To get each new version from then on, type `/plugin`, open **Marketplaces**, choose **cardigan**, then
   **Enable auto-update**.

If `claude plugin list` doesn't show `cardigan@cardigan`, add it again with the two commands above
(`/plugin marketplace add cardigan-work/claude`, then `/plugin install cardigan@cardigan`).

The package itself is in [`plugins/cardigan`](plugins/cardigan). This repository is published automatically from
Cardigan's own; changes made here directly are overwritten.
