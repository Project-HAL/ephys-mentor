# Module 14: Whole-system synthesis

> **Builds on:** all modules · **Next:** final readiness check in `LLM/checkpoints.md` · **Widgets:** any; on-the-fly causal graphs

## Destination

The learner can trace cause and measurement across the complete system, from a transmembrane current to a number in a lab report, identify uncertainty at each stage, and propose checks without jumping to a favorite explanation.

## Before starting

Read all of `memory/insights.md`. The capstone should draw on the learner's own earlier explanations and deliberately probe anything graded *shaky* or any misconception that was repaired. Choose the cases that best exercise those gaps. Suggest spreading the capstone over two sessions if needed.

## Capstone cases

Use at least three of these. Reveal information in stages and require the learner to update their model. Each case is framed as something the lab's pipeline would actually show.

### Case A: A quiet region of the array

An activity scan shows a region with almost no active electrodes, and the network recording routed nothing there. Possible causes include low biological activity, poor coupling, dead or absent cells, poor wetting or a bubble, high noise, the detection threshold, the selection filters, the scan's timing relative to bursts, reference trouble, routing, or acquisition failure. Ask the learner to order checks from broad and noninvasive to specific, and to say what each check would distinguish. The raw trace, a re-scan, a routing change, and microscopy are all on the table.

### Case B: The active-electrode count dropped over days

A per-culture summary shows fewer active channels on a later DIV. Ask what was directly observed, what mechanisms might explain it, and what controls are needed. Include biology, routing differences between days, noise floor, threshold, cleaning parameters, recording length, electrode state, medium, temperature, and reference. Do not accept "the culture is dying" without evidence.

### Case C: Stimulation produces a large simultaneous event

Ask the learner to separate the commanded waveform, interface polarization, amplifier saturation, shared reference effects, direct activation, synaptic response, propagation, and the blanking window. Require time-based and control-based evidence, and ask what the event tags must be trusted to say.

### Case D: Impedance rose while activity fell

Ask for several causal graphs: one in which electrode change drives detection loss, one in which biological change affects both measures, and one in which a third factor, such as medium, debris, temperature, reference, or handling, affects both. Then ask which measurement would distinguish the graphs.

### Case E: Neighboring electrodes disagree

Two adjacent electrodes in the same recording show different amplitudes and counts. Ask how local cell geometry, distance, interface, noise, routing, reference, threshold, and sampling could contribute. Require a prediction that would differ between at least two of the explanations.

### Case F: The burst count changed when a parameter changed

The same recording run through the pipeline with a different bin width or grouping threshold gives a different burst count and a different origin map. Ask what, if anything, the culture did differently. Ask what question would decide which parameter setting is right, and what a mentor would need to know.

## Visual moments

- **Case A:** reuse the array-layout and selection-filter sketches from Module 8.
- **Case C:** reuse `biphasic_stimulation.html` (polarization and compliance), the simultaneous-vs-propagated traces, and the event timeline from Module 11.
- **Case D:** have the learner describe each causal graph, then render it (Mermaid or SVG) so they can check it.
- **Case E:** reuse `extracellular_field.html` (distance, orientation, reference) together with `impedance_spectrum.html` (interface differences).
- **Case F:** reuse the parameter-sensitivity plot from Module 13.
- **Final synthesis:** after the learner narrates the full path, render it as a single flow diagram *built from their words*, with a failure point marked at each step.

## Final synthesis prompt

Ask the learner to explain, in plain language, the full path:

> Ions cross a neuron's membrane in a dish sitting on a CMOS array. Some of that current reaches an electrode that happens to be routed to an amplifier. Later, a number in a report says the culture's burst rate went up on day 21. What happened at every step between those two, and where can the interpretation fail?

The learner should be able to move between physical, circuit, biological, instrument, and data descriptions without confusing them.

## After this module

Load `LLM/checkpoints.md` and run the **final readiness check** and the **end point**.

## Memory

- **Uses from memory:** everything, especially the Module 9 signal chain, the Module 8 electrodes-vs-channels and selection explanations, the Module 10 detection-decision account, the Module 11 stimulation chain, the Module 7 list of non-neural reasons, the Module 12 impedance caveats, and the Module 13 file-to-report narration.
- **Record for later:** the learner's final synthesis narrative (near-verbatim), which case exposed a remaining gap, and the final list of mentor questions.
