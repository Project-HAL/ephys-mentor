# Memory specification

`memory/` holds this learner's state so that a new session, possibly with a different AI model, can pick up where the last one stopped without redoing work. Memory is the *only* thing that carries over between sessions. Anything that isn't written down is lost.

## Files

| File | Purpose | Update style |
|---|---|---|
| `memory/progress.md` | Where the learner is: module status table, **Resume here** block, Progress Notes | Edit in place (status, Resume here); append Progress Notes |
| `memory/learner_profile.md` | Who the learner is: background, goals, preferred mode and pace, what helps them | Edit in place |
| `memory/insights.md` | Key learning content: own-words explanations, repaired misconceptions, analogies, open questions, lab connections | Append under the right heading, tagged `[M#]` |
| `memory/session_log.md` | One short dated entry per session | Append |
| `memory/mentor_briefs.md` | Finished mentor discussion briefs | Append |

If a file is missing, recreate it using the format shown in the shipped blank version described below.

## When to write

Write, or queue a write in Mode B, when:

- a module checkpoint passes or fails (`progress.md`, `insights.md`);
- the learner gives a notably clear explanation in their own words: save it close to verbatim, because later modules quote it back;
- a misconception is surfaced and repaired: record what they pictured and what fixed it;
- an analogy or visual clearly worked, or clearly failed, for this learner;
- the learner says something about their lab role, project, or platform, or a goal (`learner_profile.md`);
- the learner raises a question that only a mentor or lab SOP can answer;
- a side branch is visited (note it and where you came from);
- the session ends (all files as needed).

## What makes a good insight entry

- **Specific and reusable.** Write "[M2] Explained τ as 'R sets how fast charge can arrive, C sets how much has to arrive': solid." Don't write "Learned about RC circuits."
- **Graded:** end each entry with *solid*, *provisional*, or *shaky*, and update the grade when it changes.
- **Short:** one to three lines per entry.
- **Factual about the learner's reasoning.** Don't judge the person.
- **Privacy:** record only what is useful for teaching. No personal details beyond role, background, and learning preferences.

## The "Resume here" block

This is the most important part of memory. It must let a fresh session restart mid-module:

```markdown
## Resume here
- Current module: 04_passive_membrane
- Position: Finished challenges 1–3 (circuit mapping, change R, change C). Next is challenge 4: large vs small cell.
- Next question to ask: "<exact question>"
- Warm-up retrieval question for next session: "<question testing last session's key idea>"
- Pending: <anything promised but not done, e.g., "show synaptic_integration.html for summation">
- Mode/pace: Explorer
```

## Mode A (you can write files)

Edit the files directly. Make small, targeted edits rather than rewriting whole files. At the end of a session, re-read `progress.md` to confirm the Resume here block is current.

## Mode B (you cannot write files)

Don't interrupt teaching to output memory. At a **checkpoint** or the **end of a session**, output:

1. A one-line instruction: "Save these into your `memory/` folder (replace or append as marked), then re-upload them next session."
2. For **`progress.md` and `learner_profile.md`**: the **complete updated file** in a fenced markdown block, headed `REPLACE memory/progress.md`.
3. For **`insights.md`, `session_log.md`, and `mentor_briefs.md`**: only the **new entries**, in a fenced block headed `APPEND TO memory/insights.md`, with each entry under its section heading.

If your interface can create downloadable files (for example, artifacts or file outputs), offer the files as downloads as well.

If the learner starts a session without memory files but pastes an older Progress Note or a summary, rebuild the memory from it and output the rebuilt files at the first checkpoint.

## Resetting and sharing

A learner's `memory/` folder is personal to them. To give the course to someone new, share a fresh copy of the package or reset the files in `memory/` to their blank templates, which appear exactly as shipped in the package.
