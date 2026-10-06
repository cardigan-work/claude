# Cardigan for Claude

The Cardigan package for Claude: the Cardigan connector together with Cardigan's own guides for Claude. It gives
Claude your boards, teaches it to draft updates for you to approve, and lets it keep your boards current on a
schedule.

## Add it

1. In Claude, open **Customize › Plugins › Add › Add marketplace** and paste this repository's address.
2. Open **Discover**, find **Cardigan** under New plugins, and press **+** to install it.
3. Already connected to Cardigan with its address? Keep that connection: the package's guides use it, and a second
   *Cardigan* under Connectors needs no connecting. Otherwise, connect *Cardigan* there and sign in.

In Claude Code: `/plugin marketplace add cardigan-work/claude`, then `/plugin install cardigan@cardigan`. The package's
connection asks you to sign in once: type `/mcp`, choose *cardigan*, then *Authenticate*.

Then, in a new chat, say *Set up my Cardigan*, or type `/cardigan:start`.

The package itself is in [`plugins/cardigan`](plugins/cardigan). This repository is published automatically from
Cardigan's own; changes made here directly are overwritten.
