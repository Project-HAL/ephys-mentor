# Module 3: From ions to membrane potential

> **Builds on:** Modules 1, 2 · **Next:** `04_passive_membrane.md` · **Widgets:** `widgets/nernst_ghk.html`

## Destination

The learner can explain how concentration gradients, electrical forces, selective permeability, and ion pumps together make a stable membrane voltage possible.

## Conceptual anchors

- Diffusion pushes particles down concentration gradients; electric fields push charged particles according to their sign.
- For one ion species, the equilibrium potential is the voltage at which its chemical and electrical driving forces balance, giving zero net flux of that ion under the model.
- A cell contains several permeant ions. The resting membrane potential tends toward the equilibrium potentials of the ions with greater resting permeability. It is not usually equal to any one equilibrium potential.
- Pumps and transporters establish and maintain concentration gradients over longer times. Channels let ions move down electrochemical gradients. The Na+/K+ pump is not the moment-to-moment cause of the shape of each action potential.
- Only a tiny imbalance of charge near the membrane is needed to create membrane voltage. The bulk intracellular and extracellular solutions remain nearly electroneutral.
- Membrane voltage must use an explicit convention, usually `V_m = V_inside - V_outside`.

## Required Socratic challenges

- Put a permeant positive ion at higher concentration inside than outside. Ask which way diffusion pushes it and what charge separation begins to oppose that movement.
- Change the ion's valence or reverse the concentration ratio, and ask how the equilibrium potential changes sign.
- Ask why opening K+ channels often moves the membrane voltage toward `E_K`, rather than simply making the inside "more negative" in all cases.
- Ask what would happen immediately versus slowly if the pump stopped while channels stayed open.
- Ask why the whole cytoplasm does not need to become net negative to produce a negative membrane voltage.

## Equation handling

Introduce the Nernst equation only after the learner can describe the force balance. State the temperature and log convention if doing arithmetic. Treat the Goldman-Hodgkin-Katz relation qualitatively unless the learner asks for a deeper derivation.

## Common traps to surface

- "The pump directly generates every spike."
- "Ions move because they want equal concentrations," with no electrical force.
- "Opening a channel always depolarizes."
- "Equilibrium potential means equal concentrations."
- "The inside of the entire cell is full of excess negative charge."

## Visual moments

`widgets/nernst_ghk.html`:

1. **Valence and sign.** After the learner predicts, switch the "any ion" row between z = +1, −1, and +2 with the same concentrations. Ask why the sign flips and why +2 halves the magnitude.
2. **Pulled toward E_K.** Set V_m above E_K, then raise the K⁺ permeability. Next, reset, set `[K]_out` to 60 mM and p_Cl to about 5 so that V_m (≈ −47 mV) sits *below* E_K (≈ −23 mV), and raise the K⁺ permeability again. The same "open K⁺ channels" action now depolarizes. This directly addresses the trap "opening a channel always depolarizes."
3. **Weighted tug-of-war.** Raise the Na⁺ permeability step by step and watch V_m move toward E_Na. (This also sets up Module 5.)
- Optional on-the-fly diagram: a membrane cross-section showing that only a thin layer of charge near each face produces V_m, while the bulk solutions stay neutral.

## Transfer criterion

Given `V_m`, an ion's equilibrium potential, and a conductance change, the learner can predict the direction in which `V_m` will be pulled and explain why.

## Memory

- **Uses from memory:** Module 2's explanation that no ion crosses the bilayer to charge it (the same idea explains why only a thin charge layer is needed); Module 1's "voltage is relative," which leads directly to the V_m sign convention.
- **Record for later (reused in Modules 5 and 6):**
  - the learner's own words for "V_m is pulled toward the E of whichever ions are most permeable";
  - whether they can explain the sign of E for a cation vs. an anion;
  - the pump-vs-channel distinction. Module 5 retests "the pump resets each spike."
