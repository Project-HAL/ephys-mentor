# Intuition first: the intuition gate and the use of mathematics

This is the single, authoritative statement of the course's central teaching principle. Every module, checkpoint, and readiness check refers back to it.

## The principle

Physical reasoning comes first. Build a causal model, then show how the mathematics compresses it. The equation describes the physical relation. It is not the reason the relation exists. Never accept "because the equation says so" as a complete explanation.

## The intuition gate

A concept is **not complete** because the learner got the right numerical answer. To pass, the learner must also:

- predict the qualitative result *before* calculating;
- explain why the equation has the form it does;
- say what physical process each term represents;
- translate the result back into that process after calculating.

Outcomes:

- **Numerically right, causal explanation weak:** the concept is not learned. Go back to the missing physical step.
- **Strong intuitive account, arithmetic not yet fluent:** pass provisionally. Then help the learner connect the intuition to the formal relation and its units.
- **Both sound:** pass. Record the learner's explanation in `memory/insights.md`.

Example: a larger `RC` time constant is not slow just because multiplication gives a bigger number. More resistance limits how fast charge can rearrange. More capacitance means more charge must be separated to produce the same voltage change.

## Procedure for every equation

1. Identify the physical process that produces the relation.
2. Define every symbol and its unit.
3. Describe the relation in words.
4. Ask the learner to predict the qualitative result before calculating.
5. Ask what happens when one term increases or decreases.
6. Check the extreme cases.
7. Do one easy numerical example.
8. Go back to the physical meaning and ask why the result makes sense.

A visual often works well between steps 5 and 8. Show the relation with a slider only after the learner has predicted the direction of the effect.

## Unit fluency

Use dimensional checks often. Get the learner comfortable moving between:

- volts and millivolts;
- amperes and pico-, nano-, and microamperes;
- seconds and milliseconds;
- ohms and megaohms;
- farads and picofarads.

Useful shortcuts to *derive* with the learner rather than hand over:

- mV / MΩ = nA
- pA × MΩ = µV
- MΩ × pF = µs
- nS × mV = pA
- pF / nS = ms

## Core relations

These must become usable, not merely familiar:

- `I = dQ/dt`: current is the rate at which charge crosses a chosen surface.
- `V = W/Q`: voltage difference is energy change per unit charge.
- `V = IR` and `I = GV`: resistance and conductance relate voltage difference to current in an ohmic element.
- `P = VI = I^2 R = V^2/R`: electrical power, under the stated circuit assumptions.
- `Q = CV`: capacitance relates separated charge to voltage.
- `I_C = C dV/dt`: capacitor current depends on how fast the voltage changes.
- `tau = RC`: the time scale of a first-order passive RC response.
- `E_ion = (RT/zF) ln([ion]_outside/[ion]_inside)`: an ion's equilibrium potential. Pay careful attention to valence and sign.
- `I_ion = g_ion(V_m - E_ion)`: a useful conductance-based current relation, under a declared current convention.
- `Z(f) = V(f)/I(f)`: impedance is frequency-dependent opposition to alternating or time-varying current, and it generally has both magnitude and phase.

Do not imply that all biological conductances are linear resistors, or that any single equivalent circuit is the literal microscopic structure.

## Three levels of description

The course keeps moving between three levels. Keep them visibly separate:

- **Physical:** charges, ions, fields, materials, geometry.
- **Circuit:** voltage sources, resistors, capacitors, impedances.
- **Biological or experimental:** membranes, channels, neurons, electrodes, amplifiers, arrays.

A circuit diagram is a useful compressed model. It does not claim that a cell contains tiny electronic components.
