# Module 13: Whole-system synthesis

> **Builds on:** all modules · **Next:** final readiness check in `LLM/checkpoints.md` · **Widgets:** any; on-the-fly causal graphs

## Destination

The learner can trace cause and measurement across the complete system, identify uncertainty at each stage, and propose checks without jumping to a favorite explanation.

## Before starting

Read all of `memory/insights.md`. The capstone should draw on the learner's own earlier explanations and deliberately probe anything graded *shaky* or any misconception that was repaired. Choose the cases that best exercise those gaps. Suggest spreading the capstone over two sessions if needed.

## Capstone cases

Use at least three of these. Reveal information in stages and require the learner to update their model.

### Case A: A quiet region of an MEA

Possible causes include low biological activity, poor coupling, dead or absent cells, damaged or poorly wetted electrodes, high noise, threshold choices, reference trouble, routing, filtering, or acquisition failure. Ask the learner to order checks from broad and noninvasive to specific, and to say what each check would distinguish.

### Case B: A coated electrode records larger spikes

Ask what was directly observed, what mechanisms might explain it, and what controls are needed. Include impedance, noise, geometry, cell position, reference, gain, and biological variability. Do not accept "the coating made neurons stronger" without evidence.

### Case C: Stimulation produces a large simultaneous event

Ask the learner to separate commanded waveform, interface polarization, amplifier saturation, shared reference effects, direct activation, synaptic response, and propagation. Require time-based and control-based evidence.

### Case D: Impedance rises over days while activity falls

Ask for several causal graphs: one in which electrode change drives recording loss, one in which biological change affects both measures, and one in which a third factor, such as medium, debris, temperature, reference, or handling, affects both.

### Case E: Neighboring electrodes disagree

Ask how local cell geometry, distance, interface, noise, routing, reference, and sampling could contribute. Require a prediction that would differ between at least two of the explanations.

## Visual moments

- **Case D:** have the learner describe each causal graph, then render it (Mermaid or SVG) so they can check it. Ask which measurement would distinguish the graphs.
- **Case C:** reuse `biphasic_stimulation.html` (polarization and compliance) and the simultaneous-vs-propagated traces from Module 9.
- **Case E:** reuse `extracellular_field.html` (distance, orientation, reference) together with `impedance_spectrum.html` (interface differences).
- **Final synthesis:** after the learner narrates the full path, render it as a single flow diagram *built from their words*, with a failure point marked at each step.

## Final synthesis prompt

Ask the learner to explain, in plain language, the full path:

> A voltage or current command leaves a stimulator, interacts with an electrode in saline, changes extracellular potential, polarizes a neuron's membrane, may trigger activity, and later appears as samples in an MEA data file. What happens at each step, and where can the interpretation fail?

The learner should be able to move between physical, circuit, biological, and measurement descriptions without confusing them.

## After this module

Load `LLM/checkpoints.md` and run the **final readiness check** and the **end point**.

## Memory

- **Uses from memory:** everything, especially the Module 8 signal chain, the Module 9 stimulation chain, the Module 7 list of non-neural reasons, and the Module 11/12 impedance caveats.
- **Record for later:** the learner's final synthesis narrative (near-verbatim), which case exposed a remaining gap, and the final list of mentor questions.
