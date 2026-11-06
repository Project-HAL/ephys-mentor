# Socratic Electrophysiology Mentor

A question-led, multi-session course that teaches new lab members to reason, from first principles, about electricity, neurons, extracellular recording, the MaxWell CMOS high-density MEA system, stimulation, and what the data that comes out of it actually is. By the end you should be able to take any plot from the lab's pipeline and trace it back to ions crossing a membrane, saying at each step what was measured, what was decided, and what is being inferred.

You don't read this course. You **point an AI at it**, and the AI becomes your tutor. It asks you questions, makes you predict before it explains, shows you interactive simulations, and saves your progress so you can stop and pick up later, even with a different AI.

---

## Quick start

### Option 1: an AI that can open this folder (recommended)
Examples: Claude Code, the Claude desktop app (Cowork or Code), Codex, Cursor.

1. Download and unzip this folder.
2. Open the folder in the tool.
3. Say: **"Start my electrophysiology course."** (Later: **"Resume my course."**)

The tutor reads `LLM/00_boot.md`, finds your place in `memory/`, and saves your progress there automatically.

### Option 2: a chat app where you upload files
Examples: claude.ai Projects, ChatGPT Projects or custom GPTs, Gemini Gems.

1. Create a project and upload:
   - everything in `LLM/`;
   - everything in `memory/`;
   - the module you're on from `modules/`. You can upload all of them if the app allows; if there's a file limit, upload just the current one and the next.
2. Say: **"Follow LLM/00_boot.md and start my course."**
3. At a checkpoint or when you stop, the tutor will print updated memory files. **Save them into your `memory/` folder** (replacing or appending as marked) and re-upload them next time.

### Option 3: plain chat, no files
Paste `LLM/00_boot.md` into the chat. The tutor will tell you what else it needs.

---

## Getting good visuals

The course relies on real plots and interactive widgets, not ASCII sketches. What you get depends on the app:

- **Best:** apps that render interactive content, such as Claude with **Artifacts** enabled or ChatGPT with **Canvas**. The tutor can show widgets inline.
- **Also good:** apps that can run code (e.g., ChatGPT's data analysis). The tutor can make plots.
- **Always available:** `widgets/` contains ready-made simulations. **Double-click any `.html` file** to open it in your browser. No internet needed. When the tutor mentions one, open it and try what it suggests.

If your tutor only makes text diagrams, say: *"Use the best visual tool you have, per LLM/visuals.md,"* or just open the widget yourself.

---

## How sessions work

- Sessions are short on purpose. The tutor will suggest stopping after about two modules, or sooner if the conversation gets long. Nothing is lost when you stop.
- Each new session starts with a quick warm-up question about last time, then continues exactly where you left off.
- Every few modules the tutor helps you write a **Mentor Discussion Brief**, a short page of your current understanding and questions to bring to a person in your lab.
- The tutor won't give you stimulation settings, coating recipes, or safety limits. Those come from your lab's SOPs, device manuals, and your mentor.

---

## What's in the folder

| Folder | What it's for |
|---|---|
| `LLM/` | Instructions for the AI tutor: teaching rules, the "intuition first" principle, visuals, curriculum map, checkpoints, memory format |
| `modules/` | 15 modules (00–14), from charge and voltage through the array, the acquisition chain, spike detection, stimulation, the interface, reading the output, and a capstone. The tutor loads one at a time |
| `branches/` | Optional side topics (coatings, impedance mapping, reference/grounding, noise, artifact, coupling, volume conduction, patch clamp) |
| `memory/` | **Your** progress, insights, and mentor briefs. Updated as you go |
| `widgets/` | Interactive simulations you can open in any browser |
| `archive/` | The original single-file version of the course (kept for reference; the tutor ignores it) |

## Course path

0 Orientation → 1 Charge, voltage, current → 2 Capacitance and RC → 3 Membrane potential → 4 Passive membrane → 5 Action potentials → 6 Synapses → 7 Extracellular recording → 8 The array and the switch matrix → 9 From potential to sample → 10 What a "spike" is in the file → 11 Stimulation → 12 Interface and impedance → 13 Reading the output → 14 Synthesis

---

## For lab leads and mentors

- **Local context:** `LLM/lab_context.md` names the platform (MaxWell MaxOne/MaxTwo), the analysis pipeline, and the *titles* of relevant SOPs. Fill in your preparations and mentors. The tutor uses it for examples and to point learners to the right place. It will not invent procedures.
- **Giving the course to a new person:** give them a fresh copy of the package. `memory/` belongs to one learner.
- **Checking progress:** a learner's `memory/progress.md` and `memory/mentor_briefs.md` give you a quick picture of where they are and what they're unsure about.
- **Adding widgets:** see `widgets/README.md` and the conventions in `LLM/visuals.md`.
