# Conversation Record: AI-Assisted Patient Routing

This record preserves the substantive user-facing discussion that led to the accompanying LaTeX model and PDF. It excludes internal reasoning and tool logs.

## Initial objective

**User:** Please turn the AI-routing proposal discussed in the pinned conversation into a `.tex` file that can be edited in Overleaf.

**Outcome:** `AI_Routing_Proposal.tex` was created and compiled. The proposed paper studies AI-assisted triage in hybrid healthcare, where patient compliance, congestion, and reentrant demand jointly determine the value of AI.

## Model clarification

**User:** What do the original model terms `L(x)`, `gamma`, `delta(x)`, and `G(x)` represent?

**Discussion outcome:**

- `L(x)` was interpreted as the expected non-queueing loss from an inadequate virtual encounter.
- `gamma` was identified as a reduced-form trust/default effect of an AI recommendation.
- `delta(x)` was interpreted as the probability that virtual care fails and requires in-person follow-up.
- `G(x)` was interpreted as the distribution of patient types.

## Information structure decision

**User:** Please explain why `gamma` is needed.

**Discussion outcome:** A fixed `gamma` is useful only when a recommendation has a behavioural effect beyond information. For a fully rational baseline, the preferred design is instead complementary information:

\[
\theta \longrightarrow (X,S) \longrightarrow R \longrightarrow \text{channel choice} \longrightarrow \text{queues and reentry}.
\]

Here, `theta` is latent clinical complexity, `X` is the patient's private signal, `S` is the AI's provider-data signal, and `R` is the AI recommendation. The recommendation has rational value because it changes the patient's posterior belief about the risk of virtual-care failure.

**User:** I agree with the complementary-information approach. Please develop a baseline model, solve it, and write propositions and theorems.

**Outcome:** `AI_Routing_Baseline_Model.tex` was developed with binary latent complexity and independent patient/AI signals. It derives posterior failure risk, endogenous channel choice, queueing equilibrium, and results on compliance, composition, information value, and patient discretion.

## AI score and routing threshold

**User:** What are the AI score and the threshold `tau`?

**Discussion outcome:** In the continuous extension, the AI score is a calibrated predicted risk that virtual care will fail. The routing threshold `tau` is the hospital's decision rule: a patient is recommended virtual care when the score is at or below `tau`. Score quality and the operational threshold are distinct.

## Requested polish of the baseline paper

**User:** Please add detailed proofs in an appendix; an introduction with motivations, research question, and expected outcomes; detailed justification of model settings and hospital/patient trade-offs; intuitive explanations for results; and extensions on continuous settings, outside options, endogenous participation, and priority for reentry. Do not add heterogeneity in travel burden or waiting sensitivity.

**Outcome:** The baseline model was revised accordingly. The revised PDF is included in this repository as `AI_Routing_Baseline_Model.pdf`.

## Current artifacts

- `AI_Routing_Baseline_Model.tex`: polished baseline model and results.
- `AI_Routing_Baseline_Model.pdf`: compiled nine-page PDF.
- `Conversation_Record.md`: this discussion record.
