# Natural Gas Properties & Flow Calculator

One Excel workbook that calculates **ISO 6976** gas properties, **AGA-8 DETAIL** gas properties and **ISO 5167-2** orifice flow from a single gas composition.

![Cover](images/cover.png)

> **Disclosure:** I built this workbook and sell it for **$25** on Gumroad: **[[add link](https://ahmadventures070.gumroad.com/l/natzou?_gl=1*rz4uii*_ga*MzYyMDk2ODA1LjE3NjEwMzgxMTM.*_ga_6LJN6D94N6*czE3OTI3NDA0NTgkbzYkZzEkdDE3OTI3NDA0NjQkajU0JGwwJGgw)]**. This repository holds the documentation, screenshots and validation notes only. The workbook itself is not included.

## What it calculates

| Block | Standard | Main outputs |
| --- | --- | --- |
| A. Gas properties | ISO 6976 | Gross and net calorific value (molar, mass and volume basis), Wobbe index, real-gas density, relative density, uncertainties |
| B. Gas properties | AGA Report No. 8, DETAIL method | Compressibility factor, density, speed of sound, Cp, Cv, isentropic exponent |
| C. Orifice flow | ISO 5167-2 (with B and A) | Mass, volume and energy flow, discharge coefficient, expansion factor, Reynolds number, pressure loss, uncertainty, limits-of-use check |

Use any one block or all three together.

## How it works

1. Choose which calculations you need (Yes / No).
2. Enter the gas composition once: 21 components, as mole fraction or mole percent, with optional normalisation.
3. Fill in the operating conditions for the blocks you selected.
4. Read the Results sheet.

Every input is checked. A red message appears beside the problem field, and results stay blank until the inputs are valid. There are no macros. The calculation sheets are hidden and the workbook is protected against accidental edits.

| Inputs | Results |
| --- | --- |
| ![Inputs sheet](images/inputs-sheet.png) | ![Results sheet](images/results-sheet.png) |

The example values in the screenshots are invented.

## Validation

The AGA-8 results were compared with GERG-2008 on six test gases from 0.2 to 12 MPa. Compressibility factor and density agreed within about 0.11 %. Heat capacities differ by up to about 1 %, which is the usual difference between the two models. Full results are in [docs/validation.md](docs/validation.md).

## Limits

- AGA-8 DETAIL is intended for natural gas, with about 0.1 % uncertainty between -10 and 65 °C and up to 12 MPa. Wider ranges are allowed with larger uncertainty.
- ISO 6976 volume-basis values are valid while the compression factor is above 0.9.
- ISO 5167-2 applies to corner, flange and D-D/2 tapping orifice plates in pipes of 50 to 1000 mm, beta 0.10 to 0.75.
- The workbook does not calculate dew point or check phase. Near the dew point, results are not valid.
- Heavy fractions (C7+) must be entered as n-heptane to n-decane, so results depend on that choice.
- It is an engineering aid, provided as is. Check results before using them for design, custody transfer, contractual or safety-related decisions.

## Requirements

Microsoft Excel (desktop recommended). Own copies of ISO 6976, ISO 5167 and AGA Report No. 8 are needed for reference. The standards' text is not included.

## Changelog

See [CHANGELOG.md](CHANGELOG.md).

## Licence

Documentation and images are © Ahmad, all rights reserved. Standards are referred to by name only.
