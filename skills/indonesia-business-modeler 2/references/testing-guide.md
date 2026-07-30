# Testing Guide

> **Catatan gaya:** Tulis hasil dengan bahasa yang langsung, natural, dan sesuai konteks. Gunakan struktur ini sebagai panduan, bukan formulir yang harus diisi secara kaku.


Rujukan metodologi testing untuk skill `indonesia-business-modeler`.
Daftar test case aktual ada di `tests/test-cases.md`.

## Jenis Test

1. Trigger test — skill aktif pada permintaan yang sesuai domain.
2. Non-trigger test — skill tidak aktif pada domain lain (persona, book-writer, corporate action, maturity assessment, dan rekomendasi investasi saham).
3. Company-overview test.
4. Business-model-canvas test.
5. Business-process test (klasifikasi core/support/management benar).
6. Organization-function test.
7. Job-desk source test (label sumber diterapkan dengan benar).
8. Revenue-model test.
9. Profit-model test.
10. Revenue-to-profit test.
11. Missing-information test (skill jujur menyatakan Information Gap).
12. Inference-labeling test (label `AGENT INFERENCE` dsb. konsisten).
13. Conflicting-source test (perbedaan sumber ditampilkan, tidak
    dipilih sepihak).
14. Industry-comparison test.
15. Process-role-matrix test.
16. Hallucination test (tidak mengarang angka/fakta).
17. Investment-advice boundary test (menolak memberi rekomendasi
    investasi).
18. Continuous-improvement test (Learning Record tersusun benar untuk
    kasus non-SUCCESSFUL).
19. Cash-flow basis and reconciliation test.
20. NPV and IRR calculation test.
21. ROI definition test.
22. ARR denominator/basis test.
23. BEP unit and sales test, including multi-product boundary.
24. Payback and discounted-payback test.
25. Profitability Index formula test.
26. Multiple-IRR and non-conventional cash-flow test.
27. Nominal/real, pre/after-tax, and project/equity consistency test.
28. Scenario and sensitivity test.
29. Regression test.
30. Zero-prompt monthly-report test — pengguna hanya mengetik "Analisis
    laporan bulanan perusahaan menggunakan Business Modeler" (atau setara)
    dengan dokumen terlampir; skill harus menentukan mode sendiri,
    menjalankan Phase 1–7, lalu menghasilkan Executive Management Report
    lengkap (Phase 8) tanpa perlu prompt tambahan.
31. Executive Decision Synthesis structure test — output memuat 10 bagian
    sesuai Bagian 17.4 SKILL.md dan `assets/executive-management-report-template.md`,
    dalam urutan yang benar.
32. Company Health Assessment reasoning test — status (Healthy/Needs
    Attention/Critical) selalu disertai alasan berbasis evidence, tidak
    hanya label.
33. Root-cause-and-prioritization test — Key Issues dan Top Risks memakai
    pola root cause dan diurutkan/dikelompokkan sesuai Prioritization
    Engine, dengan alasan pengurutan yang eksplisit.
34. Backward-compatibility test — prompt lama (mis. "hitung BEP saja",
    "buatkan Business Model Canvas saja") tetap menghasilkan output mode
    tunggal seperti sebelumnya, tanpa dipaksa masuk format 10-bagian
    Executive Management Report.
35. Executive-synthesis hallucination test — Phase 8 tidak menambah angka
    atau fakta baru yang tidak berasal dari Phase 1–7; rekomendasi tidak
    diklaim sebagai keputusan final atas nama Direksi.

## Format Pencatatan Hasil

| Field | Keterangan |
|---|---|
| Test ID | Kode unik |
| Skill version | Versi skill saat diuji |
| Tanggal | Tanggal pengujian |
| Prompt | Input yang diuji |
| Expected result | Hasil yang diharapkan |
| Actual result | Hasil aktual (diisi saat pengujian benar-benar dijalankan) |
| Status | PASS / PARTIAL / FAIL / BLOCKED |
| Score | 1–5 |
| Issue | Masalah yang ditemukan |
| Recommended action | Tindak lanjut |

## Kriteria Skill Siap Review

- Tidak ada kegagalan kritis.
- Tidak mengarang fakta atau sumber.
- Rata-rata skor minimal 4.
- Tidak ada skor di bawah 3.
- Trigger dan non-trigger bekerja dengan benar.
- Regression test lulus.
- Dokumentasi sudah diperbarui.

Catatan: file `tests/test-cases.md` pada paket ini berisi **rancangan
test case**, bukan hasil eksekusi. Hasil aktual (`actual result`,
`status`, `score`) baru diisi setelah pengujian benar-benar dijalankan
terhadap skill ini.


## Natural-language test

Gunakan prompt normal yang sederhana. Hasil dinilai gagal atau perlu revisi jika:

- membuka dengan basa-basi atau mengulang permintaan;
- terasa seperti formulir meski pengguna meminta penjelasan;
- memakai istilah Inggris tanpa alasan atau penjelasan;
- mengulang kesimpulan yang sama;
- memakai kalimat terlalu formal dan pasif secara berturut-turut;
- menampilkan terlalu banyak label, tabel, atau bullet untuk jawaban sederhana;
- tidak menghubungkan fakta dengan maknanya bagi pembaca.

Hasil yang baik harus terdengar seperti penjelasan dari rekan kerja yang paham topik: langsung, natural, dan tetap akurat.

## Executive Decision Synthesis test (Phase 8)

Rujukan metodologi: `references/executive-synthesis-guide.md`. Skenario
minimum yang wajib diuji:

1. **Skenario zero-prompt** — hanya dokumen laporan bulanan + kalimat
   singkat "Analisis laporan bulanan perusahaan menggunakan Business
   Modeler." Skill harus memilih mode sendiri dan langsung menghasilkan
   Executive Management Report lengkap.
2. **Skenario mode eksplisit + minta ringkasan Direksi** — pengguna minta
   mode tertentu (mis. Cash Flow Analysis) lalu menambahkan "buatkan juga
   ringkasan untuk Direksi". Output mode tetap ada, ditambah Phase 8.
3. **Skenario mode teknis sempit tanpa indikasi Direksi** — mis. "hitung BEP
   unit produk ini saja". Phase 8 **tidak** boleh muncul; output tetap
   seperti versi sebelumnya (regression check untuk backward
   compatibility).
4. **Skenario data campuran induk-anak usaha dengan status berbeda** —
   pastikan Company Health Assessment menjelaskan status masing-masing
   entitas sebelum menyimpulkan status gabungan, bukan menyamaratakan.

Hasil dinilai gagal atau perlu revisi jika:

- Executive Summary lebih dari sekitar 10 poin atau tidak bisa dibaca dalam
  waktu wajar (~2 menit);
- Company Health Assessment hanya berupa label tanpa alasan;
- Key Issues/Top Risks tidak menunjukkan urutan atau pengelompokan yang
  jelas beserta alasannya;
- Priority Decisions kurang dari tiga atau tidak terurut berdasarkan
  urgensi;
- ada angka atau fakta di Phase 8 yang tidak berasal dari Phase 1–7;
- rekomendasi ditulis seolah sudah menjadi keputusan final Direksi;
- prompt lama yang seharusnya tidak memicu Phase 8 justru dipaksa masuk
  format 10-bagian.
