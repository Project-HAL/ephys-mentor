# Module 13: Reading the output

> **Builds on:** Modules 8, 9, 10, 11 · **Next:** `14_synthesis.md` · **Widgets:** on-the-fly raster, ASDR, and layout plots; `widgets/extracellular_field.html` for the geometry behind a map

## Destination

The learner can take any plot or table the lab's pipeline produces from a MaxWell recording, trace it back to the spike table and the recording settings, and say at each step what was measured, what was decided, and what is being inferred.

## The chain this module walks

```text
raw .h5 (spike table, mapping, LSB, sampling rate, events)
  → cleaning (re-base time, integers → volts, keep negatives,
    amplitude threshold, refractory rule, drop unmapped channels,
    blank stimulation windows)
  → channel map (row index ↔ channel ↔ electrode ↔ x, y)
  → binned matrix (channels × time bins, 1 = fired at least once)
  → ASDR (fraction of channels active per bin)
  → bursts (grouping rule + rate rule → onset, peak, offset, origin)
  → per-recording tables → per-culture summaries over DIV → report
```

The lab's current implementation is the MXtreme package. Its data dictionary names every field; use those names when the learner has it open, but teach the meaning, not the API.

## Conceptual anchors

- **Every stage is a transformation with parameters.** The cleaning steps each remove or reshape rows, and the pipeline records what it did. A number in a report has a provenance; ask for it.
- **The channel map is the bridge from data to space.** A row in the binned matrix is a channel; the map says which electrode, and where. Without it a raster is a list of anonymous streams.
- **Binning destroys information on purpose.** A binary presence matrix records whether a channel fired in a bin, not how many times or when within it. The bin width sets what "simultaneous" means.
- **ASDR** (array-wide spike detection rate) is the fraction of channels active per bin. It rises when more channels fire together. It is a population summary of detection events, not a measure of any cell's rate.
- **A burst is a definition.** The grouping rule and the rate rule have parameters and produce onsets, offsets, peaks, and origins. Change the parameters and the burst count changes. "Network" vs. "mini" is a classification by peak height.
- **Burst origin** is the electrode where detections rose first within a burst. It depends on routing, coupling, and threshold as much as on where activity began.
- **Firing rate per channel** divides a count by a duration. Which duration (whole recording, a phase, time to last spike) and which count (before or after cleaning) must be stated.
- **Phases** (such as pre, train, post) come from event tags with frame numbers. A number "in the train phase" depends on the tag being correct and the window being defined.
- **Stimulation blanking** removes spikes in windows around pulses. Activity during stimulation is therefore partly unobservable by construction.
- **Per-culture summaries over DIV** compare recordings made with possibly different routings, selections, and noise floors. A trend across days is a trend in detections.

## Required Socratic challenges

- Hand the learner a raster and ask: what is a row, what is a column, what does a mark mean, and where did the row order come from?
- Ask what happens to an ASDR trace if the bin width doubles. Ask what happens to the number of "simultaneous" events.
- Present a report in which the burst count fell between two days. Ask for the causes that are not a change in the network: threshold, routing, noise, cleaning parameters, phase boundaries, blanking, recording length.
- Ask what a burst-origin heatmap can and cannot claim about where activity starts.
- Give a per-channel firing-rate table and ask which cleaning steps changed the numbers in it, and in which direction.
- Ask the learner to classify three statements from a report as measured, inferred, or unsupported.
- Ask why a culture's "active channel count over DIV" is a measurement of the pipeline as much as of the culture.

## Common traps to surface

- "The raster shows the neurons."
- "ASDR is the firing rate."
- "A burst is a thing the culture did." It is a thing the detector found.
- "The origin electrode is where the burst started."
- "The report numbers are the data."

## Visual moments

1. **Spike table → raster.** On the fly, draw a short spike table (frame, channel, amplitude), then its raster, then its binned matrix at two bin widths. Have the learner do the second bin width by hand.
2. **Binned matrix → ASDR.** Sum the columns of the matrix from moment 1 and plot it. Then add a burst-detection threshold line and ask which peaks count.
3. **Channel map → layout.** Place the raster's rows on an array layout using a small channel map. Then re-route two channels and show the same activity landing in different places.
4. **Parameter sensitivity.** On-the-fly plot: the same recording's burst count as the grouping threshold or bin width varies. Ask where the "right" value is, then ask what question would decide it.
5. **If MXtreme is available**, open one preprocessed file's provenance dictionary and step log with the learner and ask them to narrate what each step did. Do not teach the API; teach the reading.

## Transfer criterion

Given one figure from a lab report, the learner can name the field in the raw file it ultimately came from, list the transformations between, name two parameters that would change the figure, and say what a mentor should be asked before the figure is believed.

## Memory

- **Uses from memory:** Module 8's measured / inferred / unsupported habit and electrodes-vs-channels explanation, Module 9's signal chain and LSB, Module 10's "a row is a detection decision," and Module 11's artifact blanking.
- **Record for later (reused in Module 14):**
  - the learner's narration of the full chain from file to report, near verbatim;
  - their list of non-biological causes of a burst-count change;
  - how they classified the report statements (mark *solid* or *shaky*);
  - any lab-specific questions about pipeline parameters, in `insights.md` → Open questions.
