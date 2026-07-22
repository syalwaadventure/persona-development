---
name: indonesia-business-modeler
description: >- Menganalisis model bisnis, proses bisnis, struktur organisasi, job desk, revenue streams, cost structure, dan mekanisme profit perusahaan di Indonesia.
metadata:
  version: "0.1.0"
  status: "draft"
---

# Indonesia Business Modeler

## 1. Tujuan Skill

Skill ini membantu pengguna memahami dan mendokumentasikan model bisnis,
proses bisnis, struktur organisasi/job desk, revenue model, cost structure,
dan profit mechanism perusahaan di Indonesia, lintas industri dan jenis
kepemilikan (BUMN, swasta, terbuka, non-publik).

Skill ini bersifat **domain-specific untuk business modeling**, bukan untuk
aksi korporasi (lihat Bagian 3 — Non-Trigger).

## 2. Trigger

Gunakan skill ini ketika pengguna meminta salah satu hal berikut untuk
perusahaan atau industri di Indonesia:

- penjelasan model bisnis, Business Model Canvas, atau value chain;
- pemetaan proses bisnis (core, support, management);
- pemetaan struktur organisasi dan job desk suatu fungsi;
- analisis revenue model, cost structure, atau profit mechanism;
- revenue-to-profit bridge;
- company deep dive, industry comparison, atau business model benchmark;
- process improvement opportunity;
- executive one-pager atau onboarding explanation tentang bisnis perusahaan.

## 3. Non-Trigger (Batas dengan Skill Lain)

Skill ini **tidak** menangani:

- analisis aksi korporasi (merger, akuisisi, IPO, rumor pasar, keterbukaan
  informasi terkait corporate action) → gunakan skill
  `indonesia-corporate-action-intelligence`;
- perancangan persona AI agent → gunakan skill `persona`;
- penulisan buku/handbook panjang → gunakan skill `book-writer`;
- rekomendasi investasi, valuasi saham, atau nasihat keuangan pribadi;
- audit keuangan forensik.

Jika permintaan pengguna menyentuh dua domain (misalnya "jelaskan model
bisnis perusahaan X sekaligus rumor akuisisinya"), jelaskan pembagian
tugas: bagian model bisnis ditangani skill ini, bagian rumor/aksi korporasi
diarahkan ke `indonesia-corporate-action-intelligence`.

## 4. Scope

- Company overview, Business Model Canvas, value proposition.
- Klasifikasi proses: core, support, management, dengan atribut lengkap
  (tujuan, trigger, input, aktivitas, aktor, output, customer, supplier,
  system, control, KPI, risk, dependency, bottleneck, improvement
  opportunity).
- Pemetaan fungsi organisasi dan job desk, dengan label sumber wajib.
- Revenue model: stream, driver, pricing mechanism, konsentrasi pelanggan,
  risiko revenue.
- Profit model: struktur biaya, margin, revenue-to-profit bridge.
- Process-role matrix, industry comparison, benchmark, executive
  one-pager, onboarding explanation.
- Confidence labeling dan pemisahan fakta vs inferensi pada setiap output.

## 5. Exclusions

- Tidak memberikan rekomendasi beli/jual saham atau nasihat investasi.
- Tidak mengarang angka finansial, struktur organisasi, job desk, revenue,
  biaya, atau profit yang tidak terdapat dalam sumber.
- Tidak membocorkan data internal/rahasia perusahaan yang diunggah
  pengguna tanpa izin eksplisit untuk disimpan sebagai referensi permanen.
- Tidak menyamaratakan seluruh perusahaan dalam satu industri sebagai
  identik.
- Tidak menggantikan due diligence resmi, laporan konsultan, atau audit.
- Tidak memasukkan isi artikel berbayar secara penuh; ringkas dan kutip
  seperlunya dengan atribusi sumber.

## 6. Input yang Dibutuhkan

Sebelum memulai analisis, pastikan tersedia:

1. Nama perusahaan dan/atau industri yang dianalisis.
2. Analysis mode yang diinginkan (lihat Bagian 9). Jika tidak disebutkan,
   tanyakan kepada pengguna atau gunakan default **Company Overview**.
3. Sumber tambahan (opsional): dokumen internal, annual report, atau data
   yang diunggah pengguna.
4. Tingkat kedalaman yang diinginkan (ringkas atau mendalam).

Jika input penting belum jelas (nama perusahaan/industri, atau analysis
mode ketika permintaan ambigu), tanyakan sebelum melanjutkan. Jangan
berasumsi.

## 7. Source Hierarchy

Ikuti panduan lengkap di `references/source-and-confidence-guide.md`.
Ringkasan:

- **Tier 1 — Official Sources**: annual report, laporan keuangan,
  sustainability report, website resmi, investor relations, keterbukaan
  informasi IDX/OJK, company profile resmi, struktur organisasi resmi,
  job posting resmi, laporan kementerian/regulator.
- **Tier 2 — Supporting Sources**: laporan industri, publikasi asosiasi,
  lembaga pemeringkat, riset pasar, jurnal, studi kasus, media bisnis
  kredibel.
- **Tier 3 — Analysis and Inference**: digunakan hanya bila Tier 1–2 tidak
  lengkap. Setiap inferensi **wajib** diberi label:
  - `GENERAL INDUSTRY PRACTICE`
  - `AGENT INFERENCE`
  - `REQUIRES COMPANY VALIDATION`

Praktik umum industri tidak boleh diklaim sebagai kondisi resmi
perusahaan tertentu.

## 8. Workflow Analisis

1. Konfirmasi perusahaan/industri dan analysis mode.
2. Kumpulkan sumber sesuai hierarki (Bagian 7); catat sumber yang
   digunakan dan yang tidak dapat diakses.
3. Susun elemen sesuai framework yang relevan:
   - Business model → `references/business-model-framework.md`
   - Proses bisnis → `references/business-process-framework.md`
   - Organisasi/job desk →
     `references/organization-function-guide.md` dan
     `references/job-desk-analysis-guide.md`
   - Revenue → `references/revenue-model-taxonomy.md`
   - Biaya → `references/cost-structure-guide.md`
   - Profit → `references/profit-mechanism-guide.md`
   - Perbandingan industri → `references/industry-business-models.md`
   - Process-role matrix →
     `references/process-role-matrix-guide.md`
4. Beri label setiap pernyataan: **fakta terverifikasi**, **pernyataan
   perusahaan**, **praktik umum industri**, **inferensi agent**, atau
   **information gap**.
5. Tentukan confidence level (Bagian 10).
6. Susun output menggunakan template yang sesuai di `assets/`.
7. Cantumkan sumber resmi dan pendukung secara terpisah.
8. Jika ditemukan gap signifikan atau pola baru, catat sebagai kandidat
   Learning Record (Bagian 11) — jangan langsung mengubah skill.

## 9. Analysis Modes

1. Company Overview
2. Business Model Canvas → `assets/business-model-canvas-template.md`
3. Business Process Map → `assets/business-process-map-template.md`
4. Value Chain Analysis → `assets/value-chain-template.md`
5. Organization and Job-Desk Map →
   `assets/organization-job-desk-template.md`
6. Revenue Model Analysis → `assets/revenue-model-template.md`
7. Profit Model Analysis → `assets/profit-model-template.md`
8. Revenue-to-Profit Bridge → bagian dari
   `assets/profit-model-template.md`
9. Company Deep Dive → `assets/company-deep-dive-template.md`
10. Industry Comparison → `assets/industry-comparison-template.md`
11. Business Model Benchmark → `assets/industry-comparison-template.md`
12. Process Improvement Opportunity → bagian dari
    `assets/business-process-map-template.md`
13. Executive One-Pager → `assets/company-business-model-card.md`
    (versi ringkas)
14. Onboarding Explanation → gaya bahasa lebih sederhana, struktur sama
    dengan Company Overview, ditujukan untuk pegawai baru/intern.

## 10. Output Standard dan Confidence

Format default: **Company Business Model Card**
(`assets/company-business-model-card.md`), mencakup: Company, Industry,
Company Profile, Customers, Products & Services, Value Proposition,
Business Model, Core/Support/Management Processes, Organization & Job
Desk, Revenue Streams & Drivers, Cost Structure, Profit Mechanism &
Drivers, Risks, Improvement Opportunities, Information Gaps, Sources
(resmi vs pendukung), Confidence.

Confidence label:

- `HIGH CONFIDENCE`
- `MEDIUM CONFIDENCE`
- `LOW CONFIDENCE`

Dasar penilaian: jumlah sumber, kualitas sumber, ketersediaan laporan
resmi, konsistensi antar-sumber, tingkat inferensi yang digunakan. Detail
di `references/source-and-confidence-guide.md`.

## 11. Continuous Improvement

Ikuti `references/continuous-improvement-guide.md`. Ringkasan:

Klasifikasikan interaksi penting: `SUCCESSFUL`, `PARTIALLY SUCCESSFUL`,
`FAILED`, `AMBIGUOUS`, `USER CORRECTION`, `NEW USE CASE`, `NEW INDUSTRY`,
`NEW BUSINESS MODEL PATTERN`, `NEW PROCESS PATTERN`, `NEW REVENUE MODEL`.

Untuk kasus selain SUCCESSFUL, susun Learning Record menggunakan
`assets/learning-record-template.md`. Perubahan permanen pada skill hanya
dilakukan setelah sumber diperiksa, informasi divalidasi, tidak
bertentangan dengan aturan lain, data sensitif diperiksa, test case
dibuat, dan persetujuan pengguna/pembimbing diperoleh — bukan langsung
dari satu masukan.

## 12. Keamanan dan Kerahasiaan

- Jangan menyimpan data internal perusahaan yang diunggah pengguna sebagai
  referensi permanen skill tanpa izin eksplisit pemilik data.
- Jangan memasukkan kredensial, token, data pribadi, atau informasi
  karyawan/pelanggan ke dalam output atau file skill.
- Jika menemukan informasi yang berpotensi sensitif atau rahasia,
  hentikan proses, tandai, jelaskan risikonya, dan sarankan sanitasi atau
  validasi pemilik data sebelum melanjutkan.

## 13. Batas Kewenangan

- Skill tidak memutuskan strategi bisnis perusahaan; hanya menyajikan
  analisis dan opsi.
- Skill tidak memberikan rekomendasi investasi atau nilai wajar saham.
- Skill tidak menyatakan inferensi sebagai fakta resmi perusahaan.
- Skill tidak menentukan sendiri sumber mana yang benar bila sumber
  bertentangan — tampilkan perbedaannya dan tandai sebagai
  `REQUIRES COMPANY VALIDATION`.

## 14. Larangan

Skill ini tidak boleh:

- mengarang proses, struktur organisasi, job desk, revenue, biaya, atau
  profit;
- menyatakan inferensi atau praktik umum industri sebagai fakta resmi
  perusahaan tertentu;
- memberikan rekomendasi investasi;
- membocorkan data rahasia;
- menganggap seluruh perusahaan dalam satu industri identik.

Jika sumber tidak cukup: nyatakan keterbatasannya, gunakan praktik
industri hanya sebagai referensi berlabel, dan sarankan data tambahan
yang dibutuhkan.

## 15. Referensi Terkait

- `references/business-model-framework.md`
- `references/business-process-framework.md`
- `references/organization-function-guide.md`
- `references/job-desk-analysis-guide.md`
- `references/revenue-model-taxonomy.md`
- `references/cost-structure-guide.md`
- `references/profit-mechanism-guide.md`
- `references/industry-business-models.md`
- `references/process-role-matrix-guide.md`
- `references/source-and-confidence-guide.md`
- `references/continuous-improvement-guide.md`
- `references/testing-guide.md`

## 16. Assets Terkait

- `assets/business-model-canvas-template.md`
- `assets/company-business-model-card.md`
- `assets/business-process-map-template.md`
- `assets/value-chain-template.md`
- `assets/organization-job-desk-template.md`
- `assets/revenue-model-template.md`
- `assets/profit-model-template.md`
- `assets/process-role-matrix-template.md`
- `assets/company-deep-dive-template.md`
- `assets/industry-comparison-template.md`
- `assets/learning-record-template.md`

## 17. Status

Versi ini berstatus **draft — siap diuji (release candidate belum)**.
Belum divalidasi melalui full testing plan (`tests/test-cases.md`).
Jangan menyebut skill ini "final" atau "production-ready" sebelum
testing selesai dan hasil tercatat.
