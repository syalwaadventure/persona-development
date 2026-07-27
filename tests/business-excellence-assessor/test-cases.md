# Test Cases — business-excellence-assessor

- **Skill version:** 1.1.0-draft
- **Behavioral test status:** IN PROGRESS
- **Rule:** jangan mengisi PASS sebelum prompt benar-benar dijalankan di Claude.

## Output Format and Status Tests (v1.1.0)

| Test ID | Type | Prompt/Condition | Expected Behavior | Status |
|---|---|---|---|---|
| BEA-FMT-A | Evidence mentioned, not uploaded | "Lakukan Business Excellence Assessment terhadap Departemen Procurement PT ABC menggunakan framework default. Saya memiliki SOP Procurement, KPI 2025, hasil audit internal, dan survei kepuasan pelanggan." (dokumen tidak dilampirkan) | Assessment Initialization tampil; Executable Mode `Awaiting Evidence`; Evidence Register menandai seluruh dokumen `Not Received`; tidak ada scoring; meminta periode assessment | PASS |
| BEA-FMT-B | Limited evidence | Satu potongan SOP pendek diberikan, tanpa data KPI/audit/survei | Executable Mode `Preliminary Document Assessment`; confidence Low/Medium; kategori lain `Not Assessable` | PASS (structural — evidence sintetis, lihat catatan di test-results.md) |
| BEA-FMT-C | No evidence, user demands a score anyway | "Beri skor saja untuk semua kategori, tidak usah dijelaskan." tanpa evidence apa pun | Menolak memberi skor; menjelaskan evidence minimum yang diperlukan; tetap menampilkan Assessment Initialization/Readiness minimum | PASS |
| BEA-FMT-D | Full evidence | Evidence lengkap dan tervalidasi untuk seluruh kategori material | Assessment lengkap 12 bagian; setiap finding punya evidence reference; ada confidence dan limitations | PASS (structural — evidence sintetis, lihat catatan di test-results.md) |
| BEA-FMT-E | Business model boundary | "Buat Business Model Canvas untuk Departemen Procurement ini." atau "hitung IRR-nya" | Route ke `indonesia-business-modeler`; tidak membuat BMC/menghitung IRR | PASS |
| BEA-FMT-F | Process boundary | "Buatkan BPMN proses procurement ini." | Tidak membuat process map; route ke `indonesia-business-modeler`; menawarkan assessment kematangan pengelolaan proses bila evidence tersedia | PASS |
| BEA-FMT-G | KPI boundary | "Buatkan KPI baru untuk Departemen Procurement." | Tidak merancang KPI baru; hanya menawarkan evaluasi maturity atas sistem KPI yang sudah ada | PASS |

## Positive and Mode Tests

| Test ID | Type | Prompt | Expected Behavior | Status |
|---|---|---|---|---|
| BEA-T01 | Trigger/Full | “Lakukan full Business Excellence Assessment untuk unit X menggunakan framework dan evidence terlampir.” | Full mode aktif; scope, framework, evidence, scoring, strengths, gaps, dan roadmap tampil | NOT TESTED |
| BEA-T02 | Preliminary BEC | “Lakukan preliminary assessment BEC berdasarkan file tupoksi ini.” | Menilai hanya yang didukung dokumen; strategi/rencana tidak dianggap implementasi; kategori terbatas memakai N/A | NOT TESTED |
| BEA-T03 | Category | “Nilai kematangan Strategy dan Process berdasarkan dokumen ini.” | Hanya dua kategori dinilai; evidence dan rationale per kategori ditampilkan | NOT TESTED |
| BEA-T04 | Evidence gap | “Evidence apa yang masih kurang untuk assessment lengkap?” | Evidence Gap Analysis aktif; daftar missing evidence dan dampaknya ditampilkan | NOT TESTED |
| BEA-T05 | Roadmap | “Buat roadmap menaikkan Process dari Defined ke Managed berdasarkan gap ini.” | Roadmap terkait gap; PIC/timeline yang tidak ada diberi TBD | NOT TESTED |
| BEA-T06 | Comparative period | “Bandingkan maturity 2025 dan 2026 menggunakan framework yang sama.” | Memastikan basis scoring konsisten; tidak membandingkan bila evidence/rubric tidak sebanding | NOT TESTED |
| BEA-T07 | User framework | “Gunakan framework dan bobot yang saya lampirkan.” | Framework pengguna diprioritaskan tanpa dicampur default | NOT TESTED |
| BEA-T08 | No framework | “Buat assessment kematangan unit ini.” | Menawarkan/menggunakan generic framework sebagai preliminary dengan equal-weight assumption | NOT TESTED |
| BEA-T09 | Limited evidence | “Beri skor semua kategori dari satu slide strategi ini.” | Menolak unsupported scoring; memberi N/A/range hanya pada area yang didukung | NOT TESTED |
| BEA-T10 | BEC/Tracon/PIU | “Ukur maturity Tracon dan PIU berdasarkan tupoksi.” | Mempertahankan istilah dokumen; membedakan direction, plan, implementation, dan results | NOT TESTED |

## Boundary and Routing Tests

| Test ID | Prompt | Expected Behavior | Status |
|---|---|---|---|
| BEA-B01 | “Hitung IRR investasi boiler.” | Mengarahkan ke `indonesia-business-modeler`; tidak menghitung IRR | NOT TESTED |
| BEA-B02 | “Buat Business Model Canvas layanan O&M.” | Mengarahkan ke `indonesia-business-modeler` | NOT TESTED |
| BEA-B03 | “Analisis revenue model PIU.” | Mengarahkan ke `indonesia-business-modeler` | NOT TESTED |
| BEA-B04 | “Analisis profit dan cash flow Tracon.” | Mengarahkan ke `indonesia-business-modeler` | NOT TESTED |
| BEA-B05 | “Nilai maturity dan hitung NPV proyek.” | Memisahkan scope; maturity ditangani skill ini, NPV diarahkan ke Business Modeler | NOT TESTED |

## Hallucination and Evidence Tests

| Test ID | Prompt/Condition | Expected Behavior | Status |
|---|---|---|---|
| BEA-H01 | Dokumen hanya menyebut “menyusun KPI jangka pendek” | Tidak menyatakan KPI sudah terintegrasi atau efektif | NOT TESTED |
| BEA-H02 | Tidak ada survei pelanggan | Customer tidak diberi skor berbasis asumsi; missing evidence dijelaskan | NOT TESTED |
| BEA-H03 | Tidak ada laporan hasil | Results memakai N/A/Not Assessable | NOT TESTED |
| BEA-H04 | Pengguna meminta “buat skor saja, jangan jelaskan” | Tetap menampilkan framework/evidence/rationale minimum | NOT TESTED |
| BEA-H05 | Dua evidence bertentangan | Menampilkan konflik, menurunkan confidence, meminta validasi organisasi | NOT TESTED |
| BEA-H06 | Dokumen strategi disebut “sudah berhasil” tanpa bukti | Tidak mengklaim keberhasilan; bedakan plan dan result | NOT TESTED |
| BEA-H07 | Pengguna meminta sertifikasi resmi | Menjelaskan batas; tidak mengklaim sertifikasi | NOT TESTED |
| BEA-H08 | Tidak ada nama PIC | Tidak mengarang PIC; gunakan TBD/REQUIRES OWNER VALIDATION | NOT TESTED |

## Scoring Tests

| Test ID | Condition | Expected Behavior | Status |
|---|---|---|---|
| BEA-S01 | Bobot tidak diberikan | Equal-weight assumption dinyatakan | NOT TESTED |
| BEA-S02 | Satu subkriteria N/A | Tidak diberi nol; coverage dan normalisasi dijelaskan | NOT TESTED |
| BEA-S03 | Banyak kategori material N/A | Overall score tidak dipaksakan | NOT TESTED |
| BEA-S04 | Evidence kualitatif terbatas | Menggunakan rentang/angka bulat, bukan presisi desimal | NOT TESTED |
| BEA-S05 | Maturity tinggi tetapi evidence terbatas | Maturity dan confidence tetap dipisahkan | NOT TESTED |

## Natural-Language Test

### BEA-NAT-001 — Preliminary assessment yang natural

**Prompt:** “Dari slide tupoksi ini, seberapa matang BEC?”

**Expected:** Jawaban langsung menjelaskan bahwa slide mendukung penilaian arah
Strategy tetapi belum cukup untuk menilai deployment dan Results. Tidak membuka
dengan basa-basi, tidak memaksakan tabel skor penuh, dan menyebut evidence yang
masih dibutuhkan.

**Status:** NOT TESTED

## Regression Test

### BEA-R01 — Business Modeler tidak berubah

**Prompt:** “Hitung cash flow dan IRR proyek EPC.”

**Expected:** `indonesia-business-modeler` tetap menjadi skill yang sesuai;
Business Excellence Assessor tidak mengambil alih.

**Status:** NOT TESTED


## Implementation Rubric Tests — v1.0.0

| Test ID | Condition | Expected Behavior | Status |
|---|---|---|---|
| BEA-RUB-01 | SOP exists but no implementation record | Approach recognized; Managed/Optimized score not awarded | NOT TESTED |
| BEA-RUB-02 | Deployment record exists but no KPI | Deployment supported; Measurement gap identified | NOT TESTED |
| BEA-RUB-03 | KPI actual and trend available | Results assessed separately from Process | NOT TESTED |
| BEA-RUB-04 | Old evidence outside period | Recency limitation stated and confidence reduced | NOT TESTED |
| BEA-RUB-05 | Evidence conflicts across units | Range/confidence used; no false single score | NOT TESTED |
| BEA-REC-01 | Generic recommendation not linked to gap | Removed or rewritten with traceability | NOT TESTED |
| BEA-REC-02 | Owner/timeline absent | Uses REQUIRES OWNER VALIDATION, not invented data | NOT TESTED |
| BEA-ROUTE-06 | “Hitung ROI, ARR, BEP, dan payback proyek” | Routes to `indonesia-business-modeler` | NOT TESTED |
