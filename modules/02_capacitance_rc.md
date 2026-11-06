# Module 2: Capacitance and RC behavior

> **Builds on:** Module 1 · **Next:** `03_membrane_potential.md` · **Widgets:** `widgets/rc_circuit.html`

## Destination

The learner can explain why the voltage across a capacitor cannot change instantly in an ideal finite-current circuit, what a time constant means, and why a membrane behaves partly like a capacitor.

## Conceptual anchors

- A capacitor stores separated charge and electric-field energy. It does not require charge carriers to cross the insulating layer.
- Capacitance measures how much separated charge is associated with a given voltage.
- Capacitor current changes the stored charge and therefore the voltage.
- A resistor limits the charging current. As the capacitor voltage approaches the source voltage, the driving difference and the current both fall.
- In a first-order RC circuit, `tau = RC` sets the response time. After one time constant, a charging response has completed about 63% of its final change. The exact percentage matters less than understanding the time scale.
- RC circuits smooth rapid changes and create frequency-dependent behavior.

## Required Socratic challenges

- Ask what must physically change for the capacitor voltage to change.
- Present an uncharged capacitor connected through a resistor to a voltage source. Ask about the current at the first moment, much later, and in between.
- Ask separately what doubling `R` and doubling `C` do to the time course and to the final steady voltage.
- Use a biological-scale example such as `R = 100 megaohms` and `C = 100 picofarads`. Have the learner find `tau` and interpret it.
- Ask why no ion needs to cross the lipid bilayer for charge to accumulate on its two sides.
- Ask how a passive RC membrane responds differently to a brief pulse and a long pulse.

## Analogy limit

Do not call capacitance a bucket and stop there. A bucket stores material; a capacitor stores separated charge and field energy. The membrane's two conductive solutions are separated by a thin dielectric, while channels provide separate conductive paths across it.

## Visual moments

`widgets/rc_circuit.html` covers most of this module. Use **Voltage step → series RC** mode here. (Current-injection mode belongs to Module 4.)

1. **First moment vs. later.** Before showing anything, have the learner sketch in words the current and the voltage over time. Then show both panels. Ask why the current is largest at t = 0⁺.
2. **Double R vs. double C.** Freeze a reference trace, have the learner predict, then double R. Reset, then double C. Ask what changed and what didn't (the final voltage stays the same in voltage-step mode).
3. **Brief vs. long pulse.** Shrink the pulse duration well below τ. Ask why the voltage never reaches the source value.
4. **Time-constant marker.** Ask the learner to explain *physically* why the curve is steepest at the start.

## Transfer criterion

The learner can predict the qualitative voltage trace after current turns on and off, and can explain how changing resistance or capacitance changes the trace.

## Memory

- **Uses from memory:** the Module 1 definitions of voltage vs. current. "Current is rate of charge transfer" is the key that makes `I_C = C dV/dt` intuitive.
- **Record for later (important, reused in Modules 4, 9, 10, and 12):**
  - the learner's own-words explanation of *why* τ = RC (what R does, what C does);
  - their explanation of why no ion crosses the bilayer for the membrane to charge;
  - whether they grasped "capacitors pass fast changes more easily than slow ones." Module 10/12 builds impedance on this, so mark it *shaky* if unclear.
