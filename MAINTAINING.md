# Maintaining the course

Notes for anyone (human or AI) improving the course itself, as opposed to taking it. If you are an AI and the user wants to *take* the course, follow `LLM/00_boot.md` instead.

## Origin and goal

The author re-learned this material through long Socratic chats with Claude, then had an agent condense those chats into a single instruction file (now `archive/socratic_electrophysiology_mentor_v1.md`). In 2026-09 that file was restructured into this package. In 2026-11 the tail of the course was rebuilt around the lab's actual system: the end goal is no longer "understand impedance" but "understand the MaxWell CMOS HD-MEA system end to end, and be able to read what it outputs." The goals:

- **Multi-session.** Progress lives in `memory/`, so no session needs the full history, and a session started fresh (even with a different LLM) loses little.
- **Portable.** Anyone can download the folder, point any capable LLM at it, and start.
- **Real visuals.** Widgets and plots instead of ASCII art, whichever app the learner uses.
- **Intuition first.** A learner passes a concept only when they can give the physical, causal story, not just the right number.
- **Ends at the data.** The destination is a learner who can take any output of the lab's pipeline and trace it back to ions crossing membranes, saying at each step what was measured, what was decided, and what is inferred. Analysis of that output is a separate later course.

## The platform

Modules 0 to 7 are platform-independent physics. Modules 8 to 14 are built around the MaxWell Biosystems MaxOne/MaxTwo and the lab's MXtreme pipeline (`https://github.com/Project-HAL/MXtreme`; its `docs/concepts/` pages are the reference for what the system outputs). `LLM/lab_context.md` carries the platform facts the tutor may state. A lab on another system would edit that file and Modules 8 to 13.

Facts the MXtreme repo does **not** document, and which must come from the MaxWell manual before the course states them: the on-device spike detection rule and its filter, gain settings, electrode geometry and material, stimulation-unit count and compliance. Modules 9 and 10 currently teach these conceptually and send the learner to the manual.

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
| `LLM/lab_context.md` | Platform facts and local context filled in by the lab. Must never become a source of operational settings |
| `modules/NN_*.md` | One per module, 00 to 14. Modules 0 to 7 are near-verbatim from v1; 8 to 14 were rewritten in 2026-11 around the MaxWell system. Each has a header, **Visual moments**, and **Memory** (uses from / record for later) |
| `branches/*.md` | Optional side topics. Each says when to open it and how to return to the main path |
| `memory/` | Ships as blank templates. Belongs to one learner |
| `widgets/*.html` | Self-contained offline simulations. Catalog in `widgets/README.md` |

Always loaded at session start: `00_boot`, `tutor_rules`, `intuition_and_math`, `visuals`, `curriculum_map`, `lab_context`, and memory, about 33 KB in total, plus one module of about 4 KB. Keep this core small; anything situational belongs in an on-demand file.

## Invariants (don't break these)

- **No operational numbers.** No stimulation settings, safety limits, coating recipes, detection or cleaning parameter values, or acceptance thresholds anywhere. Device specifications (electrode count, pitch, channel count, sampling rate) are fine. A module may say what a parameter *does* and that its value lives in the MXtreme docs or the manual. Widget values are labeled illustrative.
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

**Done, not yet reviewed by a second reader:**
- The 2026-11 restructure: new Modules 8, 9, 10, 13; rewritten 11, 12, 14; coatings moved to a branch; filtering folded into Module 9; curriculum map, tutor rules, readiness check, lab context, README, and widget catalog updated to match.

**Not yet tested:**
- A real tutoring session through the boot, memory, and resume cycle.
- Any session through the new Modules 8 to 13. They have no prebuilt widgets yet and lean on on-the-fly plots.
- Mode B (upload-only) memory output in claude.ai or ChatGPT.
- Behavior with non-Claude models.
- Whether ChatGPT and other apps hit file-count limits on upload.

## Backlog (rough priority)

1. **Pilot session** in a fresh session: "Start my electrophysiology course," through Module 0 and part of 2, then a second session to "Resume my course." Fix whatever the boot and memory flow gets wrong.
2. **Fill the MaxWell-manual gaps** in Modules 9 and 10 (detection rule and filter, gain, electrode geometry) once the manual is at hand. Teach the mechanism; still no operational values.
3. **Widgets for the new acquisition modules**, all drawn on the fly for now:
   - Module 8: a grid of electrodes with a routing limit over a field of cells, plus an activity-scan timeline;
   - Module 9: a spike through adjustable high/low-pass filters, a sampling-rate slider with aliasing, and quantization at two LSB sizes;
   - Module 10: a noisy trace with a draggable threshold, refractory window, and detected-event markers; two channels with different noise floors;
   - Module 13: a small spike table → raster → binned matrix → ASDR, with bin width and burst threshold sliders;
   - Module 11 / artifact branch: simultaneous artifact vs. propagated response across channels, with a blanking window.
4. **Mode B pilot** in a claude.ai Project: check that the memory REPLACE/APPEND blocks are clear and complete.
5. **Trim the always-loaded core** if pilots show context pressure. For example, load `visuals.md` on demand, or compress `tutor_rules.md`.
6. **Older widget wishes:** Module 1 series/parallel resistors; impedance-mapping branch look-alike maps.
7. **Mine the author's original Claude chats** for analogies and artifacts that worked, and fold them into modules or `widgets/`.
8. **Packaging:** a release zip, and a small script or instructions to reset `memory/` to blank.

## Testing widgets

Open the file in a browser. Check the console for errors, then exercise each "Try this" item and confirm the numbers make physical sense. Also check a narrow (phone-width) and a dark-mode view.
