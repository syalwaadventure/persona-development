# Business Process Framework

Panduan mengklasifikasikan dan mendokumentasikan proses bisnis
perusahaan.

## Klasifikasi Proses

### A. Core Process
Proses yang secara langsung menciptakan nilai dan revenue bagi
perusahaan (mis. produksi, penjualan, pengerjaan proyek, layanan
pelanggan inti).

### B. Support Process
Proses yang mendukung operasi tetapi tidak langsung menghasilkan revenue
(mis. procurement, IT, HR, keuangan internal, legal, maintenance).

### C. Management Process
Proses yang mengarahkan, mengendalikan, dan mengevaluasi perusahaan
(mis. perencanaan strategis, manajemen risiko, tata kelola, budgeting,
performance management).

## Atribut Wajib per Proses

Untuk setiap proses yang diidentifikasi, dokumentasikan:

| Atribut | Penjelasan |
|---|---|
| Tujuan | Hasil yang ingin dicapai proses |
| Trigger | Peristiwa yang memulai proses |
| Input | Data/material/permintaan yang masuk |
| Aktivitas | Langkah-langkah utama |
| Aktor | Fungsi/peran yang menjalankan |
| Output | Hasil proses |
| Customer | Penerima output (internal/eksternal) |
| Supplier | Pemberi input |
| System | Sistem/aplikasi pendukung |
| Control | Mekanisme kendali/kepatuhan |
| KPI | Indikator keberhasilan |
| Risk | Risiko utama pada proses |
| Dependency | Ketergantungan pada proses lain |
| Bottleneck | Titik hambatan (bila teridentifikasi dari sumber) |
| Improvement Opportunity | Peluang perbaikan (tandai sebagai `AGENT INFERENCE` bila bukan dari sumber resmi) |

## Prinsip Penyusunan

- Jangan mengarang proses yang tidak didukung sumber. Jika proses spesifik
  perusahaan tidak ditemukan, gunakan proses generik industri dan beri
  label `GENERAL INDUSTRY PRACTICE`.
- Bottleneck dan improvement opportunity yang berasal dari analisis agent
  (bukan dokumen resmi) wajib diberi label `AGENT INFERENCE`.
- Untuk perusahaan berbasis proyek (mis. EPC, konstruksi), core process
  biasanya mengikuti siklus proyek: tender/bidding → engineering →
  procurement → construction → commissioning → handover/warranty.
- Untuk perusahaan berbasis operasi berkelanjutan (mis. manufaktur,
  perbankan, telekomunikasi), core process mengikuti siklus operasional
  reguler (mis. produksi-distribusi-penjualan, atau
  akuisisi nasabah-layanan-collection).
