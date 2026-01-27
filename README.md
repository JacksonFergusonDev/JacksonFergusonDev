# Jackson Ferguson

**Astrophysics and Systems Engineering** | *University of Victoria*

My work focuses on the interface between deterministic software systems and stochastic physical hardware. I design and validate recursive toolchains in which logistics software, power infrastructure, and custom instrumentation are developed together to reduce uncontrolled variables in physical experiments.

My current work centers on spectral characterization of non-linear analog circuits and the design of deterministic logistics systems for hardware fabrication and validation.

---

## Contact + collaboration
- Email: jackson.ferguson0@gmail.com
- LinkedIn: https://www.linkedin.com/in/jackson--ferguson
- Open to:  Instrumentation and DAQ development, analog and mixed-signal analysis, lab automation, software-defined measurement systems, and research collaborations spanning software, electronics, and physical experimentation.


---

## Currently Working On

* **Impulse Response Deconvolution:** Implementing Farina’s (2000) Exponential Sine Sweep (ESS) method to mathematically separate linear transfer functions from harmonic distortion products. The goal is to generate Bode plots with explicit linear/harmonic separation. *(Active in [`systems-audio-lab`](https://github.com/jacksonfergusondev/systems-audio-lab))*
* **Context-Aware Parsing Architecture:** Migrating the [`star-ground`](https://github.com/jacksonfergusondev/star-ground) logistics engine from regex to Context-Free Grammars (CFG). Current initiatives include implementing topology inference (clustering components to detect "Fuzz" vs. "Delay" circuits) and integrating real-time Octopart pricing APIs.

---

## Systems Engineering and Instrumentation

### [systems-audio-lab](https://github.com/jacksonfergusondev/systems-audio-lab)

**Status:** *Hardware Validated, Analysis In Progress*

<img src="https://raw.githubusercontent.com/JacksonFergusonDev/systems-audio-lab/refs/heads/main/docs/figures/fig_analysis_topology.svg" width="59%" alt="Analysis topology"> <img src="https://raw.githubusercontent.com/JacksonFergusonDev/systems-audio-lab/refs/heads/main/oscilloscope-rp2040/schematics/exports/signal_conditioning_universal-compact.svg" width="35%" alt="Universal RP2040 Analog Interface">

A systems engineering monograph documenting the design, fabrication, and empirical validation of an analog signal chain. The project required the development of four interdependent subsystems spanning software architecture, power regulation, instrumentation, and signal analysis.

* **Analog Front-End Design:** Designed a custom multi-stage signal conditioning interface to bridge high-impedance instrument signals with low-voltage RP2040 ADC inputs.

  * **Topology:** Implemented a four-stage architecture consisting of current-limited input protection, AC coupling with a cutoff frequency of approximately 3.3 Hz, switched-reference attenuation for DC and audio mode selection, and diode clamping.
  * **Versatility:** Supports line-level, high-impedance instrument-level, and 0 to 5 V sensor inputs via jumper configuration.
* **Instrumentation Architecture:** Designed a store-and-forward data acquisition system.

  * **Mechanism:** Sampling is decoupled from transmission through two capture modes. Burst mode enables high-speed, buffer-limited transient capture, while continuous mode supports long-duration monitoring.
  * **Characterization:** Measured system noise floor below 1.3 mV RMS and calibrated the sampling rate to 97.8 kSps using mains-frequency spectral reference.
* **Power Infrastructure:** Designed and fabricated a linear power supply based on the L7809 topology. Modified the reference design with parallel high-frequency bypass capacitors at input and output stages to suppress ripple and ensure a stable noise floor for analog measurements.

---

### [star-ground](https://github.com/jacksonfergusondev/star-ground)

**Logistics and Procurement Engine**

<img src="https://github.com/JacksonFergusonDev/star-ground/blob/main/assets/demo.gif?raw=true" width="45%" alt="Star Ground Demo">

A logistics engine designed to serve as a single source of truth for electronics inventory management. The system addresses common sources of nondeterminism in hardware fabrication by converting heterogeneous Bill of Materials formats into structured, validated data.

* **Architecture:** Uses deterministic parsing techniques rather than probabilistic models. PDF ingestion is performed through visual layout extraction with `pdfplumber` and regex-based fallback logic to eliminate ambiguity.
* **Inventory Management:** Implements heuristic safety-stock calculations based on component cost, failure risk, and replacement latency.
* **Reliability:** Employs snapshot-based regression testing against a curated reference library to prevent unintended changes in parsing behavior.

---

## Computational Physics

### [data-science-portfolio](https://github.com/jacksonfergusondev/data-science-portfolio)

**Statistical Inference and Modeling**

<img src="https://raw.githubusercontent.com/JacksonFergusonDev/data-science-portfolio/refs/heads/main/computational_modeling/figures/particle_attenuation.svg" width="45%" alt="Vectorized Particle Transport"> <img src="https://raw.githubusercontent.com/JacksonFergusonDev/data-science-portfolio/refs/heads/main/astrophysics/figures/gmm_redshift_distribution.svg" width="45%" alt="Gaussian Mixture Redshift Model">

A collection of computational pipelines applying statistical inference techniques to extract physical parameters from noisy observational data.

* **Galaxy Cluster Dynamics (ACO 2670):** Estimated a mass-to-light ratio of 291 ± 60 solar units using redshift-space distortion analysis and the virial theorem, providing kinematic evidence for dark matter dominance.
* **Atmospheric Reconstruction:** Solved coupled hydrostatic equilibrium and radiative transfer equations to reconstruct thermodynamic profiles of high-gravity exoplanet atmospheres.
* **Stochastic Simulation:** Validated Beer–Lambert attenuation and variance scaling behavior using discrete Monte Carlo particle transport models.

---

## Reliability Infrastructure

### [git-pulsar](https://github.com/jacksonfergusondev/git-pulsar)

**Distributed Backup Daemon**

A background service designed to reduce data loss in distributed academic and development environments.

* **Mechanism:** Creates shadow commits by writing directly to the git object database using low-level plumbing commands, preserving work without modifying the working tree or staging index.
* **Topology:** Maintains a zipper-style commit graph to track work across multiple machines and supports eventual consistency through octopus merges.

---

## Technical Stack

| Domain             | Technologies                                                 |
| :----------------- | :----------------------------------------------------------- |
| **Analysis**       | Python scientific stack, NumPy, SciPy, Pandas, Astropy, FFT  |
| **Firmware**       | RP2040 architecture, MicroPython                             |
| **Interfaces**     | Streamlit, CLI design                                        |
| **Circuit Design** | Discrete analog synthesis, Python-based schematic generation |
| **DevOps**         | Docker, GitHub Actions, pre-commit hooks, `uv`               |
| **Documentation**  | LaTeX, BibTeX                                                |

---

*In physical systems, engineering is as much about constraining uncertainty as it is about implementing logic.*