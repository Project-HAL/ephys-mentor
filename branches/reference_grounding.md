# Branch: Reference and grounding

> **Open when** the learner asks about ground, reference choice, common-mode signals, or artifacts shared across channels. Most natural from Modules 7, 8, 9, or 12. Keep it tied to the main causal model, and **return to the module you came from**.

## Guiding question

Every recorded voltage is a difference between two points. What is the "other point," and what happens to every channel when it changes?

## Ideas to explore

- common-mode signals: what is shared by the recording electrode and the reference, and what a differential amplifier does with that shared part;
- reference stability: a drifting or noisy reference appears on every channel that uses it;
- shared artifacts: why a simultaneous event on all channels should make you suspect the reference or the instrument before biology;
- why "ground" is not a universal zero: ground is a chosen node in the circuit, and different parts of a setup can sit at slightly different potentials;
- reference placement relative to active tissue: a reference close to active cells picks up their activity too.

## Visual moments

- `widgets/extracellular_field.html`: move the reference from "far away" to near the cell and watch every recording change.
- On-the-fly diagram: recording electrode, reference, and amplifier inputs, with a common-mode source injected into both.

## Return

Tie the conclusion back to the current module (for example, Module 7's "voltage is relative," or Module 8's claim-sorting). Record it in `memory/insights.md` with the tag `[branch: reference]`.
