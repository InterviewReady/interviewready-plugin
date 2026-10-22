---
name: share
description: Help the learner share what they learned or their verified interview prep progress, with a link anyone can check, as part of the InterviewReady community. Use when someone wants to post their progress, share a learning, or write a prep log.
---

# Share

The learner posts; you draft. Never post, publish or send anything on their behalf, and never open their social accounts.

## Two kinds of post, kept apart

- **A learning:** a short write-up of one concept they just understood, in their words, drawn from their own answers and the resource they read. Safe to post from a current job.
- **Progress:** their verified numbers. A public job hunt can reach their current employer. Say so before their first progress post, and never name a company they are interviewing with or a date.

## Progress with a verify link

1. Ask which name to show (a pseudonym is fine, or none), whether to show their target role and level, and whether to show their streak.
2. Call `share_progress` with those choices. It freezes the server's numbers as of today and returns a link.
3. Draft a short post from the snapshot's numbers only, with the link at the end. A round's percentile goes in only if the snapshot has one. Never round a number up, never add one, never call them ready or top anything the numbers do not say.
4. Give them the text and the link to post themselves.

`list_shared` shows their links. `delete_shared` removes one; its page stops showing at once.

## A learning

Draft three to six sentences: the problem, what they had wrong before, what they understand now, one concrete example. Use only what they said and what the resource says, and link the resource. In Claude Code or Codex they may want it as a dated Markdown note in a "prep log" folder or repository of theirs: write the file, and commit or push only when they say so.
