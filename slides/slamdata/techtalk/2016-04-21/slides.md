# Particle Swarm Optimization

SlamData Tech Talk

April 21, 2016

---

## Motivation

- Curious about Swarm Algorithms
- Excuse to spend some time with Purescript
- That's enough right?

---

## Swarming

> Swarm behavior is a collective behavior exhibited by animals of similar size which aggregate together.
>
> — Yuxing Chen, Swarm Intelligence in Design

---

## Swarm Intelligence

> Swarm intelligence is the collective behavior of decentralized, self-organized systems, natural or artificial.
>
> — Yuxing Chen, Swarm Intelligence in Design

---

## Swarm Intelligence

- Emergent
- Many mostly similar individuals
- No centralized control
- Simple rules _mostly_
- Easy to think about _at least initially_
- Individuals are usually described in a probabilistic way
- Interactions typically local
- Usually "embarrassingly parallel"
- Fault tolerant due to decentralization and self-organization

---

## Swarm Algorithms

- Simulate the intelligence of the swarm
- "Swarm Intelligence" term introduced in 1989
- Nature-inspired metaheuristics
- Many different flavors only loosely associated
- How do they compare to other optimizations and algorithms?
- Linear vs non-linear optimization?

???

metaheuristic is a higher-level procedure or heuristic designed to find, generate, or select a heuristic (partial search algorithm) that may provide a sufficiently good solution to an optimization problem, especially with incomplete or imperfect information or limited computation capacity — A survey on metaheuristics for stochastic combinatorial optimization, Bianchi et al

---

## Examples

- Flocking _plain emergence or intelligence?_
- Ant colony
- Artificial Bee Colony
- Glowworm
- River formation dynamics
- Particle swarm

???

- Ant colony — probabilistic technique for finding paths through graphs
- Bees — concurrent search of "favorable" space combined with continual sampling to find new "favorable" space
- Glowworm — ant colony with luminescence that can converge on multiple optima
- River formation dynamics — drops as swarm. imitate water erosion and deposition. has been applied to routing and robot navigation
- Particle swarm — particles searching a space via position, velocity, and fitness

---

## Applications

- Art
- Science fiction
- Biological simulations
- UAVs
- Self-assembly
- Optimization
- Data mining

---

## Particle Swarm Optimization

- _Particles_ are the members
- Introduced by Kennedy and Eberhart in 1995
- Roots in simulation of social behaviors

---

## A few PSO Applications

- Neural Network Training
- Data mining
- Combinatorial optimization
- Signal processing

---

## PSO Algorithm

Loosely:

Next velocity and position of a particle is based on:
- position and velocity of that particle
- previous best position of that particle based on some cost function
- previous best position of a particle in a defined neighborhood (e.g. the complete swarm)

---

## PSO Algorithm _(more precisely)_

Initialize:  
Positions are random within region. Velocities are randomized to small values to prevent escaping the search space.

Update: $$
\vec{v}^{\,t+1}_i = w\vec{v}^{\,t}_i +
\varphi_1\vec{U}^{\,t}_1(\vec{b}^{\,t}_i - \vec{x}^{\,t}_i) +
\varphi_2\vec{U}^{\,t}_2(\vec{l}^{\,t}_i - \vec{x}^{\,t}_i) \,
$$

$$
\vec{x}^{\,t+1}_i = \vec{x}^{\,t}_i +\vec{v}^{\,t+1}_i \,
$$

$$
\vec{b}^{\,t+1}_i = f(\vec{x}^{\,t+1}_i)
$$

$$
\vec{l}^{\,t+1} = \min(\vec{b}^{\,t}_i)
$$

---

## PSO Algorithm _(more precisely)_

- $w$: inertial weight or momentum – memory of the previous flight direction
- acceleration coefficients
  - $\varphi_1$: cognitive component – tendency of particles to return to previously found best positions
  - $\varphi_2$: social component – performance of particle relative to neighbors

- $\vec{U}^{\,t}_1$, $\vec{U}^{\,t}_2$: n×n diagonal matrices having a main diagonal with random numbers uniformly distributed in [0,1) and are regenerated for each iteration
- $\vec{b}^{\,t}_i$: particle best
- $\vec{l}^{\,t}_i$: neighborhood best
- $f$: cost function
- — _M. Clerc and J. Kennedy. The particle swarm-explosion, stability and convergence in a multidimensional complex space. 2002_


---

## Purescript based simulation

.pso-simulation[]

---

## Tools

- purescript-drawing — "Functional rendering using PureScript and HTML 5 Canvas"
- purescript-signal — Elm style FRP
- purescript-vector — Sized vectors
- A touch of smoke and mirrors due to being new to Purescript and running out of time

---

## Future exploration(s)

- More accurate translation of algorithm
- Interactivity
- Additional swarm algorithm visualizations (_Zoo_)
- Apply to a "real world" problem
- Higher dimensions

---

## Acknowledgements and references

- James McCaffrey's OSCON talk for introducing me to Swarm Algorithms
- scholarpedia.org's articles on the topic
- A few posts on the matter from the always great [the morning paper](https://blog.acolyer.org) by Adrian Colyer
- [PSO Chapter](http://www.cleveralgorithms.com/nature-inspired/swarm/pso.html) in Clever Algorithms: Nature-Inspired Programming Recipes by Jason Brownlee
- Purescript ecosystem
- [Dot Waves: A PureScript Short Story](http://bitantics.com/words/dot-waves-a-purescript-short-story/) by Kevin Sullivan for helping me get started with an animated dot
- And other's I'm sure

---

## Questions, discussion

---

## Thanks
