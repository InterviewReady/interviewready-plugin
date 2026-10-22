# InterviewReady plugin for Claude and Codex

Interview prep for software engineers from [InterviewReady](https://interviewready.io). It plans your preparation day by day up to your interview date, serves one question at a time near your level, and times and grades every answer on InterviewReady's server, so the score is the same in any app.

## Rounds

| Round | Questions | Graded by |
| :- | :- | :- |
| Coding | Problems with sample and hidden test cases | Running your code against the hidden cases |
| System design | Reference designs from InterviewReady's system design judge, with one component hidden, and capacity estimates | The judge's own answers and bounds |
| Behavioural | The question bank of InterviewReady's AI mock interviewer | The mock interviewer's rubric |
| AI engineering | The adaptive assessment on [aiengg.dev](https://aiengg.dev) | Its answer key |

Each answer sets the difficulty of the next question. A comparison with other learners appears once 30 people have answered a question.

## Skills

| Skill | What it does |
| :- | :- |
| `start` | Asks your role, level, companies, interview date and hours a week, and makes the dated plan |
| `next` | Serves the next question with its time box, takes your answer, and shows the grade, the time, your level, and one resource for what you missed |
| `week` | This week's sessions and your pace |
| `skip` | Moves a session to the first free day before the interview |
| `replan` | Changes the date, hours or companies; your answers, levels and real interviews carry over |
| `progress` | Level, accuracy and comparison per round, pace and streak |
| `apply` | Open roles from public job boards (Greenhouse, Lever, Ashby), a resume and note tailored from your real experience, and the application tracked; you submit it yourself |
| `debrief` | Records what a real interview asked |
| `your-story` | Finds real episodes in your git history and resume and rehearses them as behavioural answers |
| `offer` | Compares offers line by line and rehearses the negotiation call; offer numbers stay in the conversation |
| `share` | Drafts a post of what you learned, or of your progress with a link to the frozen numbers anyone can check; you post it |
| `delete-my-data` | Deletes everything the plugin stores about you, after you say yes |

## Install in Claude Code

```bash
claude plugin marketplace add InterviewReady/interviewready-plugin
```

```bash
claude plugin install interviewready@interviewready
```

Then run `/mcp`, choose `interviewready`, and sign in with your InterviewReady account. Start with `/interviewready:start`.

## Install in Codex

```bash
codex plugin marketplace add InterviewReady/interviewready-plugin
```

```bash
codex plugin add interviewready@interviewready
```

```bash
codex mcp login interviewready
```

Then ask Codex to start an interview prep plan.

## Your data

The plugin signs in with your InterviewReady account. It stores your plan, your answers and their grades, the applications and debriefs you save, and the progress you choose to share. The skills ask before reading your resume or git history. They instruct the assistant to keep offer details in the conversation. Content submitted as an answer, application note or debrief is stored by InterviewReady. Your host app also processes the conversation under its own privacy policy. Behavioural answers are sent to OpenAI for grading; submitted code runs on InterviewReady's code runner. Ask the plugin to delete your prep data to remove its plans, answers, applications, debriefs and shared snapshots. Your account and plugin sign-in remain.

[Privacy policy](https://interviewready.io/privacy-policy) · [Terms](https://interviewready.io/tnc)

## Layout

```
.claude-plugin/marketplace.json     Claude marketplace
.agents/plugins/marketplace.json    Codex marketplace
plugins/interviewready/
  .claude-plugin/plugin.json        Claude manifest
  plugin.json                       Codex manifest
  .mcp.json, mcp.json               the InterviewReady server, for Claude and for Codex
  skills/                           one folder per skill
```
