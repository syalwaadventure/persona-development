# Release Notes — 0.6.0-draft

## Purpose

This draft rebuild completes and clarifies all five existing skills without
adding another skill.

## Most important correction

The previous Indonesia Business Modeler used an IRR-centered name and did not
explicitly support all required metrics. Version 0.6.0-draft now supports:

- NPV;
- IRR;
- ROI;
- ARR;
- BEP Unit;
- BEP Sales;
- Payback Period;
- Discounted Payback Period;
- Profitability Index.

The financial-analysis guide now specifies formulas, basis, data requirements,
limitations, and integrity checks.

## Corporate intelligence change

CNBC International/CNBC.com is included as a global media source. International
stories are not included automatically; they must have a direct transmission
path to the four target sectors and Indonesian/Rekind relevance.

## Compatibility

- Old prompt wording “IRR Matrix” remains accepted.
- `assets/irr-matrix-template.md` remains in the package as a compatibility
  alias.
- Existing skill folder names remain unchanged.

## Validation status

Static checks are performed during build. Behavioral tests remain NOT TESTED.
The package must not be described as production-ready.
