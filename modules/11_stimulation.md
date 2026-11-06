# Module 11: Electrical stimulation

> **Builds on:** Modules 2, 5, 7, 8, 9 · **Next:** `12_interface_and_impedance.md` · **Widgets:** `widgets/biphasic_stimulation.html`

## Destination

The learner can explain how a commanded pulse from the system becomes current through an electrode, a field in the medium, a change in a neuron's membrane potential, and an entry in the recording, while recognizing the roles of waveform, geometry, interface, artifact, blanking, and safety.

## Conceptual anchors

- Stimulation drives charge through the electrode-electrolyte interface and creates an electric field in the conductive medium.
- A neuron's response depends on spatial changes in extracellular potential along its processes, cell geometry, channel state, distance, orientation, and network connections.
- Current-controlled and voltage-controlled stimulation constrain different quantities. The resulting voltage or current depends on the interface and the load. On the MaxWell system, dedicated **stimulation units** are connected to chosen electrodes through the switch matrix and driven from a digital-to-analog converter; the lab's scripts set them to voltage mode. What the current through the interface then is depends on the interface.
- A stimulation electrode is also a recording electrode. Routing it for stimulation takes a channel, and the units and electrodes have their own constraints (one unit per electrode, a limited number of units).
- Pulse amplitude, duration, polarity, phase order, interphase interval, repetition, and electrode geometry all matter.
- Charge per phase and charge density are useful safety and interface concepts, but safe limits are specific to the electrode, waveform, medium, device, and protocol.
- Charge-balanced biphasic waveforms are often used to limit net charge accumulation, but "balanced" does not guarantee zero artifact, zero irreversible reactions, or biological safety.
- A stimulation artifact can saturate the recording path or recover slowly, and can be mistaken for biological activity. The pipeline **blanks** windows around each pulse: spikes in those frames are removed before analysis. Activity during a pulse is therefore unobservable by design.
- The system writes **events** into the file: stimulation start and stop with the pulse phase, plus experiment-phase tags, each stamped with a frame number. Analyses that count "stimulation delivered" or label "pre / train / post" rely entirely on these tags.
- Direct activation, axonal activation, synaptic recruitment, network response, and artifact can overlap in time.

## Required Socratic challenges

- Ask what must happen between a stimulator command and a membrane becoming polarized.
- In voltage mode, raise the interface impedance and hold the command fixed. Ask what happens to the delivered current and the charge. Then do the same in current mode and ask what happens to the voltage and why compliance limits matter.
- Ask why doubling the pulse duration changes the delivered charge even if the amplitude is unchanged.
- Ask how a response on many channels at exactly the same sample could differ from a propagated neural response.
- Ask why reversing polarity can change which neural elements are activated.
- Ask what blanking hides and what an analysis of "response to stimulation" can therefore only measure after the window.
- Ask what evidence would separate a true evoked response from residual artifact.
- Ask what a missing or wrong event tag would do to a per-phase analysis.

## Safety boundary

Do not present any operational stimulation settings as generally safe. For real experiments, tell the learner to consult the device manual, electrode specifications, preparation-specific literature, institutional safety rules, and the lab SOP, and then to confirm the plan with the mentor. If `LLM/lab_context.md` lists the relevant SOPs, name them.

## Visual moments

`widgets/biphasic_stimulation.html` shows a current-controlled biphasic pulse into a simple interface model (Rs + Cdl ∥ R_faradaic). **All of its numbers are illustrative. Say this out loud.**

1. **Charge = current × time.** Predict first, then double the phase width. Watch the charge-per-phase readout and the capacitor voltage.
2. **Compliance.** Lower Cdl or raise Rs, which stands in for a higher-impedance interface, until the required voltage exceeds the compliance limit. The delivered current then falls below the command. Ask the learner to explain why, then ask what the voltage-mode version of this failure looks like.
3. **Balance and ratcheting.** Set the balance to 80% and run a 10-pulse train. Net charge accumulates as residual polarization. Then set it to 100% and point out that the residual isn't zero during the pulse, only near zero afterward.
4. **Phase order.** Switch cathodic-first to anodic-first and ask what changes at the interface. (Which neural elements get activated is not modeled here, so discuss that with an on-the-fly diagram.)
5. **Artifact vs. response, and the blank.** On-the-fly plot of simulated traces on several channels: an artifact is simultaneous everywhere, a propagated response has increasing latency with distance. Shade the blanking window and ask what falls inside it.
6. **The event stream.** Sketch a timeline with event tags (recording phase starts, stimulation start/stop) and the spike raster beneath. Ask the learner to say which spikes belong to which phase, and what happens if one tag is missing.

## Transfer criterion

The learner can trace a stimulation event through the command, the stimulation unit, the interface, the field, membrane polarization, possible spike generation, network response, recording artifact, blanking, event tags, and observed data.

## Memory

- **Uses from memory:** Module 2 (a capacitor charges with current × time, and its voltage can't jump; the interface is largely capacitive), Module 5 (threshold and refractoriness under pulse trains), Module 7 (the field falls off with distance, and polarity depends on geometry), and Module 8 (a stimulation electrode is a routed electrode).
- **Record for later (reused in Modules 12, 13, and 14, Case C):**
  - the learner's traced stimulation chain, in their own words;
  - their explanation of compliance, and of what voltage mode leaves uncontrolled;
  - how they would separate artifact from an evoked response, and what blanking hides;
  - any safety question that should go to the mentor (`insights.md` → Open questions).
