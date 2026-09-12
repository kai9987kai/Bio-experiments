# 🧬 Bio Experiments

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
![HTML5](https://img.shields.io/badge/HTML5-Single--File-orange)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-yellow)
![Status](https://img.shields.io/badge/status-experimental-blue)
![Platform](https://img.shields.io/badge/platform-browser-lightgrey)

**Bio Experiments** is a collection of interactive, browser-based computational biology and chemistry experiments exploring biological systems through mechanistic simulation, numerical modelling, uncertainty analysis and scientific visualization.

The repository currently focuses on three experimental areas:

- 🌿 plant physiology and vascular transport
- 🧪 fermentation and phytochemical transformation
- 🧠 neuropharmacology and interacting biological signalling systems

Each simulator is implemented as a **standalone HTML application** containing its interface, visualization, mathematical model and JavaScript simulation engine in a single file.

> **Important:** These projects are research-oriented educational simulations. They are not validated laboratory assays, clinical models, medical devices, dosing calculators or substitutes for experimental measurements.

---

## Contents

- [Overview](#overview)
- [Current Simulations](#current-simulations)
  - [BLACK 3.0 Leaf Injection Simulator](#1-black-30-leaf-injection-simulator)
  - [Blue Lotus Fermentation Chemistry Simulator](#2-blue-lotus-fermentation-chemistry-simulator)
  - [Multisystem Neuropharmacology Sandbox](#3-multisystem-neuropharmacology-sandbox)
- [Research Philosophy](#research-philosophy)
- [Model Architecture](#model-architecture)
- [Running the Simulations](#running-the-simulations)
- [Repository Structure](#repository-structure)
- [Scientific Interpretation](#scientific-interpretation)
- [Uncertainty](#uncertainty)
- [Safety](#safety)
- [Limitations](#limitations)
- [Future Development](#future-development)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

# Overview

Biological systems are highly nonlinear, multiscale and uncertain.

Even comparatively simple biological questions can involve interactions between:

- diffusion
- fluid transport
- reaction kinetics
- metabolism
- receptor signalling
- cellular stress
- tissue injury
- environmental conditions
- stochastic variation
- poorly characterized chemical composition

The purpose of **Bio Experiments** is to explore how these mechanisms can be represented computationally in interactive models.

Rather than presenting a single numerical answer as fact, the simulations are designed to expose the underlying assumptions and allow parameters to be modified interactively.

The general philosophy is:

```text
Biological hypothesis
        ↓
Mechanistic abstraction
        ↓
Mathematical model
        ↓
Numerical integration
        ↓
Interactive simulation
        ↓
Visualization
        ↓
Uncertainty-aware interpretation
```

The models therefore function primarily as **computational thought experiments**.

---

# Current Simulations

## 1. BLACK 3.0 Leaf Injection Simulator

**File:** [`black3.0_leafinjection.html`](black3.0_leafinjection.html)

An interactive plant-physiology simulation examining the hypothetical consequences of introducing a BLACK 3.0-like pigmented acrylic suspension into leaf tissue.

The model explores several coupled mechanisms including:

- injection trauma
- local tissue injury
- xylem-associated transport
- diffusion
- advection
- particle retention
- pit-membrane filtration
- acrylic/binder deposition
- embolism
- hydraulic conductance loss
- leaf water potential
- stomatal response
- tissue stress
- uncertain phytotoxic effects

### Adjustable parameters

The simulator exposes variables including:

- injection location
- injection volume
- applied pressure
- effective pigment/aggregate diameter
- pit constriction scale
- acrylic/binder solids
- entrained air
- baseline leaf hydraulic conductance
- vapour-pressure deficit
- uncertain phytotoxicity

### Conceptual transport model

The transport layer is based around a simplified advection-diffusion-deposition system:

\[
\frac{\partial C}{\partial t}
=
-\nabla \cdot (\mathbf{v}C)
+
\nabla \cdot (D\nabla C)
-
k_{dep}C
\]

where:

- \(C\) = modeled material concentration
- \(\mathbf{v}\) = transport velocity field
- \(D\) = effective diffusion coefficient
- \(k_{dep}\) = deposition/retention term

Particle movement between vascular regions is further limited according to the relationship between effective aggregate size and modeled pit-membrane constriction.

### Outputs

The interface visualizes quantities including:

- remaining leaf hydraulic conductance
- retained material
- estimated injured area
- leaf water potential
- stomatal conductance
- spatial material distribution
- hydraulic stress
- tissue viability

### Scientific caveat

The simulator does **not** claim to predict the real response of a particular plant to BLACK 3.0.

Important unknowns include:

- proprietary paint formulation
- true pigment particle-size distribution
- aggregation behaviour
- binder chemistry
- plant species
- vascular anatomy
- injection mechanics
- immune/wound responses
- chemical toxicity

The model should therefore be interpreted mechanistically rather than experimentally.

---

## 2. Blue Lotus Fermentation Chemistry Simulator

**File:** [`blue_lotus_fermentation_simulator.html`](blue_lotus_fermentation_simulator.html)

A larger computational chemistry and fermentation sandbox exploring the interaction between yeast fermentation, plant extraction and hypothetical biochemical transformation of compounds associated with *Nymphaea caerulea*.

The simulator combines:

- fermentation kinetics
- yeast growth
- substrate consumption
- ethanol generation
- environmental effects
- plant-compound extraction
- degradation
- candidate biotransformations
- uncertainty propagation
- compound classification
- reaction-network visualization

### Numerical features

The current simulator includes:

- **fourth-order Runge-Kutta integration (RK4)**
- deterministic simulation
- Monte Carlo uncertainty mode
- configurable numerical timestep
- random-seed control
- mass-balance auditing
- compound-network visualization
- CSV export
- JSON export
- internal model checks

### Fermentation inputs

Examples of adjustable conditions include:

- liquid volume
- fermentable sugar concentration
- yeast biomass
- dissolved oxygen
- temperature
- starting pH
- fermentation duration

### Botanical inputs

Plant-related parameters include:

- plant mass
- dried/fresh material
- particle size
- uncertainty profile

The botanical chemistry is intentionally represented using uncertain priors rather than assuming that every sample contains identical concentrations.

### Compound confidence system

Predicted chemical entities are separated conceptually into categories such as:

```text
Established
     ↓
Known analogue
     ↓
Chemically plausible
     ↓
Speculative prediction
```

This distinction is critical.

A chemical produced by the simulation is **not equivalent to a compound detected by analytical chemistry**.

Predicted candidates should instead be treated as hypotheses that could potentially be investigated using techniques such as:

- LC-MS
- LC-MS/MS
- GC-MS
- HPLC
- NMR spectroscopy
- authentic reference standards

### Monte Carlo modelling

Where biological or chemical parameters are uncertain, repeated runs can explore a distribution of possible outcomes instead of returning a single deterministic trajectory.

Conceptually:

\[
\theta_i \sim P(\theta)
\]

followed by:

\[
Y_i = f(\theta_i)
\]

for many independently sampled parameter sets.

This helps distinguish robust model behaviour from behaviour that depends strongly on uncertain assumptions.

### Interpretation warning

This simulator is **not**:

- a chemical identification instrument
- a laboratory assay
- evidence that a compound exists in a real fermentation
- a potency calculator
- a dosing tool
- a safety calculator

Analytical identification requires actual experimental measurement.

---

## 3. Multisystem Neuropharmacology Sandbox

**File:** [`neuropharmacology_multidrug_brain_simulator.html`](neuropharmacology_multidrug_brain_simulator.html)

An uncertainty-aware systems-neuroscience sandbox examining interactions between several different pharmacological and biological mechanisms.

The current conceptual system includes:

- LSD-like serotonergic signalling
- Semax-associated neurotrophic signalling
- nicotine / nicotinic acetylcholine receptor activity
- ketamine-associated NMDA receptor blockade
- blue-lotus alkaloid uncertainty
- a generic neural-cell graft state

The simulator deliberately models these as **normalized target-engagement variables rather than physical doses**.

No real injection concentration, volume, coordinate, needle geometry or dose-conversion system is provided.

### Biological systems represented

The model explores interactions involving:

- 5-HT₂A signalling
- glutamatergic activity
- NMDA receptors
- AMPA-associated signalling
- nicotinic acetylcholine receptors
- dopamine-system modulation
- receptor desensitization
- BDNF/TrkB-associated signalling
- plasticity-related pathways
- network excitation/inhibition
- inflammatory state
- neural stress
- graft viability
- immune incompatibility

### Network visualization

The simulator provides a dynamic systems-level representation in which biological nodes and pathways respond to changing modeled conditions.

Outputs include:

- serotonergic signalling
- glutamate drive
- plasticity signal
- network stress
- excitation/inhibition balance
- nicotine desensitization
- BDNF/TrkB state
- inflammatory state
- graft viability
- evidence confidence

### Uncertainty modelling

The model allows uncertainty to be re-sampled so that poorly constrained biological relationships are not represented as exact constants.

Particular uncertainty applies to:

- multi-drug interactions
- blue-lotus composition
- graft behaviour
- immune response
- cross-pathway nonlinearities

This is especially important because combinations of biological interventions generally have much weaker evidence than the individual mechanisms considered independently.

---

# Research Philosophy

The project follows several principles.

## 1. Mechanisms before animation

Visualizations should correspond to an underlying state variable or mathematical process wherever practical.

The objective is not simply to generate visually convincing biological behaviour.

The objective is to ask:

> **What mechanisms would have to exist for this behaviour to occur?**

---

## 2. Separate evidence from speculation

Models may contain several levels of confidence.

For example:

```text
Well-established mechanism
        │
        ├── experimentally constrained parameter
        │
        └── literature-supported interaction
                    │
                    ▼
             uncertain interaction
                    │
                    ▼
             hypothesis-generating
                    │
                    ▼
              speculative state
```

The interface should distinguish these categories rather than presenting every output with equal confidence.

---

## 3. Make uncertainty visible

Biological parameters are rarely exact.

Where possible, future versions should describe important parameters using distributions:

\[
X \sim P(\theta)
\]

rather than assuming:

\[
X = constant
\]

Monte Carlo simulation can then propagate parameter uncertainty into model outputs.

---

## 4. Preserve mass and state consistency

Where a model tracks physical material, state transitions should ideally obey conservation constraints.

A simplified balance can be expressed as:

\[
M_{initial}
=
M_{remaining}
+
M_{transformed}
+
M_{removed}
+
M_{degraded}
\]

Large residual errors may indicate numerical instability or model inconsistency.

---

## 5. Distinguish simulation from measurement

A simulated compound is not a detected compound.

A simulated receptor response is not a measured receptor response.

A simulated tissue injury state is not experimental histology.

Computational models are most useful when they generate **testable hypotheses**, not when their outputs are mistaken for measurements.

---

# Model Architecture

Although each experiment has a different biological model, the applications generally follow a similar architecture:

```text
┌───────────────────────────────────────┐
│            User Parameters            │
└───────────────────┬───────────────────┘
                    │
                    ▼
┌───────────────────────────────────────┐
│        Parameter Validation           │
└───────────────────┬───────────────────┘
                    │
                    ▼
┌───────────────────────────────────────┐
│       Biological State Model          │
│                                       │
│  transport • kinetics • signalling    │
└───────────────────┬───────────────────┘
                    │
                    ▼
┌───────────────────────────────────────┐
│        Numerical Integration          │
└───────────────────┬───────────────────┘
                    │
                    ▼
┌───────────────────────────────────────┐
│      Derived Biological Metrics       │
└───────────────────┬───────────────────┘
                    │
              ┌─────┴─────┐
              ▼           ▼
        Visualization   Data Export
```

---

# Technology

The current project intentionally keeps its technical stack lightweight.

### Front end

- HTML5
- CSS3
- modern JavaScript
- Canvas API
- SVG where appropriate

### Numerical modelling

Depending on the experiment:

- explicit state updates
- differential-equation approximations
- RK4 numerical integration
- diffusion/advection approximations
- stochastic parameter sampling
- Monte Carlo simulation
- mass-balance checking
- nonlinear response functions

### Architecture

The applications currently use a:

> **single-file browser simulation architecture**

This means each `.html` file contains its own interface and simulation logic.

Advantages include:

- no installation
- no build system
- easy offline use
- easy archiving
- easy experimentation
- minimal dependencies
- straightforward source inspection

---

# Running the Simulations

## Option 1 — Open directly

Clone the repository:

```bash
git clone https://github.com/kai9987kai/Bio-experiments.git
cd Bio-experiments
```

Then open any simulator in a modern browser.

For example:

```text
black3.0_leafinjection.html
blue_lotus_fermentation_simulator.html
neuropharmacology_multidrug_brain_simulator.html
```

---

## Option 2 — Local web server

Python can be used to serve the repository locally:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000/
```

This is useful during development because the files behave as normal web resources rather than `file://` documents.

---

# Repository Structure

```text
Bio-experiments/
│
├── black3.0_leafinjection.html
│   └── Plant transport and tissue-response simulator
│
├── blue_lotus_fermentation_simulator.html
│   └── Fermentation, extraction and chemistry simulator
│
├── neuropharmacology_multidrug_brain_simulator.html
│   └── Systems neuropharmacology sandbox
│
├── CODE_OF_CONDUCT.md
│   └── Community participation guidelines
│
├── SECURITY.md
│   └── Security reporting information
│
├── LICENSE
│   └── MIT License
│
└── README.md
    └── Project documentation
```

---

# Scientific Interpretation

The models operate at different abstraction levels.

They should not automatically be interpreted as quantitative predictors.

A useful hierarchy is:

| Level | Meaning |
|---|---|
| Mechanistic | Represents a biologically plausible process |
| Quantitative | Parameters correspond to measurable quantities |
| Calibrated | Parameters have been fitted to experimental data |
| Validated | Predictions have been tested against independent data |
| Predictive | Model has demonstrated useful out-of-sample performance |

Most experiments in this repository currently belong primarily to the **mechanistic / hypothesis-generation** end of this spectrum.

That distinction is important.

---

# Uncertainty

Several sources of uncertainty affect biological simulations.

### Parameter uncertainty

The true value of a parameter is unknown.

### Structural uncertainty

The equations themselves may omit important biology.

### Measurement uncertainty

Published experimental values may contain error.

### Biological variability

Different organisms, tissues, cells or samples may respond differently.

### Chemical uncertainty

Botanical products and complex mixtures may have poorly characterized or highly variable composition.

### Interaction uncertainty

Combining several mechanisms often produces behaviour that cannot be reliably inferred from studies of each mechanism independently.

Future versions should increasingly quantify these uncertainties rather than representing them using single constants.

---

# Numerical Validation

Useful validation strategies for future models include:

### Conservation tests

Verify mass or energy conservation where applicable.

### Limiting-case tests

For example:

```text
zero substrate → zero product
zero exposure → baseline signalling
zero transport → no spatial redistribution
```

### Timestep convergence

Compare:

\[
\Delta t
\]

with:

\[
\frac{\Delta t}{2}
\]

and verify that the resulting trajectories converge.

### Parameter sensitivity

Estimate:

\[
S_i =
\frac{\partial Y}{\partial \theta_i}
\]

to identify which uncertain parameters dominate the model output.

### Monte Carlo convergence

Increase the number of samples and test whether estimated distributions stabilize.

### Experimental validation

Where real datasets exist, simulated outputs should ultimately be compared with independent experimental observations.

---

# Safety

Some simulations explore hazardous or medically sensitive scenarios.

They are provided for computational and educational exploration only.

## Do not use these models as instructions for real experiments involving:

- injection of substances into humans
- injection into brain tissue
- administration of psychoactive substances
- intracranial transplantation
- unregulated stem-cell procedures
- preparation of psychoactive mixtures
- determination of drug doses
- prediction of individual medical responses

Direct introduction of chemicals or biological material into nervous tissue can cause severe injury including:

- haemorrhage
- infection
- seizures
- inflammatory injury
- tissue destruction
- immune reactions
- abnormal cell growth
- neurological disability
- coma
- death

The neuropharmacology simulator intentionally uses normalized scenario variables rather than actionable exposure quantities.

---

# Botanical and Fermentation Safety

Fermentation models are also simulations rather than food-safety instruments.

They do not establish whether a real preparation is:

- microbiologically safe
- chemically safe
- free from contamination
- correctly fermented
- pharmacologically predictable
- suitable for consumption

Likewise, predicted molecular transformations do not demonstrate that those compounds actually exist in a physical sample.

Only experimental analytical chemistry can establish composition.

---

# Limitations

Current limitations include:

- simplified biological geometry
- limited spatial resolution
- uncertain kinetic constants
- phenomenological approximations
- incomplete metabolic pathways
- incomplete receptor-network representation
- limited species-specific modelling
- incomplete chemical databases
- simplified enzyme kinetics
- simplified pharmacodynamics
- uncertain multi-agent interaction models
- uncertain botanical composition
- no direct experimental calibration for several scenarios
- limited validation against independent datasets

Increasing visual complexity should therefore not be confused with increasing scientific certainty.

---

# Future Development

Potential future improvements include:

### Numerical modelling

- adaptive timestep integration
- automatic stiffness detection
- implicit ODE solvers
- PDE solvers
- stochastic differential equations
- Bayesian parameter estimation
- Sobol sensitivity analysis
- Latin-hypercube sampling
- uncertainty intervals
- ensemble simulation

### Chemistry

- structured reaction networks
- enzyme-specific kinetics
- molecular identifiers
- SMILES representation
- InChI/InChIKey support
- reaction provenance
- mass/charge validation
- isotope-aware analysis
- thermodynamic feasibility estimates

### Plant biology

- explicit vascular graphs
- xylem/phloem separation
- stomatal models
- species presets
- transpiration models
- 2D/3D tissue meshes
- compartment-specific transport

### Neuroscience

- receptor occupancy models
- neural population dynamics
- region-specific signalling
- excitatory/inhibitory population models
- plasticity timescales
- pharmacokinetic compartments
- receptor internalization
- tolerance/desensitization dynamics

Any medically sensitive extensions should continue to avoid transforming the project into real-world procedural or dosing guidance.

### Visualization

- WebGL rendering
- interactive network graphs
- parameter heatmaps
- phase-space plots
- confidence bands
- uncertainty distributions
- pathway diagrams
- comparative experiment mode

### Reproducibility

Future versions could additionally export:

```json
{
  "model": "example",
  "version": "x.x.x",
  "parameters": {},
  "random_seed": 12345,
  "numerical_method": "RK4",
  "timestamp": "...",
  "results": {}
}
```

This would allow simulations to be reproduced exactly.

---

# Suggested Long-Term Project Structure

As the repository expands, the project could eventually migrate toward:

```text
Bio-experiments/
│
├── experiments/
│   ├── plant/
│   ├── fermentation/
│   ├── chemistry/
│   └── neuroscience/
│
├── models/
│   ├── transport/
│   ├── kinetics/
│   ├── pharmacology/
│   └── uncertainty/
│
├── datasets/
│
├── references/
│
├── tests/
│
├── docs/
│
└── index.html
```

This would allow common numerical components to be shared between experiments while maintaining reproducibility.

---

# Scientific Development Goals

Long-term development should aim to move individual experiments through:

```text
Concept
   ↓
Mechanistic model
   ↓
Documented assumptions
   ↓
Parameter provenance
   ↓
Numerical verification
   ↓
Sensitivity analysis
   ↓
Experimental calibration
   ↓
Independent validation
```

A model should only be described as predictive when sufficient validation supports that claim.

---

# Contributing

Contributions, scientific corrections and model improvements are welcome.

Useful contributions include:

- correcting biological mechanisms
- identifying better parameter estimates
- improving numerical stability
- adding scientific references
- adding validation datasets
- adding automated tests
- improving accessibility
- improving visualization
- identifying unsupported assumptions
- improving uncertainty modelling

When proposing a new mechanism, ideally include:

1. the biological mechanism
2. the mathematical representation
3. parameter units
4. parameter source
5. evidence quality
6. expected limitations
7. a reference where appropriate

Please see [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) before contributing.

Security-related issues should follow [`SECURITY.md`](SECURITY.md).

---

# Disclaimer

This software is provided for:

- education
- computational experimentation
- scientific visualization
- hypothesis generation
- software development
- exploration of mathematical models

It is **not medical advice**.

It is **not experimental proof**.

It is **not a laboratory protocol**.

It is **not a clinical decision-support system**.

It is **not a dosing calculator**.

Simulation outputs should not be interpreted as evidence that the same result would occur in a living organism or physical experiment.

---

# License

This project is licensed under the **MIT License**.

See [`LICENSE`](LICENSE) for the complete license text.

Copyright © 2026 **Kai Piper**

---

# Author

**Kai Piper**

GitHub: [@kai9987kai](https://github.com/kai9987kai)

Repository:

https://github.com/kai9987kai/Bio-experiments

---

## ⭐ Bio Experiments

**Explore biology computationally — while keeping a clear boundary between models, hypotheses and experimental evidence.**