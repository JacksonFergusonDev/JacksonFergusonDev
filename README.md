<div align="center">

# Jackson Ferguson

Software engineer. I build systems that extract signal from noise — in software, hardware, and data.

<a href="https://github.com/JacksonFergusonDev/protostar" title="Protostar">
  <img src="https://raw.githubusercontent.com/JacksonFergusonDev/protostar/refs/heads/main/docs/assets/favicon.svg" width="80" style="max-width:100%; height:auto;" alt="Protostar logo">
</a>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<a href="https://github.com/jacksonfergusondev/focal" title="Focal">
  <img src="https://raw.githubusercontent.com/JacksonFergusonDev/focal/refs/heads/main/assets/logo.svg" width="80" style="max-width:100%; height:auto;" alt="Focal logo">
</a>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<a href="https://github.com/jacksonfergusondev/git-pulsar" title="Git-Pulsar">
  <img src="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/assets/logo.svg" width="80" style="max-width:100%; height:auto;" alt="Git-Pulsar logo">
</a>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<a href="https://github.com/JacksonFergusonDev/star-ground" title="Star-Ground">
  <img src="https://raw.githubusercontent.com/JacksonFergusonDev/star-ground/refs/heads/main/assets/logo.svg" width="80" style="max-width:100%; height:auto;" alt="Star-Ground logo">
</a>

> Physics & Astronomy Alum (UVic) • Available for Systems Engineering roles

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A0A0A?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jackson--ferguson/)
[![Email](https://img.shields.io/badge/Email-0A0A0A?style=for-the-badge&logo=gmail&logoColor=white)](mailto:jackson.ferguson0@gmail.com)

</div>

---

## Featured Engineering Systems

<div align="center">

<a href="https://github.com/JacksonFergusonDev/protostar">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/protostar/refs/heads/main/docs/assets/readme-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/protostar/refs/heads/main/docs/assets/readme-light.svg">
    <img alt="Protostar Logo"
         src="https://raw.githubusercontent.com/JacksonFergusonDev/protostar/refs/heads/main/docs/assets/readme-light.svg"
         width="350"
         style="max-width:100%; height:auto;">
  </picture>
</a>

**High-Velocity, Deterministic Environment Scaffolding**

[![PyPI Version](https://img.shields.io/pypi/v/protostar?color=22d3ee&labelColor=0A0A0A&logo=pypi&logoColor=white)](https://pypi.org/project/protostar/)
[![CI](https://img.shields.io/github/actions/workflow/status/jacksonfergusondev/protostar/ci.yml?color=22d3ee&labelColor=0A0A0A&label=CI)](https://github.com/jacksonfergusondev/protostar/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/actions/workflow/status/jacksonfergusondev/protostar/release.yml?color=22d3ee&labelColor=0A0A0A&label=release)](https://github.com/jacksonfergusondev/protostar/actions/workflows/release.yml)
[![Codecov](https://img.shields.io/codecov/c/github/JacksonFergusonDev/protostar?color=22d3ee&labelColor=0A0A0A&logo=codecov&logoColor=white)](https://codecov.io/gh/JacksonFergusonDev/protostar)
[![Python](https://img.shields.io/badge/python-3.12+-22d3ee?labelColor=0A0A0A&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![Documentation](https://img.shields.io/badge/docs-ReadTheDocs-22d3ee?labelColor=0A0A0A&logo=readthedocs&logoColor=white)](https://protostar.readthedocs.io/en/stable/)

<img src="https://raw.githubusercontent.com/JacksonFergusonDev/protostar/refs/heads/main/docs/assets/demo_headless.gif" width="70%" alt="Protostar Headless Demo">

</div>

A modular CLI engine designed to eliminate project initialization drift. It automates the generation of complex repository architectures, strictly separating declarative intent from imperative disk operations to guarantee idempotent scaffolding.

* **Manifest-First Architecture:** Modules do not write directly to disk. They declare requirements into a centralized `EnvironmentManifest` during the build phase. The `SystemExecutor` flushes this state in a strict topological order (Validation -> Directories -> AST Merging -> Shell Subprocesses) to prevent partial failures and fragmented environments.

* **Non-Destructive AST Merging:** Utilizes `tomlkit` to manipulate the Abstract Syntax Tree of target configuration files (like `pyproject.toml`). It safely deep-merges tooling payloads (Ruff, Mypy, Pytest) without stripping existing keys, dependencies, or user comments.

* **Domain-Specific Scaffolding:** Evaluates capability matrices for specialized domains. For example, the Astrophysics preset automatically resolves scientific dependencies (`astropy`, `photutils`), scaffolds `data/fits` telemetry directories, configures `nbdime` for jupyter notebook diffing, and injects binary-safety limits into `.gitattributes`.

* **Subprocess Isolation & Telemetry:** All network and shell operations (e.g., `uv init`, `git init`) are routed through a sandboxed wrapper. Output streams are captured and formatted into actionable diagnostics upon failure, preventing terminal pollution and generating URL-encoded crash reports containing environment vectors for unhandled exceptions.

* **Performance Bounds:** Engineered to bypass Python's typical CLI startup overhead. Integrates tightly with Astral's `uv` for sub-second dependency resolution, with execution latency strictly bounded by automated `hyperfine` benchmarking in the CI pipeline.

---

<div align="center">

## [Systems Audio Lab](https://github.com/jacksonfergusondev/systems-audio-lab)

**A Vertically Integrated Audio Analysis Platform**

![Analysis Status](https://img.shields.io/badge/analysis-in__progress-white?style=flat-square&color=white&labelColor=black)
![Version](https://img.shields.io/badge/version-v1.0__prototype-white?style=flat-square&color=white&labelColor=black)
![Python](https://img.shields.io/badge/python-3.13-white?style=flat-square&color=white&labelColor=black)
[![Ruff](https://img.shields.io/badge/style-ruff-white?style=flat-square&color=white&labelColor=black)](https://github.com/astral-sh/ruff)
[![Mypy](https://img.shields.io/badge/mypy-checked-white?style=flat-square&color=white&labelColor=black)](https://mypy-lang.org/)

<img src="https://raw.githubusercontent.com/JacksonFergusonDev/systems-audio-lab/refs/heads/main/docs/figures/fig_analysis_topology.svg" width="59%" alt="Analysis topology"> <img src="https://raw.githubusercontent.com/JacksonFergusonDev/systems-audio-lab/refs/heads/main/oscilloscope-rp2040/schematics/exports/signal_conditioning_universal-compact.svg" width="35%" alt="Universal RP2040 Analog Interface">

</div>

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

<div align="center">

<a href="https://github.com/JacksonFergusonDev/focal">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/focal/refs/heads/main/assets/readme-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/focal/refs/heads/main/assets/readme-light.svg">
    <img alt="Focal Logo"
         src="https://raw.githubusercontent.com/JacksonFergusonDev/focal/refs/heads/main/assets/readme-light.svg"
         width="250"
         style="max-width:100%; height:auto;">
  </picture>
</a>

**CLI tool for instantly extracting token-efficient codebase context for LLM workflows.**

[![Version](https://img.shields.io/github/v/release/JacksonFergusonDev/focal?style=flat-square&labelColor=0A0A0A&color=fb923c)](https://github.com/JacksonFergusonDev/focal/releases)
[![CI](https://img.shields.io/github/actions/workflow/status/JacksonFergusonDev/focal/ci.yml?style=flat-square&color=fb923c&labelColor=0A0A0A&label=CI)](https://github.com/JacksonFergusonDev/focal/actions/workflows/ci.yml)
[![Python](https://img.shields.io/badge/python-3.10+-fb923c?style=flat-square&labelColor=0A0A0A&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![Ruff](https://img.shields.io/badge/style-ruff-fb923c?style=flat-square&labelColor=0A0A0A)](https://github.com/astral-sh/ruff)
[![Mypy](https://img.shields.io/badge/mypy-checked-fb923c?style=flat-square&labelColor=0A0A0A)](https://mypy-lang.org/)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-fb923c?style=flat-square&labelColor=0A0A0A&logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)

</div>

Gathering context for an LLM usually means copying and pasting multiple files, scraping git diffs, and manually formatting terminal outputs. Focal automates this boilerplate repository extraction, feeding AI assistants exactly what they need to understand codebases, PR intents, or external documentation.

* **Pipeline Native:** Core routing and file manipulation are handled by fast UNIX utilities (`rg`, `fd`, `fzf`, `bat`), strictly reserving the Python backend for complex data transformations like parsing Jupyter Notebook ASTs, resolving Git commit topologies, or stripping HTML structure.
* **High Signal, Low Noise:** Aggressively filters out binary blobs, lockfiles, minified assets, and DOM noise using strict heuristic sets to maximize LLM attention window efficiency.
* **Clipboard-First Execution:** Outputs are automatically calculated for token length and piped directly to your system's native clipboard manager (`pbcopy`, `wl-copy`, `xclip`). No intermediate files; just run the command and paste.

---

<div align="center">

<a href="https://github.com/JacksonFergusonDev/star-ground">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/star-ground/refs/heads/main/assets/readme-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/star-ground/refs/heads/main/assets/readme-light.svg">
    <img alt="Star Ground Logo"
         src="https://raw.githubusercontent.com/JacksonFergusonDev/star-ground/refs/heads/main/assets/readme-light.svg"
         width="350"
         style="max-width:100%; height:auto;">
  </picture>
</a>

**A Deterministic Dependency Manager for Physical Hardware**

[![Version](https://img.shields.io/github/v/release/JacksonFergusonDev/star-ground?style=flat-square&labelColor=0A0A0A&color=4ade80)](https://github.com/JacksonFergusonDev/star-ground/releases)
![Python Version](https://img.shields.io/badge/python-3.13-4ade80?style=flat-square&labelColor=0A0A0A&logo=python&logoColor=white)
[![CI](https://github.com/JacksonFergusonDev/star-ground/actions/workflows/ci.yml/badge.svg?style=flat-square)](https://github.com/JacksonFergusonDev/star-ground/actions/workflows/ci.yml)
[![Docker](https://github.com/JacksonFergusonDev/star-ground/actions/workflows/docker-publish.yml/badge.svg?style=flat-square)](https://github.com/JacksonFergusonDev/star-ground/actions/workflows/docker-publish.yml)
[![Ruff](https://img.shields.io/badge/style-ruff-4ade80?style=flat-square&labelColor=0A0A0A)](https://github.com/astral-sh/ruff)
[![Mypy](https://img.shields.io/badge/mypy-checked-4ade80?style=flat-square&labelColor=0A0A0A)](https://mypy-lang.org/)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-4ade80?style=flat-square&labelColor=0A0A0A&logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)

<img src="https://github.com/JacksonFergusonDev/star-ground/blob/main/assets/demo.gif?raw=true" width="70%" alt="Star Ground Demo">

</div>

In software, `uv sync` resolves dependencies instantly. In hardware, a missing resistor is a blocking failure. This tool treats physical inventory as a strict dependency tree, reducing the **Logistical Entropy** of manufacturing.

* **Invariants over Inference:** Rejects probabilistic parsing (LLMs) in favor of a Hybrid Spatial/Regex engine to ensure 100% data integrity.
* **Yield Management:** Implements "Nerd Economics" (heuristic buffering) to transform procurement from simple arithmetic into a risk-management strategy.
* **Reliability:** Verified via Snapshot Regression testing against a *Golden Master* library of PDFs.

---

<div align="center">

<a href="https://github.com/JacksonFergusonDev/git-pulsar">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/assets/readme-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/assets/readme-light.svg">
    <img alt="Git Pulsar Logo"
         src="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/assets/readme-light.svg"
         width="350"
         style="max-width:100%; height:auto;">
  </picture>
</a>

**Fault-Tolerant State Capture for Distributed Development**

[![PyPI Version](https://img.shields.io/pypi/v/git-pulsar?style=flat-square&color=a78bfa&labelColor=0A0A0A&logo=pypi&logoColor=white)](https://pypi.org/project/git-pulsar/)
[![CI](https://img.shields.io/github/actions/workflow/status/JacksonFergusonDev/git-pulsar/ci.yml?style=flat-square&color=a78bfa&labelColor=0A0A0A&label=CI)](https://github.com/JacksonFergusonDev/git-pulsar/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/actions/workflow/status/JacksonFergusonDev/git-pulsar/release.yml?style=flat-square&color=a78bfa&labelColor=0A0A0A&label=release)](https://github.com/JacksonFergusonDev/git-pulsar/actions/workflows/release.yml)
[![Python](https://img.shields.io/badge/python-3.12+-a78bfa?style=flat-square&labelColor=0A0A0A&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![Uses Rich](https://img.shields.io/badge/uses-rich-a78bfa?style=flat-square&labelColor=0A0A0A&logo=rich&logoColor=white)](https://github.com/Textualize/rich)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-a78bfa?style=flat-square&labelColor=0A0A0A&logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/demo/demo_dark.gif">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/demo/demo_light.gif">
  <img alt=" Git Pulsar Demo"
       src="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/demo/demo_light.gif"
       width="70%">
</picture>

</div>

Standard git commits conflate *saving work* (High Noise) with *publishing features* (High Signal). Pulsar decouples them by creating an immutable, out-of-band state graph.

* **Zero-Interference:** Manipulates the git object database directly (`write-tree`) via a temporary index, guaranteeing it never locks or corrupts the user's active staging area.
* **Distributed Reconciliation:** Merges work from multiple machines (Laptop/Desktop) using a "Zipper Graph" to prevent split-brain history.

---

## Infrastructure & DevOps

<div align="center">

### [CI/CD Tooling](https://github.com/jacksonfergusondev/ci-cd-tooling)

**Centralized CI/CD infrastructure and release automation.**

[![CI](https://img.shields.io/github/actions/workflow/status/JacksonFergusonDev/ci-cd-tooling/ci.yml?style=flat-square&color=white&labelColor=black&label=CI)](https://github.com/JacksonFergusonDev/ci-cd-tooling/actions/workflows/ci.yml)
[![Python](https://img.shields.io/badge/python-3.14+-white?style=flat-square&color=white&labelColor=black)](https://www.python.org/downloads/)
[![Ruff](https://img.shields.io/badge/style-ruff-white?style=flat-square&color=white&labelColor=black)](https://github.com/astral-sh/ruff)
[![Mypy](https://img.shields.io/badge/mypy-checked-white?style=flat-square&color=white&labelColor=black)](https://mypy-lang.org/)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-white?style=flat-square&color=white&labelColor=black)](https://github.com/pre-commit/pre-commit)

</div>

Instead of duplicating GitHub Actions across multiple repositories, I built a single source of truth for my pipeline logic. This repo houses reusable workflows and the custom Python automation required to bridge PyPI releases with Homebrew distribution.

* **Automated Sync Engine:** A custom Python script that polls PyPI for new releases, extracts source distribution vectors, dynamically resolves dependencies using Astral's `uv`, and splices the resulting resource blocks into Ruby formulae.

* **Workflow Delegation:** Dependent repositories simply invoke the remote `.github/workflows/update-homebrew.yml` pipeline upon release, abstracting away the complexity of the Homebrew sync.

* **Deterministic Toolchain:** Enforces strict formatting (`ruff`), type-checking (`mypy`), and Markdown linting (`markdownlint-cli2`) across all contained automation scripts.

---

## Data Analysis & Physics

<div align="center">

### [Data Science Portfolio](https://github.com/jacksonfergusondev/data-science-portfolio)

**A collection of computational pipelines bridging theoretical astrophysics, atmospheric science, and statistical inference.**

![Status](https://img.shields.io/badge/status-archived-red?style=flat-square&labelColor=0A0A0A)
[![uv](https://img.shields.io/badge/uv-enabled-white?style=flat-square&color=white&labelColor=black)](https://github.com/astral-sh/uv)
[![Ruff](https://img.shields.io/badge/style-ruff-white?style=flat-square&color=white&labelColor=black)](https://github.com/astral-sh/ruff)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-white?style=flat-square&color=white&labelColor=black)](https://github.com/pre-commit/pre-commit)
[![Jupyter](https://img.shields.io/badge/jupyter-notebook-white?style=flat-square&color=white&labelColor=black)](https://jupyter.org/)
![Python](https://img.shields.io/badge/python-3.12+-white?style=flat-square&color=white&labelColor=black)

<img src="https://raw.githubusercontent.com/JacksonFergusonDev/data-science-portfolio/refs/heads/main/computational_modeling/figures/particle_attenuation.svg" width="45%" alt="Vectorized Particle Transport"> <img src="https://raw.githubusercontent.com/JacksonFergusonDev/data-science-portfolio/refs/heads/main/astrophysics/figures/gmm_redshift_distribution.svg" width="45%" alt="Gaussian Mixture Redshift Model">

</div>

Applied statistical methods to extract physical measurements from noisy astronomical and experimental data.

* **Galaxy Cluster Mass Estimation (ACO 2670):** Used velocity measurements of galaxies in a cluster to estimate total mass through the virial theorem, finding a mass-to-light ratio of 291 ± 60 (solar units)—evidence that most of the cluster's mass is dark matter rather than visible stars.

* **Exoplanet Atmosphere Modeling:** Solved equations for atmospheric pressure and temperature profiles to model the atmospheres of high-gravity exoplanets.

* **Monte Carlo Particle Simulation:** Validated theoretical attenuation equations by simulating individual particle interactions and confirming expected statistical behavior.

---

## Technical Stack

| Domain | Technologies |
| :--- | :--- |
| **Systems & CLI** | Python 3.10+, Bash, UNIX primitives (`rg`, `fd`, `fzf`), `rich` |
| **Quality & CI/CD** | `pytest`, `ruff`, `mypy`, `pre-commit`, GitHub Actions |
| **Data & Analysis** | NumPy, SciPy, Pandas, Streamlit, Jupyter |
| **Infrastructure** | Docker, `uv` (Dependency Locking), Homebrew |
| **Hardware Lab** | MicroPython, RP2040, Custom analog signal conditioning |
| **Documentation** | LaTeX, BibTeX |

---

## Beyond the Terminal

When I'm not building deterministic toolchains, I'm usually deep in the Coast Mountains, either skiing or scrambling alpine ridges. I treat DJing and event logistics the same way I treat software: as complex systems that require careful routing, signal integrity, and risk management.

---

## Contact + Collaboration

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jackson--ferguson/)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:jackson.ferguson0@gmail.com)
