# Validation summary

## Method

The AGA-8 DETAIL results were compared with GERG-2008, calculated independently with the CoolProp library, at six conditions. The ISO 6976 and ISO 5167-2 results were compared with the reference spreadsheets they were built from, using the same inputs.

## ISO 6976 and ISO 5167-2

For the reference test cases, ISO 6976 results matched exactly. The orifice-flow case matched the reference to about 1e-8 (relative difference).

## AGA-8 DETAIL against GERG-2008

Mole fractions as entered, normalised to 1. Differences are relative, in percent.

| Case | Gas (mole fraction) | T, P | Z | Density | Cp | Cv | Speed of sound |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Lean, medium pressure | CH4 0.917, N2 0.021, CO2 0.012, C2H6 0.032, C3H8 0.011, iC4 0.002, nC4 0.003, iC5 0.0008, nC5 0.0007, nC6 0.0005 | 20 °C, 3.5 MPa | 0.03 | 0.03 | 0.23 | 0.24 | 0.03 |
| Lean, higher pressure | CH4 0.90, N2 0.03, CO2 0.02, C2H6 0.035, C3H8 0.01, nC4 0.005 | 15 °C, 8 MPa | 0.003 | 0.004 | 0.13 | 0.23 | 0.04 |
| Rich | CH4 0.80, N2 0.02, CO2 0.03, C2H6 0.07, C3H8 0.04, iC4 0.01, nC4 0.015, nC5 0.005, nC6 0.005, nC7 0.005 | 60 °C, 10 MPa | 0.11 | 0.11 | 0.66 | 1.09 | 0.08 |
| Low pressure | CH4 0.85, N2 0.10, CO2 0.02, C2H6 0.03 | 35 °C, 0.2 MPa | 0.0002 | 0.0004 | 0.006 | 0.008 | 0.0008 |
| Sour | CH4 0.86, N2 0.05, CO2 0.06, C2H6 0.02, H2S 0.01 | -5 °C, 12 MPa | 0.04 | 0.04 | 0.08 | 0.03 | 0.11 |
| Hydrogen blend | CH4 0.85, H2 0.10, N2 0.02, C2H6 0.03 | 25 °C, 5 MPa | 0.01 | 0.009 | 0.27 | 0.34 | 0.02 |

Compressibility factor and density agree within about 0.11 % in every case. Heat capacities differ more, up to about 1.1 %. This is a difference between the AGA-8 and GERG-2008 models, not between two implementations of the same model.

## A spreadsheet pitfall worth knowing

In Excel, a unary minus binds tighter than the power operator, so `EXP(-x^k)` is evaluated as `EXP((-x)^k)`. For even k that flips the sign of the exponent. In an AGA-8 density-term sum this has almost no effect near atmospheric pressure, but at pipeline pressure it matters: for a sour gas at -5 °C and 12 MPa the compressibility factor was 6.4 % off before the term was written as `EXP(-(x^k))`. If you build your own AGA-8 spreadsheet, check every `EXP(-x^k)` in it.

## Not covered

- Dew point and phase boundaries.
- Gas with large C7+ fractions: only about 0.5 % n-heptane was tested.
- Results outside the ranges tested above.
