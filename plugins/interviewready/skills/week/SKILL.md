---
name: week
description: Show the learner's InterviewReady prep plan for today, this week or the whole plan, with pace against the interview date. Use when someone asks about their plan, schedule or what is coming up.
---

# The plan

Call `get_plan` with `show` set to `today`, `week` (default) or `all`, whichever they asked for.

Show from the result only:

- Days to the interview and the pace code in plain words (not started, on track, behind, well behind), with sessions done of sessions due.
- The sessions as a table: date, round, kind, questions done of target, status. Overdue pending sessions first, marked overdue.
- Skipped sessions with their reason, if any.

Offer the next step: start the next due session (the `next` skill) or move one (the `skip` skill).
