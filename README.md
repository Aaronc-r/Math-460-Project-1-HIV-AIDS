Mathematica Notebook for Math 460: Mathematical Modeling Project 1

This repository contains a Wolfram Mathematica notebook for studying a
four-compartment population model and comparing a baseline scenario with
three intervention scenarios.

## Overview

The notebook defines a system of ordinary differential equations (ODEs)
for four state variables:

-   (S(t))
-   (U(t))
-   (P(t))
-   (A(t))

The model tracks how the population is distributed among these
compartments over time. The total population is constrained to be 1,000,
and the notebook uses the initial condition

\[ (S(0),U(0),P(0),A(0))=(760,200,30,10). \]

The notebook compares a baseline model with three intervention scenarios
labeled **Testing & Education**, **Antivirals**, and **Needle
Exchange**.

## Repository Contents

-   `Math460_Project1_Model.nb` --- Mathematica notebook containing the
    model definitions, parameter sets, equilibrium analysis, stability
    classification, and numerical simulations.

## Model

The general model is defined by

\[
```{=tex}
\begin{aligned}
S' &= -\frac{\beta cSU}{1000}-\frac{\omega cSP}{1000}-\tau S,\\
U' &= \frac{\beta cSU}{1000}+\frac{\omega cSP}{1000}-\alpha U+\tau S,\\
P' &= \epsilon\alpha U-\mu P,\\
A' &= (1-\epsilon)\alpha U+\mu P.
\end{aligned}
```
\]

Here,
(`\alpha`{=tex},`\beta`{=tex},`\omega`{=tex},`\epsilon`{=tex},`\mu`{=tex},c,`\tau`{=tex})
are model parameters. The notebook assigns different parameter values to
each scenario to represent the baseline and intervention assumptions.

### Initial Conditions

  Variable      Initial value
  ----------- ---------------
  (S(0))                  760
  (U(0))                  200
  (P(0))                   30
  (A(0))                   10
  **Total**         **1,000**

### Scenarios

The notebook compares these four parameter sets:

  ------------------------------------------------------------------------------------------------------------------------------------
  Scenario       (`\alpha`{=tex})   (`\beta`{=tex})   (`\omega`{=tex})   (`\epsilon`{=tex})   (`\mu`{=tex})     \(c\)   (`\tau`{=tex})
  ------------ ------------------ ----------------- ------------------ -------------------- --------------- --------- ----------------
  Baseline                    0.5              0.15                0.2                0.784             0.2        10                0

  Testing &                  0.75             0.075                  0                0.784             0.2         5              0.4
  Education                                                                                                          

  Antivirals                 0.75              0.15               0.02                0.784            0.02        10              0.4

  Needle                     0.75              0.15                  0                0.784             0.2        10              0.2
  Exchange                                                                                                            
  ------------------------------------------------------------------------------------------------------------------------------------

These are the parameter values encoded in the notebook; their
interpretation depends on the model assumptions used for the project.

## What the Notebook Does

1.  **Defines the models** --- sets up the baseline system and the three
    intervention variants.
2.  **Sets model parameters** --- collects scenario-specific values in a
    parameter table.
3.  **Finds equilibria** --- solves for states where all derivatives are
    zero, subject to nonnegative compartment sizes and a total
    population of 1,000.
4.  **Classifies stability** --- examines the Jacobian/eigenvalue
    behavior at equilibrium states.
5.  **Runs numerical simulations** --- solves each scenario over a time
    horizon of 1,000.
6.  **Checks numerical consistency** --- samples trajectories to check
    that the total population remains close to 1,000.
7.  **Plots trajectories** --- visualizes transient and long-term
    behavior for comparison across scenarios.

## Requirements

-   Wolfram Mathematica (the notebook was created with Mathematica
    13.3).

## How to Run

1.  Clone or download this repository.
2.  Open `Math460_Project1_Model.nb` in Wolfram Mathematica.
3.  Evaluate the notebook cells from top to bottom. If you want a clean
    run, restart the kernel before evaluating the notebook.
4.  Review the parameter table, equilibrium and stability results,
    numerical checks, and trajectory plots.

The notebook uses symbolic calculations as well as numerical ODE
solving, so some cells may take time to evaluate.

## Notes

-   The numerical simulations use the initial conditions listed above
    for all four scenarios.
-   The notebook uses a long integration horizon of (t=1000) for
    numerical validation.
-   Results depend on the model equations and chosen parameters. The
    scenarios should be interpreted as comparisons within this model
    rather than as universal predictions.

## Author
