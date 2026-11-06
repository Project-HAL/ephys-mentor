# Module 7: What extracellular electrodes measure

> **Builds on:** Modules 1, 5, 6 · **Next:** `08_multielectrode_arrays.md` · **Widgets:** `widgets/extracellular_field.html`

## Destination

The learner can explain extracellular voltage as a relative measurement shaped by transmembrane current, the conductive volume, geometry, reference choice, and the recording chain.

## Conceptual anchors

- An extracellular electrode does not read the inside of a neuron. It samples the local electric potential in a conductive medium, relative to a reference.
- Transmembrane currents create sources and sinks in the extracellular medium. Their fields spread through volume conduction and combine.
- Recorded amplitude and waveform depend on distance, cell and process geometry, orientation, synchrony, tissue conductivity, electrode size and interface, reference, bandwidth, and electronics.
- A brief extracellular spike is related to an action potential but is not a miniature copy of the intracellular voltage.
- Slower extracellular signals can reflect summed synaptic and other transmembrane currents, filtering, and distant sources. Interpretation depends on the preparation and bandwidth.
- Signal polarity is not a universal label for excitation or inhibition. It depends on geometry, reference, filtering, and current flow.
- The recording chain includes the electrode interface, reference, amplifier, filters, sampling, digitization, and later processing.

## Required Socratic challenges

- Ask why moving an electrode farther from a neuron usually changes the recorded amplitude even if the neuron's intracellular spike is unchanged.
- Ask how changing the reference could change every channel without changing the cells.
- Present two synchronized cells and two unsynchronized cells, and ask how summation might differ.
- Ask whether no detected spike proves that a nearby neuron did not fire.
- Ask why filtering can change waveform shape and apparent timing.
- Ask the learner to distinguish biological absence, weak coupling, electrode failure, reference trouble, and filtering as possible causes of a quiet channel.

## Common traps to surface

- "Each electrode records one neuron."
- "The electrode measures the action potential directly."
- "Negative means inhibitory."
- "Bigger extracellular amplitude means a biologically bigger spike."
- "A quiet electrode proves that no cell is active nearby."

## Visual moments

`widgets/extracellular_field.html` shows a two-point (sink/source) model of a neuron in a uniform conductive medium, with a movable recording electrode and reference.

1. **Distance.** Predict first, then move the recording electrode away from the soma. Look at the amplitude-vs-distance panel. The cell's current waveform never changed.
2. **Polarity depends on position.** Place the electrode near the soma, then near the dendrite end. The same spike gives opposite polarity. This addresses "negative means inhibitory."
3. **Reference.** Move the reference from "far away" to a spot near the cell. Every recorded value changes, but the cell doesn't.
4. **Synchrony.** Turn on cell 2 and change its timing offset from 0 (synchronous) to ±1 ms. Compare the summed trace.
5. **Orientation.** Rotate the cell while keeping the electrode fixed.
- Filtering isn't in this widget. If the learner asks, open `branches/filtering.md` or build an on-the-fly widget.
- Draw the signal chain on the fly (membrane current → field → interface → amplifier → filter → ADC → file). It becomes the backbone of Module 8.

## Transfer criterion

The learner can give at least four non-neural reasons why two electrodes might record different amplitudes from similar nearby activity.

## Memory

- **Uses from memory:** Module 1's "voltage is always relative to something" (quote it back; it is now literally the reference electrode); Module 5's answer about extracellular vs. intracellular spikes, which should now be revisited and upgraded; and Module 6's answer about what an MEA can detect of synapses.
- **Record for later (reused in Modules 8 and 13):**
  - the learner's list of non-neural reasons for amplitude differences;
  - their explanation of why reference choice affects all channels;
  - any "each electrode = one neuron" or "negative = inhibitory" misconception, and its repair.
