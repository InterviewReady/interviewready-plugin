---
name: next
description: Serve the learner's next InterviewReady interview question, take their answer, and give feedback from the server. Use when someone asks what is next, wants to practise, continue their prep, or answer a question.
---

# The next question

The `interviewready` MCP server picks the question, starts its clock, grades the answer and compares it with other learners. You run the conversation around it. Everything the learner is told about their score, time or standing comes from a tool result.

## 1. Get the question

Call `next_question`.

- `status: question`: show it (step 2).
- `status: debrief_due`: a real interview in `debrief_for` has passed. Follow the `debrief` skill for it first, then come back here.
- `status: done_for_today`: say today's sessions are done, name `next_slot` (date and round), and offer extra practice. If they want it, call `next_question` with `extra: true`.
- `status: bank_exhausted`: say plainly that every question in that round's bank has been answered and the bank is being grown. Offer another round with `extra: true`.
- An error saying there is no plan: follow the `start` skill.

## 2. Show the question

- The stem exactly as served. Show `code` in a code block if present.
- The options with their ids: `a)`, `b)`, ... For a design question the ids are component names; show the text.
- `multiple_answer: true`: say that more than one option can be right.
- `kind: capacity`: they answer with one whole number in the stated units. Invite them to reason out loud first, then give the number.
- `kind: coding`: show the statement and the `samples` (input and expected output). Ask which language they want (python, javascript, java, cpp, go, csharp, typescript). In a terminal app, write the matching `starter` code to a new file in a scratch folder (for example `interviewready/<problem>.py`) and tell them to solve it there in their editor; elsewhere show the starter in a code block. They may run the samples locally. When they say done, read the file and submit its full contents as the answer with `language`. Never write or fix the solution for them.
- `kind: behavioural`: ask the question as served. They answer with one real story in their own words. If the story is thin, probe with the served `follow_ups`, one at a time, never suggesting content. What the course asks of a story: a real time from the last 12 to 18 months, told in order like a film replayed, saying "I" not "we", what they thought and felt then, what they did, and what happened, with numbers. Start with success stories before failures. Submit everything they said about it, joined, as the answer.
- The time box in minutes or seconds. If `seconds_so_far` is above zero the question was already open: say the clock kept running.

Then wait. Do not answer it, do not narrow the options, do not hint. If they ask for a hint, give the smallest one that helps and keep count.

## 3. Submit

As soon as they answer, call `submit_answer` with `attempt_id`, their answer (option id, comma-separated ids, or the number) and `hints_used`. Do not correct or improve their answer before submitting.

## 4. Feedback

From the result, in this order, short:

1. Right or wrong. If wrong, the correct answer. Then the `explanation` in your own words, tied to what they chose.
   - Coding: from `code`, whether it compiled (show `compile_output` if not), cases passed of total, how many hidden cases failed, and each failed sample's input, expected and got. Then the target complexity from `correct_answer`.
   - Behavioural: each of the five `criteria` (real episode, own action, intent, competency at the tipping level, result) as met or not, with the grader's reason, and the one change that would most improve the story.
2. Time: their seconds against the time box. If `paused` is true, say it was left open and does not count as slow. If `median_seconds_when_right` and `faster_than_percent_of_right_answers` are present, give them. If they are null, say how many people have answered right so far (`right_answers_compared`) and that a comparison needs `pool_needed`.
3. This question: `percent_right` across others when present; otherwise how many others answered (`answered_by_others`) of the `pool_needed`.
4. Their round level and band. The round percentile when present; otherwise how many learners are compared so far.
5. Next difficulty: harder after a right answer, easier after a wrong one.
6. The `resource`, as one line with its link. Recommend nothing else and never make up a link.
7. Session progress: questions done of the target. When the session is complete, give the pace code from the result in plain words (on track, behind, well behind).

Then ask if they want the next question. If yes, go back to step 1.

## Rules

- Never estimate a percentile, a median or a level the tool did not return.
- Never reveal a question before `next_question` serves it, and never reuse an `attempt_id` after its feedback.
- One question at a time.
