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

These are the parameter values encoded in the notebook; the
interpretation depends on the model assumptions used for the project.

