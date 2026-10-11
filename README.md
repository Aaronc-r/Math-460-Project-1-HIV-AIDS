Math 460: Mathematical Modeling - Project 1

This repository contains a Wolfram Mathematica notebook for studying a
four-compartment population model and comparing a baseline scenario with
three intervention scenarios.

## Overview

We created a system of  4 ordinary differential equations (ODEs)
for four state variables:

-   S(t): Susceptible Population
-   U(t): Unconsciously Infected Population Living with HIV
-   P(t): Consciously Infected Population Living with HIV
-   A(t): Infected Population Living with AIDS

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

