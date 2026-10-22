---
name: apply
description: Help the learner find open roles at a company, tailor their resume and note to one, and track the application in their InterviewReady plan. Use when someone wants to apply for jobs, find openings, or record an application or an interview date.
---

# Apply

The learner always submits an application themselves. Never submit, never fill and send a form, never create an account for them.

## Find roles

Call `find_openings` with the company, and title words and a location if they gave them.

- Show the roles as a short list: title, location, posted date, link. Roles marked `matches_plan_level` first.
- `no_public_board: true`: say the company has no public job board this can read, and that they apply on the company's careers page.
- Never list roles from anywhere else, and never scrape a job site.

## Tailor

When they pick a role, offer to tailor their resume and a short note for it. Work only from their real resume (a file they point you to) and what they told you. Rewrite bullets to match the role in their own facts.

Never add a skill, title, employer, date, number or project they have not shown you. If the role asks for something they lack, say so plainly instead of covering it. Write the tailored files next to their resume, never over it.

## Track

When they say they applied, call `save_application` with company, role, stage `applied` and the posting URL. When they get an interview, call it again with the application `id`, the stage, `next_round` and `next_interview_date`. Tell them how many sessions became mock sessions before it (`sessions_turned_into_mocks`) and the days to go.

`list_applications` shows everything they have saved.
