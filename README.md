# bioEmu_GPCR

AI-Powered Protein Dynamics & Functional Insights Leveraging BioEmu with GPCR Focus 🚀

## Overview

Welcome to **bioEmu_GPCR** — a cutting-edge computational toolkit designed to harness the transformative power of **BioEmu** (Microsoft’s biomolecular emulator) to explore the dynamic conformational landscapes of proteins, with a special focus on **G-Protein-Coupled Receptors (GPCRs)**.

As a dedicated PhD researcher in computational biology, I developed this repository to show how BioEmu’s innovative deep learning approach can accelerate *biologically meaningful* structural ensemble generation and multifaceted analyses — democratizing access to protein dynamics studies which traditionally demanded massive computational resources and months of simulation time.

## Why BioEmu? Revolutionizing Protein Simulations 🔥

BioEmu is a state-of-the-art generative deep learning model trained extensively on protein structural ensembles, enabling it to rapidly sample thousands of **physically-plausible** conformations of any protein monomer from purely sequence input, bypassing the cumbersome need for long, resource-intensive molecular dynamics (MD) simulations.

| Feature               | Classical MD               | Cryo-EM                    | BioEmu       |
|-----------------------|---------------------------|----------------------------|--------------------------|
| **Time to Conformers**| Weeks to months           | Days to weeks              | Minutes to hours         |
| **Sample Diversity**  | Limited by sampling time  | Snapshot, static structures| Diverse equilibrium ensembles |
| **Computational Cost**| HPC-required              | Specialized instruments    | Single GPU workstation   |
| **Application Scope** | Detailed atomic dynamics  | High-resolution snapshots | Large-scale ensemble generation |

> **BioEmu bridges the divide between accuracy and scalability — unlocking dynamic views on protein function at a fraction of traditional costs and time.**

## GPCRs: Molecular Switches Shaping Physiology and Medicine

**G protein-coupled receptors** (GPCRs) constitute a large family of membrane proteins that sense signals outside the cell and activate inside signal transduction pathways and, ultimately, cellular responses.

1. **Cellular Signal Transduction**<br>
GPCRs convert extracellular signals (hormones, neurotransmitters, sensory stimuli) into intracellular responses by activating heterotrimeric G-proteins, triggering pathways that regulate critical cellular activities including gene expression, metabolism, and motility.

2. **Sensory Perception**<br>
They mediate vision (e.g., rhodopsin in photoreceptors), taste, smell, and pheromone detection, allowing organisms to react to their environment dynamically.

3. **Neurological and Psychiatric Disorders**<br>
GPCRs regulate neurotransmitters like serotonin, dopamine, and glutamate, influencing mood, cognition, pain perception, and are implicated in diseases such as depression, schizophrenia, and neurodegeneration.

4. **Immune System Modulation**<br>
These receptors control immune cell migration, differentiation, and inflammatory responses. Aberrant GPCR signaling is linked to autoimmune diseases and immunodeficiencies.

5. **Cancer Biology**<br>
GPCRs contribute to tumor growth, metastasis, and the tumor microenvironment, making them critical targets in oncology drug discovery.

GPRC Represents targets for over 30% of current drugs, detailed understanding of GPCR conformational landscapes enables rational drug development, including allosteric modulators and biased agonists that offer enhanced therapeutic profiles.

## Features & Capabilities ✨

- ⚡ **Rapid structure generation:** Easily obtain thousands of equilibrated conformations from FASTA sequences using BioEmu.  
- 🔍 **Comprehensive dynamics analysis:** Calculate RMSD, RMSF, and residue contact maps to reveal protein flexibility and structural variability.  
- 💧 **Functional site exploration:** Examine gating residues, hydration profiles, ligand binding sites, and cryptic pockets with built-in analyses.  
- 🎨 **Publication-quality visualization:** Integrated plotting modules make data interpretation straightforward and elegant.  
- 🛠️ **User-friendly CLI & modular APIs:** Run full or selective analyses seamlessly with minimal commands, ideal for integration into diverse workflows.  

## Project Structure
```
bioEmu_GPCR/
├── README.md                    # Project overview and instructions
├── requirements.txt             # Python dependencies
├── analysis/                    # All analysis source code and scripts
│   ├── __init__.py
│   ├── core.py                  # Main analysis class with RMSD, RMSF, binding site, etc.
│   └── utils.py                 # Helper functions for plotting, data loading, etc.
├── GPCR/                        
│   ├── gpcr.fasta               # FASTA file input for BioEmu sampling
│   ├── pdb/                     # Generated PDB conformations
│   ├── xtc/                     # Generated trajectories
│   ├── figures/                 # Plots and visualization images
│   └── reports/                 # Textual and CSV analysis outputs
├── scripts/                     
│   ├── run_sampling.py          # Script to sample conformers with BioEmu using GPCR/input.fasta
│   ├── run_analysis.py          # Script to perform chosen analyses on data in GPCR/
│   └── run_all.py               # Combined pipeline script
└── notebooks/                   
    ├── tutorial.ipynb
    └── visualization.ipynb
```

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

## Biological Applications

+ **Rapid Generation of GPCR Structural Ensembles**: Sample diverse conformers capturing active, inactive, and intermediate states.

+ **Quantitative Dynamics Profiling (RMSD & RMSF)**: Pinpoint flexible loops and rigid cores critical for activation.

+ **Gating Residue and Allosteric Network Analysis**: Characterize residue contacts and motions underpinning signal transduction.

+ **Cryptic Pocket Detection for Drug Discovery**: Reveal transient binding sites missed by static structures.

+ **Ligand Binding Site Prediction and Characterization**: Cross-validate predicted pockets with known ligand interaction sites.

+ **Conformational Impact of Mutations**: Assess how mutations alter dynamic behavior and potential drug responses.

+ **Ensemble-Enhanced Virtual Screening Support**: Provide receptor ensembles to improve docking realism.

## Citation 📚

If you use this project in your research, please cite:
```
@article{lin2024scalable,
  title={Scalable emulation of protein equilibrium ensembles},
  author={Lin, Ze and Frey, Nathaniel C. and others},
  journal={Nature Methods},
  year={2024}
}

@software{bioEmu_GPCR,
  title={Aquaporin-1 Conformational Analysis with BioEmu},
  author={Aditi Laddha},
  year={2025},
  url={https://github.com/adi1bioinfo/bioEmu_GPCR}
}
```

## Contribution & Contact 🤝

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (git checkout -b feature/new-feature)
3. Commit changes (git commit -am 'Add new feature')
4. Push to branch (git push origin feature/new-feature)
5. Open a Pull Request

Areas for contribution:

* Additional membrane transport proteins
* Performance optimizations
* Enhanced visualization tools
* Additional analysis metrics
* Documentation improvements


## References