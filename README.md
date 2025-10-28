# Tutorial for Isaac Lab Projects

This repository is a tutorial repository, designed to go hand in hand with the Getting Started walkthrough found in the Isaac Lab [docs](https://isaac-sim.github.io/IsaacLab). Each branch of the repository 
represents another stage of the walkthrough, with the main branch being the "final state" of the tutorial project.

```math

```


```math
% 1. Observation (Naive)
\mathbf{obs} = 
\begin{bmatrix}
\mathbf{v} \\
\mathbf{c}
\end{bmatrix},
\quad
\dim(\mathbf{obs}) = 6 + 3 = 9

% 2. Forward vector
\mathbf{f}_{world} = q_{root} \otimes [1, 0, 0]

% 3. Reward (Naive)
r_{total} = r_{forward} + r_{alignment}
\quad
r_{forward} = v_{b,x},
\quad
r_{alignment} = \mathbf{f}_{world} \cdot \mathbf{c}

% 4. Observation Tuning
\mathrm{dot} = \mathbf{f}_{world} \cdot \mathbf{c}
\quad
\mathrm{cross}_z = (\mathbf{f}_{world} \times \mathbf{c})_z
\quad
v_{forward} = v_{b,x}
\quad
\mathbf{obs} = 
\begin{bmatrix}
\mathrm{dot} \\
\mathrm{cross}_z \\
v_{forward}
\end{bmatrix}

% 5. Reward (Tuned Multiplicative)
r_{total} = r_{forward} \cdot r_{alignment}
\quad
r_{forward} = v_{b,x},
\quad
r_{alignment} = \mathbf{f}_{world} \cdot \mathbf{c}

% 6. Reward with Exponential Alignment
r_{total} = r_{forward} \cdot e^{r_{alignment}}
\quad
r_{alignment} = \mathbf{f}_{world} \cdot \mathbf{c},
\quad
r_{forward} = v_{b,x}

```
