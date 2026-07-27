# Changelog — Business Excellence Assessor

## [1.1.0-draft] — 2026-07-27

### Major revision — structured, assessor-grade output

- Menambahkan Section 0 "Format Wajib dan Etika Interaksi": setiap respons
  assessment wajib membuka dengan blok **Assessment Initialization**
  (tabel), tidak lagi naratif seperti jawaban chatbot biasa, dan tidak
  boleh menyebut proses internal pembacaan SKILL.md.
- Menambahkan pemisahan **Requested Mode vs Executable Mode** (5b) agar
  permintaan "Full Assessment" tidak otomatis dilabeli Full Assessment
  bila evidence belum memadai.
- Menambahkan taksonomi **Assessment Status** yang konsisten (5c):
  `Awaiting Evidence`, `Not Assessable`, `Preliminary Document Assessment`,
  `Full Assessment`, `Completed with Limitations`.
- Menambahkan **Assessment Readiness Check** (5d) dengan label kualitatif
  (Available/Missing/Confirmed/Default Assumption/dst.) dan larangan
  eksplisit terhadap persentase readiness buatan.
- Menambahkan **Evidence Register** wajib (7a) dan lifecycle evidence
  `Mentioned → Received → Validated → Used in Scoring`, termasuk update
  pada `references/evidence-assessment-guide.md` dan
  `assets/evidence-register-template.md`.
- Menambahkan struktur respons khusus saat evidence belum tersedia (9a):
  Blocking Issues, Next Required Actions, dan Assessor's Note — didukung
  asset baru `assets/preliminary-assessment-template.md`.
- Memperbarui struktur output Full Assessment (Bagian 12) menjadi 12
  bagian: Executive Assessment Summary, Scope and Methodology, Evidence
  Register, Assessment Readiness, Category Assessment, Consolidated
  Maturity Profile, Key Strengths, Areas for Improvement, Evidence Gaps,
  Prioritized Improvement Roadmap, Limitations and Confidence, Conclusion.
  `assets/full-assessment-template.md` disusun ulang mengikuti struktur ini.
- Memperkuat guardrail domain (3a) dan menambahkan larangan eksplisit
  terhadap fitur tanpa dasar: assessment ID acak, angka readiness buatan,
  skor tanpa evidence, bobot tanpa label asumsi, data/nama assessor fiktif,
  serta due date/owner yang tidak diberikan (Guardrails 19–22).
- Menambahkan Test A–G (Output Format and Status Tests) pada
  `tests/business-excellence-assessor/test-cases.md` dan mencatat hasil
  behavioral test pada `test-results.md`.
- Tidak ada perubahan pada skill lain (`indonesia-business-modeler`,
  `persona`, `book-writer`, dst.) dan tidak ada perluasan domain di luar
  maturity assessment.

### Status

Draft; behavioral test sebagian dijalankan (lihat `test-results.md` untuk
rincian test yang PASS vs test yang masih memerlukan dokumen evidence
aktual dari pengguna untuk divalidasi penuh).

## [1.0.0-draft] — 2026-07-27

### Major revision

- Menambahkan rubric enam dimensi: Approach, Deployment, Measurement, Learning, Integration, dan Results.
- Menambahkan evidence gate agar dokumen/SOP tidak otomatis dianggap bukti implementasi atau hasil.
- Menambahkan traceability dan prioritization guide untuk recommendation roadmap.
- Memperjelas routing ke Business Modeler untuk NPV, IRR, ROI, ARR, BEP, payback, cash flow, dan model bisnis.
- Memperluas test coverage untuk approach-only evidence, result gap, recommendation traceability, dan cross-skill routing.

### Status

Draft; static validation dilakukan dalam package 0.6.0-draft. Behavioral tests belum dijalankan.

## [0.1.0-draft] — 2026-07-27

### Ditambahkan

- `SKILL.md` untuk maturity assessment berbasis framework dan evidence.
- Enam analysis mode: Full Assessment, Category Assessment, Preliminary
  Document Assessment, Evidence Gap Analysis, Maturity Improvement Roadmap,
  dan Comparative Assessment.
- Routing boundary yang memisahkan maturity assessment dari fungsi
  `indonesia-business-modeler`.
- Framework generik tujuh kategori yang configurable.
- Maturity scale Level 1–5, scoring guide, aturan N/A, coverage, preliminary
  score, dan confidence level.
- Context guide yang hanya menggunakan isi dokumen Tupoksi & Strategi
  Kompartemen Pusat Keunggulan Bisnis 2025.
- Lima output template dan behavioral test plan.

### Status

**Draft — siap diuji, belum production-ready.** Static validation telah
dijalankan. Behavioral test di Claude belum dijalankan.
