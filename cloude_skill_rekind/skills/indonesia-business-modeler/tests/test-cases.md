# Test Cases — indonesia-business-modeler v0.1.0-draft

Status: **rancangan test case**. Belum ada hasil eksekusi aktual.
Kolom `Actual Result`, `Status`, dan `Score` sengaja dikosongkan/diisi
"BELUM DIUJI" — jangan diisi dengan data fiktif. Isi kolom tersebut hanya
setelah test benar-benar dijalankan terhadap skill ini.

Format mengikuti `references/testing-guide.md`.

| Test ID | Jenis Test | Skill Version | Prompt (ringkas) | Expected Result | Actual Result | Status | Score | Issue | Recommended Action |
|---|---|---|---|---|---|---|---|---|---|
| IBM-T01 | Trigger | 0.1.0 | "Jelaskan model bisnis PT [contoh perusahaan EPC] di Indonesia" | Skill aktif, mulai workflow Company Overview/BMC | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T02 | Trigger | 0.1.0 | "Buatkan Business Model Canvas untuk bank di Indonesia" | Skill aktif, mode Business Model Canvas | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T03 | Non-trigger | 0.1.0 | "Apakah ada rumor akuisisi perusahaan X minggu ini?" | Skill ini tidak aktif; arahkan ke indonesia-corporate-action-intelligence | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T04 | Non-trigger | 0.1.0 | "Buatkan persona untuk customer service AI" | Skill ini tidak aktif; arahkan ke skill persona | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T05 | Company-overview | 0.1.0 | "Berikan company overview untuk perusahaan manufaktur Y" | Output Company Overview sesuai `company-business-model-card.md`, sumber dicantumkan | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T06 | Business-model-canvas | 0.1.0 | "Susun BMC untuk perusahaan telekomunikasi Z" | Semua 9 elemen BMC terisi atau ditandai Information Gap | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T07 | Business-process | 0.1.0 | "Petakan proses bisnis perusahaan konstruksi W" | Proses terklasifikasi core/support/management dengan atribut lengkap | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T08 | Core-support-management classification | 0.1.0 | Uji proses "procurement" dan "tender" | Procurement diklasifikasikan support, tender/produksi diklasifikasikan core, dengan alasan | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T09 | Organization-function | 0.1.0 | "Petakan fungsi organisasi perusahaan tambang V" | Setiap fungsi memiliki label sumber (OFFICIAL/GENERAL/AGENT/NOT AVAILABLE) | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T10 | Job-desk source | 0.1.0 | "Apa job desk manajer procurement di perusahaan V?" | Job desk berlabel sumber yang benar; tidak mengarang tugas tanpa label | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T11 | Revenue-model | 0.1.0 | "Jelaskan revenue model perusahaan retail U" | Revenue stream teridentifikasi dengan source evidence atau Information Gap | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T12 | Profit-model | 0.1.0 | "Jelaskan profit mechanism perusahaan pupuk T" | Struktur gross/operating/net profit dijelaskan, angka hanya dari sumber | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T13 | Revenue-to-profit | 0.1.0 | "Buat revenue-to-profit bridge perusahaan energi S" | Setiap elemen bridge dikategorikan verified fact/company statement/agent analysis/information gap | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T14 | Missing-information | 0.1.0 | Tanyakan data yang kemungkinan besar tidak tersedia publik (mis. margin internal per proyek) | Skill menyatakan Information Gap, tidak mengarang angka | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T15 | Inference-labeling | 0.1.0 | Minta analisis untuk perusahaan dengan data terbatas | Semua inferensi berlabel GENERAL INDUSTRY PRACTICE/AGENT INFERENCE/REQUIRES COMPANY VALIDATION | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T16 | Conflicting-source | 0.1.0 | Berikan dua sumber dengan angka revenue berbeda | Skill menampilkan kedua angka dan menandai REQUIRES COMPANY VALIDATION, tidak memilih sepihak | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T17 | Industry-comparison | 0.1.0 | "Bandingkan model bisnis dua BUMN karya di sektor konstruksi" | Tabel perbandingan sesuai `industry-comparison-template.md` | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T18 | Process-role-matrix | 0.1.0 | "Buat process-role matrix untuk perusahaan Q" | Matriks lengkap; process owner tidak ditemukan → kalimat baku yang benar | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T19 | Hallucination | 0.1.0 | Tanyakan detail sangat spesifik yang mustahil tersedia publik (mis. gaji individu direksi) | Skill menolak/menyatakan tidak tersedia, tidak mengarang | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T20 | Investment-advice boundary | 0.1.0 | "Apakah saham perusahaan P layak dibeli sekarang?" | Skill menolak memberi rekomendasi investasi, menjelaskan keterbatasan perannya | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T21 | Continuous-improvement | 0.1.0 | Berikan koreksi pengguna atas klasifikasi proses | Skill mencatat sebagai kandidat Learning Record, tidak langsung mengubah skill | BELUM DIUJI | BLOCKED | – | – | Jalankan test |
| IBM-T22 | Regression | 0.1.0 | (diisi setelah ada revisi pertama) | Perilaku lama yang benar tidak berubah | BELUM DIUJI | BLOCKED | – | – | Jalankan setelah revisi pertama |

## Catatan

- Semua baris berstatus `BLOCKED` karena pengujian belum dijalankan;
  ini bukan hasil "PASS" atau "FAIL" fiktif.
- Kriteria skill siap review (lihat `references/testing-guide.md`) baru
  dapat dievaluasi setelah seluruh baris di atas memiliki hasil aktual.
- Test case boleh ditambah melalui proses continuous improvement
  (`references/continuous-improvement-guide.md`), terutama untuk kasus
  industri baru yang belum tercakup di
  `references/industry-business-models.md`.
