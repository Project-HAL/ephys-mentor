# Branch: Electrode coatings (PEDOT, platinum black)

> **Open when** the learner asks why electrodes are coated, what PEDOT or platinum black do, or how to judge whether a coating "worked." Most natural from Module 12, or from the seal-and-coupling or noise branches. On a CMOS array the lab does not coat its own electrodes, so this is context for reading papers and other platforms. **Return to the module you came from.**

## Guiding question

How can an electrode's effective surface area change without its footprint changing, and what does that do, and not do, to recording and stimulation?

## Ideas to explore

- PEDOT-based coatings and platinum black increase the electrochemically active surface area without increasing the geometric footprint by the same amount.
- Greater effective area lowers the capacitive part of the interface impedance over useful frequency ranges. It does not lower the solution resistance, which is set by geometry and the medium. This is why a coating that lowers impedance at one frequency may not fix every recording or stimulation problem.
- Lower polarization for the same charge: `Q = CV`, so more capacitance means less voltage for the same injected charge (Module 11).
- PEDOT conducts electronically and supports ionic interaction through its doped polymer structure. Platinum black is a high-surface-area platinum morphology that can be mechanically fragile. Both depend strongly on deposition, thickness, adhesion, medium, and aging.
- Lower impedance is not the only measure of quality. Stability, biocompatibility, adhesion, charge-injection behavior, noise, uniformity, cleaning tolerance, and drift all matter.
- A coating can look intact while its electrical behavior has changed, or look rough while still functioning. Visual and electrical checks answer different questions.
- Evaluating a coating claim needs before/after measures, controls, repeated measurements, and an explicit success criterion. Do not accept "the coating made the spikes bigger" without asking about coupling, cell position, noise, gain, and reference.

## Visual moments

- `widgets/impedance_spectrum.html`: freeze the "Small bare electrode" preset, then raise the **effective-area multiplier**. Predict first which part of the spectrum drops and which does not. Move the marker from 10 Hz to 10 kHz and compare the bare/coated ratio at each.
- `widgets/biphasic_stimulation.html`: raise Cdl (a proxy for more effective area) and watch the polarization voltage fall for the same charge.

## Practical boundary

Teach the reasoning needed to evaluate coating data. Do not invent deposition recipes, cleaning methods, or acceptance thresholds. Those belong in verified platform instructions and lab SOPs.

## Return

Tie back to the module you came from (Module 12: what effective area changes and what it cannot; Module 14, Case B or E). Record the learner's conclusion in `memory/insights.md` with the tag `[branch: coatings]`.
