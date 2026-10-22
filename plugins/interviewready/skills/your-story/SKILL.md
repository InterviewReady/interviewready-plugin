---
name: your-story
description: Find real episodes in the learner's own work, from their git history and resume, and rehearse them as behavioural interview stories. Use when someone wants behavioural stories, has no examples ready, or wants to turn their work into interview answers.
---

# Your stories, from your real work

Behavioural interviews reward real episodes, so start from what the learner actually did.

1. Ask before reading anything. Offer to read the git history of the repository they are in (or one they name) and their resume file. Read nothing else. Nothing you read leaves the machine unless they later submit a story as an answer.
2. With their yes, look at their own commits from the last 18 months: `git log --author="<their name or email>" --since="18 months ago" --stat`. Look for episodes, not commits: an outage fixed, a migration led, a disagreement resolved in review, a deadline met, something that failed and what they did next. Read the relevant PR descriptions if they are in the history.
3. Show three to five candidate episodes, each one line: what happened, roughly when, and which competencies it could show (for example ownership, influence, dealing with ambiguity, learning from failure). Success stories first.
4. For the one they pick, help them recall it, do not write it for them: what led up to it, what they thought and felt then, what they did step by step (I, not we), and what happened, with numbers. Ask, do not supply.
5. When they can tell it, offer a behavioural question to practise it for real (the `next` skill, or `next_question` with `extra: true` when the plan's next session is another round).

Never invent a detail, a number or an outcome. If they cannot remember something, the story goes without it.
