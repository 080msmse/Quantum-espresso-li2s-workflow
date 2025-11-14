# Quantum-espresso-li2s-workflow
A complete Quantum ESPRESSO workflow for Li₂S structure optimization, convergence testing, and formation energy calculation.

# Quantum ESPRESSO Workflow for Li₂S

A complete and automated workflow for performing density functional theory (DFT) calculations on Li₂S (Lithium Sulfide) using Quantum ESPRESSO. This script handles convergence testing, structure optimization (ionic + cell), final energy calculation, band structure and DOS plotting, and formation energy analysis.

## 🚀 Features

- **Convergence Testing**: Automated convergence of plane-wave energy cutoff (`ecutwfc`) and k-point grid.
- **Structure Optimization**: Two-step relaxation (ions only, then cell+ions) using `relax` and `vc-relax` calculations.
- **Electronic Properties**: Calculates band structure, density of states (DOS), and projected DOS (PDOS).
- **Formation Energy**: Computes the formation energy of Li₂S from reference elemental phases.
- **Automated Plotting**: Generates publication-ready plots for bands, DOS, and convergence tests.

## 📋 Prerequisites

Before using this workflow, ensure you have the following installed:

- **Quantum ESPRESSO** (pw.x, bands.x, projwfc.x)
- **Python 3.x** with the following packages:
  - `pymatgen` (for structure handling and input file generation)
  - `numpy`
  - `matplotlib`
  - `PIL` (Pillow)

## ⚙️ Installation & Setup

1.  **Clone this repository**:
    ```bash
    git clone https://github.com/YOUR_USERNAME/your-repo-name.git
    cd your-repo-name
    ```

2.  **Configure Paths**:
    Edit the "User settings" section in the main Python script to point to your directories:
    ```python
    WORK_DIR = "/path/to/your/working/directory"
    PSEUDO_DIR = "/path/to/your/pseudopotentials"
    CIF_PATH = os.path.join(WORK_DIR, "Li2S.cif")  # Optional, fallback structure is provided
    ```

3.  **Add Pseudopotentials**:
    Place your pseudopotential files (`.UPF`) for Li and S in the `PSEUDO_DIR` folder. The script will automatically map them to the elements.

## 🧪 Usage

Simply run the main Python script. The workflow is fully automated.

```bash
python qe_workflow.py
