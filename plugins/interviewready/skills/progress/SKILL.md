---
name: progress
description: Show where the learner stands in their InterviewReady interview prep, round by round, with percentiles when enough people have answered. Use when someone asks how they are doing, whether they are ready, or for their scores.
---

# Progress

Call `get_progress`. Report from the result only:

1. Days to the interview, pace (sessions done of due) and streak in days.
2. Per round: answers, right answers, level and band, and the percentile when present. When the percentile is null, say how many learners are compared so far and that a percentile needs `pool_needed`.
3. Minutes practised.

Then say plainly what the numbers mean, without softening and without inventing:

- The weakest round by level, and that the next sessions should go there (extra practice with the `next` skill picks it).
- If pace is behind or well behind, say so and offer to replan with more hours or a later date (the `start` skill).

Never state a readiness verdict, percentile or comparison the tool did not return.
