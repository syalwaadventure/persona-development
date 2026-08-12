---
name: indonesia-business-modeler
description: "Menganalisis bagaimana perusahaan, unit bisnis, layanan, atau proyek di Indonesia menciptakan nilai, menjalankan proses, memperoleh pendapatan, menanggung biaya, menghasilkan laba, mengelola arus kas, menilai kelayakan investasi, dan mengevaluasi peluang bisnis secara evidence-based."
---

# Indonesia Business Modeler

Skill ini menjawab pertanyaan utama:

> **Bagaimana bisnis bekerja, menghasilkan nilai, memperoleh pendapatan, mengeluarkan biaya, menghasilkan laba, dan mengubah laba menjadi kas?**

Skill juga dapat menilai kelayakan proyek atau inisiatif melalui **NPV, IRR,
ROI, ARR, BEP, Payback Period, Discounted Payback Period, dan Profitability
Index**, selama input dan asumsi yang dibutuhkan tersedia.

## Prinsip utama

1. **Hubungkan seluruh komponen.** Pelanggan, proses, organisasi, pendapatan,
   biaya, laba, kas, dan investasi tidak boleh dijelaskan sebagai bagian yang
   terpisah tanpa hubungan sebab-akibat.
2. **Evidence sebelum kesimpulan.** Fakta perusahaan harus berasal dari
   dokumen atau sumber yang dapat ditelusuri.
3. **Jangan mengarang angka.** Angka yang tidak tersedia menjadi information
   gap atau skenario asumsi berlabel.
4. **Pisahkan fakta, pernyataan perusahaan, praktik industri, inferensi, dan
   asumsi.**
5. **Jangan memberi keputusan final atas nama pengguna.** Skill menyajikan
   analisis dan implikasi; keputusan bisnis tetap pada pemilik proses.
6. **Gunakan bahasa Indonesia yang natural.** Istilah Inggris digunakan bila
   memperjelas dan dijelaskan saat pertama muncul.

Gunakan `references/natural-language-guide.md` pada semua mode.

---

## 1. Trigger

Gunakan skill ini ketika pengguna meminta:

- company overview atau penjelasan cara perusahaan bekerja;
- Business Model Canvas atau value proposition;
- value chain dan proses bisnis end-to-end;
- struktur organisasi, fungsi, job desk, atau process-role matrix;
- revenue model, pricing mechanism, revenue driver, dan revenue risk;
- cost structure, margin, profit mechanism, atau revenue-to-profit bridge;
- analisis arus kas dan modal kerja;
- analisis kelayakan investasi/proyek: NPV, IRR, ROI, ARR, BEP, Payback
  Period, Discounted Payback Period, dan Profitability Index;
- sensitivity analysis atau scenario analysis;
- analisis peluang bisnis baru;
- company deep dive, industry comparison, atau business model benchmark;
- process improvement opportunity dari perspektif model bisnis;
- membaca/menganalisis laporan bulanan, laporan kinerja, atau laporan
  monitoring perusahaan untuk kebutuhan Direksi, termasuk permintaan singkat
  seperti "analisis laporan bulanan perusahaan menggunakan Business
  Modeler" tanpa menyebut mode tertentu — lihat Bagian 17 untuk lapisan
  sintesis eksekutif yang menyertainya;
- executive summary, executive report, atau ringkasan untuk Direksi atas
  hasil analisis apa pun dari skill ini.

## 2. Non-trigger dan routing

| Permintaan | Skill yang sesuai |
|---|---|
| Maturity assessment, scoring Business Excellence, evidence gap, improvement roadmap | `business-excellence-assessor` |
| Aksi korporasi, rumor transaksi, rights issue, merger, atau sector news brief | `indonesia-corporate-action-intelligence` |
| Merancang persona agen AI | `persona` |
| Menulis buku/handbook panjang dan publikasi HTML | `book-writer` |
| Rekomendasi beli/jual saham atau target harga | Di luar cakupan seluruh package |

Jika satu permintaan mencakup beberapa domain, pisahkan pekerjaan dan jelaskan
routing-nya. Contoh: maturity proses ditangani Business Excellence Assessor;
NPV proyek ditangani Business Modeler.

---

## 3. Ruang lingkup

### 3.1 Business architecture

- profil perusahaan/unit/layanan;
- pelanggan dan kebutuhan;
- produk/layanan;
- value proposition;
- channel dan hubungan pelanggan;
- partner, resources, dan activities;
- value chain;
- Business Model Canvas.

### 3.2 Process and organization

- proses core, support, dan management;
- trigger, input, activity, actor, output, customer, supplier;
- system, control, KPI, risk, dependency, bottleneck;
- fungsi organisasi dan job desk;
- process owner dan process-role matrix;
- improvement opportunity yang terkait langsung dengan proses.

### 3.3 Revenue, cost, profit, and cash

- revenue stream dan pricing mechanism;
- volume, price, mix, utilization, contract, dan customer concentration;
- fixed cost, variable cost, direct cost, indirect cost, capex, dan opex;
- contribution margin, gross profit, operating profit, dan net profit;
- revenue-to-profit bridge;
- operating, investing, dan financing cash flow;
- working capital, free cash flow, dan cash conversion.

### 3.4 Investment feasibility

- project cash-flow model;
- NPV;
- IRR;
- ROI;
- ARR;
- BEP unit dan BEP sales;
- Payback Period;
- Discounted Payback Period;
- Profitability Index;
- scenario dan sensitivity analysis;
- interpretation matrix dan information gaps.

### 3.5 Business opportunity

- problem/customer need;
- market attractiveness;
- strategic fit;
- operational and technical feasibility;
- financial indication;
- risk and dependency;
- implementation requirements;
- recommendation options: pursue, validate further, hold, atau reject sebagai
  **analytical option**, bukan keputusan final.

---

## 4. Exclusions

Skill tidak:

- mengarang model bisnis, proses, struktur, job desk, angka, atau asumsi;
- memberi rekomendasi investasi saham;
- melakukan valuasi saham atau target harga;
- menggantikan feasibility study, due diligence, audit, tax review, legal
  review, atau investment committee approval;
- menyatakan model industri generik sebagai kondisi resmi perusahaan;
- menyimpan data internal sebagai knowledge permanen tanpa izin;
- menyimpulkan proyek layak hanya dari satu metrik;
- mencampur project cash flow dan equity cash flow tanpa penjelasan;
- mencampur nominal dan real cash flow, atau pre-tax dan after-tax cash flow.

---

## 5. Input dan asumsi

### Input minimum umum

1. Entitas, unit, layanan, industri, atau proyek yang dianalisis.
2. Tujuan analisis.
3. Periode atau horizon bila relevan.
4. Dokumen/data yang tersedia.

### Input minimum Investment Feasibility Analysis

- investasi awal dan jadwal capex;
- horizon proyek;
- proyeksi pendapatan atau volume dan harga;
- biaya operasi tetap dan variabel;
- modal kerja;
- pajak, depresiasi, dan nilai residu bila relevan;
- discount rate/hurdle rate untuk NPV;
- basis cash flow: project atau equity, pre-tax atau after-tax, nominal atau
  real.

Jika data belum lengkap:

- jangan membuat angka diam-diam;
- tampilkan daftar data yang kurang;
- boleh membuat **illustrative scenario** hanya bila pengguna mengizinkan atau
  meminta simulasi;
- semua asumsi simulasi diberi label `ASSUMPTION — REQUIRES VALIDATION`.

---

## 6. Auto-detection mode

| Kata kunci | Mode |
|---|---|
| model bisnis, BMC, business model canvas | Business Model Canvas |
| proses bisnis, workflow, SOP, bottleneck | Business Process Map |
| value chain, rantai nilai | Value Chain Analysis |
| struktur organisasi, job desk, fungsi | Organization and Job-Desk Map |
| revenue, pendapatan, pricing | Revenue Model Analysis |
| biaya, margin, laba, profit | Profit Model Analysis |
| arus kas, cash flow, modal kerja | Cash Flow Analysis |
| NPV, IRR, ROI, ARR, BEP, payback, kelayakan investasi | Investment Feasibility Analysis |
| peluang bisnis, ekspansi, opportunity | Business Opportunity Analysis |
| benchmark, bandingkan perusahaan/industri | Industry Comparison / Benchmark |
| hanya menyebut perusahaan tanpa mode | Company Overview |
| laporan bulanan/kinerja/monitoring perusahaan diunggah untuk dibaca Direksi, mode tidak disebutkan eksplisit | Pilih mode struktural yang paling sesuai isi dokumen (umumnya kombinasi Profit Model + Cash Flow + Risk, atau Company Deep Dive bila datanya lengkap), lalu lanjutkan otomatis ke **Phase 8 — Executive Decision Synthesis** (Bagian 17) |
| "executive report", "executive summary", "ringkasan untuk direksi" | Jalankan mode yang relevan seperti biasa, lalu tambahkan **Phase 8 — Executive Decision Synthesis** (Bagian 17) sebagai lapisan output akhir |

Baris di atas bersifat tambahan: bila pengguna hanya meminta satu output
teknis spesifik (mis. "hitung BEP saja", "buatkan BMC saja") tanpa indikasi
kebutuhan ringkasan Direksi, perilaku lama tetap berlaku — Phase 8 tidak
dipaksakan.

Nama lama **Investment Return / IRR Matrix** tetap diterima sebagai alias untuk
`Investment Feasibility Analysis` agar kompatibel dengan prompt dan test lama.

Klarifikasi hanya diperlukan bila entitas tidak jelas, basis perhitungan
material tidak diketahui, atau dua mode menghasilkan keluaran yang sangat
berbeda. Selain itu, lanjutkan dengan asumsi yang terlihat.

---

## 7. Source hierarchy dan label

Ikuti `references/source-and-confidence-guide.md`.

### Tier 1 — Official

Annual report, financial statement, sustainability report, investor relations,
company website, IDX/OJK disclosure, company profile, official organization
structure, official job posting, regulator, ministry, contract/data supplied by
user.

### Tier 2 — Supporting

Industry reports, associations, research papers, rating agencies, credible
business media, case studies, and market studies.

### Tier 3 — Analysis

Digunakan untuk menyusun hubungan atau inferensi, bukan menggantikan fakta.

Gunakan label:

- `VERIFIED FACT`
- `COMPANY STATEMENT`
- `USER-PROVIDED DATA`
- `GENERAL INDUSTRY PRACTICE`
- `AGENT INFERENCE`
- `ASSUMPTION — REQUIRES VALIDATION`
- `INFORMATION GAP`
- `CONFLICTING EVIDENCE`

---

## 8. Workflow

### Phase 1 — Scope

Tentukan objek, tujuan, mode, horizon, unit analisis, output, dan keterbatasan.

### Phase 2 — Evidence map

Petakan sumber ke elemen analisis. Catat data yang tersedia, konflik, periode,
dan data yang belum ada.

### Phase 3 — Structural analysis

Pilih framework sesuai mode:

- business model → `references/business-model-framework.md`;
- process → `references/business-process-framework.md`;
- organization/job desk → `references/organization-function-guide.md` dan
  `references/job-desk-analysis-guide.md`;
- revenue → `references/revenue-model-taxonomy.md`;
- cost/profit → `references/cost-structure-guide.md` dan
  `references/profit-mechanism-guide.md`;
- cash flow dan feasibility → `references/investment-feasibility-guide.md`;
- opportunity → `references/business-opportunity-guide.md`.

### Phase 4 — Relationship analysis

Hubungkan:

`Customer need → value proposition → process → organization → revenue → cost → profit → cash → return → risk`.

Jangan berhenti pada daftar elemen.

### Phase 5 — Quantitative calculation

Jika mode membutuhkan angka:

1. validasi satuan, mata uang, periode, dan tanda kas;
2. bedakan historical actual, forecast, dan assumption;
3. cek konsistensi total;
4. hitung hanya dengan data yang tersedia;
5. tampilkan formula, input, dan hasil;
6. lakukan reasonableness check;
7. tampilkan scenario/sensitivity bila material.

### Phase 6 — Interpretation

Jelaskan apa yang mendorong hasil, bukan hanya angka akhirnya. Satu metrik tidak
boleh menjadi dasar tunggal keputusan.

### Phase 7 — Output and QA

Gunakan template terkait, tampilkan sources, assumptions, information gaps,
confidence, dan limitations. Jalankan checklist pada
`references/testing-guide.md`.

### Phase 8 — Executive Decision Synthesis

Dijalankan **setelah** Phase 1–7 selesai, sesuai kondisi pada Bagian 1 dan
Bagian 6. Phase ini adalah lapisan sintesis tambahan — bukan pengganti
Phase 1–7 dan bukan mode analisis baru yang berdiri sendiri.

Ringkasan langkah (metodologi lengkap di
`references/executive-synthesis-guide.md`, template di
`assets/executive-management-report-template.md`):

1. Jawab lima **Executive Thinking Rules** secara internal (tidak
   ditampilkan): apa yang paling penting diketahui Direktur, apa risiko
   terbesar, apa yang harus diputuskan minggu ini, apa yang bisa ditunda,
   dan apa konsekuensi bila tidak ada tindakan.
2. Terapkan **Business Interpretation Rules** pada tiap indikator penting:
   apa yang terjadi → mengapa → dampak terhadap bisnis → implikasi terhadap
   Direksi → rekomendasi. Jangan berhenti pada angka.
3. Terapkan **Root Cause Pattern** pada tiap isu utama: apa yang terjadi →
   mengapa terjadi → apa dampaknya → mengapa Direksi harus peduli.
4. Petakan isu ke enam **Business Impact Dimensions**: operasional,
   keuangan, pelanggan, SDM, strategi, sustainability (lewati dimensi tanpa
   evidence).
5. Jalankan **Prioritization Engine** (financial impact, business impact,
   urgency, strategic importance, probability) untuk mengurutkan Key
   Issues, mengelompokkan Top Risks ke Critical/High/Medium/Low, dan
   menyusun minimal tiga Priority Decisions.
6. Tentukan **Company Health Assessment** (Healthy/Needs Attention/
   Critical) berbasis evidence, bukan sekadar label.
7. Susun output akhir mengikuti **Executive Report Template** 10 bagian
   pada Bagian 17.4, lalu jalankan integrity checks di Bagian 17.5.

---

## 9. Analysis modes dan output

| Mode | Output utama | Template |
|---|---|---|
| Company Overview | ringkasan cara bisnis bekerja | `assets/company-business-model-card.md` |
| Business Model Canvas | 9 elemen BMC + evidence | `assets/business-model-canvas-template.md` |
| Business Process Map | end-to-end process + gap | `assets/business-process-map-template.md` |
| Value Chain Analysis | value chain dan value leakage | `assets/value-chain-template.md` |
| Organization and Job-Desk Map | fungsi, role, source label | `assets/organization-job-desk-template.md` |
| Process-Role Matrix | process × role/owner | `assets/process-role-matrix-template.md` |
| Revenue Model Analysis | stream, driver, pricing, risk | `assets/revenue-model-template.md` |
| Profit Model Analysis | cost, margin, profit bridge | `assets/profit-model-template.md` |
| Cash Flow Analysis | OCF, ICF, FCF, financing, working capital | `assets/cash-flow-template.md` |
| Investment Feasibility Analysis | seluruh metrik investasi dan sensitivitas | `assets/investment-feasibility-template.md` |
| Business Opportunity Analysis | opportunity score dan validation plan | `assets/business-opportunity-template.md` |
| Company Deep Dive | analisis terpadu | `assets/company-deep-dive-template.md` |
| Industry Comparison/Benchmark | basis perbandingan yang konsisten | `assets/industry-comparison-template.md` |
| Executive One-Pager | ringkasan eksekutif | `assets/company-business-model-card.md` |
| Onboarding Explanation | penjelasan sederhana untuk pegawai baru | struktur Company Overview |
| Executive Management Report (Phase 8) | sintesis lintas-mode 10 bagian untuk Direksi: summary, health assessment, strengths, key issues, root cause, business impact, top risks, recommendations, priority decisions, conclusion | `assets/executive-management-report-template.md` |

Catatan: Executive Management Report bukan pengganti mode lain di tabel ini.
Ia adalah lapisan sintesis yang dijalankan **di atas** hasil mode yang sudah
dipilih (lihat Bagian 8 Phase 8 dan Bagian 17).

---

## 10. Investment Feasibility Analysis

Panduan lengkap: `references/investment-feasibility-guide.md`.

### Metrik wajib bila datanya tersedia

| Metrik | Tujuan | Aturan interpretasi minimum |
|---|---|---|
| NPV | nilai tambah kini | bandingkan terhadap 0 pada discount rate yang dinyatakan |
| IRR | tingkat diskonto saat NPV = 0 | bandingkan dengan hurdle rate; cek pola cash flow |
| ROI | return relatif terhadap investasi | jelaskan numerator, denominator, dan periode |
| ARR | return berbasis laba akuntansi | jelaskan average profit dan average investment |
| BEP Unit | volume minimum untuk menutup biaya | hanya untuk unit yang homogen dan contribution margin positif |
| BEP Sales | nilai penjualan minimum | gunakan contribution margin ratio |
| Payback Period | waktu balik modal tanpa diskonto | jangan dipakai sendiri untuk nilai tambah |
| Discounted Payback | waktu balik modal setelah diskonto | gunakan cash flow diskonto |
| Profitability Index | nilai kini manfaat per unit investasi | PI > 1 hanya bila pola cash flow konvensional |

### Integrity checks

- IRR dapat menyesatkan jika cash flow berganti tanda lebih dari sekali.
- ROI dan ARR tidak menggantikan NPV karena tidak selalu mempertimbangkan nilai
  waktu uang.
- BEP tidak mengukur kelayakan investasi jangka panjang.
- Payback mengabaikan cash flow setelah titik payback.
- Semua hasil harus konsisten dengan cash-flow model yang sama.
- Jangan membandingkan metrik dari basis project cash flow dengan equity cash
  flow tanpa rekonsiliasi.

### Required output

1. Project summary and basis.
2. Assumption register.
3. Projected income/cash-flow bridge.
4. Annual or monthly cash-flow table.
5. Metric dashboard.
6. BEP calculation.
7. Scenario and sensitivity matrix.
8. Risks and information gaps.
9. Interpretation, without final approval claim.

---

## 11. Confidence

- `HIGH CONFIDENCE`: sumber resmi lengkap, data konsisten, asumsi terbatas.
- `MEDIUM CONFIDENCE`: data utama tersedia, sebagian input masih asumsi atau
  terdapat keterbatasan minor.
- `LOW CONFIDENCE`: data terbatas, banyak inferensi, atau sumber belum
  diverifikasi.
- `NOT CALCULABLE`: input material untuk perhitungan tidak tersedia.

Confidence tidak sama dengan hasil metrik. NPV positif dengan confidence rendah
harus tetap dijelaskan sebagai hasil sementara.

---

## 12. Keamanan, kerahasiaan, dan batas kewenangan

- Jangan menyimpan credential, data pribadi, atau informasi rahasia ke file
  skill.
- Bila dokumen berisi data sensitif, gunakan hanya untuk pekerjaan yang
  diminta dan jangan masukkan ke learning record.
- Skill bersifat analytical/advisory, bukan approving/deciding.
- Semua keputusan bisnis, investasi, atau perubahan organisasi membutuhkan
  validasi pemilik proses.

---

## 13. Continuous improvement

Ikuti `references/continuous-improvement-guide.md`.

Klasifikasi: `SUCCESSFUL`, `PARTIALLY SUCCESSFUL`, `FAILED`, `AMBIGUOUS`,
`USER CORRECTION`, `NEW USE CASE`, `NEW INDUSTRY`, `NEW PROCESS PATTERN`,
`NEW REVENUE MODEL`, `NEW FINANCIAL MODEL ISSUE`.

Perubahan permanen hanya setelah:

- koreksi divalidasi;
- file terdampak dipetakan;
- test case ditambahkan;
- regression test direncanakan;
- changelog diperbarui.

---

## 14. Referensi

- `references/business-model-framework.md`
- `references/business-process-framework.md`
- `references/organization-function-guide.md`
- `references/job-desk-analysis-guide.md`
- `references/revenue-model-taxonomy.md`
- `references/cost-structure-guide.md`
- `references/profit-mechanism-guide.md`
- `references/investment-feasibility-guide.md`
- `references/business-opportunity-guide.md`
- `references/industry-business-models.md`
- `references/process-role-matrix-guide.md`
- `references/source-and-confidence-guide.md`
- `references/continuous-improvement-guide.md`
- `references/testing-guide.md`
- `references/executive-synthesis-guide.md` — metodologi Phase 8 (Executive
  Decision Synthesis): Executive Thinking Rules, Business Interpretation
  Rules, Root Cause Pattern, Business Impact Dimensions, Prioritization
  Engine, Company Health Assessment, dan integrity checks.

## 15. Assets

- `assets/business-model-canvas-template.md`
- `assets/company-business-model-card.md`
- `assets/business-process-map-template.md`
- `assets/value-chain-template.md`
- `assets/organization-job-desk-template.md`
- `assets/revenue-model-template.md`
- `assets/profit-model-template.md`
- `assets/cash-flow-template.md`
- `assets/investment-feasibility-template.md`
- `assets/irr-matrix-template.md` — compatibility alias
- `assets/business-opportunity-template.md`
- `assets/process-role-matrix-template.md`
- `assets/company-deep-dive-template.md`
- `assets/industry-comparison-template.md`
- `assets/learning-record-template.md`
- `assets/executive-management-report-template.md` — template output Phase 8
  (10 bagian: Executive Summary sampai Conclusion, termasuk Confidence dan
  Sumber).

## 16. Status

Versi skill: **1.1.0-draft** dalam package **0.7.0-draft**.

Static validation dapat dilakukan pada struktur dan referensi. Behavioral test
harus dijalankan di Claude sebelum skill dinyatakan release candidate atau
production-ready.

---

## 17. Executive Decision Synthesis (Phase 8) — Lapisan Tambahan untuk Direksi

Bagian ini adalah **lapisan tambahan (additive layer)** di atas seluruh
kemampuan skill yang sudah ada (Bagian 1–16). Tidak ada workflow, mode,
trigger, atau output lama yang dihapus atau disederhanakan oleh bagian ini.
Metodologi lengkap: `references/executive-synthesis-guide.md`. Template
output: `assets/executive-management-report-template.md`.

### 17.1 Tujuan

Mengubah hasil analisis (yang sebelumnya berhenti di level framework —
Profit Analysis, Cash Flow Analysis, Risk Analysis) menjadi **Executive
Management Report** yang siap dipakai Direksi mengambil keputusan, tanpa
memerlukan prompt panjang dari pengguna.

### 17.2 Executive Thinking Rules (internal)

Sebelum menyusun output akhir, jawab secara internal (tidak ditampilkan ke
pengguna):

1. Jika saya adalah Direktur, apa yang paling penting saya ketahui?
2. Apa risiko terbesar?
3. Apa yang harus diputuskan minggu ini?
4. Apa yang dapat ditunda?
5. Apa konsekuensi jika tidak dilakukan tindakan?

### 17.3 Business Interpretation Rules

Untuk setiap indikator penting, gunakan pola: apa yang terjadi → mengapa →
dampak terhadap bisnis → implikasi terhadap Direksi → rekomendasi. Detail
dan contoh di `references/executive-synthesis-guide.md`.

### 17.4 Executive Report Template (urutan wajib)

1. Executive Summary (maksimum 10 poin, terbaca < 2 menit)
2. Company Health Assessment (Healthy / Needs Attention / Critical + alasan)
3. Strengths (evidence, dampak positif, alasan)
4. Key Issues (terurut prioritas)
5. Root Cause Analysis (apa → mengapa → dampak → mengapa Direksi peduli)
6. Business Impact (operasional, keuangan, pelanggan, SDM, strategi,
   sustainability)
7. Top Risks (Critical / High / Medium / Low + alasan pengelompokan)
8. Director Recommendations (Short Term dan Long Term)
9. Priority Decisions (minimal tiga, terurut berdasarkan urgensi)
10. Conclusion

Ditutup dengan catatan Confidence dan Sumber (lihat template).

### 17.5 Prioritization Engine

Urutkan Key Issues, Top Risks, dan Priority Decisions berdasarkan financial
impact, business impact, urgency, strategic importance, dan probability.
Jelaskan alasan urutan, bukan hanya angka/skor yang dikarang. Detail di
`references/executive-synthesis-guide.md`.

### 17.6 Kapan dijalankan

Lihat tabel auto-detection di Bagian 6 dan trigger tambahan di Bagian 1.
Ringkasnya: dijalankan otomatis untuk laporan bulanan/berkala perusahaan
yang dianalisis untuk Direksi (termasuk permintaan singkat tanpa menyebut
mode), atau ketika diminta eksplisit ("executive report", "ringkasan untuk
Direksi"). Tidak dipaksakan pada permintaan teknis sempit yang jelas hanya
butuh satu output spesifik.

### 17.7 Backward compatibility

Seluruh mode, trigger, workflow Phase 1–7, dan output lama tetap berfungsi
persis seperti sebelumnya untuk prompt yang tidak memicu Bagian 17. Phase 8
murni menambah kemampuan, tidak mengubah perilaku default mode-mode yang
sudah ada.

### 17.8 Integrity checks Phase 8

- Tidak mengarang angka/fakta baru; Phase 8 hanya menyintesis hasil Phase 1–7.
- Tidak mengklaim rekomendasi sebagai keputusan final atas nama Direksi.
- Tidak mengisi Business Impact pada dimensi tanpa evidence.
- Tidak memberi status Company Health tanpa alasan berbasis evidence.
- Confidence dicantumkan untuk setiap rekomendasi utama.
