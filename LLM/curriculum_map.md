# Curriculum map

Modules are the required destinations. They are not scripts to recite. Move forward only when the learner can explain the module's central causal links and use them in a new case, meaning the module's **transfer criterion** is met and the intuition gate in `LLM/intuition_and_math.md` has passed.

Load one module file at a time.

## The causal spine

**charge and energy → voltage and current → resistance and capacitance → membrane voltage → ion channels → action potentials and synapses → extracellular signals → the array and its routing → amplifier, filter, sampler, file → spike detection → stimulation → the interface, as context → reading the output → the whole system**

The destination is a learner who can take any output of the lab's recording system and trace it back, step by step, to ions crossing membranes, naming at each step what was measured, what was decided, and what is being inferred.

## The platform

The course is built around the **MaxWell Biosystems CMOS high-density MEA** (MaxOne / MaxTwo) and the lab's analysis pipeline. The physics modules (0 to 7) are platform-independent. Modules 8 to 14 use the MaxWell system as the concrete case: its switch matrix, its on-device spike detection, its file layout, and the pipeline's cleaning, binning, and burst-detection steps. Device specifications (electrode count, pitch, channel count, sampling rate) are fine to state. The exact detection rule, gain settings, and any operational parameters come from the device manual and the pipeline's own documentation, named in `LLM/lab_context.md`; never invent them.

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
| 8 | `modules/08_array_and_switch_matrix.md` | Electrodes ≠ channels; routing, scans, and selection shape what is recorded | 7 | `extracellular_field.html`; on-the-fly routing diagrams |
| 9 | `modules/09_from_potential_to_sample.md` | Offset, gain, filters, sampling, LSB: a microvolt becomes an integer | 2, 7, 8 | `rc_circuit.html`; on-the-fly sampling plots |
| 10 | `modules/10_spikes_in_the_file.md` | A spike-table row is a detection decision, not an action potential | 5, 7, 9 | on-the-fly threshold plots; `action_potential.html` |
| 11 | `modules/11_stimulation.md` | Command → stim unit → interface → field → membrane → response, artifact, blanking, events | 2, 5, 7, 8, 9 | `biphasic_stimulation.html` |
| 12 | `modules/12_interface_and_impedance.md` | Interface is not a wire; impedance read cautiously, as context | 2, 9, 11 | `impedance_spectrum.html`, `biphasic_stimulation.html` |
| 13 | `modules/13_reading_the_output.md` | Spike table → channel map → binned matrix → ASDR → bursts → report | 8, 9, 10, 11 | on-the-fly raster, ASDR, layout plots |
| 14 | `modules/14_synthesis.md` | Trace cause and measurement through the full system | all | on-the-fly causal graphs |

### Note on module 12

Module 12 is deliberately lighter than the modules around it. On a CMOS array the learner does not choose, coat, or characterize electrodes, so the interface is something to account for when channels differ, not something to engineer. If the learner's work involves other platforms or coating studies, open `branches/coatings.md` from there. If Module 9 recorded frequency-dependence as *shaky*, start Module 12 with its resistor-vs-capacitor challenge.

## Side branches

Open a branch **only** when it resolves a learner question or strengthens the current concept, never to show off extra knowledge. When you enter a branch, record the module you came from, and return to it explicitly at the end.

| Branch | File | Open when the learner asks about... |
|---|---|---|
| Electrode coatings | `branches/coatings.md` | PEDOT, platinum black, why electrodes are coated on other platforms, judging a coating claim |
| Impedance mapping | `branches/impedance_mapping.md` | spatial impedance maps, electrode-to-electrode differences, array quality |
| Reference and grounding | `branches/reference_grounding.md` | ground, reference choice, common-mode signals, shared artifacts |
| Noise | `branches/noise.md` | noise sources, noise vs. impedance, "why is this channel noisy" |
| Seal and coupling | `branches/seal_coupling.md` | cell-electrode proximity, adhesion, seal resistance |
| Spatial reach and volume conduction | `branches/volume_conduction.md` | why neighboring sites correlate, source localization |
| Stimulation artifact | `branches/stimulation_artifact.md` | saturation, blanking, recovery, artifact vs. response |
| Patch clamp bridge | `branches/patch_clamp_bridge.md` | voltage clamp, current clamp, intracellular recording |

Filtering, sampling, and aliasing are no longer a branch. They are the main path in Module 9.

## Boundary of the course

The course ends at **reading** the pipeline's output: knowing what a raster, an ASDR trace, a burst table, and a per-DIV summary are made of. It stops before **analyzing** that output: spike sorting, firing statistics as a research tool, network and connectivity measures, dimensionality reduction, decoding, criticality, and model validation. Those belong to a separate later course. Give a short answer only when it is needed to mark the boundary.
