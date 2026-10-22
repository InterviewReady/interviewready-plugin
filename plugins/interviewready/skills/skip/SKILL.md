---
name: skip
description: Move one of the learner's InterviewReady prep sessions to the first free day before the interview. Use when someone cannot do a session, wants to skip today, or reschedule.
---

# Skip a session

1. If they did not say which session, call `get_plan` with `show: today` and use the first pending session. Confirm it with them in one line.
2. Call `skip_slot` with its `slot_id` and their reason in their own words.
3. Say where it moved (`moved_to.date`). If `dropped` is true, say no day before the interview was free, so the session is gone, and suggest more hours a week or a later date (the `replan` skill changes the plan and keeps their answers).
