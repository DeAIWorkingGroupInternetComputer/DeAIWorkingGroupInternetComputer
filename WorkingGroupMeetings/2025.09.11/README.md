# 2025.09.11 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
This talk by Sanjeev Namjoshi (VERSES) introduced **Active Inference** and the **Free Energy Principle** as a unifying framework for perception, action, learning, and self-organization. It explained how agents build generative models to minimize free energy by aligning predictions with observations, balancing exploration and exploitation, and maintaining identity within preferred states. Key concepts included surprisal, variational free energy, Markov blankets, predictive coding, and Bayesian mechanics as a potential “fourth branch of physics.” Practical notes highlighted modularity, multi-agent systems, and data efficiency compared to deep RL, with current tooling spanning Matlab (SPM), PyMDP, RXInfer, and ActiveInference.jl. VERSES applies these ideas in industrial domains such as robotics, logistics, and supply chains, valuing interpretability, efficiency, and adaptability.

### Links shared during the call:
* https://snamjoshi.github.io/
* Upcoming book by Sanjeev on Active Inference: https://mitpress.mit.edu/9780262050951/fundamentals-of-active-inference/
https://docs.google.com/presentation/d/1V-GCkXn8Du0SJa7Nhjy93JBEveKX-ynLVUtpneGhiNc/edit?usp=sharing
* https://www.verses.ai/blog/whitepaper-mastering-gameworld-10k-in-minutes-with-the-axiom-digital-brain
* https://github.com/VersesTech/axiom
* https://github.com/VersesTech/gameworld
* https://github.com/infer-actively/pymdp
* https://www.sciencedirect.com/science/article/pii/S0149763423004694

## Long Version
# Guest & Topic

* Speaker: Sanjeev Namjoshi (Machine Learning Engineer, VERSES)
* Talk: Introduction to Active Inference & the Free Energy Principle (engineering-first view; minimal neuroscience)
* Agenda: Sanjeev will be giving a high-level overview of active inference in both discrete and continuous state-spaces and connect it to the broader free energy principle and the field of Bayesian mechanics. The presentation will delve into what variational free energy is and why it is so useful and important for building robust statistical models that represent the environments they are coupled to.  The presentation will end by describing how the free energy principle plays a role in self-organization, such as the kind seen in living systems, and how Bayesian mechanics is developing to provide analytical tools to analyze complex adaptive systems.

Sanjeev Namjoshi holds a PhD in neuroscience from the University of Texas at Austin and is currently working as a machine learning engineer at VERSES.AI. His theoretical research interests lie at the intersection of neuroscience and machine learning, particularly the computational modeling and simulation of living systems. Sanjeev has over 12 years of combined experience in academia and industry where he has performed research in molecular biology, bioinformatics, and computational neuroscience as well as lead teams to build machine learning-based software.

---

# Why it matters for DeAI

* Broadens the AI toolbox beyond “just LLMs.”
* Promises data-efficient, goal-directed agents that can run under resource constraints—relevant for decentralized stacks.

---

# Core ideas

## Agent–Environment framing:

* Environment = generative process (hidden states evolve, emit observations).
* Agent = generative model (internal probabilistic mirror of causes of data).
* Interface via a Markov blanket; agent only sees data, infers hidden causes.

## Discrete active inference (categorical states):

* Bayesian network with hidden states S → observations O.
* Exact Bayes update (log-space + softmax) shown on a toy “wet ground ↔ raining” example.
* In practice, replace exact inference with variational Bayes: minimize Variational Free Energy (VFE) to approximate the posterior.

## Surprisal & VFE:

* Surprisal = −log p(data); low surprisal ⇢ good model alignment.
* Surprisal is usually intractable; VFE upper-bounds it (Jensen’s inequality).
* Minimizing VFE = better fit, implicit Occam’s razor (avoids overfitting).

## Dynamics & action

* Time-evolving models: add a transition matrix (discrete case) for state dynamics.

### Actions & planning:

* Agent evaluates policies (action sequences) and selects via Expected Free Energy (EFE).
* EFE has two parts:

  * Reward/goal-seeking (match preferred observations).
  * Information-seeking (reduce uncertainty/entropy) → automatic explore–exploit balance.
* Can also drive parameter learning (seek data to reduce uncertainty in model parameters).
* Extensions: hierarchical models, multiple modalities, factorial state factors.

## Continuous active inference

* Switch to continuous states/observations and smooth functions:

  * Observation model o ≈ G(s) + noise (Gaussian).
* Common simplification: track the mode/mean; VFE reduces to precision-weighted prediction errors:

  * Sensory PE: actual data vs. predicted data (o − G(s))
  * State PE: prior state vs. posterior state
* Precisions (inverse variances) weight trust in data vs. model; can be learned (meta-optimization).

### From SDE to ODE & filtering:

* Environment dynamics as SDE; convert to ODE using the VFE gradient flow, then numerical integrate (generalized Bayesian filtering).
* Demo: agent tracks drifting state; VFE drops to \~0 and stays at steady state.

### Colored noise & generalized coordinates:

* Real-world “noise” often autocorrelated (not white); model it to improve predictions.
* Use generalized coordinates of motion (state plus higher-order derivatives via Taylor expansion) to capture trajectories of signals and noise.

---

# Action–Perception Cycle and Control Theory

* Actions influence observations through the environment.
* Free energy is not directly a function of action → need chain rule via observations.
* Forward models link actions ↔ observations.
* Control theory analogy: thermostats, cruise control, submarines, refineries.

**Example:**

* Environment state fluctuates around 20.
* Agent expects 5 → actions drive state toward expectation.
* Oscillatory corrections minimize free energy.
* Robotics analogy: moving a robotic arm smoothly to reduce prediction error.

---

# Hierarchical Generative Models & Predictive Coding

* Hierarchical Bayesian networks represent states, parameters, priors, and observations.
* Predictions flow downward, sensory data flows upward.
* Errors at each layer = information for updating the model.

**Predictive coding:**

* Compression of information by only learning from errors.
* Efficient adaptation without regenerating the entire environment model.

---

# Free Energy Principle

* Agents occupy preferred states = identity.
* Example: temperature preference between 30–50°, with death outside.
* Over time, agents drift toward and remain in these preferred states.
* This set of states forms a non-equilibrium steady state (NESS) or attractor manifold.
* Exiting the manifold = failure to predict environment → risk of death or collapse.
* Free energy minimization keeps agents within identity-preserving states.

---

# Markov Blankets & Modularity

* Markov blankets define the boundary between agent and environment.
* Everything outside = treated as noise.

**Key benefits:**

* Tractability of inference.
* Modularity and composability.
* Multi-agent systems can share beliefs, reduce uncertainty, and correct biases.
* Prevents “delusional” models (e.g., hallucinations if only trusting priors, or instability if only trusting sensory data).

---

# Bayesian Mechanics – A Proposed Fourth Branch of Physics

* Developed by Karl Friston and colleagues.
* Treats surprisal as an informational Lagrangian.

**Links:**

* Information geometry (agents move on manifolds of probability distributions).
* Non-equilibrium thermodynamics (entropy, dissipation).
* Suggests classical, statistical, and quantum mechanics can be derived as special cases.
* Quantum free energy principle: entanglement as bottlenecked information exchange across Markov blankets.

---

# Active Inference as a Unifying Framework

* Integrates perception, action, learning, and attention.
* Agents minimize free energy across all processes to adapt and survive.

**Bridges discrete and continuous domains:**

* From robotics and supply chains to thermodynamic and probabilistic systems.

---

# Q\&A Highlights

* Modular models: like mixture-of-experts; combine separate models (e.g., wind vs. rain) into joint inference.
* Unknown unknowns:

  * In theory, free energy minimization suffices.
  * In practice, priors and structure are engineered.
  * Multi-agent setups help discover relevance and share beliefs.
* Preferences: often engineered, but biologically learned via evolution; current models explore learning them but face challenges.
* Access to environment: agents only access data streams (like humans via senses), not the “true environment.”

---

# Practical Implementation Notes

* Axiom (Verses): gradient-free active inference for Atari-like tasks.

  * Runs on modest GPUs (e.g., NVIDIA 3090).
  * More data-efficient than deep RL.

**Current software ecosystem:**

* SPM (Matlab): Friston’s original neuroimaging library (slow, but comprehensive).
* PyMDP (Python/JAX): discrete active inference, more performant.
* RXInfer: for engineering problems with active inference elements.
* ActiveInference.jl: Julia package.
* Experimental: variational Bayesian Gaussian splatting libraries.

---

# Verses Tech Applications

* Focus: industrial domains

  * Robotics.
  * Logistics.
  * Supply chains.

**Values of active inference:**

* Interpretability (traceable reasoning).
* Data efficiency (works with limited data).
* Flexibility (applies to both discrete and continuous systems).