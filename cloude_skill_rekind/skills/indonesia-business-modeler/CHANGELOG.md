# Changelog — indonesia-business-modeler

Format mengikuti semantic versioning (MAJOR.MINOR.PATCH) sesuai aturan
Project "Persona Development".

## [0.1.0-draft] — 2026-07-22

### Status
Prototype awal, status **draft — siap diuji**. Belum melalui eksekusi
testing plan; belum divalidasi sebagai release candidate.

### Ditambahkan
- `SKILL.md` — definisi lengkap skill: tujuan, trigger, non-trigger,
  scope, exclusions, input, source hierarchy, workflow analisis,
  14 analysis mode, output standard, confidence model, continuous
  improvement, keamanan, batas kewenangan, larangan.
- 12 file `references/`: business-model-framework,
  business-process-framework, organization-function-guide,
  job-desk-analysis-guide, revenue-model-taxonomy, cost-structure-guide,
  profit-mechanism-guide, industry-business-models,
  process-role-matrix-guide, source-and-confidence-guide,
  continuous-improvement-guide, testing-guide.
- 11 file `assets/`: business-model-canvas-template,
  company-business-model-card, business-process-map-template,
  value-chain-template, organization-job-desk-template,
  revenue-model-template, profit-model-template,
  process-role-matrix-template, company-deep-dive-template,
  industry-comparison-template, learning-record-template.
- `tests/test-cases.md` — 22 rancangan test case (trigger, non-trigger,
  8 analysis-mode test, missing-information, inference-labeling,
  conflicting-source, hallucination, investment-advice boundary,
  continuous-improvement, regression). Belum ada hasil eksekusi.

### Diketahui Belum Lengkap / Risiko Terbuka
- Testing plan belum dijalankan — semua test case berstatus BLOCKED.
- `references/industry-business-models.md` baru mencakup pola umum
  tingkat tinggi per kelompok industri; perlu diperluas melalui
  continuous improvement seiring bertambahnya kasus nyata.
- Belum ada validasi lapangan (uji ke pengguna Business Excellence/
  Strategy/BD sesungguhnya).
