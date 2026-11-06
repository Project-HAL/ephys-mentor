# Module 11: PEDOT and platinum black at a practical level

> **Builds on:** Module 10 (and the basics of Module 12) · **Next:** `12_impedance.md` · **Widgets:** `widgets/impedance_spectrum.html`

## Destination

The learner understands why rough or porous coatings are used, what benefits they may provide, what can go wrong, and what evidence is needed before trusting a coated electrode.

## Conceptual anchors

- PEDOT-based coatings and platinum black can increase the electrochemically active surface area without increasing the geometric footprint by the same amount.
- Greater effective area often lowers interface impedance over useful frequency ranges and can reduce recording noise or stimulation polarization. The result depends on deposition, thickness, morphology, adhesion, medium, frequency, and aging.
- PEDOT conducts electronically and supports ionic interaction through its doped polymer structure. Its behavior depends strongly on formulation and processing.
- Platinum black is a high-surface-area platinum morphology. It can reduce impedance but may be mechanically fragile or change with handling and use.
- Lower impedance is not the only measure of quality. Stability, biocompatibility, adhesion, charge-storage or injection behavior, noise, uniformity, cleaning tolerance, and long-term drift may all matter.
- A coating can look intact while its electrical behavior has changed, or look rough while still functioning. Visual and electrical checks answer different questions.
- Platform and lab procedures govern deposition, conditioning, sterilization, acceptance, and reuse.

## Required Socratic challenges

- Ask how increasing microscopic area can lower impedance while the geometric area stays fixed.
- Ask why a coating that lowers impedance at one frequency may not improve every recording or stimulation problem.
- Ask what measurements would separate a uniform coating benefit from a few failed electrodes.
- Ask how adhesion failure, fouling, or cracking might show up in impedance, noise, stimulation voltage, or spatial maps.
- Ask the learner to design a comparison using before/after measures, controls, repeated measurements, and an explicit success criterion, without inventing a lab recipe.

## Practical boundary

Teach the reasoning needed to evaluate coating data. Do not invent deposition recipes, cleaning methods, or acceptance thresholds. Those belong in verified platform instructions and lab SOPs (see `LLM/lab_context.md` if filled in).

## Visual moments

`widgets/impedance_spectrum.html`:

1. **Effective area.** Freeze the "Small bare electrode" preset, then raise the **effective-area multiplier**. Predict first: which part of the spectrum drops, and which part doesn't? Rs is set by geometry and the medium, so the coating can't lower it. This one observation answers "why lower impedance at one frequency may not fix every problem."
2. **Where the benefit lands.** Move the frequency marker from 10 Hz to 10 kHz and compare the bare/coated ratio at each.
3. **Stimulation side.** In `biphasic_stimulation.html`, raise Cdl (a proxy for more effective area) and watch the polarization voltage fall for the same charge.
- For the experiment-design challenge, the learner should draft the design themselves. A table of before/after/control/success criterion is a fine visual *after* they draft it.

## Transfer criterion

The learner can explain why "lower impedance" is useful but insufficient as a complete claim that a coating is better.

## Memory

- **Uses from memory:** Module 10's metal→ion interface account and bubble explanation, and Module 2's `Q = CV` (more area → more capacitance → less voltage for the same charge).
- **Record for later (reused in Module 13, Case B):**
  - the learner's comparison design, as a summary;
  - their list of quality measures beyond impedance;
  - any lab-specific coating questions for the mentor (`insights.md` → Open questions).
