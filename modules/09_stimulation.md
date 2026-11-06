# Module 9: Electrical stimulation

> **Builds on:** Modules 2, 5, 7 · **Next:** `10_electrode_interface.md` · **Widgets:** `widgets/biphasic_stimulation.html`

## Destination

The learner can explain how current through an electrode changes the extracellular potential and can polarize excitable membranes, while recognizing the roles of waveform, geometry, interface, artifact, and safety.

## Conceptual anchors

- Stimulation drives charge through the electrode-electrolyte interface and creates an electric field in the conductive medium.
- A neuron's response depends on spatial changes in extracellular potential along its processes, cell geometry, channel state, distance, orientation, and network connections.
- Current-controlled and voltage-controlled stimulation constrain different quantities. The resulting voltage or current depends on the interface and the load.
- Pulse amplitude, duration, polarity, phase order, interphase interval, repetition, and electrode geometry all matter.
- Charge per phase and charge density are useful safety and interface concepts, but safe limits are specific to the electrode, waveform, medium, device, and protocol.
- Charge-balanced biphasic waveforms are often used to limit net charge accumulation, but "balanced" does not guarantee zero artifact, zero irreversible reactions, or biological safety.
- A stimulation artifact can saturate the recording path or recover slowly, and can be mistaken for biological activity.
- Direct activation, axonal activation, synaptic recruitment, network response, and artifact can overlap in time.

## Required Socratic challenges

- Ask what must happen between a stimulator command and a membrane becoming polarized.
- Hold the commanded current fixed and increase the interface impedance. Ask what may happen to the electrode voltage and why compliance limits matter.
- Ask why doubling the pulse duration changes the delivered charge even if the current amplitude is unchanged.
- Ask how a response on many channels at exactly the same sample could differ from a propagated neural response.
- Ask why reversing polarity can change which neural elements are activated.
- Ask what evidence would separate a true evoked response from residual artifact.

## Safety boundary

Do not present any operational stimulation settings as generally safe. For real experiments, tell the learner to consult the device manual, electrode specifications, preparation-specific literature, institutional safety rules, and the lab SOP, and then to confirm the plan with the mentor. If `LLM/lab_context.md` lists the relevant SOPs, name them.

## Visual moments

`widgets/biphasic_stimulation.html` shows a current-controlled biphasic pulse into a simple interface model (Rs + Cdl ∥ R_faradaic). **All of its numbers are illustrative. Say this out loud.**

1. **Charge = current × time.** Predict first, then double the phase width. Watch the charge-per-phase readout and the capacitor voltage.
2. **Compliance.** Lower Cdl or raise Rs, which stands in for a higher-impedance interface, until the required voltage exceeds the compliance limit. The delivered current then falls below the command. Ask the learner to explain why.
3. **Balance and ratcheting.** Set the balance to 80% and run a 10-pulse train. Net charge accumulates as residual polarization. Then set it to 100% and point out that the residual isn't zero during the pulse, only near zero afterward.
4. **Phase order.** Switch cathodic-first to anodic-first and ask what changes at the interface. (Which neural elements get activated is not modeled here, so discuss that with an on-the-fly diagram.)
- For the "every channel at the same sample" challenge, make an on-the-fly plot of simulated traces on several channels: an artifact is simultaneous everywhere, while a propagated response has increasing latency with distance.

## Transfer criterion

The learner can trace a stimulation event through the instrument, interface, field, membrane polarization, possible spike generation, network response, recording artifact, and observed data.

## Memory

- **Uses from memory:** Module 2 (a capacitor charges with current × time, and its voltage can't jump; the interface is largely capacitive), Module 5 (threshold and refractoriness under pulse trains), and Module 7 (the field falls off with distance, and polarity depends on geometry).
- **Record for later (reused in Modules 10 and 13, Case C):**
  - the learner's traced stimulation chain, in their own words;
  - their explanation of compliance, i.e., why a current source can't always deliver the commanded current;
  - how they would separate artifact from an evoked response;
  - any safety question that should go to the mentor (`insights.md` → Open questions).
