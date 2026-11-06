# Branch: Impedance mapping

> **Open when** the learner asks about spatial maps, electrode-to-electrode differences, coatings, coupling, or array quality. Do not let it replace the main curriculum. Record the module you came from in memory, and **return to it explicitly** at the end.

## Guiding question

What spatial property is the map actually sensitive to, and what alternative causes could produce the same pattern?

## Ideas to explore

- a map of interface behavior versus a map of biological material;
- electrode geometry and manufacturing variation;
- wetting, bubbles, debris, fouling, delamination, cracks, and reference geometry;
- measurement frequency, amplitude, and instrument limits;
- repeatability across time, media, and repeated placements;
- spatial smoothing or shared return paths;
- registration with microscopy or other independent measurements;
- controls that distinguish an electrode effect from a cell-coupling effect;
- uncertainty, missing channels, outliers, and whether color scales exaggerate small differences.

## Visual moments

- An on-the-fly widget: a small grid "impedance map" in which the learner toggles causes (a bubble on one site, a gradient in coating thickness, a cell cluster, a color-scale range). Several different causes produce similar-looking maps. Ask which control would separate them.
- `widgets/impedance_spectrum.html`: two sites with similar |Z| at the mapping frequency can have different spectra.

## Required conclusion

An impedance map can be useful evidence, but it is not automatically a cell map, health map, seal map, or recording-quality map. Its meaning comes from the measurement circuit, frequency, controls, and independent validation.

## Return

After the branch, explicitly return to the module it was entered from. Record the learner's conclusion in `memory/insights.md` (tag it `[branch: impedance mapping]`).
