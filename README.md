# Jackson Ferguson

**Computational Astrophysics and Systems Engineering** | *University of Victoria*

I apply the rigor of the scientific method to software engineering. My work focuses on **Vertical Integration** and **Entropy Reduction**, building systems where software precision meets hardware reality.

Whether analyzing the spectral composition of a galaxy cluster or managing a physical supply chain, my goal is the same: to build deterministic tools that extract **Signal from Noise**.

---

## Contact + Collaboration
- Email: [jackson.ferguson0@gmail.com](mailto:jackson.ferguson0@gmail.com)
- LinkedIn: [jackson--ferguson](https://www.linkedin.com/in/jackson--ferguson)
- Open to: Instrumentation development, data acquisition systems, circuit measurement and characterization, lab automation, and scientific Python development
- Interests: Research collaborations involving hardware, software, and experimental validation

---

## Featured Engineering Systems

### 1. [systems-audio-lab](https://github.com/jacksonfergusondev/systems-audio-lab)
**A Vertically Integrated Audio Analysis Platform**

<img src="https://raw.githubusercontent.com/JacksonFergusonDev/systems-audio-lab/refs/heads/main/docs/figures/fig_analysis_topology.svg" width="59%" alt="Analysis topology"> <img src="https://raw.githubusercontent.com/JacksonFergusonDev/systems-audio-lab/refs/heads/main/oscilloscope-rp2040/schematics/exports/signal_conditioning_universal-compact.svg" width="35%" alt="Universal RP2040 Analog Interface">

A complete electronics workbench built to measure and analyze audio circuits. Rather than buying test equipment, I built four interconnected systems from scratch: a logistics tool for parts management, a clean power supply, a guitar overdrive pedal to test, and a custom oscilloscope to capture the data. The project documents the full process from component ordering to frequency response analysis.

* **RP2040 Oscilloscope (Primary Instrument):** Built a USB oscilloscope and spectrum analyzer around the RP2040 microcontroller with a custom analog front-end circuit:
  * Four-stage signal conditioning: current limiting for protection, AC coupling (3 Hz cutoff), switchable voltage dividers for different input ranges, and diode clamps to prevent overvoltage
  * Store-and-forward firmware architecture separates high-speed sampling from USB transmission to avoid data loss
  * Measured noise floor of 1.3 mV RMS, calibrated sampling rate to 97.8 kSps using 60 Hz mains frequency as reference
  * Python analysis tools for FFT, waveform rendering, and automated transfer function measurement
  * Supports line-level audio, high-impedance instrument signals, and 0-5V sensor inputs via jumper configuration

* **Linear Power Supply:** Assembled a 9V voltage regulator based on the L7809 chip to provide clean DC power for the test circuit.

* **Red Llama Overdrive (Device Under Test):** Built a guitar overdrive pedal using CD4049 CMOS inverter chips biased into their linear region to generate soft-clipping distortion. This circuit serves as the test subject for frequency response and harmonic distortion analysis.

* **Component Management:** Developed alongside the star-ground logistics system to track parts inventory and ensure all components were ordered correctly before starting assembly.

The complete workflow—from BOM generation to spectral analysis—is documented in detail, including schematics, firmware source code, and Jupyter notebooks showing the measurement and analysis process.

---

### 2. [star-ground](https://github.com/jacksonfergusondev/star-ground)
**A Deterministic Dependency Manager for Physical Hardware**

<img src="https://github.com/JacksonFergusonDev/star-ground/blob/main/assets/demo.gif?raw=true" width="45%" alt="Star Ground Demo">

In software, `uv sync` resolves dependencies instantly. In hardware, a missing resistor is a blocking failure. This tool treats physical inventory as a strict dependency tree, reducing the **Logistical Entropy** of manufacturing.

* **Invariants over Inference:** Rejects probabilistic parsing (LLMs) in favor of a Hybrid Spatial/Regex engine to ensure 100% data integrity.
* **Yield Management:** Implements "Nerd Economics" (heuristic buffering) to transform procurement from simple arithmetic into a risk-management strategy.
* **Reliability:** Verified via Snapshot Regression testing against a *Golden Master* library of PDFs.

---

### 3. [git-pulsar](https://github.com/jacksonfergusondev/git-pulsar)
**Fault-Tolerant State Capture for Distributed Development**

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/demo/demo_dark.gif">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/demo/demo_light.gif">
  <img alt="Pulsar demo"
       src="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/demo/demo_light.gif"
       width="380"
       style="max-width:100%; height:auto;">
</picture>

Standard git commits conflate *saving work* (High Noise) with *publishing features* (High Signal). Pulsar decouples them by creating an immutable, out-of-band state graph.

* **Zero-Interference:** Manipulates the git object database directly (`write-tree`) via a temporary index, guaranteeing it never locks or corrupts the user's active staging area.
* **Distributed Reconciliation:** Merges work from multiple machines (Laptop/Desktop) using a "Zipper Graph" to prevent split-brain history.

---

## Data Analysis & Physics

### [data-science-portfolio](https://github.com/jacksonfergusondev/data-science-portfolio)

**Computational Physics and Statistical Modeling**

<img src="https://raw.githubusercontent.com/JacksonFergusonDev/data-science-portfolio/refs/heads/main/computational_modeling/figures/particle_attenuation.svg" width="45%" alt="Vectorized Particle Transport"> <img src="https://raw.githubusercontent.com/JacksonFergusonDev/data-science-portfolio/refs/heads/main/astrophysics/figures/gmm_redshift_distribution.svg" width="45%" alt="Gaussian Mixture Redshift Model">

Applied statistical methods to extract physical measurements from noisy astronomical and experimental data.

* **Galaxy Cluster Mass Estimation (ACO 2670):** Used velocity measurements of galaxies in a cluster to estimate total mass through the virial theorem, finding a mass-to-light ratio of 291 ± 60 (solar units)—evidence that most of the cluster's mass is dark matter rather than visible stars.

* **Exoplanet Atmosphere Modeling:** Solved equations for atmospheric pressure and temperature profiles to model the atmospheres of high-gravity exoplanets.

* **Monte Carlo Particle Simulation:** Validated theoretical attenuation equations by simulating individual particle interactions and confirming expected statistical behavior.

---

## 🛠 Technical Stack

| Domain | Toolkit |
| :--- | :--- |
| **Analysis** | Python Scientific Stack (NumPy, SciPy, Pandas), FFT, Signal Processing |
| **Firmware** | MicroPython |
| **Interfaces** | Streamlit, CLI design |
| **DevOps** | Docker, GitHub Actions, `uv` (Dependency Locking) |
| **Circuit Design** | Python-based schematic generation |
| **Documentation** | LaTeX, BibTeX |

---

*In physical systems, engineering is as much about constraining uncertainty as it is about implementing logic.*
