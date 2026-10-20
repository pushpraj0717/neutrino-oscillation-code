# Investigating Neutrino Oscillations Through Numerical Simulation

A Python/Jupyter study of neutrino flavour oscillations, built from the two-flavour vacuum model up to the full three-flavour PMNS framework, including a quantitative look at CP violation. Every numerical result is checked against an analytical prediction or a physical consistency condition.

**Author:** Pushprajsinh Rathod · B.S. Physics, Pandit Deendayal Energy University (PDEU)

## What this project does

1. **Two-flavour vacuum model** – implements
   `P(να→νβ) = sin²(2θ) · sin²(1.267 Δm² L / E)` with vectorised NumPy.
2. **Validation against theory** – compares the numerically located maxima/minima (SciPy `find_peaks`) with the analytical oscillation length `L_osc = πE / (1.267|Δm²|)`. The first maximum agrees to **0.015 %** (1033.30 km numerical vs 1033.15 km analytical).
3. **Parameter dependence** – varies energy, Δm² and mixing angle one at a time, showing that E and Δm² set the oscillation *length* while θ sets the *amplitude*.
4. **Three-flavour oscillations** – builds the complex PMNS matrix, verifies unitarity (U†U = I), and computes νe → νe/νμ/ντ probabilities, checking that they sum to 1 at every baseline.
5. **Two- vs three-flavour comparison** – quantifies the error of the two-flavour approximation for νμ → νe (0.0498 vs 0.0537 at 1000 km, 2 GeV).
6. **CP-violating phase** – scans δ_CP ∈ {0°, 90°, 180°, 270°, 195°}, computes neutrino vs antineutrino appearance probabilities and the asymmetry
   `A_CP = P(νμ→νe) − P(ν̄μ→ν̄e)`. As expected, A_CP = 0 for δ_CP = 0° and 180°, and non-zero otherwise (±0.025 at 90°/270°, 1000 km, 2 GeV).

## Key results

| Check | Result |
|---|---|
| First maximum, numerical vs analytical | 1033.30 km vs 1033.15 km (0.015 % diff.) |
| PMNS unitarity | max deviation ~10⁻¹⁶ |
| Σ P(νe → νβ) | 1.000000 across the whole baseline range |
| A_CP at δ_CP = 0°, 180° | 0 (as required in vacuum) |

## Parameters used

| Quantity | Value |
|---|---|
| θ₁₂ / θ₂₃ / θ₁₃ | 33.4° / 49.0° / 8.6° |
| δ_CP (reference) | 195° |
| Δm²₂₁ | 7.42 × 10⁻⁵ eV² |
| Δm²₃₁ | 2.517 × 10⁻³ eV² |

## Limitations

- Vacuum propagation and coherent oscillations only; **matter (MSW) effects are not included**.
- Results are theoretical predictions with fixed literature-style parameters; no fit to experimental data.
- The two-flavour toy model uses an illustrative Δm² and θ.

## Possible extensions

- Constant-density matter effects (MSW) for long-baseline experiments
- Comparison with real experimental data (e.g. T2K / NOvA / Daya Bay public results)
- Parameter-space scans and sensitivity to the mass ordering and δ_CP

## Running it

```bash
pip install numpy scipy matplotlib jupyter
jupyter notebook "Investigating_Neutrino_Oscillations_Through_Numerical_Simulation.ipynb"
```
Or open it directly in Google Colab.

## Repository structure

```
.
├── Investigating_Neutrino_Oscillations_Through_Numerical_Simulation.ipynb
├── README.md
├── requirements.txt      # numpy, scipy, matplotlib
└── figures/              # optional: export key plots here
```

## Tech

Python · NumPy · SciPy · Matplotlib · Jupyter

## License

MIT (or your choice) – add a `LICENSE` file.
