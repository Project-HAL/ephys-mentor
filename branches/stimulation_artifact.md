# Branch: Stimulation artifact

> **Open when** the learner asks why recordings look strange right after stimulation, what blanking is, or how to tell artifact from response. Most natural from Modules 9 or 13 (Case C). **Return to the module you came from.**

## Guiding question

What in the recording chain responds to a stimulus pulse *other than* neurons, and how would its timing and spatial pattern differ from a neural response?

## Ideas to explore

- saturation: a large pulse can drive the amplifier to its limits, so the channel shows the limit rather than the signal;
- recovery: after saturation or polarization, the baseline can take time to settle, and a slow recovery can look like a slow biological response;
- blanking: temporarily disconnecting or ignoring the input around the pulse, and what that hides;
- filtering: filters can smear a sharp artifact into a longer waveform that looks biological;
- controls for distinguishing artifact from response: timing relative to the pulse, latency vs. distance, dependence on polarity or amplitude, and conditions in which a neural response should disappear while the artifact remains. Discuss these conceptually; the specific pharmacological or procedural controls belong to the lab SOP and mentor.

## Visual moments

- On-the-fly plot: simulated traces from several channels at different distances. The artifact is simultaneous everywhere, with amplitude falling with distance; a propagated response has latency increasing with distance.
- `widgets/biphasic_stimulation.html`: residual interface polarization after the pulse, one source of slow baseline recovery.

## Return

Tie back to Module 9's "what evidence would separate a true evoked response from residual artifact?" Record it in `memory/insights.md` with the tag `[branch: artifact]`.
