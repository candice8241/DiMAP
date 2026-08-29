# DiMAP

DiMAP is a desktop application for processing X-ray diffraction data from high-pressure diamond anvil cell (DAC) experiments. It provides an integrated workflow from detector calibration through integration, peak fitting, strain and line-width analysis, and equation-of-state (EoS) fitting. The user interface is built with PyQt6.

## Features

- **Detector calibration** — pyFAI-based geometry calibration (PONI) with interactive peak picking
- **Data integration** — HDF5 preview, masking, sector integration, and batch processing
- **Full-pattern analysis** — 2D mapping, Rietveld, Pawley, and Le Bail refinement
- **Peak fitting** — single-file and batch peak fitting with CSV export
- **Strain analysis** — d-spacing vs pressure, sin²ψ and Γ plots, orientation distribution functions (E-WIMV)
- **Line-width analysis** — Caglioti microstrain, WA, MWA, and MWH methods
- **EoS fitting** — interactive Birch–Murnaghan, Vinet, and related models (EosFit7c-style)
- **Utilities** — Ruby/Sm fluorescence pressure gauges, HDF5 browser, format conversion, custom plots

## Requirements

- Python 3.9 or newer (3.10 or 3.11 recommended)
- Windows or Linux

Optional: OpenCL runtime and `pyopencl` for accelerated pyFAI integration.

## Installation

1. Clone or download this repository.
2. Install dependencies:

```bash
pip install -r requirements.txt
```

## Usage

Launch the application:

```bash
python main.py
```

To build a standalone executable, use PyInstaller with the bundled spec file.

## Application Overview

| Module | Description |
|--------|-------------|
| Calibrate | Detector geometry calibration and peak picking |
| Integration | Data Mining, 2D Mapping, and full-pattern Refine |
| Peakfit | Automated peak fitting on integrated 1D profiles |
| Strain | Lattice strain plots and ODF analysis |
| Line width | Peak broadening and WA / MWA / MWH analysis |
| EOS | Interactive equation-of-state fitting |
| Tools | Pressure calibration, HDF5 tools, and custom plotting |

## Workflow

A typical processing sequence:

1. Calibrate the detector and generate a PONI file.
2. Integrate raw data via **Integration → Data Mining**.
3. Fit peaks in **Peakfit** and export results.
4. Analyze strain or line width, or fit an EoS in the corresponding module.
5. Determine pressure with **Tools → Pressure Calculator** when needed.

## References

- EoS fitting: Angel, R.J., Alvaro, M., Gonzalez-Platas, J. (2014) EosFit7c and a Fortran module for equation of state calculations. *Z. Kristallogr.* **229**(5), 405–419.
- CIF phase loading follows the Dioptas reflection-intensity algorithm.

## License

See repository license terms if provided.
