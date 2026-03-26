# CPqPy_V2
A fully Python-based, modular and reproducible framework for reactive transport modeling in Soil and Groundwater 

CPqPy_V2: Coupled COMSOL-PHREEQC in Python
CPqPy_V2 is a modular, reproducible Python-based framework designed for fully coupled reactive transport modeling (RTM) in soil and groundwater systems.

By integrating the multiphysics capabilities of COMSOL with the geochemical precision of PHREEQC, this framework allows for automated, bidirectional data exchange at each time-step. Unlike its predecessor, CPqPy_V2 is entirely independent of the MATLAB environment, offering a more accessible and streamlined workflow for the scientific community.

🚀 Key Features
Python-Native: Complete independence from MATLAB, improving portability and reducing licensing hurdles.

Modular Architecture: Functional components are decoupled, allowing users to easily swap or extend geochemical modules or physical solvers.

Bidirectional Coupling: Seamless data exchange between COMSOL (physics/transport) and PHREEQC (chemistry) at the time-step scale.

Validated Accuracy: Proven numerical consistency against benchmark cases (Cation Exchange and Pesticide Transport).

Reproducible Research: Designed with an emphasis on open-source accessibility and automated workflows.

🛠 Architecture
The framework is built on a modular design to ensure that the physical simulation and chemical reaction components can be maintained and updated independently.

Transport Engine: Handles spatial discretization and fluid flow (COMSOL Multiphysics).

Chemical Engine: Manages complex aqueous speciation and mineral kinetics (PHREEQC).

Interface Layer: Python-based automation that synchronizes time-stepping and data mapping.

📂 Project Structure (Required for Reproducibility)
To ensure the scripts can locate files using relative paths, please organize your local directory as follows:

Plaintext
CPqPy_V2_Project/
├── main_1.py              # Initialization runner (Calls comsol_1 & phreeqc_1)
├── comsol_1.py            # Physics initialization script
├── phreeqc_1.py           # Chemical equilibrium initialization script
├── models/                # Directory for COMSOL models
│   └── Case1_first.mph    # Initialization .mph file
├── database/              # Directory for PHREEQC databases
│   └── phreeqc.dat        # PHREEQC database file
├── Results/               # Directory for automated data exchange (txt/csv)
└── README.md

📋 Prerequisites
To run CPqPy_V2, you will need:

Python 3.8+

COMSOL Multiphysics 6.0+ (with MPH interface/API enabled)

RAM: 16 GB recommended.
CPU: 4 cores or more.
Operating System: Windows 10/11 (required for COMSOL-Python MPH interface).

Required Python packages: numpy, os, sys, shutil, time, Mph (for COMSOL-Python bridging), phreeqc(for Phreeqc-Python bridging)


Python Dependencies:

Bash
pip install numpy mph phreeqpy
🏁 Quick Start: Runnable Example (Single-Step)
This repository includes a pre-configured test case to verify your environment. The scripts use relative paths and will automatically redirect COMSOL's export path to the local /Results folder.

Start COMSOL Server: Open the "COMSOL Multiphysics Server" application on your computer.

Prepare Files: Ensure Case1_first.mph is in the models/ folder and phreeqc.dat is in the database/ folder.

Run the Test:

Bash
python main_1.py
Verification: Upon completion (~2 minutes), check the Results/ folder. You should see outcon.txt and infile.txt. Compare these with any provided expected results to confirm success.

Proposed by Yaqiang Wei, Jiao Zhang in 2026 Contact: yakiwei@yahoo.com
