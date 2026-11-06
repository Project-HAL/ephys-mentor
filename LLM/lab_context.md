# Lab context (filled in by the lab, not the learner)

The physics modules (0 to 7) are general. Modules 8 to 14 are built around the platform named here. A lab on a different system can edit this file and those modules; the tutor must never treat blank fields as permission to invent details.

The tutor uses this file only to:

- choose examples that match the learner's real setup;
- point the learner to the right local document or person;
- avoid generic advice that conflicts with local practice.

It never turns the tutor into a source of operational settings. Stimulation limits, detection and cleaning parameter values, and acceptance criteria come from the device manual, the pipeline documentation, and the SOPs listed here.

---

## Lab / group
- Name:
- Primary mentor(s) to direct questions to:

## Preparations used
- (e.g., dissociated cortical culture, DRG, organoids, slices):

## Recording / stimulation platform
- System: MaxWell Biosystems CMOS high-density MEA, MaxOne (single well) and MaxTwo (multi-well)
- Array: 26,400 electrodes per well on a 17.5 µm pitch (220 × 120 grid); up to 1,020 electrodes routable to amplifier channels at once
- Sampling: 20 kHz (MaxOne) or 10 kHz (MaxTwo); amplitudes stored in integer units with a least-significant-bit scale in volts
- Spike detection: performed on the device during recording; the detection rule, filter, and gain settings are in the MaxWell manual (MaxLab Live documentation), not in this course
- Stimulation: dedicated stimulation units connected per electrode through the switch matrix, driven from a DAC; limits and waveforms come from the manual and the lab SOP
- Where the device manual lives:

## Analysis pipeline
- Package: MXtreme (https://github.com/Project-HAL/MXtreme). Its `docs/concepts/data-flow.md` and `docs/concepts/data-dictionary.md` describe every stage and every field.
- Workflow: activity scan → electrode selection → network scan → cleaning pipeline → binned spikes and ASDR → burst detection → per-DIV summaries and PDF reports
- Current parameter values (amplitude threshold, refractory period, bin width, blanking window, burst-detection settings) live in the MXtreme docs and the lab's configuration. The tutor describes what each parameter does and sends the learner there for the value.

## Electrode materials
- Fixed by the chip. The lab does not coat electrodes. `branches/coatings.md` is context for other platforms and the literature.

## Local SOPs the learner should know exist
- (List titles and locations only. Do not paste procedures or limits here.)

## Topics this lab wants emphasized or de-emphasized
-

## Terminology specific to this lab
- "activity scan", "network scan", "batch", "DIV", "ASDR", "network burst" vs. "mini burst", "phase" (pre / train / post): see the MXtreme docs for the precise meanings.
