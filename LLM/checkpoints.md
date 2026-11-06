# Checkpoints, mentor handoff, and course end

Load this file when a module is ending, when a mentor brief is due, or when the final readiness check begins.

## Module checkpoint

At the end of each module:

1. Give one unfamiliar transfer problem, based on the module's transfer criterion.
2. Ask for a qualitative prediction before allowing any calculation.
3. Ask the learner to explain the physical chain in their own words, including what each relevant mathematical term represents.
4. Change one feature of the case and ask the learner to predict the result without reaching for an equation first.
5. Ask for a confidence rating from 1 to 5 and one remaining uncertainty.
6. If the answer is numerically right but the causal explanation is weak, the module does not pass. Go back to the missing physical step (see `LLM/intuition_and_math.md`).
7. If causal and formal reasoning are both sound, the module passes. Then:
   - write the Progress Note into `memory/progress.md` (format below);
   - save the learner's best own-words explanation from this module to `memory/insights.md`;
   - update the module status table and the **Resume here** block;
   - in Mode B, output the updated memory files now, because a checkpoint is a natural save point.

### Progress Note format

```markdown
### Progress Note: Module N (YYYY-MM-DD)
- Completed:
- Physical intuition demonstrated:
- Mathematics connected to that intuition:
- Still uncertain about:
- Useful side branches visited:
- Next module:
- Question to bring to a mentor:
```

Keep it short and factual. It supports continuity and is not a grade.

## Mentor discussion brief

After every two or three modules, or whenever the learner asks, help them prepare a short brief to take to a human mentor:

```markdown
## Mentor Discussion Brief (YYYY-MM-DD, after Module N)
### My current model
[Three to six sentences in the learner's own words]

### Where I am unsure
- [Specific uncertainty]

### A lab connection I want to test
- [Observation, prediction, or comparison]

### Questions for my mentor
- [Question that depends on this lab, preparation, platform, or research goal]
```

Ask the learner to draft the brief first. Then help tighten it without replacing their reasoning. Save the final version to `memory/mentor_briefs.md`. When the learner comes back with answers from their mentor, record those answers in `memory/insights.md` under "Lab-specific answers from mentor". They override general assumptions from then on.

## Final readiness check

Do not use a trivia quiz. Ask the learner to reason through new cases. Require predictions before calculations. The learner must explain why the mathematics takes the form it does and must translate every result back into a physical process. "Because the equation says so" means the concept needs more work.

Before you write the final cases, read `memory/insights.md` and target any items marked shaky or any misconceptions that were repaired earlier.

The learner is ready to move on when they can:

- distinguish charge, voltage, current, resistance, conductance, capacitance, and impedance;
- explain a passive RC response and the membrane time constant;
- connect ion gradients and selective conductance to membrane potential;
- explain an action potential through changing channel states and currents;
- use reversal potential and driving force to reason about synaptic effects;
- explain what extracellular electrodes measure relative to a reference;
- explain why electrodes and channels are different things on the array, and how routing, scanning, and electrode selection decide what gets recorded;
- trace a microvolt at an electrode through offset compensation, gain, filtering, sampling, and quantization to an integer and a frame number, and convert back;
- explain that a spike-table row is a detection decision, name what it misses and invents, and say what the raw trace adds;
- trace stimulation from command through the stimulation unit, interface, field, and membrane to the recorded response, artifact, blanking window, and event tags;
- explain why the electrode interface is not a wire and interpret an impedance value cautiously, with frequency, conditions, and controls;
- take a raster, an ASDR trace, a burst table, or a per-DIV summary and trace it back to the spike table, naming the transformations and parameters in between;
- distinguish direct measurement from decision from inference, at every stage;
- propose a discriminating check when several explanations fit an observation.

## End point and next curriculum

When the learner meets the readiness criteria, do not drift into advanced analysis. Close with:

- a connected summary built largely from the learner's own explanations, drawn from `memory/insights.md`;
- a list of remaining questions for the mentor;
- a final Progress Note;
- a suggestion that the next, separate course could cover analysis of the output this course taught them to read.

That later course could include spike sorting, firing statistics as research tools, burst and network analysis, population activity, dimensionality reduction, decoding, criticality, connectivity, and model validation. Do not teach those topics here unless a short answer is needed to mark the boundary of this course.
