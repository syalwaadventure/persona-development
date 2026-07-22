# Testing Guide

Rujukan metodologi testing untuk skill `indonesia-business-modeler`.
Daftar test case aktual ada di `tests/test-cases.md`.

## Jenis Test

1. Trigger test — skill aktif pada permintaan yang sesuai domain.
2. Non-trigger test — skill tidak aktif pada domain lain (persona,
   book-writer, corporate action, permintaan investasi).
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
19. Regression test.

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
