# Scoring and Maturity Guide

Panduan ini mengatur cara memberi skor tanpa menciptakan presisi palsu.

## 1. Maturity scale default

| Level | Rentang | Makna |
|---|---:|---|
| Level 1 — Initial | 0–20 | Praktik ad hoc, bergantung individu, standar dan evidence sangat terbatas |
| Level 2 — Developing | 21–40 | Praktik mulai ada tetapi dokumentasi, implementasi, dan pengukuran belum konsisten |
| Level 3 — Defined | 41–60 | Proses dan peran telah didefinisikan; implementasi cukup luas, integrasi dan evaluasi masih berkembang |
| Level 4 — Managed | 61–80 | Proses diterapkan dan diukur secara konsisten; keputusan menggunakan data dan improvement ditindaklanjuti |
| Level 5 — Optimized | 81–100 | Perbaikan berkelanjutan terintegrasi, praktik baik direplikasi, dan hasil konsisten serta berkelanjutan |

Skala dapat diganti bila pengguna menyediakan rubric lain.

## 2. Syarat sebelum scoring

Skor hanya boleh diberikan jika tersedia:

1. scope assessment;
2. framework dan subkriteria;
3. rubric atau anchor penilaian;
4. evidence yang relevan;
5. rationale;
6. confidence level.

Jika salah satu unsur material tidak tersedia, gunakan skor rentang, `N/A`, atau
`Not Assessable`.

## 3. Formula

`Category Score = Σ(Sub-criterion Score × Sub-criterion Weight)`

`Overall Score = Σ(Category Score × Category Weight)`

Bobot ditulis dalam proporsi 0–1 atau persentase yang totalnya 100%.

## 4. Aturan bobot

- Gunakan bobot framework pengguna jika tersedia.
- Jika tidak ada, gunakan bobot setara dan nyatakan sebagai `ASSUMPTION`.
- Jangan membuat bobot khusus BEC, Tracon, atau PIU tanpa sumber atau arahan.
- Jika subkriteria `N/A`, jangan otomatis memberi nol.
- Normalisasi ulang hanya pada subkriteria yang assessable dan tampilkan
  **coverage ratio**.

Contoh:

- 5 subkriteria, 4 dapat dinilai → coverage 80%.
- Category score boleh ditampilkan sebagai preliminary jika subkriteria yang
  tidak dinilai tidak bersifat material.
- Jika area yang tidak dinilai material, tampilkan `N/A` untuk category score.

## 5. Preliminary vs final

### Preliminary Score

Digunakan ketika:

- evidence hanya berupa dokumen terbatas;
- wawancara atau observasi belum dilakukan;
- framework default digunakan;
- sebagian evidence belum diverifikasi;
- terdapat category coverage yang belum penuh.

Format yang disarankan: `60–70 (Preliminary, Medium Confidence)`.

### Final Score

Hanya digunakan ketika framework, rubric, bobot, scope, evidence, dan review
sudah lengkap serta disetujui sesuai proses assessment pengguna. Skill tidak
boleh mengklaim sertifikasi atau audit final.

## 6. Menghindari presisi palsu

- Jangan menulis 72,35 dari evidence kualitatif terbatas.
- Gunakan angka bulat atau rentang.
- Skor tunggal boleh digunakan jika rubric jelas dan evidence cukup.
- Jelaskan alasan perbedaan skor antar-subkriteria.

## 7. Confidence level

| Confidence | Kriteria minimum |
|---|---|
| High Confidence | Evidence cukup, relevan, konsisten, terbaru, dan terverifikasi |
| Medium Confidence | Evidence tersedia dan relevan tetapi belum lengkap atau ada inkonsistensi minor |
| Low Confidence | Evidence terbatas, belum diverifikasi, atau kesimpulan bergantung pada inferensi |
| Not Assessable | Evidence tidak cukup untuk scoring |

Confidence bukan skor maturity. Organisasi dapat memiliki maturity tinggi tetapi
confidence rendah jika evidence yang diberikan terbatas.

## 8. Aturan N/A

Gunakan `N/A` ketika:

- tidak ada evidence;
- evidence tidak terkait periode atau unit yang dinilai;
- evidence hanya menyatakan rencana tanpa implementasi untuk kriteria yang
  menilai penerapan;
- framework tidak memiliki rubric untuk subkriteria tersebut;
- basis antarunit tidak dapat dibandingkan.

Jelaskan:

- apa yang belum tersedia;
- mengapa skor tidak diberikan;
- evidence tambahan yang dibutuhkan;
- dampaknya pada overall score.

## 9. Overall score

Overall score boleh dihitung hanya jika:

- semua kategori material assessable;
- total weight jelas;
- basis scoring konsisten;
- coverage cukup untuk kesimpulan.

Jika tidak, tulis:

> Overall score belum dapat dihitung secara bertanggung jawab. Hasil saat ini
> hanya menunjukkan maturity per kategori yang memiliki evidence.

## 10. Score rationale

Setiap skor/rentang minimal memuat:

- evidence pendukung;
- praktik yang ditemukan;
- gap terhadap rubric;
- status implementasi;
- confidence;
- missing evidence.
