# Module 6: Synapses and integration

> **Builds on:** Modules 3, 4, 5 · **Next:** `07_extracellular_recording.md` · **Widgets:** `widgets/synaptic_integration.html`

## Destination

The learner can reason about chemical and electrical synapses, postsynaptic conductance changes, reversal potentials, and temporal and spatial integration.

## Conceptual anchors

- At a chemical synapse, presynaptic electrical activity leads to transmitter release. Receptors then change the postsynaptic conductance through direct or indirect mechanisms.
- A synaptic current depends on both conductance and driving force: opening more channels does not by itself determine the direction of the current.
- "Excitatory" and "inhibitory" describe effects on spike probability in context. A conductance can shunt voltage changes even when it causes little voltage deflection itself.
- Postsynaptic potentials spread and sum through the cell's passive and active properties.
- Electrical synapses pass current through gap junctions and can couple cells bidirectionally or asymmetrically, depending on the junction's properties.
- Network activity emerges from cells and connections, but this course stops before formal network analysis.

## Required Socratic challenges

- Give a membrane voltage and a synaptic reversal potential, and ask for the current direction and the expected pull on voltage.
- Move the membrane voltage closer to reversal and ask what happens to the driving force.
- Compare two inputs arriving close together in time with the same inputs arriving far apart.
- Ask how a conductance increase can inhibit by shunting even if the membrane voltage barely changes.
- Ask which parts of a synaptic event an extracellular MEA might detect directly, indirectly, or not at all.

## Visual moments

`widgets/synaptic_integration.html` models a passive single compartment with conductance-based synapses. Its current convention is positive = outward, which you should state to the learner.

1. **Driving force.** Hold synapse A fixed and use the holding current to move the baseline V_m toward E_A. Predict first. The event shrinks, and it reverses sign once the baseline passes E_A.
2. **Same receptor, different effect.** Set E_A = −60 mV. From a baseline of −70 mV it depolarizes, and from −50 mV it hyperpolarizes. This is the transfer criterion made visible.
3. **Temporal summation.** Change the interval between A's two events, then change τ_m. (This connects back to Module 4.)
4. **Shunting.** Turn on synapse B with E_B = the resting potential, timed with A. B alone barely moves V_m, yet A's EPSP shrinks. Ask the learner to explain this with conductances in parallel.
- Spatial integration and gap junctions aren't simulated. Use on-the-fly diagrams if needed, and say so.

## Transfer criterion

The learner can explain why the same receptor conductance may have different voltage effects in different cells or at different membrane voltages.

## Memory

- **Uses from memory:** Module 3's `I = g(V − E)` intuition, Module 4's temporal summation explanation (quote it back), and Module 5's point that spike probability is what "excitatory" ultimately refers to.
- **Record for later:**
  - the learner's own-words explanation of driving force and shunting;
  - their answer to what an MEA can detect of synaptic events (Module 7 picks this up: slower extracellular signals reflect summed synaptic currents).
