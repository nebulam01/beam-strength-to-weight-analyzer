# Beam Strength-to-Weight Interactive Analyzer

An interactive **Google Colab** engineering tool built with `ipywidgets`, `NumPy`, `Pandas`, and `Matplotlib` to compare model beam cross-sections by **strength-to-weight ratio** under equal span length, loading method, and material mass.

## Overview

When evaluating structural efficiency, comparing beams with different masses or spans can be misleading. This analyzer holds **span length ($L$)**, **beam mass ($m$)**, **material**, and **load method** constant—resulting in an identical cross-sectional area ($A$) across profiles—so the effect of cross-section geometry on bending strength, deflection, and structural efficiency can be isolated.

### Supported Cross-Sections (Color-Matched Across Plots)
- **Solid Rectangle**
- **Hollow Box**
- **I-Beam**
- **C-Channel**

### Supported Load Methods
- **3-Point Bending (Center Load)**
- **4-Point Bending (L/3 Loads)**
- **Cantilever (Tip Load)**

## Key Features

- **Interactive English UI (`ipywidgets`):** Adjust material, load method, comparison metric, span length, beam mass, and safety factor in real time.
- **Multi-Section Checkbox Filtering:** Select any subset of cross-sections to compare side by side.
- **Consistent Color Coding:** Each cross-section uses a fixed color across the bar chart, load-deflection curves, and scaled cross-section drawings.
- **Load vs. Deflection & Geometry Plots:** Visualizes stiffness behavior up to maximum allowable load ($F_{\max}$) alongside scaled cross-sectional geometries and the neutral axis.
- **Strength & Stiffness Summary Card:** Highlights the highest strength-to-weight performer and evaluates whether operating conditions stay within benchmark deflection ($L/250$) and wall/flange slenderness limits.

## How to Run in Google Colab

1. Open a new notebook in [Google Colab](https://colab.research.google.com/).
2. Paste the analyzer script into a code cell and run it.
3. Use the sliders, dropdowns, and checkboxes to test different configurations and inspect the updated charts and summary.

## Engineering Notes

- Allowable bending stress is calculated as $\sigma_{\text{allow}} = \sigma_y / \text{SF}$, and bending capacity is derived from section modulus $S_x = I_x / y_{\max}$ for the selected load case.
- Deflection limits ($L/250$) and slenderness checks serve as engineering indicators for serviceability and thin-wall local buckling sensitivity; physical prototypes should also be verified with experimental testing or finite element analysis (FEA).
