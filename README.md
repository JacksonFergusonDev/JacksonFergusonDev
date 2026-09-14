<div align="center">

# Jackson Ferguson

**I build reliable systems across software, infrastructure, and hardware.**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A0A0A?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jackson--ferguson/)
[![Email](https://img.shields.io/badge/Email-0A0A0A?style=for-the-badge&logo=gmail&logoColor=white)](mailto:jackson.ferguson0@gmail.com)

</div>

Physics & Astronomy graduate focused on building reliable technical systems across abstraction boundaries. I'm particularly interested in **DevOps, robotics, and physical AI**, with an emphasis on automation, deterministic behaviour, failure handling, and understanding how software interacts with the physical systems beneath it.

---

## Selected Technical Projects

<div align="center">

<a href="https://protostar.readthedocs.io/stable/">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/protostar/refs/heads/main/docs/assets/readme-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/protostar/refs/heads/main/docs/assets/readme-light.svg">
    <img alt="Protostar Logo"
         src="https://raw.githubusercontent.com/JacksonFergusonDev/protostar/refs/heads/main/docs/assets/readme-light.svg"
         width="350"
         style="max-width:100%; height:auto;">
  </picture>
</a>

**Deterministic, transaction-aware scaffolding for modern Python projects**

[![PyPI Version](https://img.shields.io/pypi/v/protostar?color=22d3ee&labelColor=0A0A0A&logo=pypi&logoColor=white)](https://pypi.org/project/protostar/)
[![CI](https://img.shields.io/github/actions/workflow/status/jacksonfergusondev/protostar/ci.yml?color=22d3ee&labelColor=0A0A0A&label=CI)](https://github.com/jacksonfergusondev/protostar/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/actions/workflow/status/jacksonfergusondev/protostar/release.yml?color=22d3ee&labelColor=0A0A0A&label=release)](https://github.com/jacksonfergusondev/protostar/actions/workflows/release.yml)
[![Codecov](https://img.shields.io/codecov/c/github/JacksonFergusonDev/protostar?color=22d3ee&labelColor=0A0A0A&logo=codecov&logoColor=white)](https://codecov.io/gh/JacksonFergusonDev/protostar)
[![Python](https://img.shields.io/badge/python-3.12+-22d3ee?labelColor=0A0A0A&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![Documentation](https://img.shields.io/readthedocs/protostar/stable?color=22d3ee&labelColor=0A0A0A&logo=readthedocs&logoColor=white)](https://protostar.readthedocs.io/stable/)

<a href="https://protostar.readthedocs.io/stable/">
  <img alt="Protostar Headless Demo"
        src="https://raw.githubusercontent.com/JacksonFergusonDev/protostar/refs/heads/main/docs/assets/demo_headless.gif"
        width="800"
        style="max-width:100%; height:auto;">
</a>

</div>

Protostar treats project initialization as a controlled state transition rather than a sequence of shell commands. Repository state is calculated first as structured data, then applied by a separate execution engine with explicit failure and rollback semantics.

- **Plan first, execute second:** `plan()` is read-only and produces an `EnvironmentManifest` containing the exact intended filesystem, configuration, dependency, and subprocess operations. `execute(manifest)` is the only phase permitted to perform side effects, so `--dry-run --json` exposes the same plan that live execution consumes.

- **Bounded transactional rollback:** A mutation journal records transaction-managed paths before modification, filesystem writes pass through a transaction-aware interface, and managed subprocesses are terminated before rollback. Failed or interrupted executions restore journaled files in reverse order to their original bytes and modes rather than leaving a partially configured workspace.

- **Headless core:** The engine communicates through structured `InitRequest`, `EnvironmentManifest`, and `ExecutionResult` objects and contains no terminal interaction. Prompts, progress displays, collision decisions, and JSON serialization remain in the CLI layer, allowing the same core lifecycle to support humans, CI, and automation.

- **Semantic configuration composition:** Uses `tomlkit` AST manipulation and format-aware merge logic instead of replacing existing configuration files. Tooling can be introduced while preserving unrelated keys, comments, formatting, and existing project state.

- **Failure handling as architecture:** Pre-flight validation occurs before mutation, dependency-installation failures are fatal, collision states are represented explicitly, and the transaction boundary is documented rather than implying that arbitrary external side effects can always be reversed.

---

<div align="center">

## [Systems Audio Lab](https://github.com/jacksonfergusondev/systems-audio-lab)

**End-to-end audio instrumentation spanning analog electronics, embedded acquisition, and Python signal analysis**

![Analysis Status](https://img.shields.io/badge/analysis-in__progress-white?style=flat-square&color=white&labelColor=black)
![Version](https://img.shields.io/badge/version-v1.0__prototype-white?style=flat-square&color=white&labelColor=black)
![Python](https://img.shields.io/badge/python-3.13-white?style=flat-square&color=white&labelColor=black)
[![Ruff](https://img.shields.io/badge/style-ruff-white?style=flat-square&color=white&labelColor=black)](https://github.com/astral-sh/ruff)
[![Mypy](https://img.shields.io/badge/mypy-checked-white?style=flat-square&color=white&labelColor=black)](https://mypy-lang.org/)

<a href="https://github.com/JacksonFergusonDev/systems-audio-lab/tree/main/docs">
  <img src="https://raw.githubusercontent.com/JacksonFergusonDev/systems-audio-lab/refs/heads/main/docs/figures/fig_analysis_topology.svg" width="59%" alt="Analysis topology">
</a>
<a href="https://github.com/JacksonFergusonDev/systems-audio-lab/tree/main/oscilloscope-rp2040">
  <img src="https://raw.githubusercontent.com/JacksonFergusonDev/systems-audio-lab/refs/heads/main/oscilloscope-rp2040/schematics/exports/signal_conditioning_universal-compact.svg" width="35%" alt="Universal RP2040 Analog Interface">
</a>

##### [📄 Read the Full Engineering Report (PDF)](https://raw.githubusercontent.com/JacksonFergusonDev/systems-audio-lab/main/docs/systems_audio_tech_report.pdf)

</div>

Built as a complete measurement chain rather than a collection of isolated electronics projects. To quantitatively characterize a CD4049 CMOS guitar overdrive, I built the supporting infrastructure myself: low-noise power regulation, the analog device under test, an RP2040-based data-acquisition instrument, and the host-side signal-processing pipeline.

- **Custom instrumentation:** Designed a configurable analog front end for the RP2040 ADC supporting high-impedance instruments, line-level audio, and DC sensor inputs. The signal path handles current limiting, AC coupling, midpoint biasing, attenuation, and input protection before acquisition.

- **Hardware tradeoffs:** Component choices were made around measurable constraints rather than rules of thumb. For example, the high-impedance protection stage uses silicon rather than Schottky clamps to trade a higher clamp voltage for substantially lower reverse leakage, preserving measurement headroom and DC accuracy.

- **Timing-aware acquisition:** Store-and-forward firmware captures into memory before USB transmission, decoupling sample timing from host-side USB latency. The prototype achieved a calibrated **97.8 kSps** sample rate with a measured **1.3 mV RMS** read-noise floor.

- **Empirical validation:** Python/Jupyter tooling performs calibrated waveform analysis, Hann-windowed FFTs, and harmonic characterization. Measurements resolved the Red Llama's soft-knee saturation and strong second-harmonic component; active sweep generation and transfer-function deconvolution are the next stage of the analysis.

---

<div align="center">

## [CI/CD & Release Infrastructure](https://github.com/JacksonFergusonDev/ci-cd-release-infrastructure)

**Reusable release automation and distribution infrastructure for Python projects**

[![CI](https://img.shields.io/github/actions/workflow/status/JacksonFergusonDev/ci-cd-release-infrastructure/ci.yml?style=flat-square&color=white&labelColor=black&label=CI)](https://github.com/JacksonFergusonDev/ci-cd-release-infrastructure/actions/workflows/ci.yml)
[![Python](https://img.shields.io/badge/python-3.13+-white?style=flat-square&color=white&labelColor=black)](https://www.python.org/downloads/)
[![Ruff](https://img.shields.io/badge/style-ruff-white?style=flat-square&color=white&labelColor=black)](https://github.com/astral-sh/ruff)
[![Mypy](https://img.shields.io/badge/mypy-checked-white?style=flat-square&color=white&labelColor=black)](https://mypy-lang.org/)
[![prek](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/j178/prek/master/docs/assets/badge-v0.json&style=flat-square&color=white&labelColor=black)](https://github.com/j178/prek)

</div>

Centralized infrastructure for release policy that would otherwise be duplicated across repositories. Application projects remain thin callers while versioning, publication, Homebrew synchronization, dependency resolution, and failure handling live in one tested source of truth.

- **Two-phase release orchestration:** A read-only pre-flight phase validates tools, repository cleanliness, branch state, remote synchronization, SemVer metadata, and tag availability before any release state is changed.

- **Transactional publication:** Execution updates `pyproject.toml`, synchronizes and validates `uv.lock`, creates the release commit and annotated tag, then publishes branch and tag together with `git push --atomic`. Local state is rolled back if execution fails or is interrupted before successful publication.

- **PyPI → Homebrew automation:** Reusable workflows wait for new PyPI distributions, verify source checksums, resolve dependency trees with `uv`, generate Homebrew resource blocks, update Ruby formulae, and run `brew audit`. A separate path supports projects whose dependencies are exported directly from their repository manifests.

- **Reusable by design:** Automation scripts use PEP 723 inline metadata so they can be executed directly with `uv run`, while caller repositories delegate to centralized GitHub Actions rather than maintaining copies of the release logic.

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

**Deterministic dependency management for physical hardware**

[![Version](https://img.shields.io/github/v/release/JacksonFergusonDev/star-ground?style=flat-square&labelColor=0A0A0A&color=4ade80)](https://github.com/JacksonFergusonDev/star-ground/releases)
![Python Version](https://img.shields.io/badge/python-3.14-4ade80?style=flat-square&labelColor=0A0A0A&logo=python&logoColor=white)
[![CI](https://github.com/JacksonFergusonDev/star-ground/actions/workflows/ci.yml/badge.svg?style=flat-square)](https://github.com/JacksonFergusonDev/star-ground/actions/workflows/ci.yml)
[![Docker](https://github.com/JacksonFergusonDev/star-ground/actions/workflows/docker-publish.yml/badge.svg?style=flat-square)](https://github.com/JacksonFergusonDev/star-ground/actions/workflows/docker-publish.yml)
[![Ruff](https://img.shields.io/badge/style-ruff-4ade80?style=flat-square&labelColor=0A0A0A)](https://github.com/astral-sh/ruff)
[![Mypy](https://img.shields.io/badge/mypy-checked-4ade80?style=flat-square&labelColor=0A0A0A)](https://mypy-lang.org/)

<a href="https://star-ground.streamlit.app/">
  <img alt="Star Ground Demo"
        src="https://github.com/JacksonFergusonDev/star-ground/blob/main/assets/demo.gif?raw=true"
        width="600"
        style="max-width:80%; height:auto;">
</a>

</div>

Software package managers make dependency resolution deterministic; physical projects still fail because someone forgot a ten-cent component. Star Ground applies the same mindset to hardware procurement, converting inconsistent BOMs and inventory into a validated, reproducible pipeline.

- **Structured ingestion:** A Strategy-based parsing layer normalizes PDF, CSV, pasted text, uploaded files, URLs, and presets behind a common interface. PDF ingestion prefers spatial table extraction and deterministic parsing rather than probabilistic inference where an incorrect component value can invalidate a physical build.

- **Grammar-based normalization:** A `pyparsing` grammar converts engineering notation such as `10k`, `4.7u`, and BS 1852 values such as `4k7` into exact `Decimal` base units, avoiding fragile string matching and unnecessary floating-point ambiguity.

- **Physical-aware outputs:** Procurement logic calculates net need before applying category-specific safety buffers, while generated field manuals sort components by physical Z-height so the software output reflects the actual assembly process.

- **Layered verification:** Golden-master snapshots detect regressions against real BOM documents, Hypothesis fuzzes malformed and edge-case values while checking mathematical invariants, and `Streamlit.AppTest` exercises the full paste/upload → parse → download workflow in CI.

---

<div align="center">

<a href="https://github.com/JacksonFergusonDev/git-pulsar">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/assets/readme-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/assets/readme-light.svg">
    <img alt="Git Pulsar Logo"
         src="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/assets/readme-light.svg"
         width="320"
         style="max-width:100%; height:auto;">
  </picture>
</a>

**Fault-tolerant state capture for distributed development**

[![PyPI Version](https://img.shields.io/pypi/v/git-pulsar?style=flat-square&color=a78bfa&labelColor=0A0A0A&logo=pypi&logoColor=white)](https://pypi.org/project/git-pulsar/)
[![CI](https://img.shields.io/github/actions/workflow/status/JacksonFergusonDev/git-pulsar/ci.yml?style=flat-square&color=a78bfa&labelColor=0A0A0A&label=CI)](https://github.com/JacksonFergusonDev/git-pulsar/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/actions/workflow/status/JacksonFergusonDev/git-pulsar/release.yml?style=flat-square&color=a78bfa&labelColor=0A0A0A&label=release)](https://github.com/JacksonFergusonDev/git-pulsar/actions/workflows/release.yml)
[![Python](https://img.shields.io/badge/python-3.12+-a78bfa?style=flat-square&labelColor=0A0A0A&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![Uses Rich](https://img.shields.io/badge/uses-rich-a78bfa?style=flat-square&labelColor=0A0A0A&logo=rich&logoColor=white)](https://github.com/Textualize/rich)

<a href="https://github.com/JacksonFergusonDev/git-pulsar">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/demo/demo_dark.gif">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/demo/demo_light.gif">
    <img alt="Git Pulsar Demo"
        src="https://raw.githubusercontent.com/JacksonFergusonDev/git-pulsar/refs/heads/main/demo/demo_light.gif"
        width="600"
        style="max-width:80%; height:auto;">
  </picture>
</a>

</div>

Git's normal commit workflow makes one history serve two different purposes: recovering unfinished work and publishing meaningful project history. Git Pulsar separates those concerns by maintaining an immutable, out-of-band graph of recoverable workspace states.

- **Recovery without staging interference:** Constructs Git objects through a temporary index and `write-tree`, leaving the user's active index and deliberate commit workflow untouched.

- **Distributed reconciliation:** State captured independently across multiple machines is reconciled through a "Zipper Graph" rather than allowing separate recovery histories to diverge into split-brain state.

---

<div align="center">

<a href="https://github.com/JacksonFergusonDev/dark-matter">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/dark-matter/refs/heads/main/assets/readme-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/dark-matter/refs/heads/main/assets/readme-light.svg">
    <img alt="Dark Matter Logo"
         src="https://raw.githubusercontent.com/JacksonFergusonDev/dark-matter/refs/heads/main/assets/readme-light.svg"
         width="360"
         style="max-width:100%; height:auto;">
  </picture>
</a>

**Dependency-graph-aware storage analysis for Homebrew**

[![PyPI Version](https://img.shields.io/pypi/v/dark-matter-cli?style=flat-square&color=94a3b8&labelColor=0A0A0A&logo=pypi&logoColor=94a3b8)](https://pypi.org/project/dark-matter-cli/)
[![CI](https://img.shields.io/github/actions/workflow/status/JacksonFergusonDev/dark-matter/ci.yml?style=flat-square&color=94a3b8&labelColor=0A0A0A&label=CI)](https://github.com/JacksonFergusonDev/dark-matter/actions/workflows/ci.yml)
[![Python](https://img.shields.io/badge/python-3.12+-94a3b8?style=flat-square&labelColor=0A0A0A)](https://www.python.org/downloads/)
[![Ruff](https://img.shields.io/badge/style-ruff-94a3b8?style=flat-square&labelColor=0A0A0A)](https://github.com/astral-sh/ruff)
[![Mypy](https://img.shields.io/badge/mypy-checked-94a3b8?style=flat-square&labelColor=0A0A0A)](https://mypy-lang.org/)

</div>

Homebrew exposes package sizes and dependency metadata, but neither alone answers what an explicitly installed package actually costs once shared infrastructure is accounted for. Dark Matter reconstructs the dependency DAG and attributes transitive storage costs across the packages that share them.

- **Graph-aware attribution:** Computes both direct package size and weighted recursive size, fractionally allocating shared dependencies rather than charging their full footprint to every parent. The resulting **Bloat Ratio** distinguishes self-contained tools from small packages that pull in disproportionately large dependency trees.

- **Measurement semantics:** Separates physical analysis of installed Cellar contents from theoretical analysis of Homebrew's catalog. Theoretical modes use compressed bottle sizes, so absolute values are treated as estimates while relative ratios remain the useful comparison—an explicit limitation rather than hidden measurement error.

- **Targeted and ecosystem-scale analysis:** Supports full-catalog leaderboards alongside `inspect`, `compare`, and `explain` paths for individual packages, plus CSV/JSON export for downstream analysis.

---

<div align="center">

<a href="https://github.com/JacksonFergusonDev/focal">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/focal/refs/heads/main/assets/readme-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JacksonFergusonDev/focal/refs/heads/main/assets/readme-light.svg">
    <img alt="Focal Logo"
         src="https://raw.githubusercontent.com/JacksonFergusonDev/focal/refs/heads/main/assets/readme-light.svg"
         width="220"
         style="max-width:100%; height:auto;">
  </picture>
</a>

**Fast, curated codebase context for LLM-assisted development**

[![Version](https://img.shields.io/github/v/release/JacksonFergusonDev/focal?style=flat-square&labelColor=0A0A0A&color=fb923c)](https://github.com/JacksonFergusonDev/focal/releases)
[![CI](https://img.shields.io/github/actions/workflow/status/JacksonFergusonDev/focal/ci.yml?style=flat-square&color=fb923c&labelColor=0A0A0A&label=CI)](https://github.com/JacksonFergusonDev/focal/actions/workflows/ci.yml)
[![Python](https://img.shields.io/badge/python-3.10+-fb923c?style=flat-square&labelColor=0A0A0A&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![Ruff](https://img.shields.io/badge/style-ruff-fb923c?style=flat-square&labelColor=0A0A0A)](https://github.com/astral-sh/ruff)
[![Mypy](https://img.shields.io/badge/mypy-checked-fb923c?style=flat-square&labelColor=0A0A0A)](https://mypy-lang.org/)

</div>

A small CLI for turning repositories, diffs, CI failures, notebooks, PDFs, and web documentation into focused context that can be pasted directly into an LLM conversation.

- **Architecture follows workload:** A lightweight Bash dispatcher sends common operations directly through compiled UNIX tools such as `rg`, `fd`, and `fzf`; Python is reserved for structured work such as Git topology, APIs, notebooks, PDFs, and DOM processing.

- **Context rather than autonomy:** Filters generated/binary noise, enforces context-size bounds, supports local and cached remote repositories, and formats Git/GitHub state for clipboard-first use without attempting to become an autonomous coding agent.

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

<a href="https://github.com/JacksonFergusonDev/data-science-portfolio/tree/main/computational_modeling">
<img src="https://raw.githubusercontent.com/JacksonFergusonDev/data-science-portfolio/refs/heads/main/computational_modeling/figures/particle_attenuation.svg" width="45%" alt="Vectorized Particle Transport">
</a>
<a href="https://github.com/JacksonFergusonDev/data-science-portfolio/tree/main/astrophysics">
<img src="https://raw.githubusercontent.com/JacksonFergusonDev/data-science-portfolio/refs/heads/main/astrophysics/figures/gmm_redshift_distribution.svg" width="45%" alt="Gaussian Mixture Redshift Model">
</a>

</div>

Applied statistical methods to extract physical measurements from noisy astronomical and experimental data.

- **Galaxy Cluster Mass Estimation (ACO 2670):** Used velocity measurements of galaxies in a cluster to estimate total mass through the virial theorem, finding a mass-to-light ratio of 291 ± 60 (solar units)—evidence that most of the cluster's mass is dark matter rather than visible stars.

- **Exoplanet Atmosphere Modeling:** Solved equations for atmospheric pressure and temperature profiles to model the atmospheres of high-gravity exoplanets.

- **Monte Carlo Particle Simulation:** Validated theoretical attenuation equations by simulating individual particle interactions and confirming expected statistical behavior.

---

## Technical Stack

| Domain | Technologies |
| :--- | :--- |
| **Systems & CLI** | Python 3.10–3.14, Bash, Git internals, Click, Rich, Questionary, UNIX tooling (`rg`, `fd`, `fzf`) |
| **Infrastructure & Release** | GitHub Actions, reusable workflows, `uv`, PyPI, Homebrew, Docker / GHCR |
| **Parsing & Data Pipelines** | `tomlkit`, `pdfplumber`, `pyparsing`, Pint, NumPy, SciPy, Pandas |
| **Testing & Verification** | `pytest`, Hypothesis, snapshot/regression testing, Bats, ShellCheck, `mypy`, Ruff |
| **Hardware & Instrumentation** | MicroPython, RP2040, ADC acquisition, analog signal conditioning, circuit fabrication |
| **Analysis & Applications** | Jupyter, Streamlit, Matplotlib, `fpdf2` |
| **Documentation** | Zensical / MkDocs, Read the Docs, LaTeX, BibTeX |

---

## Beyond the Terminal

When I'm not building deterministic toolchains, I'm usually deep in the Coast Mountains, either skiing or scrambling alpine ridges. I treat DJing and event logistics the same way I treat software: as complex systems that require careful routing, signal integrity, and risk management.

---

## Contact + Collaboration

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jackson--ferguson/)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:jackson.ferguson0@gmail.com)
