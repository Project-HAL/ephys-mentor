# Module 8: Multielectrode arrays

> **Builds on:** Module 7 · **Next:** `09_stimulation.md` · **Widgets:** `widgets/extracellular_field.html`; on-the-fly signal-chain diagram

## Destination

The learner can reason about an MEA as a spatially sampled, reference-dependent measurement system with strengths, blind spots, and tradeoffs.

## Conceptual anchors

- An MEA provides many extracellular measurement sites. It is not a direct picture of every neuron.
- Electrode pitch, size, material, routing, sampling plan, and active-area geometry affect what can be observed.
- More electrodes do not automatically mean more independent neurons or more biological truth.
- Spatial sampling can reveal propagation and coordinated activity, but apparent patterns can also come from volume conduction, a shared reference, artifacts, filtering, or selection effects.
- Detection depends on coupling and noise as well as on biology.
- Recording, stimulation, and impedance measurement may use the same physical electrodes in different instrument modes, but they are not the same measurement.

## Required Socratic challenges

- Compare a dense small array with a sparse wide array. Ask what each gains and loses.
- Ask why adjacent electrodes may show similar waveforms.
- Ask what observations would help distinguish propagating biological activity from a simultaneous artifact.
- Ask why a change in the number of active electrodes might reflect culture state, electrode state, thresholding, reference quality, or acquisition settings.
- Have the learner trace a signal from membrane current to a saved digital sample.

## Interpretation discipline

Require the learner to sort claims into three classes:

- directly measured;
- inferred under stated assumptions;
- not supported by the measurement alone.

Use this habit throughout the later modules.

## Visual moments

1. **Adjacent electrodes.** In `extracellular_field.html`, place the recording electrode at two nearby spots and compare their traces. Why are they similar? Then compare two spots far apart.
2. **Signal chain.** Build it on the fly (Mermaid or SVG): membrane current → extracellular field → electrode interface → amplifier → filters → ADC/sampling → saved file. Have the learner annotate each box with one way the interpretation could fail there.
3. **Optional on-the-fly widget:** a grid of electrodes at adjustable pitch over a field of randomly placed cells, showing which cells fall within "detectable" distance of any electrode. Use it for the dense-vs-sparse challenge.
- If the learner sorts claims well, a quick three-column table (measured / inferred / unsupported) is a fine visual.

## Transfer criterion

Given an MEA observation, the learner can name the measured quantity, the biological interpretation, and at least two alternative explanations or controls.

## Memory

- **Uses from memory:** the learner's Module 7 list of non-neural reasons for amplitude differences (quote it and extend it to the array level), and their reference explanation.
- **Record for later (heavily reused in Module 13):**
  - their annotated signal chain, in their own words;
  - how well they use the measured / inferred / unsupported sort (mark *solid* or *shaky*);
  - any lab connection, such as the platform they will actually use, in `insights.md` → Lab connections.
