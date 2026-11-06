# Module 5: Action potentials

> **Builds on:** Modules 3, 4 · **Next:** `06_synapses_integration.md` · **Widgets:** `widgets/action_potential.html`

## Destination

The learner can explain an action potential as a regenerative, time-dependent change in ionic conductances, and can connect threshold, refractory periods, and propagation to that mechanism.

## Conceptual anchors

- Depolarization changes the state of voltage-gated channels.
- Fast inward current can produce positive feedback: depolarization opens channels, inward current depolarizes further, and more channels open.
- Inactivation of the inward conductance and delayed activation of an outward conductance end the upstroke and repolarize the membrane.
- Threshold is a dynamical tipping region, not a universal fixed voltage painted on every neuron.
- Absolute and relative refractory periods arise from channel state and lingering conductance changes, not from the neuron "running out of electricity."
- Propagation is local regeneration along excitable membrane. The same ions do not travel from the soma to the axon terminal during one spike.
- Spike amplitude is not normally the code for stimulus strength once a spike is generated. Timing and rate often carry more information, depending on cell and circuit context.

## Required Socratic challenges

- Ask why passive depolarization alone would decay, but an action potential can regenerate.
- Ask the learner to identify the positive-feedback step and the recovery steps.
- Change sodium-channel availability and ask how excitability, the upstroke, or refractory behavior might change.
- Ask why a stronger suprathreshold input does not simply create an action potential twice as tall.
- Ask how local current from one axon segment can bring the next segment toward threshold.
- Ask what an extracellular recording of a spike shares with an intracellular action potential, and what it lacks.

## Common traps to surface

- "An action potential is electricity traveling as electrons down the axon."
- "Threshold is a hard universal number."
- "The pump resets the membrane after every spike."
- "A larger extracellular spike must mean a larger intracellular action potential."

## Visual moments

`widgets/action_potential.html` is a Hodgkin-Huxley model: squid axon parameters, a single compartment, no propagation.

1. **Below vs. above threshold.** In prediction mode, increase the pulse amplitude in small steps. Ask for the prediction at each step. The small responses decay passively (Module 4); the large one runs away. Then switch the lower panel to the gates (m, h, n) and ask the learner to locate the positive-feedback step.
2. **Threshold isn't a fixed number.** Compare a short strong pulse with a long weak pulse. Both reach "threshold," but at different voltages.
3. **Stronger input ≠ taller spike.** Double a suprathreshold amplitude and compare the peak voltages.
4. **Refractoriness.** Turn on the second pulse and shorten the interval. Ask the learner to predict when the second spike fails, and explain it using h and n.
5. **Sodium availability.** Reduce Na⁺ availability and ask what happens to the upstroke and to excitability.
6. **Rate coding.** Use a long pulse (tens of ms) and raise the amplitude. Ask whether spike height or spike count carries the stimulus strength.
- Propagation is not simulated. Use an on-the-fly diagram of local current loops ahead of the active region, and state this limitation.

## Transfer criterion

The learner can tell the causal story from a small depolarization, through regenerative activation, repolarization, and refractoriness, to propagation, using channel states rather than a memorized list of phases.

## Memory

- **Uses from memory:** Module 3's "V_m pulled toward the most permeable ion's E." The upstroke is the Na⁺ permeability jumping, and repolarization is K⁺ winning back. Module 4's passive decay explains why subthreshold inputs fade. Also recheck any pump misconception recorded in Module 3.
- **Record for later:**
  - the learner's causal AP story in their own words (Module 7 needs "transmembrane currents during a spike" as the source of extracellular signals);
  - their explanation of refractoriness (Module 9 uses it for stimulation trains);
  - their answer to "extracellular vs. intracellular spike," to revisit in Module 7.
