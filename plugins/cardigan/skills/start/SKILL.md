---
name: start
description: "Sets up Cardigan with a new person in one chat: gathers how they work, agrees a layout and sends Cardigan one import for them to approve. Use when the person says \"Set up my Cardigan\", asks to set up Cardigan or their first boards, or has no board of their own in Cardigan yet."
---

<!-- Written by npm run plugin:build from app/lib/mcp/guides/start.ts. Edit the guide there. -->

Set up my Cardigan: my first boards, from my own work. Use the Cardigan connector. Show me what you find before you draft anything.

# Setting up Cardigan with a new person

In one chat of about five minutes, learn how this person works, agree a layout with them, and send Cardigan one import. The person then finishes in Cardigan in one visit. Never send them back and forth between this chat and Cardigan.

Read guide:setting-up-cardigan first. It holds the rules of thumb, what done looks like, and the lists of pattern and framework guides. Read guide:cardigan-limits before you send anything.

## The chat, in order

1. **Say what will happen.** You set Cardigan up here, in this chat, in about five minutes. Then they approve it in Cardigan. Nothing goes on a board until they approve it. Say that this chat is the whole setup: if they stop before you send, nothing is kept. If you cannot run a scheduled task, say so now, in one sentence: you will update Cardigan first each time they open you.
2. **Gather context before you ask.** Start from what they typed on Cardigan's welcome page, if anything: where_things_stand gives it as theirWords. Use what you already remember about them. Offer what to read: their email and calendar from the last two weeks, the calendar only, or what they tell you. Offer email or a calendar only if you can read it through your own connections. Say: "Cardigan doesn't read your email. I read it, and send Cardigan only what I draft." If they say no, or you can read nothing, ask one question: "What is the next thing you have due, and who is it for?" Do not press about reading. From then on, build only from what they let you read and what they say. If they chose the calendar only, use nothing from their email.
3. **Show what you found,** as Sure and Not sure, grouped the way they group their work. Ask about the gaps only. Then always ask: "What is on that I did not find?" Two weeks of email never holds everything.
4. **Find out how they work, in one round of questions.** Ask at most three questions, as short lines, with no sub-questions. In the whole chat, ask at most eight questions. Never ask what you can work out from what you read, and never ask again what they skipped. Before you show a layout, have at least three pieces of work the person named, or their word to build with less. Every client they name gets its place in the layout. If you found no work for a client, or cannot tell which client a piece of work is for, ask, in one question for all of them. Say what you assumed. If what you read shows the person passing on someone else's decisions, ask once whose work this is. You need:
   - what keeps getting dropped;
   - everything on the go, to the end of each piece of work, and what each waits on;
   - who each piece of work is for, and whether each client, engagement or event is for a different client;
   - who needs to see where it stands;
   - where the work lives, and which of those places you can read;
   - what they use you for today;
   - who hands them work, and who they hand it to.
5. **Ask the two settings, once each, in Cardigan's words.** Put them at the end of the message that shows the layout, so the person answers everything in one reply. Never ask either one a second time.
   - "How much may I change on your boards without asking?" Offer the three choices evenly, and steer toward none. Never choose for the person, and never fill a setting in to save a turn. If they do not answer, Cardigan's own starting choice stays, and you say so: Manually approve (you approve every change), Auto-approve small changes (everyday changes go straight on), Auto-approve all (everything that can be undone goes straight on).
   - "Shall I check Cardigan every hour on weekdays, 8:00 to 18:00?" Ask this only if you can run a scheduled task. Say in a few words what the check does for them. If they want fewer checks, such as once each morning, offer shorter hours, such as 8:00 to 9:00. Set the check up in this chat. Never leave it for after they approve.
6. **Pick the guides that fit.** Open the framework guide for their kind of customer, if one fits, and the pattern guide for each area of work they have.
7. **Build first, then show exactly what you built.** Write what you will send to Cardigan before you show anything. Then show the person all of it: one line on who you set this up for, written fresh for this person, then every workspace, board, project, column, field, label and milestone, each with one reason in their words, and the true counts of boards and cards. Send nothing they have not seen. Ask whether to send it. If they want a change, change it here and show only what changed. For a person who writes one line at a time, show the layout as a short list: one line for each workspace and board with its reason in a few words, and the counts. Show it once. Do not repeat the counts or the layout in later messages. Once they say yes, change nothing, and send in your very next message. If you find you must change something, show the change and ask again.
8. **Send once.** What you send holds the workspaces, boards and cards, the custom AI instructions for each board, the person's own instructions, the two settings choices and your one-line summary. Send each workspace with propose_additions and `workspace.create`, alone in its draft; the first carries the person's own part in `person`. Then send each of its boards with propose_additions and `board.from_file`, one board a draft, with the `workspaceId` the workspace gave back, straight after the workspace and without waiting for a go-ahead. guide:cardigan-limits gives the fields. Every card and every checklist step comes from their real work and says where it came from. Never invent work, and never add an empty placeholder. A card is a piece of work this person does. A meeting on a calendar is not a card by itself. If you cannot tell what they owe before or after it, ask or leave it out. Never make up a follow-up. Stay inside Cardigan's limits. If their work does not fit, say what you left out and why.
9. **Close, in the message that sends.** Say "sent" only when you have sent. Count from what you sent, and say those numbers. Say whether the hourly check is on. Say what is left for them in Cardigan: approve the boards, check the two settings and review the AI instructions. It is one visit of a few minutes. Promise nothing for after they approve: anything Cardigan cannot take now, you offer at a later update, without asking them to come back.

## The two sets of instructions

Fill in these lines, and write nothing outside them.

- **The person's own instructions** have two lines: how I work; what to ask me first or never do. Every rule goes in the second line, once. The first line says how they work, and names no client, colleague, product, project or date. Write only what the person told you in this chat. If they gave no rule, the second line says "Nothing yet".
- **A board's custom AI instructions** have four lines: what one card is; what each column means; what Done means; who to ask about this board (the person themselves, unless they named someone else who is in Cardigan). A board's lines hold no rule: no "ask", no "never", no "always".
- Show the person their two lines in the layout, so they see them before you send. Send them as shown.

## When the person differs

- **They say no to the layout a second time.** Stop. Your whole next message is these words and nothing else: "Which one thing would make it right?" Offer no layout, and no question that describes one. Build the next layout only from their answer.
- **Their answers are a few words.** Switch at once to one short question in each message: "What is due next on that?" "Who else do you work for, even a small job?" "What is waiting on someone else?" "What else is due before the end of the month?" Keep going until you have three pieces of work, or they say build. A piece of work is something to do. A client's name alone is not one, and you never make a card to hold a client's place. For this person you may ask ten questions in all. After five short questions, build with what you have. Never tell the person to start a new chat.
- **They want it built now.** Stop asking and build from what you have. Say what you assumed. Something you read that clashes with a date they care about goes on the board as a card, not left out.
- **A date is missing.** Make the card with no date. Never make a card that only asks the person for a date.
- **The talk wanders.** Come back to the goal.
- **They joined a workspace someone else runs.** Build no workspace and no board. Read the boards they can open, without asking which exist. In your first answer after reading, tell them which cards there look like theirs, by board, and leave everyone else's cards out. Also list the work you found in what you may read, such as their calendar, that has no card. With their yes, put their name on their cards, and add the missing work as cards on the board it belongs to. Say which work has no board yet. Ask one question in each message, the two settings included. Set up their own AI instructions, by that name, and their two settings. In the close, say what waits for their yes in Cardigan: their name on those cards, and any new cards. They have no boards to approve.
- **You cannot run a scheduled task.** You said so at the start. Do not ask about the hourly check. If they push back, answer once, with one small routine: when they open you, they say "Update my boards from today", and you bring every board up to date in one go and show what moved. Cardigan's morning email, with what is due, is their reminder. If they raise it again, answer with one line, "Understood. The hourly check stays off, and 'Update my boards from today' covers it.", and go on. Leave it out of the layout. In the close, say "The hourly check is off." and nothing more about it. Give no cause you have not checked.
- **They already have boards.** Tidy what is there. Make nothing twice.
- **They came back in a new chat.** Ask Cardigan what is left with where_things_stand, which answers `setup` (what is done and what is left), and pick up there. If nothing was sent yet, say that you kept nothing from the earlier chat. Then read what you can again, and ask only what is still missing.
- **They own a workspace with a team.** Before the layout, ask about the team: each role, and each hand-off between roles. Ask it even when they are in a hurry, as one question. If they do not answer, write the roles as you see them from what you read, as one line in the layout for them to correct.
- **You guessed their kind of work wrong.** Say so, and change the layout in the chat.
- **Cardigan cannot do what they asked.** Say so in one sentence before you send, and offer the nearest thing. Wait for their yes.

## Rules

- Owner or Admin is the person's place in Cardigan. It says nothing about their job, or whether they work alone. Take both from what they tell you and what you read. What they say in this chat wins over anything else.
- Use Cardigan's words for its parts, with their meaning. Team only hides a card from people outside the workspace. It does not hide a card from a teammate. A board that only some teammates can open does that.
- Speak to the person in their words. Say "what I send to Cardigan". Never say "the import", "a board file" or "a scheduled rule" to them, and never explain how Cardigan is built.
- Tie nothing you will do to a day of the week.
- Use each part you can give a reason for, and leave the rest out. A milestone that repeats a card's due date is not a reason.

<!-- guide version 55ae62fa7a -->
