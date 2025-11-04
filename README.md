# bioEmu_GPCR: AI-Powered Protein Dynamics & Functional Insights Leveraging BioEmu with GPCR Focus 🚀

---

## Overview

Welcome to **bioEmu_GPCR** — a cutting-edge computational toolkit designed to harness the transformative power of **BioEmu** (Microsoft’s biomolecular emulator) to explore the dynamic conformational landscapes of proteins, with a special focus on **G-Protein-Coupled Receptors (GPCRs)**.

As a dedicated PhD researcher in computational biology, I developed this repository to show how BioEmu’s innovative deep learning approach can accelerate *biologically meaningful* structural ensemble generation and multifaceted analyses — democratizing access to protein dynamics studies which traditionally demanded massive computational resources and months of simulation time.

---

## Why BioEmu? Revolutionizing Protein Simulations 🔥

BioEmu is a state-of-the-art generative deep learning model trained extensively on protein structural ensembles, enabling it to rapidly sample thousands of **physically-plausible** conformations of any protein monomer from purely sequence input, bypassing the cumbersome need for long, resource-intensive molecular dynamics (MD) simulations.

| Feature               | Classical MD               | Cryo-EM                    | BioEmu       |
|-----------------------|---------------------------|----------------------------|--------------------------|
| **Time to Conformers**| Weeks to months           | Days to weeks              | Minutes to hours         |
| **Sample Diversity**  | Limited by sampling time  | Snapshot, static structures| Diverse equilibrium ensembles |
| **Computational Cost**| HPC-required              | Specialized instruments    | Single GPU workstation   |
| **Application Scope** | Detailed atomic dynamics  | High-resolution snapshots | Large-scale ensemble generation |

> **BioEmu bridges the divide between accuracy and scalability — unlocking dynamic views on protein function at a fraction of traditional costs and time.**

---

## Deep Dive into GPCR Dynamics — Why They Matter 🎯

**G protein-coupled receptors** (GPCRs) constitute a large family of membrane proteins that sense signals outside the cell and activate inside signal transduction pathways and, ultimately, cellular responses. GPCRs are pivotal molecular gatekeepers in human physiology — regulating senses, neurotransmission, immune responses, and countless cellular pathways.

Why focus on GPCRs?

- 🌟 **Conformational plasticity:** GPCRs transit through multiple dynamic states governing activation, ligand specificity, and signaling.  
- 🔄 **Pharmacological importance:** Over 30% of approved drugs target GPCRs, yet many mechanisms remain elusive due to structural dynamics.  
- 🔍 **Cryptic sites and allosteric modulation:** AI-driven ensemble sampling reveals transient pockets invisible in static crystal structures, opening novel drug discovery avenues.  
- 🧩 **Intrinsic challenges:** Traditional experimental or MD methods struggle to capture rare but functionally critical states.

**bioEmu_GPCR** empowers researchers to rapidly generate large, functionally rich conformer sets of GPCRs and perform comprehensive analyses — including RMSD, RMSF, contact networks, functional residue's dynamics, binding site predictions, cryptic pocket detection and pore hydration, — driving mechanistic insights and aiding drug-design pipelines.

---

## Features & Capabilities ✨

- ⚡ **Rapid structure generation:** Easily obtain thousands of equilibrated conformations from FASTA sequences using BioEmu.  
- 🔍 **Comprehensive dynamics analysis:** Calculate RMSD, RMSF, and residue contact maps to reveal protein flexibility and structural variability.  
- 💧 **Functional site exploration:** Examine gating residues, hydration profiles, ligand binding sites, and cryptic pockets with built-in analyses.  
- 🎨 **Publication-quality visualization:** Integrated plotting modules make data interpretation straightforward and elegant.  
- 🛠️ **User-friendly CLI & modular APIs:** Run full or selective analyses seamlessly with minimal commands, ideal for integration into diverse workflows.  
---

## Project Structure

<pre> ## Project Structure bioEmu_GPCR/ ├── README.md # Project overview and instructions ├── requirements.txt # Python dependencies ├── bioemu_sampling.py # Script for BioEmu-based conformer sampling ├── bioemu_analysis.py # Main analysis class & CLI for analysis tasks ├── GPCR/ # Example protein folder (sequence, outputs) │ ├── input.fasta # Input sequence for BioEmu │ ├── residues.yaml # Key residue/gating annotations │ ├── pdb/ # Generated PDB structures │ ├── xtc/ # Generated trajectory files │ ├── figures/ # Output plots, images │ └── reports/ # Analysis text/CSV reports ├── examples/ │ ├── basic_analysis.py # Minimal working analysis example │ └── custom_workflow.py # Custom use-cases and extensions ├── notebooks/ │ ├── gpcr_workflow.ipynb # Jupyter notebook tutorial │ └── visualization.ipynb # Interactive exploratory analysis ├── output/ # (git-ignored) Generated results from runs │ ├── analysis_results.png # Visualization figures │ └── analysis_report.txt # Text summary ├── tests/ │ └── test_analysis.py # Unit & integration tests └── LICENSE # Open source license file </pre>

## Installation & Quickstart ⚙️

### Setup
```
git clone https://github.com/adi1bioinfo/bioEmu_GPCR.git
cd bioEmu_GPCR
conda create -n bioemu_env python=3.11
conda activate bioemu_env
pip install -r requirements.txt
```
For optional molecular dynamics relaxation capabilities:
```
pip install bioemu[md]
```
### Sampling & Analysis

Run conformer generation:
```
python bioemu_sampling.py --protein_dir GPCR --num_samples 100
```
Run full analysis pipeline or specific modules:
```
python bioemu_analysis.py --protein_dir GPCR --run_all
```
or selective analyses:
```
python bioemu_analysis.py --protein_dir GPCR --rmsd --contact --cryptic
```
---

## Citation 📚

If you use this project in your research, please cite:
```
@article{lin2024scalable,
  title={Scalable emulation of protein equilibrium ensembles},
  author={Lin, Ze and Frey, Nathaniel C. and others},
  journal={Nature Methods},
  year={2024}
}

@software{aquaporin_bioemu_2025,
  title={Aquaporin-1 Conformational Analysis with BioEmu},
  author={Aditi Laddha},
  year={2025},
  url={https://github.com/adi1bioinfo/bioEmu_GPCR}
}
```
---

## Contribution & Contact 🤝

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (git checkout -b feature/new-feature)
3. Commit changes (git commit -am 'Add new feature')
4. Push to branch (git push origin feature/new-feature)
5. Open a Pull Request

Areas for contribution:

Additional membrane transport proteins
* Performance optimizations
* Enhanced visualization tools
* Additional analysis metrics
* Documentation improvements

## References