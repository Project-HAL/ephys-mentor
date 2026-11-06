# Maintaining the course

Notes for anyone (human or AI) improving the course itself, as opposed to taking it. If you are an AI and the user wants to *take* the course, follow `LLM/00_boot.md` instead.

## Origin and goal

The author re-learned this material through long Socratic chats with Claude, then had an agent condense those chats into a single instruction file (now `archive/socratic_electrophysiology_mentor_v1.md`). In 2026-09 that file was restructured into this package. The goals:

- **Multi-session.** Progress lives in `memory/`, so no session needs the full history, and a session started fresh (even with a different LLM) loses little.
- **Portable.** Anyone can download the folder, point any capable LLM at it, and start.
- **Real visuals.** Widgets and plots instead of ASCII art, whichever app the learner uses.
- **Intuition first.** A learner passes a concept only when they can give the physical, causal story, not just the right number.

## Architecture

| Path | Role |
|---|---|
| `LLM/00_boot.md` | Entry point: environment detection (Mode A writes files; Mode B is upload-only and prints memory for the learner to save), load order, session protocol |
| `LLM/tutor_rules.md` | Role, the 15 non-negotiable rules, rhythm, hint ladder, modes, teaching loop, style, self-check |
| `LLM/intuition_and_math.md` | **Single source** for the intuition gate and math procedure. Other files point here; don't restate it elsewhere |
| `LLM/visuals.md` | Capability ladder (inline HTML → files → code plots → SVG/Mermaid → prebuilt widgets) and conventions for new widgets |
| `LLM/curriculum_map.md` | Module table, prerequisites, widgets, branch triggers, course boundary |
| `LLM/checkpoints.md` | Module checkpoint, Progress Note, mentor brief, final readiness check. Loaded on demand |
| `LLM/memory_spec.md` | What to record, when, and in what format. Loaded on demand |
| `LLM/lab_context.md` | Optional local context filled in by a lab. Must never become a source of operational settings |
| `modules/NN_*.md` | One per module. Content is verbatim from v1, plus a header, **Visual moments**, and **Memory** (uses from / record for later) |
| `branches/*.md` | Optional side topics. Each says when to open it and how to return to the main path |
| `memory/` | Ships as blank templates. Belongs to one learner |
| `widgets/*.html` | Self-contained offline simulations. Catalog in `widgets/README.md` |

Always loaded at session start: `00_boot`, `tutor_rules`, `intuition_and_math`, `visuals`, `curriculum_map`, `lab_context`, and memory, about 33 KB in total, plus one module of about 4 KB. Keep this core small; anything situational belongs in an on-demand file.

## Invariants (don't break these)

- **No operational numbers.** No stimulation settings, safety limits, coating recipes, or acceptance thresholds anywhere. Widget values are labeled illustrative.
- **One module file loaded at a time.** Cross-module dependencies go through memory ("Uses from memory"), never through loading another module.
- **Module template.** Keep the header line, the original sections, Visual moments, and the Memory section in every module.
- **Widgets.** One file, no network or CDN, units on every control, prediction mode, freeze/compare where useful, a "Try this" list, and a note on what the model simplifies. Must work in light and dark mode and at narrow widths.
- **Cross-references.** When you rename or add a file, update `curriculum_map.md`, `00_boot.md` (folder map), `widgets/README.md`, and the root `README.md`.

## Status (2026-11)

**Done and checked:**
- All seven widgets load with no console errors, and their physics gives sensible values:
  - RC: τ = RC;
  - HH: threshold about 6 µA/cm² for a 1 ms pulse, refractory failure below about 10 ms, rate coding with long steps;
  - GHK: about −65 mV with default concentrations;
  - impedance: bare ≈ 765 kΩ at 1 kHz, coated ×30 ≈ 29 kΩ;
  - stimulation: compliance clipping, and ratcheting at 80% charge balance.

**Not yet tested:**
- A real tutoring session through the boot, memory, and resume cycle.
- Mode B (upload-only) memory output in claude.ai or ChatGPT.
- Behavior with non-Claude models.
- Whether ChatGPT and other apps hit file-count limits on upload.

## Backlog (rough priority)

1. **Pilot session** in a fresh session: "Start my electrophysiology course," through Module 0 and part of 2, then a second session to "Resume my course." Fix whatever the boot and memory flow gets wrong.
2. **Mode B pilot** in a claude.ai Project: check that the memory REPLACE/APPEND blocks are clear and complete.
3. **Trim the always-loaded core** if pilots show context pressure. For example, load `visuals.md` on demand, or compress `tutor_rules.md`.
4. **Widgets not yet built**, all marked "on-the-fly" in the modules for now:
   - Module 1: series and parallel resistors;
   - Module 8: electrode grid pitch vs. a field of cells (dense vs. sparse);
   - filtering branch: high/low-pass filters on a spike, plus aliasing;
   - artifact branch: simultaneous artifact vs. propagated response across channels;
   - impedance-mapping branch: different causes that produce look-alike maps.
5. **Mine the author's original Claude chats** for analogies and artifacts that worked, and fold them into modules or `widgets/`.
6. **Packaging:** a release zip, and a small script or instructions to reset `memory/` to blank.
7. Decide whether Module 12 (impedance) should move before Module 11. For now, `curriculum_map.md` lets the tutor bring it forward.

## Testing widgets

Open the file in a browser. Check the console for errors, then exercise each "Try this" item and confirm the numbers make physical sense. Also check a narrow (phone-width) and a dark-mode view.
