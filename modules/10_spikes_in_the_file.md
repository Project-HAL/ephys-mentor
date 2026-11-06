# Module 10: What a "spike" is in the file

> **Builds on:** Modules 5, 7, 9 · **Next:** `11_stimulation.md` · **Widgets:** on-the-fly threshold-detection plots; `widgets/action_potential.html` for the intracellular contrast

## Destination

The learner understands that a row in the spike table is the outcome of a detection decision made by the recording system, not a neuron's action potential. They can say what the decision depends on, what it misses, what it invents, and what the raw trace adds.

## Conceptual anchors

- The MaxWell system detects spikes on the device during recording and stores a **spike table**: for each detected event, the frame, the channel, and an amplitude in integer units. Raw traces are stored only when the recording asks for them.
- Detection is a **threshold decision** on a filtered trace. A sample that crosses the threshold becomes a row. The threshold is set relative to each channel's noise, so a noisier channel needs a bigger deflection to register. The exact rule and filter are the device's; the manual is the source, not this course.
- Extracellular spikes near a soma are usually **negative-going**. Positive deflections can be real, but they are often the far side of someone else's spike, an artifact, or noise. The lab's pipeline keeps only negative deflections for most analyses.
- **Amplitude** in the table is the detected peak in integer units. It depends on distance, geometry, and coupling (Module 7), on the electrode and filter (Module 9), and on which sample happened to be nearest the peak. It is not a measure of the neuron's intracellular spike.
- A **refractory check** removes a second detection too soon after the first on the same channel, on the grounds that one cell cannot fire that fast. It also removes a real second cell's spike if two cells share a channel.
- **Missed spikes** (small, distant, or coincident with noise) and **false spikes** (noise crossings, artifact edges) both exist. Changing the threshold trades one for the other. No threshold gives "the true spikes."
- A channel's spike count is therefore a function of biology, coupling, electrode state, noise, filter, threshold, and routing. "Active electrode" is a definition, not an observation.
- The raw trace is the only place to check what a detected row looks like, see what was missed, and judge the noise floor. Without raw data, the spike table must be read with its detection rule in mind.

## Required Socratic challenges

- Show (or describe) a filtered trace with a threshold line. Ask the learner to mark which deflections become rows, then lower the threshold and ask again.
- Ask why the same culture recorded on a quieter electrode would produce more rows, with no change in the cells.
- Ask what a positive deflection on a channel might be, and what the choice to discard positives costs.
- Ask what a refractory rule of a few milliseconds assumes, and when that assumption fails.
- Give two channels with equal spike counts and different amplitude distributions. Ask what can and cannot be concluded.
- Ask why the "spike" in the table and the action potential in `action_potential.html` are different objects, and how they are related.
- Ask what the learner would look at in the raw trace before trusting a surprising spike count.

## Common traps to surface

- "The spike table lists the action potentials."
- "A bigger amplitude means a stronger neuron."
- "More spikes means more activity." It may mean a lower noise floor or a different threshold.
- "Negative-only filtering is a biological fact." It is a reasonable rule with costs.
- "If it's in the file, it happened."

## Visual moments

1. **Threshold detection.** On-the-fly plot: a synthetic trace with spikes of several sizes plus noise, a draggable threshold, and markers for detected events. Add a refractory window and show which detections it removes.
2. **Noise-relative threshold.** Two channels with different noise floors and identical embedded spikes. Same rule, different counts.
3. **Intracellular vs. extracellular.** `action_potential.html` for the intracellular waveform, next to a sketched extracellular spike and a single table row (frame, channel, amplitude). Ask the learner to connect the three.
4. **Amplitude distribution.** On-the-fly histogram of amplitudes on one channel. Ask what a bimodal shape might mean, and what else could produce it.

## Transfer criterion

Given a change in a channel's spike count between two recordings, the learner can list at least five causes that are not a change in the neurons, and can say which of them the raw trace would resolve.

## Memory

- **Uses from memory:** Module 5's causal AP story, Module 7's non-neural reasons for amplitude differences, Module 9's signal chain and LSB explanation, and Module 8's "active electrode is a definition."
- **Record for later (reused in Modules 13 and 14):**
  - the learner's own words for "a row in the spike table is a detection decision";
  - their list of non-neural causes of a spike-count change;
  - their explanation of the amplitude vs. intracellular spike distinction;
  - any "if it's in the file, it happened" misconception, and its repair.
