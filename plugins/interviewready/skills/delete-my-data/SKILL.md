---
name: delete-my-data
description: Delete everything the learner's InterviewReady prep stores about them. Use only when someone asks to delete their prep data, erase their history, or stop InterviewReady keeping their answers.
---

# Delete my prep data

This cannot be undone. Never call `delete_my_prep_data` with `confirm: true` unless the learner said yes in this conversation, after you told them what goes.

1. Tell them exactly what is deleted, from the tool's own description: their plan and sessions, every answer and its score, their job applications, their interview debriefs, and their shared progress snapshots, whose links stop working at once. Their InterviewReady account, courses and sign-in stay.
2. If they only want one shared link gone, `delete_shared` does that; `list_shared` shows the links. Offer it and stop if that is what they meant.
3. Ask for a plain yes to deleting all of it. Anything short of a yes means nothing is deleted.
4. Call `delete_my_prep_data` with `confirm: true`. Report the counts it returns (plans, sessions, answers, applications, debriefs, shared snapshots) as they are.
5. Say that to remove the plugin's access as well, they can sign the server out: in Claude Code, `/mcp`, choose interviewready, Clear authentication; in Codex, `codex mcp logout interviewready`. Deleting the InterviewReady account itself is not something this plugin does.

Starting a new plan later begins from nothing: no levels, no history.
