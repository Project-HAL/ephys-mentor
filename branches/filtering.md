# Branch: Frequency response and filtering

> **Open when** the learner asks about high-pass or low-pass filters, why waveforms look different in different software, sampling rate, or aliasing. Most natural from Modules 7, 8, or 12. **Return to the module you came from.**

## Guiding question

A filter keeps some frequencies and suppresses others. What does that do to the *shape* and *timing* of a brief event like a spike?

## Ideas to explore

- high-pass and low-pass filters as the RC idea from Module 2 in a new role: an RC circuit already treats fast and slow changes differently;
- phase shift: filters can delay or distort parts of a waveform, which changes apparent timing and shape;
- choice of band: a spike band and a slow-signal band show different aspects of the same activity;
- sampling rate and aliasing: signals faster than half the sampling rate cannot be represented correctly and can masquerade as slower signals;
- processing later in the pipeline (digital filters, re-referencing) reshapes the data again. Always ask what processing produced the waveform you are looking at.

## Visual moments

- Optional on-the-fly widget: a spike-like waveform passed through adjustable high- and low-pass filters, showing how the shape and apparent peak time change. Add a sampling-rate slider to demonstrate aliasing on a sine wave.
- `widgets/rc_circuit.html`: the same RC element, viewed as a filter, smooths a brief pulse (Module 2's brief-vs-long pulse).

## Return

Tie back to Module 7's "why filtering can change waveform shape and apparent timing." Record it in `memory/insights.md` with the tag `[branch: filtering]`.
