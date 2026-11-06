# Module 10: The electrode-electrolyte interface

> **Builds on:** Modules 2, 9 · **Next:** `11_pedot_platinum_black.md` · **Widgets:** `widgets/impedance_spectrum.html`, `widgets/biphasic_stimulation.html`

## Destination

The learner can explain why a metal electrode in saline is not an ideal wire, and why interface behavior affects recording, stimulation, noise, polarization, and frequency response.

## Conceptual anchors

- In metal, current is electronic; in electrolyte, current is ionic. The interface must couple these two domains.
- Charge can be accommodated through double-layer charging and, depending on the material and voltage range, through faradaic charge-transfer reactions.
- The electrical double layer behaves partly like a capacitance, but real interfaces are nonideal, distributed, and history-dependent.
- Solution resistance, interfacial capacitance or constant-phase behavior, charge-transfer resistance, diffusion, surface contamination, bubbles, cracks, and geometry can all matter.
- A reference electrode is part of the measurement circuit. Its placement and stability affect recorded voltages.
- Electrode polarization is a change in electrode potential caused by current through the interface. It matters especially during and after stimulation.
- Equivalent circuits summarize behavior over a chosen range. Don't read fitted components as unique microscopic truths.

## Required Socratic challenges

- Ask what must be converted when current passes from a metal lead into saline.
- Ask why a clean dry electrode can behave differently after wetting and equilibration.
- Ask why a bubble or poor wetting can increase apparent impedance and noise.
- Ask why a reference problem can affect many channels at once.
- Ask why an interface can pass a fast transient differently from a slow change.

## Visual moments

1. **Interface circuit.** Draw Rs + (Cdl ∥ Rct) on the fly. Before labeling, ask the learner which physical process each element stands for. Then state the limit: it summarizes behavior and is not the literal structure. (This parallels the Module 4 warning.)
2. **Fast vs. slow.** In `impedance_spectrum.html`, have the learner predict |Z| at low and high frequency *before* showing the plot. Ask which element "wins" at each end and why, in terms of Module 2's capacitor intuition.
3. **Bubble / poor wetting.** Use the "Bubble / poor wetting" preset, which reduces effective area. Predict, then compare it with a frozen reference trace.
4. **Polarization.** Go back to `biphasic_stimulation.html` and watch the interface (Cdl) voltage during and after a pulse. This is electrode polarization.

## Transfer criterion

The learner can explain why the same electrode may behave differently across frequency, time, medium, and prior stimulation history.

## Memory

- **Uses from memory:** Module 2's "capacitors pass fast changes more easily than slow ones." If it's marked *shaky*, bring Module 12's resistor-vs-capacitor challenge forward now (see `LLM/curriculum_map.md`). Also use Module 9's compliance explanation and Module 7's reference explanation.
- **Record for later (reused in Modules 11 and 12):**
  - the learner's own-words account of the metal→ion conversion;
  - their explanation of why a bubble raises impedance;
  - whether frequency-dependence feels intuitive yet (mark *solid*, *provisional*, or *shaky*).
