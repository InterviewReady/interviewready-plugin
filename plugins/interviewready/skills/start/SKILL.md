---
name: start
description: Start or replace an InterviewReady interview prep plan. Use when someone wants to prepare for interviews, plan a job switch, or set an interview date, role or target companies.
---

# Start a prep plan

You are setting up the learner's dated interview prep plan on InterviewReady. The `interviewready` MCP server keeps the plan, picks every question, times it and grades it. You collect the inputs and present the result.

If they already have a plan and want to change part of it (a date, hours, companies), follow the `replan` skill instead.

## 1. Ask, in one message

Ask these five together, and say any can be skipped:

1. The role they are preparing for (for example backend, frontend, full stack, ML or AI engineer, engineering manager).
2. Their level: mid, senior, staff or principal.
3. Target companies, one or more.
4. The interview date, if they have one. No date means a six week plan.
5. Hours a week they can practise.

Do not ask for their timezone if you can read it. In a terminal, `readlink /etc/localtime` ends in the IANA name (for example `.../zoneinfo/Asia/Kolkata` gives `Asia/Kolkata`); on Linux `cat /etc/timezone` may hold it. Do not use `date +%Z`: it gives an abbreviation like IST, which the server cannot read. If you cannot find an IANA name, ask which city they are in and pass the matching name.

## 2. Make the plan

The rounds are ai_engineering, system_design, coding and behavioural.

Call `start_plan` with what they gave. Pass `rounds` only if they asked for specific rounds; otherwise leave it empty so every round the server can grade today is included.

If the tool says to sign in, tell them to connect the InterviewReady server (in Claude Code, `/mcp`, choose interviewready, Authenticate; in Codex, `codex mcp login interviewready`), sign in with their InterviewReady account, and try again. Then stop.

## 3. Show it

From the tool result only:

- Interview date and days to go.
- The rounds in the plan. If `rounds_not_served_yet` is not empty, say those rounds are not available yet and the plan covers the others.
- This week's sessions as a short table: date, round, kind (diagnostic, practice, mock), questions.
- How many questions each round's bank holds (`questions_in_bank`).

Then offer to start today's first session. If they say yes, follow the `next` skill.

Never invent a session, a date or a number that the tool did not return.
