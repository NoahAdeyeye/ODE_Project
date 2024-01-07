# Engineering Programming and Applications - Project

During my sophomore fall semester, I took differential equations, where I learned about ODEs. In the previous semester, I had taken Engineering Programming and Applications, during which I modeled ODEs. With increased knowledge about ODEs and differential equations from this semester, I revisited and revised my Engineering Programming and Applications project.

## Introduction

This project implements several numerical methods to solve Ordinary Differential Equations (ODEs). Specifically, it provides simulations for two models: SIR (Susceptible-Infectious-Recovered) and SIRV (SIR with Vaccination).

## How It Works

The code includes a general ODESolver class and three specific solver classes: ForwardEuler, RungeKutta4, and AdamsB. These classes are utilized to solve ODEs numerically.

The SIR and SIRV models are implemented as callable classes, and the simulation is performed using the ODESolver classes.

## Example

Here's an example of using the code to simulate the SIR model:

```python
import numpy as np
import matplotlib.pyplot as plt
from ODESolver import ForwardEuler
from ODESolver import RungeKutta4
from ODESolver import AdamsB

# Define SIR parameters and initial conditions
sir = SIR(0.1, 0.0005, 1500, 1, 0)
solver = ForwardEuler(sir)
solver.set_initial_conditions(sir.initial_conditions)

# Define time steps and solve the ODE
time_steps = np.linspace(0, 60, 1001)
u, t = solver.solve(time_steps)

# Plot the results
plt.plot(t, u[:, 0], label="Susceptible")
plt.plot(t, u[:, 1], label="Infected")
plt.plot(t, u[:, 2], label="Recovered")
plt.legend()
plt.show()
```

## How to Use

To use the code for your own simulations, follow these steps:

1. Import the necessary classes from the ODESolver module.
2. Define your ODE problem by creating a callable class.
3. Choose a solver method (e.g., ForwardEuler, RungeKutta4, AdamsB).
4. Set the initial conditions and solve the ODE by providing time points.

## Dependencies

This project depends on the following libraries:

- **NumPy**: For numerical operations.
- **Matplotlib**: For plotting results.

Experiment!
