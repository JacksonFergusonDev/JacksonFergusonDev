# Jackson Ferguson

**Astrophysics and Systems Engineering** | *University of Victoria*

I build measurement systems that combine hardware and software to collect reliable data from physical experiments. My projects focus on reducing sources of error and uncertainty by developing custom instrumentation, power supplies, and data acquisition tools together as integrated systems.

Current projects include analyzing non-linear behavior in analog audio circuits and building tools to manage electronics inventory and component procurement.

---

## Contact + Collaboration
- Email: jackson.ferguson0@gmail.com
- LinkedIn: https://www.linkedin.com/in/jackson--ferguson
- Open to: Instrumentation development, data acquisition systems, circuit measurement and characterization, lab automation, and research collaborations involving hardware, software, and experimental validation.

---

## Currently Working On

* **Circuit Frequency Response Analysis:** Implementing the Exponential Sine Sweep method to measure how audio circuits respond across different frequencies and separate linear behavior from distortion. Working toward automated generation of frequency response plots. *(Active in [`systems-audio-lab`](https://github.com/jacksonfergusondev/systems-audio-lab))*
* **Improved Bill of Materials Parsing:** Upgrading the [`star-ground`](https://github.com/jacksonfergusondev/star-ground) component database to better handle different PDF formats and extract pricing information automatically from supplier APIs.

---

## Hardware and Instrumentation Projects

### [systems-audio-lab](https://github.com/jacksonfergusondev/systems-audio-lab)

**Status:** *Hardware Complete, Analysis Software In Development*

<img src="https://raw.githubusercontent.com/JacksonFergusonDev/systems-audio-lab/refs/heads/main/docs/figures/fig_analysis_topology.svg" width="59%" alt="Analysis topology"> <img src="https://raw.githubusercontent.com/JacksonFergusonDev/systems-audio-lab/refs/heads/main/oscilloscope-rp2040/schematics/exports/signal_conditioning_universal-compact.svg" width="35%" alt="Universal RP2040 Analog Interface">

A complete electronics workbench built to measure and analyze audio circuits. Rather than buying test equipment, I built four interconnected systems from scratch: a logistics tool for parts management, a clean power supply, a guitar overdrive pedal to test, and a custom oscilloscope to capture the data. The project documents the full process from component ordering to frequency response analysis.

* **RP2040 Oscilloscope (Primary Instrument):** Built a USB oscilloscope and spectrum analyzer around the RP2040 microcontroller with a custom analog front-end circuit:
  * Four-stage signal conditioning: current limiting for protection, AC coupling (3 Hz cutoff), switchable voltage dividers for different input ranges, and diode clamps to prevent overvoltage
  * Store-and-forward firmware architecture separates high-speed sampling from USB transmission to avoid data loss
  * Measured noise floor of 1.3 mV RMS, calibrated sampling rate to 97.8 kSps using 60 Hz mains frequency as reference
  * Python analysis tools for FFT, waveform rendering, and automated transfer function measurement
  * Supports line-level audio, high-impedance instrument signals, and 0-5V sensor inputs via jumper configuration

* **Linear Power Supply:** Assembled a 9V voltage regulator based on the L7809 chip to provide clean DC power for the test circuit:
  * Added input/output capacitors to filter ripple from cheap wall adapters
  * Installed heatsink and ventilation to handle thermal dissipation under load
  * Reverse polarity protection using Schottky diode
  * Low-noise design prevents power supply artifacts from contaminating measurements

* **Red Llama Overdrive (Device Under Test):** Built a guitar overdrive pedal using CD4049 CMOS inverter chips biased into their linear region to generate soft-clipping distortion. This circuit serves as the test subject for frequency response and harmonic distortion analysis.

* **Component Management:** Developed alongside the star-ground logistics system to track parts inventory and ensure all components were ordered correctly before starting assembly.

The complete workflow—from BOM generation to spectral analysis—is documented in detail, including schematics, firmware source code, and Jupyter notebooks showing the measurement and analysis process.

---

### [star-ground](https://github.com/jacksonfergusondev/star-ground)

**Electronics Inventory Management Tool**

<img src="https://github.com/JacksonFergusonDev/star-ground/blob/main/assets/demo.gif?raw=true" width="45%" alt="Star Ground Demo">

A database system for tracking electronics components and extracting parts lists from supplier PDFs. Designed to reduce errors in component ordering and maintain accurate inventory counts.

* **PDF Processing:** Uses visual layout detection (pdfplumber) and pattern matching to extract component data from bills of materials in different formats. Deterministic parsing approach ensures consistent results rather than relying on probabilistic interpretation.

* **Inventory Tracking:** Calculates suggested stock levels based on component cost, likelihood of failure during assembly, and supplier lead times.

* **Testing:** Uses snapshot-based regression tests with a library of real-world PDFs to catch unintended changes in parsing behavior.

---

## Data Analysis Projects

### [data-science-portfolio](https://github.com/jacksonfergusondev/data-science-portfolio)

**Computational Physics and Statistical Modeling**

<img src="https://raw.githubusercontent.com/JacksonFergusonDev/data-science-portfolio/refs/heads/main/computational_modeling/figures/particle_attenuation.svg" width="45%" alt="Vectorized Particle Transport"> <img src="https://raw.githubusercontent.com/JacksonFergusonDev/data-science-portfolio/refs/heads/main/astrophysics/figures/gmm_redshift_distribution.svg" width="45%" alt="Gaussian Mixture Redshift Model">

Applied statistical methods to extract physical measurements from noisy astronomical and experimental data.

* **Galaxy Cluster Mass Estimation (ACO 2670):** Used velocity measurements of galaxies in a cluster to estimate total mass through the virial theorem, finding a mass-to-light ratio of 291 ± 60 (solar units)—evidence that most of the cluster's mass is dark matter rather than visible stars.

* **Exoplanet Atmosphere Modeling:** Solved equations for atmospheric pressure and temperature profiles to model the atmospheres of high-gravity exoplanets.

* **Monte Carlo Particle Simulation:** Validated theoretical attenuation equations by simulating individual particle interactions and confirming expected statistical behavior.

---

## Software Tools

### [git-pulsar](https://github.com/jacksonfergusondev/git-pulsar)

**Automatic Git Backup Service**

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/demo/demo_dark.gif">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/demo/demo_light.gif">
  <img alt="Pulsar demo"
       src="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/demo/demo_light.gif"
       width="380"
       style="max-width:100%; height:auto;">
</picture>

A background daemon that automatically saves work-in-progress by creating git commits without affecting your working files or staging area. Designed to prevent data loss when working across multiple computers.

* Uses git's internal object database to store snapshots
* Maintains a separate commit history that can be merged with main work when needed
* Supports synchronization across machines through merge commits

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