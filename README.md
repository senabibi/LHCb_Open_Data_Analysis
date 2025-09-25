# LHC Open Data Project with RDataFrame Integration

## Overview

This project demonstrates the integration of ROOT's RDataFrame with the LHC Open Data Project, focusing specifically on LHCb experiment data analysis. We have successfully bridged a critical gap in LHC Open Data implementations by providing native RDataFrame examples where previously only uproot/NumPy-based approaches existed.

## Project Background

### RDataFrame Advantages

RDataFrame is ROOT's modern, high-level declarative interface for data analysis with a columnar approach, offering several key benefits:

- **Multi-threading**: Leverages multi-core architectures for efficient parallel processing
- **Auto-optimization**: Declarative programming with lazy execution and caching mechanisms
- **Python-friendly**: Comprehensive Python bindings providing seamless access to ROOT's C++ functionality
- **Interoperability**: Full compatibility with NumPy and pandas ecosystems

### LHC Open Data Project Integration

Our analysis revealed a significant implementation gap across LHC experiments:

| Experiment | RDataFrame Support | Status |
|------------|-------------------|--------|
| **ATLAS** | ✅ Available | Complete |
| **CMS** | ✅ Available | Complete |
| **LHCb** | ❌ Missing | **Now Resolved** |

**Our Contribution**: Developed comprehensive RDataFrame tutorials and analysis pipelines for LHCb Open Data, demonstrating superior performance and enhanced usability compared to existing approaches.

## Data Analysis Workflow

![Data Analysis Pipeline](https://github.com/senabibi/LHCb_Open_Data_Analysis/blob/main/flow_2.png)


Our sophisticated data analysis pipeline processes LHCb open datasets through the following stages:

### 1. Data Input & Basic Selections
- Raw data ingestion from ROOT files
- Basic quality cuts: `PZ > 0`, `!isMuon`

### 2. Multi-Path Transformations
The workflow branches into multiple parallel transformation paths:
- **Mass calculations**: m²ππ (3 pairs), m²KK (3 pairs), m²Kπ (6 pairs)
- **Kinematic variables**: pT, energy terms (e_pi, e_K)
- **Momentum calculations**: p² values (p12, p23, p13)

### 3. Event Categorization
Critical component featuring 200+ lines of nested conditional logic:
- Hierarchical IF-ELIF decision trees
- ProbK and ProbPi threshold optimizations
- Charge-dependent selection criteria

**Output Categories**:
- 🟢 **KKK Category** (`category == 1`)
- 🟠 **πππ Category** (`category == 2`)
- 🟣 **Kππ Categories** (`categories 3, 4, 5`)

### 4. Final Analysis Products
- Invariant mass distributions
- Dalitz plots
- pT/pZ spectra
- ProbK vs ProbPi correlation studies
