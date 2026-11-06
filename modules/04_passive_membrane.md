# Module 4: The passive membrane as an RC system

> **Builds on:** Modules 2, 3 · **Next:** `05_action_potentials.md` · **Widgets:** `widgets/rc_circuit.html` (current-injection mode), `widgets/synaptic_integration.html`

## Destination

The learner can connect the membrane's physical structure to an equivalent circuit, and can reason about input resistance, membrane capacitance, leakage, time constant, and passive voltage spread.

## Conceptual anchors

- The lipid bilayer acts as a capacitor. Open channels provide conductances in parallel with that capacitance.
- Batteries in an equivalent membrane circuit represent equilibrium potentials maintained by ion gradients. They are not literal batteries inside the cell.
- Injected current first charges the membrane capacitance, and later flows more through the steady ionic conductances.
- Higher input resistance produces a larger steady voltage change for the same injected current, all else equal.
- The time constant controls temporal integration. Cable properties and the length constant control spatial spread; geometry and membrane and internal resistance matter.
- A real neuron has distributed membrane, branches, active conductances, and nonuniform channel densities. A single RC compartment is a starting model.

## Required Socratic challenges

- Ask the learner to map the bilayer, saline, channels, and ion gradients onto a circuit.
- Hold the injected current fixed and change the membrane resistance. Ask about the final voltage and the time course.
- Hold the resistance fixed and change the capacitance. Ask what changes and what does not.
- Compare a large cell and a small cell qualitatively, separating total capacitance from specific capacitance.
- Ask why two cells can share a membrane time constant yet show different input resistances or capacitances.
- Give a current pulse and ask the learner to sketch or describe charging and recovery.

## Visual moments

1. **Circuit mapping.** Draw the membrane equivalent circuit (SVG or Mermaid): C_m in parallel with g_leak, which is in series with E_leak. Ask the learner to label which physical thing each element stands for *before* you label it.
2. **`rc_circuit.html`, current-injection mode.** Hold I fixed and change R. Unlike Module 2's voltage-step mode, the *final* voltage now changes. Ask why, contrasting it with Module 2. Then watch the current panel: I_C dominates early and I_R dominates late.
3. **Same τ, different R and C.** Freeze a trace, then double R and halve C. τ is unchanged but the steady voltage differs. Use this for the challenge about two cells sharing τ.
4. **Temporal summation.** In `synaptic_integration.html`, vary the interval between two inputs and the membrane τ. This previews Module 6 and is the transfer case for this module.

## Transfer criterion

The learner can use an RC model to explain temporal summation while naming at least two ways a real neuron departs from that model.

## Memory

- **Uses from memory:** the learner's Module 2 explanation of τ, which should be quoted back and extended rather than re-taught, and Module 3's "V_m pulled toward E," which is where the battery in the circuit comes from.
- **Record for later:**
  - the learner's circuit mapping in their own words (Module 12 revisits equivalent circuits for electrodes, and the "a model is not literal structure" warning applies there too);
  - their explanation of temporal summation (Module 6 builds on it);
  - which departures from the RC model they named.
