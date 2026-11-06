# Branch: Patch clamp bridge

> **Open when** the learner asks about voltage clamp, current clamp, or intracellular recording, or when their lab work involves patch clamp (check `memory/learner_profile.md`). Most natural from Modules 4, 5, or 6. **Return to the module you came from.**

## Guiding question

Voltage clamp and current clamp control different quantities. What does each one hold fixed, what does it let vary, and therefore what does it measure?

## Ideas to explore

- current clamp: you set the injected current and watch the membrane voltage respond (this is Module 4's current-injection picture);
- voltage clamp: you command the membrane voltage, and the amplifier supplies whatever current is needed to hold it there, so the measured current reflects membrane currents at that voltage;
- why clamping voltage is useful for studying conductances: `I = g(V − E)` with V held fixed isolates changes in g (Module 3's relation);
- the parallel with stimulation (Module 11): controlling current and controlling voltage constrain different quantities, and the other one depends on the load;
- intracellular vs. extracellular: patch clamp measures across the membrane, while an MEA measures in the medium relative to a reference (Module 7).

## Visual moments

- `widgets/rc_circuit.html`: current-injection mode *is* current clamp on a passive membrane. Ask what a voltage-clamp version would show (a capacitive transient at the step, then steady current).
- `widgets/synaptic_integration.html`: use the holding current as a crude "clamp" to shift V_m and see the driving force change.

## Return

Tie back to the originating module. Record it in `memory/insights.md` with the tag `[branch: patch clamp]`.
