# Module 12: Impedance as supporting context

> **Builds on:** Modules 2, 10 · **Next:** `13_synthesis.md` · **Widgets:** `widgets/impedance_spectrum.html` · **Branch often entered from here:** `branches/impedance_mapping.md`

## Destination

The learner can interpret impedance magnitude and phase as frequency-dependent interface information, use simple equivalent circuits cautiously, and avoid treating a single impedance value as a direct measure of neural health or electrode quality.

## Conceptual anchors

- Resistance is a special case of impedance. Capacitive and other dynamic elements make voltage and current differ in timing as well as amplitude.
- Impedance is complex and frequency-dependent. Both magnitude and phase can carry information.
- The chosen frequency should relate to the phenomenon of interest. A value at one frequency does not describe the whole interface.
- A spectrum can help distinguish broad behaviors, but several physical changes can produce similar spectra.
- Measurement amplitude, bias, equilibration, medium, temperature, reference or counter electrode, cabling, and instrument range can affect results.
- Equivalent-circuit fits can be nonunique. A good numerical fit does not prove that the chosen circuit is the true physical mechanism.
- Impedance can support quality control, detect large changes, and guide troubleshooting. It does not by itself identify cells, prove good neural coupling, or explain every recording difference.

## Required Socratic challenges

- Compare a resistor and a capacitor under slow and fast changes.
- Ask why the same electrode has no single context-free "impedance."
- Present two electrodes with the same impedance magnitude at one frequency but different phase or spectra. Ask what can and cannot be concluded.
- Ask how solution resistance, effective surface area, fouling, a bubble, or a crack might alter measurements, while noting the ambiguity.
- Ask what independent observations would strengthen an impedance-based interpretation.

## Visual moments

`widgets/impedance_spectrum.html`:

1. **Resistor vs. capacitor.** Use the "Resistor only" and "Capacitor only" presets. Predict the |Z| slope and the phase for each before showing them.
2. **No single impedance.** Use the default electrode and sweep the marker frequency. Ask the learner to say what "the impedance is 1 MΩ" is missing.
3. **Same |Z|, different story.** Freeze one configuration, then adjust Rs, Q, and n until |Z| at 1 kHz roughly matches while the spectra differ. Ask what can and cannot be concluded.
4. **CPE exponent.** Lower n from 1 toward 0.7 and ask how the phase changes. Tie this to "real interfaces are nonideal and distributed" (Module 10).

## Transfer criterion

The learner can state what was measured, at which frequency and under which conditions, and can separate observation from interpretation.

## Memory

- **Uses from memory:** Module 2 (capacitor current depends on dV/dt, which is *why* impedance falls with frequency; quote the learner's τ explanation), Module 10's frequency-dependence grade, and Module 11's point that area lowers the capacitive part but not Rs.
- **Record for later (reused in Module 13, Cases B, D, and E):**
  - the learner's own words for "an impedance number is incomplete without frequency and conditions";
  - their answer to the same-|Z|-different-spectra challenge;
  - if the impedance-mapping branch was visited, its conclusion.
