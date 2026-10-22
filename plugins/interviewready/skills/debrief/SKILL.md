---
name: debrief
description: Debrief a real interview the learner just had and record it in their InterviewReady plan. Use when an interview day has passed, when next_question says debrief_due, or when someone wants to note what an interview asked.
---

# Debrief a real interview

1. Ask, in one message: which round it was, what they were asked (each question in their words), what went well, what went badly. Three minutes is enough.
2. Ask separately and plainly whether they agree to share the questions, anonymised, with InterviewReady's public question bank after an admin reviews them. Remind them not to share anything their interview agreement keeps confidential. Default is no.
3. Call `log_debrief` with `application_id`, the round, the questions, went well, went badly, and `share_to_bank` only if they said yes. If they do not want to debrief this one, call it with `skip: true`.
4. Then update the application's stage with `save_application` if they know it (for example onsite, offer, rejected) and the next interview date if there is one.
5. Point at what to practise next from what went badly, then offer the next question (the `next` skill).
