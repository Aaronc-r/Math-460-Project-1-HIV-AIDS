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



