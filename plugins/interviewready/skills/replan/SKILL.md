---
name: replan
description: Change the learner's InterviewReady prep plan without losing what they have done. Use when someone has a new interview date, wants more or fewer hours a week, new target companies, or different rounds.
---

# Change the plan

A new plan replaces the old one on the server. What the learner has done carries over: every answer and its level per round, and the real interviews they told you about (the days before each still become mock sessions). A round they have already answered starts with practice, not another diagnostic. The new plan starts today; sessions finished under the old plan are not listed in it.

1. Call `get_plan` with `show: week`. If it says there is no plan, follow the `start` skill instead.
2. Ask what changes, unless they already said: interview date, hours a week, companies, rounds, role or level.
3. Call `start_plan` with the changed fields and every other field as the current plan has it (`role`, `level`, `companies`, `interview_date`, `hours_per_week`, `rounds`, `timezone`). If the current interview date has passed, the tool refuses it: ask for a new date or leave it empty for six weeks.
4. Show, from the tool result only: the interview date and days to go, this week's sessions (date, round, kind, questions), and the pace. Say in one line that their answers, levels and real interviews carried over.

If the change is a new real interview with a company, use the `apply` skill to save it instead: an application's interview date reshapes the plan without replacing it.
