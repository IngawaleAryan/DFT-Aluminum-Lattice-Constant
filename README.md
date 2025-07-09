# DFT-Aluminum-Lattice-Constant
Calculating the equilibrium lattice constant of FCC Aluminum using Density Functional Theory with Quantum ESPRESSO.
# First-Principles Calculation of Aluminum's Lattice Constant

## Project Overview

This repository documents a first-principles study to determine the equilibrium lattice constant and equation of state for face-centered cubic (FCC) Aluminum. The project was executed using Density Functional Theory (DFT) as implemented in the Quantum ESPRESSO software package.

The primary goal was to apply fundamental computational materials science techniques to predict a core material property from scratch, providing a practical demonstration of the DFT simulation workflow.

## Methodology

The equilibrium lattice constant corresponds to the atomic arrangement with the minimum possible ground-state energy. To find this minimum, a series of Self-Consistent Field (SCF) calculations were performed across a range of lattice constants.

1.  **System Setup:** A template input file (`Al_template.in`) was created for a 1-atom FCC Aluminum primitive cell. Key parameters like the plane-wave cutoff energy (`ecutwfc`) and k-point mesh density were established for convergence.
2.  **Energy Calculations:** The lattice constant (`celldm(1)`) was manually varied from 7.50 to 7.90 Bohr in steps of 0.10 Bohr. For each value, a new SCF calculation was run to find the total electronic energy.
3.  **Data Aggregation:** The lattice constant (converted to Angstroms) and the corresponding total energy (in Rydbergs) for each run were systematically collected into a data file (`eos.dat`).
4.  **Analysis & Visualization:** The generated data was plotted using `Gnuplot` to visualize the Equation of State (EOS) curve, representing Energy vs. Lattice Constant.

## Results & Analysis

The resulting Equation of State plot clearly shows the expected parabolic relationship between lattice constant and energy.

![Equation of State for FCC Aluminum](Aluminum_EOS_Plot.png)

From the generated data in `eos.dat`, the minimum energy was found to be **-39.50229837 Ry**, which corresponds to an equilibrium lattice constant of **4.0217 Å**.

This calculated value is in excellent agreement with the widely accepted experimental value for Aluminum (~4.05 Å), validating the accuracy of the DFT approach for predicting fundamental material properties.

## Tools and Environment

*   **Simulation Package:** Quantum ESPRESSO
*   **Theory:** Density Functional Theory (DFT)
*   **Operating System:** Ubuntu on Windows Subsystem for Linux (WSL)
*   **Data Analysis & Plotting:** Gnuplot, Bash
*   **Key Skills:** First-principles simulation, DFT input file creation, convergence testing, data extraction, scientific plotting.
