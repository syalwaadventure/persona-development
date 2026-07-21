# Learning Record Template

Dibuat untuk setiap interaksi yang **bukan** SUCCESSFUL. Disimpan di `learning/corporate-action/`.

Learning Record adalah **usulan**, bukan perubahan. Perubahan permanen hanya terjadi setelah divalidasi dan disetujui manusia.

---

## Template

```markdown
# Learning Record — [CAI-L-nnn]

| Field | Isi |
|---|---|
| **Learning ID** | CAI-L-[nomor urut] |
| **Tanggal** | [tanggal] |
| **Kategori** | PARTIALLY SUCCESSFUL / FAILED / AMBIGUOUS / USER CORRECTION / NEW USE CASE / NEW PATTERN / NEW SOURCE / NEW CORPORATE-ACTION TYPE |
| **Skill version** | v[x.y.z] |
| **Status** | NEW |

## 1. Pertanyaan atau kasus
[Prompt pengguna atau situasi yang memicu temuan. Kutip apa adanya.]

## 2. Perilaku saat ini
[Apa yang dilakukan skill. Uraikan faktual, tanpa pembelaan.]

## 3. Perilaku yang diharapkan
[Apa yang seharusnya dilakukan, dan mengapa.]

## 4. Gap
[Selisih antara keduanya, dirumuskan sebagai satu masalah yang jelas.]

## 5. Sumber yang diperlukan untuk validasi
[Dokumen, peraturan, atau sumber resmi yang harus diperiksa sebelum
usulan ini dapat diterima. Untuk USER CORRECTION: sumber apa yang
membuktikan koreksi pengguna benar.]

## 6. Usulan perubahan
[Perubahan konkret. Sebutkan bagian mana dari file mana.]

## 7. File yang terdampak
- [ ] SKILL.md
- [ ] references/source-guide.md
- [ ] references/corporate-action-taxonomy.md
- [ ] references/event-status-guide.md
- [ ] references/scoring-guide.md
- [ ] references/verification-and-dedup.md
- [ ] references/analysis-guide.md
- [ ] references/timeline-and-calendar.md
- [ ] references/continuous-improvement-guide.md
- [ ] references/testing-guide.md
- [ ] assets/[—]

## 8. Risiko perubahan
[Apakah perubahan ini dapat menimbulkan konflik dengan aturan lain?
Apakah melonggarkan pengaman? Apakah mempersempit cakupan?]

## 9. Regression test yang perlu ditambahkan
| Test ID | Jenis | Prompt | Kriteria lulus |
|---|---|---|---|
| CAI-T-[n]-R | [—] | [—] | [—] |

## 10. Frekuensi
[Berapa kali pola ini muncul. Perubahan permanen diusulkan setelah
minimal dua kemunculan.]

## 11. Riwayat status
| Tanggal | Status | Catatan |
|---|---|---|
| [—] | NEW | Dibuat |
```

---

## Alur status

**NEW** → **UNDER REVIEW** → **VERIFIED** → **APPROVED** / **REJECTED** → **IMPLEMENTED**

| Status | Arti | Syarat masuk |
|---|---|---|
| NEW | Baru dicatat | — |
| UNDER REVIEW | Sedang diperiksa | Sumber validasi diidentifikasi |
| VERIFIED | Sumber diperiksa, temuan terbukti | Bukti tersedia |
| APPROVED | Disetujui untuk diterapkan | Persetujuan manusia |
| REJECTED | Tidak diterapkan | Alasan wajib dicatat |
| IMPLEMENTED | Sudah diterapkan | Perubahan file + regression test + changelog |

Learning yang REJECTED **tidak dihapus**. Alasan penolakan berguna agar usulan serupa tidak berulang.

---

## Contoh terisi

```markdown
# Learning Record — CAI-L-001

| Field | Isi |
|---|---|
| Learning ID | CAI-L-001 |
| Tanggal | 20 Juli 2026 |
| Kategori | NEW CORPORATE-ACTION TYPE |
| Skill version | v0.1.0 |
| Status | NEW |

## 1. Pertanyaan atau kasus
"Ini termasuk aksi korporasi apa? Perusahaan wajib menawarkan pembelian
saham publik setelah pengendalinya berganti."

## 2. Perilaku saat ini
Skill mengklasifikasikannya sebagai "perubahan pengendali", tanpa menyebut
kewajiban penawaran kepada pemegang saham publik yang mengikutinya.

## 3. Perilaku yang diharapkan
Mengenali bahwa perubahan pengendali dalam kondisi tertentu memicu kewajiban
tender offer, dan menampilkannya sebagai kategori terkait dengan jadwal serta
tenggatnya sendiri.

## 4. Gap
Taksonomi belum memuat tender offer wajib sebagai kategori atau sebagai
konsekuensi otomatis dari perubahan pengendali.

## 5. Sumber yang diperlukan untuk validasi
Peraturan OJK tentang pengambilalihan perusahaan terbuka; contoh keterbukaan
informasi tender offer wajib dari dua emiten berbeda.

## 6. Usulan perubahan
Tambahkan "tender offer wajib" pada rumpun Transaksi Kepemilikan di
corporate-action-taxonomy.md, beserta aturan pembeda terhadap akuisisi saham
biasa, dan catatan bahwa perubahan pengendali dapat memicunya.

## 7. File yang terdampak
- [x] references/corporate-action-taxonomy.md
- [x] references/timeline-and-calendar.md (jenis agenda: batas waktu penawaran)

## 8. Risiko perubahan
Rendah. Menambah kategori tidak melonggarkan pengaman mana pun. Perlu dijaga
agar tidak setiap perubahan pengendali otomatis dilabeli tender offer —
kewajiban itu bergantung pada kondisi tertentu.

## 9. Regression test
| Test ID | Jenis | Prompt | Kriteria lulus |
|---|---|---|---|
| CAI-T-006-R | Classification | Kasus perubahan pengendali disertai penawaran ke publik | Menyebut kategori utama dan kategori terkait; tidak menyamakan dengan akuisisi saham biasa |

## 10. Frekuensi
1 kali. Menunggu kemunculan kedua sebelum diusulkan sebagai perubahan permanen.

## 11. Riwayat status
| Tanggal | Status | Catatan |
|---|---|---|
| 20 Jul 2026 | NEW | Dibuat |
```

*Contoh di atas bersifat ilustratif untuk menunjukkan format.*

---

## Aturan

1. **Satu Learning Record satu masalah.** Jangan menggabungkan beberapa temuan.
2. **Koreksi pengguna bukan otomatis fakta.** Field 5 wajib diisi sebelum status naik ke VERIFIED.
3. **Frekuensi minimal dua** sebelum perubahan permanen diusulkan, kecuali temuan menyangkut keamanan atau kesalahan faktual yang jelas.
4. **Usulan yang melonggarkan pengaman ditolak** — misalnya mempermudah menaikkan status, menurunkan syarat verifikasi, atau melunakkan larangan rekomendasi investasi.
5. **Setelah IMPLEMENTED**, sertakan: file yang diperbarui, semantic version, changelog entry, nama branch, commit message, dan regression test.
