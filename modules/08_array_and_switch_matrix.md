# Module 8: The array and the switch matrix

> **Builds on:** Module 7 · **Next:** `09_from_potential_to_sample.md` · **Widgets:** `widgets/extracellular_field.html`; on-the-fly routing and scan diagrams

## Destination

The learner can reason about a high-density CMOS multielectrode array as a spatially sampled, reference-dependent measurement in which **electrodes and channels are different things**, where "which electrodes are recorded" is a decision made before any data exist, and where an array-wide picture is assembled from partial views.

## Conceptual anchors

- An MEA provides many extracellular measurement sites. It is not a direct picture of every neuron.
- On a CMOS high-density array such as the MaxWell MaxOne or MaxTwo, the electrodes (tens of thousands, on a pitch of a few cell diameters) far outnumber the amplifier channels (about a thousand). A **switch matrix** connects a chosen subset of electrodes to the channels. An electrode that is not routed records nothing.
- A **channel** is an amplifier and its data stream. An **electrode** is a metal site on the array. The **mapping** between them is a routing choice stored with each recording. The same channel number can mean a different electrode in a different recording.
- Routing has constraints. Not every arbitrary set of electrodes can be wired at once, and the routing solver may leave some requested electrodes out.
- An **activity scan** covers the whole array by recording several different subsets one after another. The resulting array-wide map is stitched from recordings made at different times. Cells that were quiet during their subset's turn look silent.
- Choosing recording electrodes from a scan is a filter: by spike sign, amplitude, rate, and spatial spread. The chosen set is a biased sample of the culture, and the bias is a design decision, not a property of the biology.
- More electrodes do not automatically mean more independent neurons or more biological truth. Neighboring electrodes on a fine pitch often see the same cell.
- Spatial sampling can reveal propagation and coordinated activity, but apparent patterns can also come from volume conduction, a shared reference, artifacts, filtering, or selection effects.
- Recording, stimulation, and impedance measurement may use the same physical electrodes in different instrument modes, but they are not the same measurement.

## Required Socratic challenges

- Ask what has to happen between "there is a cell over electrode 12,345" and "there is a trace from that cell in the file." Draw out routing as a step.
- Give two recordings of the same culture on different days with different routings. Ask whether "channel 40 got quieter" means anything.
- Ask why an activity scan of a culture with slow, sparse bursting can mark active regions as silent.
- Ask how the electrode-selection filters (sign, amplitude, rate, spacing) change what the network recording can and cannot show. Ask what kind of cell or region each filter is most likely to exclude.
- Compare a dense small array with a sparse wide array. Ask what each gains and loses, then relate it to choosing a spatially spread subset on a dense array.
- Ask why adjacent electrodes may show similar waveforms.
- Ask what observations would help distinguish propagating biological activity from a simultaneous artifact.
- Ask why a change in the number of active electrodes between days might reflect culture state, routing, electrode state, the selection thresholds, reference quality, or acquisition settings.

## Common traps to surface

- "Each electrode records one neuron."
- "Channel 40 is a place on the chip."
- "The activity scan is a snapshot of the whole culture."
- "The network recording shows the culture." It shows the chosen electrodes, during that recording.
- "An electrode with no spikes has no cell near it."

## Interpretation discipline

Require the learner to sort claims into three classes:

- directly measured;
- inferred under stated assumptions;
- not supported by the measurement alone.

Use this habit throughout the later modules.

## Visual moments

1. **Adjacent electrodes.** In `extracellular_field.html`, place the recording electrode at two nearby spots and compare their traces. Why are they similar? Then compare two spots far apart.
2. **Electrodes vs. channels.** Draw on the fly (SVG or Mermaid): a grid of many electrodes, a small bank of amplifiers, and switches between them. Have the learner route a few electrodes, then show the mapping table (channel, electrode, x, y) that the recording stores.
3. **Activity scan as a time-sliced map.** Draw the array as several colored tiles recorded one after another on a timeline. Place a burst in time and ask which tiles catch it.
4. **Selection as a filter.** Show an array-wide map of per-electrode spike amplitude and rate, then apply the sign, amplitude, rate, and spacing filters one by one and watch the chosen set shrink. Ask what each step removed.
- **Optional on-the-fly widget:** a grid of electrodes at adjustable pitch over a field of randomly placed cells, showing which cells fall within "detectable" distance of any electrode, with a routing limit on how many electrodes can be active.

## Transfer criterion

Given an MEA observation, the learner can name the measured quantity, the biological interpretation, and at least two alternative explanations or controls, and can say whether the observation depends on which electrodes were routed.

## Memory

- **Uses from memory:** the learner's Module 7 list of non-neural reasons for amplitude differences (quote it and extend it to the array level), and their reference explanation.
- **Record for later (reused in Modules 10, 13, and 14):**
  - their explanation of electrodes vs. channels vs. mapping, in their own words;
  - their account of how electrode selection biases the network recording;
  - how well they use the measured / inferred / unsupported sort (mark *solid* or *shaky*);
  - any lab connection, such as the platform they will actually use, in `insights.md` → Lab connections.
