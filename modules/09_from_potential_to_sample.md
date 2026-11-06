# Module 9: From extracellular potential to a stored sample

> **Builds on:** Modules 2, 7, 8 · **Next:** `10_spikes_in_the_file.md` · **Widgets:** `widgets/rc_circuit.html` (as a filter); on-the-fly sampling and quantization plots

## Destination

The learner can trace a tiny extracellular voltage through the amplifier, filters, sampler, and converter to an integer in a file, and can say what each stage adds, removes, or distorts. They can convert between stored integers and volts and explain why a sampling rate and a filter band are choices with consequences.

## Conceptual anchors

- The electrode potential is microvolts riding on a much larger, slowly drifting offset. The amplifier must magnify the small, fast part without being pushed to its limits by the large, slow part.
- **Offset compensation** before a recording sets each channel's baseline near the middle of its range. It is a per-channel adjustment to the electronics, not a property of the cells.
- **Gain** is a multiplication. A higher gain gives finer voltage resolution but a smaller range before the amplifier saturates. Saturation means the channel reports its limit, not the signal.
- **Filtering** is the RC idea from Module 2 in a new role. A high-pass filter removes slow drift and slow signals. A low-pass filter removes fast noise and limits what the sampler must capture. Both change the shape and apparent timing of a brief event like a spike.
- **Sampling** takes the continuous signal at regular instants. Each instant is a **frame**. The sampling rate sets the time resolution. Anything faster than half the sampling rate cannot be represented and can masquerade as a slower signal (aliasing).
- **Quantization** turns each sample into an integer. The **least significant bit (LSB)** is the voltage step between neighboring integer values. Stored amplitudes are in these integer units until multiplied by the LSB. On the MaxWell system, time is stored as a frame counter and the file carries the LSB and sampling rate as settings.
- The recording chain is therefore: electrode → offset-compensated amplifier → filters → sampler → analog-to-digital converter → stored integers, plus the mapping that says which electrode each channel was. Every stage is a place where interpretation can fail.

## Required Socratic challenges

- Ask why a microvolt signal on a volt-scale offset is hard to amplify, and what offset compensation does about it.
- Hold the signal fixed and raise the gain. Ask what improves and what breaks.
- Ask why a high-pass filter makes a spike look different in two pieces of software with different settings.
- Present a sine wave sampled at a rate just below twice its frequency. Ask what the samples look like, then ask why a spike's sharp peak might be missed or shifted at a given rate.
- Give an amplitude stored as an integer and an LSB. Ask the learner to say what it means in volts, and then to say why the same spike would have a different integer value at a different gain.
- Ask why two recordings with different sampling rates (for example, on MaxOne and MaxTwo) need care before their frame numbers are compared.

## Common traps to surface

- "The file contains the voltage." It contains integers plus a scale factor.
- "Filtering only removes noise." It also reshapes signal.
- "A higher sampling rate is always better." Ask what it costs and what it does not fix.
- "Offset compensation changes the cells." It changes the amplifier.

## Visual moments

1. **RC as a filter.** In `rc_circuit.html`, send a brief pulse through the RC element and watch it smooth and delay. Then say: this is what a low-pass filter does to a spike.
2. **High-pass vs. low-pass on a spike.** On-the-fly plot: a spike-like waveform through adjustable high-pass and low-pass corners. Predict first how the peak time and the after-wave change.
3. **Sampling and aliasing.** On-the-fly plot: a sine wave with a sampling-rate slider. Show the sampled points alone, then overlay the true wave.
4. **Quantization.** On-the-fly plot: a smooth spike, then the same spike as integer steps at two LSB sizes. Ask which features survive.
5. **The chain.** Build the signal chain (electrode → amplifier → filter → sampler → ADC → file) and have the learner annotate each box with one way the interpretation could fail there. This diagram is reused in Modules 10, 13, and 14.

## Transfer criterion

Given a stored sample (an integer, a frame number, a channel) and the recording's settings, the learner can say what physical quantity it represents, in what units and at what time, and can name two processing stages that shaped it.

## Memory

- **Uses from memory:** Module 2's "capacitors pass fast changes more easily than slow ones" (quote it back; it is now a filter), Module 7's point that filtering changes waveform shape and timing, and Module 8's electrodes-vs-channels explanation.
- **Record for later (reused in Modules 10, 12, 13, and 14):**
  - the learner's annotated signal chain, in their own words;
  - their explanation of what the LSB and frame number are;
  - their account of why filtering reshapes a spike;
  - whether frequency-dependence now feels intuitive (mark *solid*, *provisional*, or *shaky*). Module 12 builds impedance on it.
