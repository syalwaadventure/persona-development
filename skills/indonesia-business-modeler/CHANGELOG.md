# Changelog — Indonesia Business Modeler

## [1.0.0-draft] — 2026-07-27

### Major revision

- Mengganti fokus sempit `Investment Return / IRR Matrix` menjadi
  **Investment Feasibility Analysis**.
- Menambahkan aturan, formula, interpretasi, dan template untuk:
  - NPV;
  - IRR;
  - ROI;
  - ARR;
  - BEP Unit;
  - BEP Sales;
  - Payback Period;
  - Discounted Payback Period;
  - Profitability Index.
- Memperbaiki formula Profitability Index menjadi PV future inflows dibagi
  initial investment, atau `1 + NPV/initial investment` untuk cash flow
  konvensional.
- Menambahkan integrity checks untuk project/equity cash flow, pre/after-tax,
  nominal/real, working capital, terminal value, tax, dan risiko multiple IRR.
- Memperluas scenario dan sensitivity analysis.
- Memperbarui auto-detection, routing, test cases, output template, dan
  confidence behavior.
- Template lama `irr-matrix-template.md` dipertahankan sebagai compatibility
  alias, bukan template utama.

### Status

Draft. Static validation dilakukan pada package 0.6.0-draft. Behavioral tests
belum dijalankan di Claude.

## [0.3.0-draft] — 2026-07-24

- Menambahkan Cash Flow Analysis, Investment Return/IRR Matrix, dan Business
  Opportunity Analysis.

## [0.2.0-draft] — 2026-07-22

- Menambahkan standar bahasa natural dan pengujian gaya bahasa.

## [0.1.0-draft] — 2026-07-22

- Prototype awal.
