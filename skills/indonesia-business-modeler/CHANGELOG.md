# Changelog — Indonesia Business Modeler

## [1.1.0-draft] — 2026-07-30

### Minor (additive) — Executive Decision Synthesis

Latar belakang: behavioral testing menggunakan laporan bulanan perusahaan
(PT Tracon Industri) menunjukkan output skill masih terasa seperti
Financial Analyst (berhenti di level framework: Profit/Cash Flow/Risk
Analysis), belum seperti Executive Advisor yang menghasilkan insight siap
pakai untuk Direksi.

Perubahan ini **murni menambah kemampuan**. Tidak ada workflow, mode,
trigger, reference, atau template lama yang dihapus, diganti, atau
disederhanakan.

Ditambahkan:

- **Phase 8 — Executive Decision Synthesis** pada workflow (Bagian 8
  SKILL.md), dijalankan setelah Phase 1–7 selesai, tanpa mengubah Phase
  1–7.
- **Bagian 17 — Executive Decision Synthesis** pada SKILL.md: Executive
  Thinking Rules (internal), Business Interpretation Rules (pola apa →
  mengapa → dampak → implikasi → rekomendasi), Root Cause Pattern,
  Business Impact Dimensions, Prioritization Engine, Company Health
  Assessment, Executive Report Template (10 bagian), dan integrity checks.
- Reference baru: `references/executive-synthesis-guide.md`.
- Asset baru: `assets/executive-management-report-template.md`.
- Baris trigger baru di Bagian 1 dan baris auto-detection baru di Bagian 6
  untuk permintaan laporan bulanan/executive report tanpa mode eksplisit,
  termasuk skenario zero-prompt: "Analisis laporan bulanan perusahaan
  menggunakan Business Modeler."
- Baris mode baru "Executive Management Report (Phase 8)" di tabel Bagian 9,
  dengan catatan eksplisit bahwa ini lapisan sintesis, bukan pengganti mode
  lain.
- Test case baru #30–#35 di `references/testing-guide.md`, termasuk
  zero-prompt test, structure test, health-assessment reasoning test,
  root-cause/prioritization test, backward-compatibility regression test,
  dan hallucination test khusus Phase 8.

Tidak diubah/dihapus:

- Seluruh trigger, non-trigger, exclusions, input/asumsi, auto-detection
  lama, source hierarchy, seluruh mode analisis (Company Overview s.d.
  Investment Feasibility Analysis, Business Opportunity, Industry
  Comparison, dst.), seluruh reference dan asset lama, serta seluruh test
  case #1–#29.

### Status

Draft. Static validation dilakukan terhadap struktur package. Behavioral
test (termasuk skenario zero-prompt dan backward-compatibility regression)
harus dijalankan di Claude sebelum dinyatakan release candidate.

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
