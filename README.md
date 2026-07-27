# Claude Skill Rekind — Package 0.6.0-draft

Package ini berisi lima skill yang saling melengkapi dan memiliki routing yang
jelas.

| Skill | Fungsi utama | Bukan untuk |
|---|---|---|
| `persona` | Merancang, merevisi, mengaudit, dan menguji persona agent | Menjalankan analisis domain |
| `book-writer` | Menyusun dan memublikasikan buku/handbook HTML | Laporan pendek atau analisis domain |
| `indonesia-business-modeler` | Model bisnis, proses, organisasi, revenue, cost, profit, cash flow, dan investment feasibility | Maturity scoring atau corporate-action verification |
| `indonesia-corporate-action-intelligence` | Corporate-action verification dan four-sector Rekind intelligence brief | Business model/financial feasibility atau investment advice |
| `business-excellence-assessor` | Evidence-based maturity assessment dan improvement roadmap | NPV/IRR/ROI/ARR/BEP/payback atau BMC |

## Perubahan utama 0.6.0-draft

### Indonesia Business Modeler

Investment analysis diperluas dari IRR Matrix menjadi **Investment Feasibility
Analysis**, mencakup:

- NPV;
- IRR;
- ROI;
- ARR;
- BEP Unit dan BEP Sales;
- Payback Period;
- Discounted Payback Period;
- Profitability Index;
- scenario dan sensitivity analysis.

Formula Profitability Index diperbaiki. Aturan basis cash flow, working capital,
tax, nominal/real, project/equity, dan multiple-IRR risk ditambahkan.

### Indonesia Corporate Action Intelligence

- CNBC Indonesia dipertahankan sebagai media Indonesia prioritas.
- **CNBC International/CNBC.com** ditambahkan sebagai international Tier 2
  source.
- Mode Rekind Sector Intelligence menggunakan hard filter:
  **Energi, Oil & Gas, Petrokimia, dan Pupuk**.
- Berita internasional wajib memiliki global-to-Indonesia/Rekind transmission
  path.
- Analisis diperluas ke project/tender, value chain, supply-demand, feedstock,
  EPC/O&M/utilities implications, horizon, risk/opportunity, dan next signal.

### Business Excellence Assessor

Menambahkan rubric enam dimensi: Approach, Deployment, Measurement, Learning,
Integration, dan Results; serta recommendation traceability/prioritization.

### Persona

Menambahkan Fast Build mode, definition of complete persona, dan routing antar
skill.

### Book Writer

Menambahkan source traceability matrix, publication QA report, deliverables per
mode, dan kontrol konsistensi untuk buku panjang.

## Struktur

```text
skills/      source setiap skill
  <skill>/SKILL.md
  <skill>/references/
  <skill>/assets/
tests/       test cases dan test results
docs/        installation, routing, audit, release notes, validation
feedback/    correction and learning logs
learning/    approved lessons and unresolved questions
```

## Status

Package berstatus **draft**.

Static validation dapat memastikan struktur, path, frontmatter, markdown fence,
HTML dependency, dan ZIP integrity. Static validation tidak membuktikan bahwa
behavioral response di Claude sudah benar. Seluruh test case masih harus
dijalankan sebelum package disebut release candidate atau production-ready.

## Dokumen penting

- `docs/skill-routing-matrix.md`
- `docs/release-notes-v0.6.0.md`
- `docs/full-skill-audit-v0.6.0.md`
- `docs/validation-report.json`
- `CHANGELOG.md`
