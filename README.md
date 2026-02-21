# CFD-Based-Design-Optimization-Study-of-a-Martian-Ascent-CD-Nozzle-

Project Overview
This project presents the design, CFD analysis, and optimization of a convergent–divergent (CD) rocket nozzle intended for ascent from the Martian surface.
Unlike Earth-based propulsion problems, Martian ascent poses unique challenges due to:
Extremely low ambient pressure (~610 Pa)
Reduced gravity
Overexpanded flow regimes
Tight efficiency margins for safe ascent
The objective of this project is not maximum thrust, but safe, efficient ascent, achieved by identifying an optimal chamber pressure range using CFD validation and regression-based prediction.

Objectives
Design a CD nozzle using isentropic flow relations
Adapt the nozzle for Martian surface conditions
Validate performance using CFD (ANSYS Fluent)
Perform a chamber pressure sweep
Identify a safe and efficient operating range
Predict the optimal chamber pressure using Python-based regression models

Methodology (From Scratch → Optimization)
1️. Isentropic Nozzle Design (Baseline)
The design process begins with classical isentropic gas dynamics:
Target exit Mach number selected based on high-expansion requirements
Area ratio (Ae/A*) obtained from isentropic relations
Throat and exit diameters computed
Initial nozzle geometry defined (converging + diverging)
This step provides a 1D, ideal baseline design, assuming inviscid, perfectly expanded flow.

2️. Transition to Martian Conditions
Since Mars has no Earth-like atmosphere, a surrogate Martian environment was constructed inside the CFD solver:
Ambient pressure set to Martian surface values (~610 Pa)
Ideal gas assumptions retained
Energy equation enabled
Compressible turbulence modeling applied
The goal was physical similarity, not exact chemical replication.

3️. CFD Analysis (ANSYS Fluent)
The nozzle was analyzed under multiple chamber pressures to understand real flow behavior:
Pressure-based solver
Compressible flow with energy effects
Shock behavior, expansion, and exit flow examined
Mass flow rate and thrust extracted directly from CFD
A pressure sweep was performed across a defined range to capture trends instead of single-point results.

4️. Multi-Nozzle Ascent Configuration
Initial results showed that a single nozzle could not meet ascent thrust requirements alone.
Instead of redesigning the nozzle:
A two-nozzle configuration was proposed
Thrust and mass flow were scaled accordingly
Flow properties (Mach, temperature, pressure) remain unchanged per nozzle
This reflects real ascent module design philosophy.

5️. Performance Metrics Evaluated
For each chamber pressure:
Thrust
Mass flow rate
Specific thrust (F/ṁ)
Thrust-to-weight ratio (T/W)
Exit Mach number
Pressure ratio (Pe/Pa)
This allowed identification of:
Over-inefficient regions
Diminishing returns at high chamber pressures
Stable ascent-capable operating zones

6️. Data-Driven Optimization (Python)
CFD results were post-processed using Python:
Polynomial regression (degree = 3)
Smooth performance curves generated
Non-physical extremes filtered out
Optimal operating point identified from trend behavior

Final Prediction:
Optimal chamber pressure ≈ 2.75 MPa (for air as working fluid only)
This value provides efficient thrust generation with stable ascent margins, without unnecessary system penalties.

Key Results 
Fully expanded supersonic flow on Mars (Pe ≫ Pa)
Exit Mach number ≈ 3
Two-nozzle configuration satisfies ascent thrust requirements
Optimal chamber pressure identified using regression
Clear efficiency trends established across pressure sweep
All plots, contours, and processed results are included in this repository.

NOTE: For a comprehensive study on the ascent properties, air has been used as a working fluid for the initial analysis. Eventual studies carried out actual propellant as the working fluid, which shall be considered later.

Data & Access Policy (Important)
To preserve originality and academic/professional integrity, the following are intentionally not shared publicly:
Exact ANSYS Fluent setup
Boundary condition values
Solver tuning parameters
Thermophysical property adjustments
CFD journal / case files
Python optimization scripts

Publicly available:
Methodology
Performance plots
Contours
Final results
Engineering conclusions

Tools & Technologies
ANSYS Fluent – CFD analysis
Python – Data processing & regression
Pandas / NumPy / Matplotlib
Classical Gas Dynamics
Compressible Flow Theory

Key Engineering Takeaway
This project demonstrates that Mars ascent is not a thrust problem, but an efficiency and optimization problem.
Rather than maximizing output, the system was engineered to:
Respect environmental constraints
Avoid diminishing returns
Achieve stable, repeatable ascent performance

Disclaimer
This is a conceptual engineering project intended for learning, analysis, and demonstration of capability.
It is not a flight-certified design, nor a research work proving the usability.

Closing Note
Designing for Earth is easy.
Designing for Mars forces you to think.
This project reflects a from-scratch, physics-first, simulation-validated approach to extraterrestrial propulsion — executed with modern CFD and data-driven optimization tools.
