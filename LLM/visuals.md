# Visuals: widgets, plots, and diagrams

Real visuals such as interactive sliders, live plots, and clean diagrams make a big difference in this course. Many of its ideas are time courses (RC charging, action potentials, synaptic summation), spatial patterns (extracellular fields), or frequency behavior (impedance). Words and ASCII art handle these badly.

**Default expectation:** at key moments, and whenever the learner asks, produce a real visual using the best capability you have. You do not need permission to make one. Do not wait to be asked at the moments listed in each module's "Visual moments" section.

## Step 1: know what you can do

At the start of a session, work out which of these you can do. Use the highest one available:

| Rank | Capability | Examples | What to do |
|---|---|---|---|
| 1 | Render interactive HTML or JS inline | Claude artifacts, ChatGPT Canvas, other HTML widget tools | Build or render an interactive widget with sliders and live plots |
| 2 | Write files the learner can open | Claude Code, Cowork, Codex, other agents (Mode A) | Point to a prebuilt file in `widgets/`, or write a new one to `widgets/generated/`, and tell the learner the exact path to open in a browser |
| 3 | Run code that produces images | Python with matplotlib in ChatGPT or Claude analysis tools | Make static plots. Use a small grid of panels to show a parameter sweep |
| 4 | Render SVG or Mermaid in markdown | Many chat interfaces | Draw circuit diagrams, causal chains, and signal-chain block diagrams |
| 5 | None of the above | Plain-text chat | Send the learner to the prebuilt widget in `widgets/` (double-click to open in any browser, no internet needed). Describe the picture carefully in words. Use ASCII only for trivially simple sketches |

Capabilities stack. In Mode A with artifacts available, you can render inline *and* save a copy to `widgets/generated/`.

**Prebuilt widgets come first.** `widgets/README.md` lists tested, self-contained HTML widgets for the most important concepts. When one fits, use it:

- If you can render HTML inline and the file is readable, render it as-is, copying the code verbatim. Don't rewrite it.
- If you can't render inline, give the learner the file name to open (for example `widgets/rc_circuit.html`) and tell them which controls to try.

## Step 2: use visuals Socratically

A visual is a tool for prediction and explanation. It does not replace them.

1. **Predict first.** Before showing the plot or moving the slider, ask the learner what they expect and why. Every prebuilt widget has a **"Prediction mode"** checkbox that hides the result until the learner clicks Reveal. Suggest it.
2. **Show one change at a time.** Name the single parameter to change.
3. **Ask the learner to explain what they see** in physical terms: "What is the charge doing during this part of the curve?"
4. **Then transfer.** "Now predict what happens if you double C instead."
5. **Name the model's limits.** Every widget simplifies something. Say what, as `LLM/tutor_rules.md` requires for analogies.

Don't make a visual when the learner should first build the picture themselves. For example, ask them to *describe* the charging curve before you show it. Don't show so much at once that the learner stops reasoning.

## When to make a visual

- At every **Visual moment** listed in the current module file.
- When the learner asks for one ("show me", "can you plot that", "I can't picture it").
- At hint-ladder step 3 or later, if isolating a variable visually would help.
- When comparing two cases side by side (double R vs double C, near vs far electrode, bare vs coated electrode).
- For diagrams: circuit equivalents, the recording signal chain, stimulation causal chains, and capstone causal graphs.

## Building a widget on the fly

When no prebuilt widget fits, build one that follows these conventions so the course stays consistent:

- **One self-contained HTML file.** Inline CSS and JS, no network requests, no external libraries. It has to work offline when double-clicked.
- **Controls:** sliders or inputs with visible values *and units*. Use logarithmic sliders for quantities that span decades (R, C, frequency).
- **Plots:** labeled axes with units, a legend, and a dashed reference line for key values (steady state, reversal potentials, τ).
- **Prediction mode:** a checkbox that hides results until the learner clicks Reveal. Changing a control while it is on hides the results again.
- **Freeze a reference trace** whenever a comparison matters, so the learner can see before and after together.
- **Honesty:** a short note saying what the model simplifies. Label any numbers as "illustrative values, not lab settings or safety limits."
- **Readable in light and dark mode**, and usable on a laptop screen.
- A short **"Try this"** list of two to four predict-then-test prompts connected to the current module.

In Mode A, save new widgets to `widgets/generated/<short_name>.html` and add a line to `memory/insights.md` under "Visuals that helped", so later sessions can reuse them. If a generated widget proves broadly useful, tell the learner it could be promoted into `widgets/` for everyone.

## Static plots (rank 3)

If you can only make static images:

- Plot the comparison as overlaid traces or a two- to four-panel grid (for example R = 50, 100, 200 MΩ).
- Label axes with units and mark the key quantity (τ, peak, reversal).
- Ask for the prediction *before* running the code, and say so in your message.

## Diagrams (rank 4)

Prefer Mermaid or SVG for:

- circuit equivalents (membrane R ∥ C with battery; electrode Rs + (Cdl ∥ Rct));
- signal chains (membrane current → field → electrode interface → amplifier → filter → ADC → file);
- causal graphs for the capstone cases (Module 13, Case D).

Keep diagrams small and ask the learner to explain or redraw them.
