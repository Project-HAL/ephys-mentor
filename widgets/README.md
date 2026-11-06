# Widgets

Self-contained interactive simulations. **Double-click any `.html` file to open it in a browser.** No internet or installation is needed.

Every widget has:
- sliders with units;
- a **Prediction mode** checkbox that hides results until you click Reveal (predict first, then look);
- a **Try this** list of predict-then-test prompts;
- a note saying what the model simplifies. All values are illustrative.

## Catalog

| File | Shows | Modules | Key moments |
|---|---|---|---|
| `rc_circuit.html` | RC charging and discharging. Voltage-step (series RC) and current-injection (membrane R ∥ C) modes; freeze a reference trace | 2, 4 (branches: filtering, patch clamp) | Current at t = 0⁺ vs. later; double R vs. double C; brief vs. long pulse; why the final V depends on R only in current mode |
| `nernst_ghk.html` | Nernst potentials for K⁺, Na⁺, Cl⁻, and any ion (choose z); GHK resting V_m on a number line; driving-force direction table | 3 | Sign and valence; "opening K⁺ channels" depolarizing when V_m < E_K; weighted tug-of-war |
| `synaptic_integration.html` | Passive compartment with two conductance-based synapses (alpha functions); holding current; driving force; shunting | 4, 6 (branch: patch clamp) | Driving force → reversal; same receptor, opposite effect; temporal summation vs. τ_m; shunting inhibition |
| `action_potential.html` | Hodgkin-Huxley model: V, gates (m, h, n), conductances, currents; two pulses; Na⁺ availability; K⁺ scaling | 5 | Threshold as a tipping region; stronger ≠ taller; refractoriness via h and n; rate coding with long steps |
| `extracellular_field.html` | 2-D potential map from sink/source neurons; click to place recording electrode and reference; two cells with timing offset; amplitude vs. distance | 7, 8 (branches: reference, volume conduction) | Distance falloff; polarity depends on position; reference changes every channel; synchrony; neighbors correlate |
| `impedance_spectrum.html` | Bode plot (|Z| and phase) of R_s + (CPE ∥ R_ct); effective-area multiplier; presets; frozen reference | 10, 11, 12 (branch: impedance mapping) | Resistor vs. capacitor; "no single impedance"; coatings lower the capacitive part but not R_s; same |Z|, different spectrum |
| `biphasic_stimulation.html` | Current-controlled biphasic pulse into R_s + (C_dl ∥ R_f); compliance limit; charge per phase and density; train polarization | 9, 10, 11 | Charge = I × t; compliance clipping; imbalance ratchets polarization; more C_dl → less polarization |

## For the tutor (LLM)

- If you can render HTML inline (for example, as artifacts or a canvas), render the file **verbatim**. Don't rewrite it.
- If you can't, tell the learner the file name to open and which controls to try, and ask for their prediction first.
- New widgets you build go in `generated/` and follow the conventions in `LLM/visuals.md`.

## Adding widgets

Anyone can add a widget here. Keep to the conventions in `LLM/visuals.md`: one self-contained file, no network, units on everything, prediction mode, a "Try this" list, and an honest "what this simplifies" note. Add a row to the table above and a mention in the relevant module's "Visual moments" section.
