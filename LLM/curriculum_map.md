# Curriculum map

Modules are the required destinations. They are not scripts to recite. Move forward only when the learner can explain the module's central causal links and use them in a new case, meaning the module's **transfer criterion** is met and the intuition gate in `LLM/intuition_and_math.md` has passed.

Load one module file at a time.

## The causal spine

**charge and energy → voltage and current → resistance and capacitance → membrane voltage → ion channels → action potentials and synapses → extracellular signals → electrodes and MEAs → stimulation → electrode materials and impedance**

## Modules

| # | File | Destination (one line) | Builds on | Prebuilt widgets |
|---|---|---|---|---|
| 0 | `modules/00_orientation.md` | Three levels of description; circuit as compressed model | — | — |
| 1 | `modules/01_charge_voltage_current.md` | Distinguish charge, voltage, current, resistance, power | 0 | — (on-the-fly circuit diagram) |
| 2 | `modules/02_capacitance_rc.md` | Capacitor voltage can't jump; meaning of τ | 1 | `rc_circuit.html` |
| 3 | `modules/03_membrane_potential.md` | Gradients, forces, permeability, and pumps give V_m | 1, 2 | `nernst_ghk.html` |
| 4 | `modules/04_passive_membrane.md` | Membrane as RC; input resistance; summation | 2, 3 | `rc_circuit.html`, `synaptic_integration.html` |
| 5 | `modules/05_action_potentials.md` | Regenerative conductance changes; threshold; refractoriness | 3, 4 | `action_potential.html` |
| 6 | `modules/06_synapses_integration.md` | Driving force, reversal potential, shunting, integration | 3, 4, 5 | `synaptic_integration.html` |
| 7 | `modules/07_extracellular_recording.md` | Extracellular voltage is relative, geometric, filtered | 1, 5, 6 | `extracellular_field.html` |
| 8 | `modules/08_multielectrode_arrays.md` | MEA as spatially sampled, reference-dependent measurement | 7 | `extracellular_field.html` |
| 9 | `modules/09_stimulation.md` | Command → interface → field → membrane → response/artifact | 2, 5, 7 | `biphasic_stimulation.html` |
| 10 | `modules/10_electrode_interface.md` | Metal/saline interface is not a wire | 2, 9 | `impedance_spectrum.html`, `biphasic_stimulation.html` |
| 11 | `modules/11_pedot_platinum_black.md` | Why rough coatings help, and what "better" requires | 10 (and 12's basics) | `impedance_spectrum.html` |
| 12 | `modules/12_impedance.md` | Magnitude, phase, and frequency; cautious equivalent circuits | 2, 10 | `impedance_spectrum.html` |
| 13 | `modules/13_synthesis.md` | Trace cause and measurement through the full system | all | on-the-fly causal graphs |

### Note on the impedance ordering

Module 12 formalizes impedance, but Modules 10 and 11 already rely on frequency-dependent behavior. If the learner hasn't yet connected "a capacitor passes fast changes more easily than slow ones" (Module 2) to the idea of frequency, bring Module 12's first challenge (a resistor vs. a capacitor under slow and fast changes) forward into Module 10. Record that you did this in `memory/progress.md`, then treat Module 12 as consolidation and extension.

## Side branches

Open a branch **only** when it resolves a learner question or strengthens the current concept, never to show off extra knowledge. When you enter a branch, record the module you came from, and return to it explicitly at the end.

| Branch | File | Open when the learner asks about... |
|---|---|---|
| Impedance mapping | `branches/impedance_mapping.md` | spatial impedance maps, electrode-to-electrode differences, coatings, coupling, array quality |
| Reference and grounding | `branches/reference_grounding.md` | ground, reference choice, common-mode signals, shared artifacts |
| Noise | `branches/noise.md` | noise sources, noise vs. impedance, "why is this channel noisy" |
| Seal and coupling | `branches/seal_coupling.md` | cell-electrode proximity, adhesion, seal resistance |
| Spatial reach and volume conduction | `branches/volume_conduction.md` | why neighboring sites correlate, source localization |
| Stimulation artifact | `branches/stimulation_artifact.md` | saturation, blanking, recovery, artifact vs. response |
| Frequency response and filtering | `branches/filtering.md` | high/low-pass filters, phase shift, aliasing, sampling rate |
| Patch clamp bridge | `branches/patch_clamp_bridge.md` | voltage clamp, current clamp, intracellular recording |

## Boundary of the course

Stop before advanced neural-data analysis: spike sorting, firing statistics, bursts, population activity, dimensionality reduction, decoding, criticality, connectivity, and model validation. Those belong to a separate later course. Give a short answer only when it is needed to mark the boundary.
