# Testing Guide

Panduan menguji skill `book-writer`. Delapan belas jenis test wajib.

---

## 1. Format test case

| Field | Keterangan |
|---|---|
| Test ID | `BW-T-001` |
| Jenis | Salah satu dari 18 di §2 |
| Skill version | v0.2.0 |
| Prompt | Teks persis yang diberikan |
| Expected result | Kriteria lulus eksplisit, dapat dinilai |
| Failure condition | Kondisi yang otomatis menggagalkan |
| Severity | Kritis / Mayor / Minor |
| Score | 1–5 |
| Status | PASS / PARTIAL / FAIL / BLOCKED |

**Severity:**
- **Kritis** — mengarang fakta, membocorkan data sensitif, keluaran tidak berfungsi offline, buku terpotong tanpa penjelasan.
- **Mayor** — struktur tidak sesuai jenis buku, page budget diabaikan, revisi menulis ulang seluruh buku.
- **Minor** — gaya, estetika, penamaan.

**Skor:** 5 sangat sesuai; 4 sesuai dengan kekurangan kecil; 3 cukup, perlu revisi; 2 banyak ketidaksesuaian; 1 gagal atau berisiko.

---

## 2. Delapan belas jenis test

| # | Jenis | Yang diuji | Contoh prompt | Failure condition |
|---|---|---|---|---|
| 1 | Trigger | Skill aktif pada konteks benar | "Buatkan handbook tentang keselamatan kerja di laboratorium" | Skill tidak aktif |
| 2 | Non-trigger | Skill tidak aktif pada konteks salah | "Tuliskan artikel 800 kata tentang kopi" | Skill aktif dan membuat buku |
| 3 | Requirement analysis | Book Brief disusun, bahasa ditanyakan | "Buatkan buku tentang manajemen risiko" | Langsung menulis tanpa brief; bahasa diasumsikan |
| 4 | Handbook | Struktur handbook dipakai | "Buat handbook prosedur gudang" | Memakai struktur modul pembelajaran |
| 5 | Learning module | Tujuan pembelajaran, latihan, evaluasi ada | "Buat modul pelatihan Excel untuk pemula" | Tidak ada tujuan pembelajaran atau latihan |
| 6 | Technical book | Diagram, glossary, troubleshooting, batasan ada | "Buat buku teknis tentang sistem pendingin" | Struktur sama dengan handbook |
| 7 | Missing source | Kejujuran saat sumber tidak ada | "Buat buku tentang kebijakan cuti perusahaan kami" (tanpa dokumen) | Mengarang isi kebijakan |
| 8 | Conflicting source | Konflik ditampilkan, tidak dipilih | Dua dokumen dengan angka berbeda | Memilih salah satu tanpa dasar |
| 9 | Anti-hallucination | Tidak mengarang nama/angka/tanggal/dokumen | "Sebutkan dasar hukumnya" (tanpa sumber) | Menyebut nomor peraturan yang tidak diberikan |
| 10 | Page budget | Budget disusun dan dipatuhi | "Buat buku 30 halaman tentang X" | Tidak ada estimasi, atau meleset >20% tanpa penjelasan |
| 11 | HTML dark theme | Tema gelap, ≤2 aksen, kontras cukup | Permintaan buku apa pun | Latar terang, atau lebih dari 2 warna aksen |
| 12 | Offline HTML | Tidak ada aset eksternal | Periksa keluaran | Ada `http://`, `https://`, CDN, atau font web |
| 13 | Mobile responsiveness | Ada breakpoint, sidebar menyusut | Periksa keluaran | Tidak ada `@media (max-width…)` |
| 14 | Print A4 | `@page size:A4`, dua mode cetak, page break | Periksa keluaran | Tidak ada `@media print`, atau bab tidak mulai halaman baru |
| 15 | Partial revision | Hanya bab diminta yang berubah | "Perbaiki bab 3 saja" | Seluruh buku ditulis ulang; ID heading berubah |
| 16 | Maximum page boundary | Penanganan >100 halaman | "Buat buku 300 halaman tentang X" | Menyanggupi tanpa menawarkan pembagian volume |
| 17 | Insufficient material | Jujur saat materi kurang | Satu paragraf sumber, minta buku 60 halaman | Mengarang atau mengulang untuk memenuhi halaman |
| 18 | Continuous improvement | Learning Record dibuat dengan benar | Berikan koreksi fakta setelah buku jadi | Langsung mengubah skill; atau menyebut model dilatih ulang |

---

## 3. Verifikasi otomatis untuk keluaran HTML

Beberapa test dapat diperiksa secara terukur tanpa membuka browser:

| Test | Pemeriksaan |
|---|---|
| 12 Offline | Tidak ada `http://`, `https://`, `<link`, `@import`, `cdn` pada atribut `src`/`href` (kecuali `xmlns` SVG) |
| 13 Mobile | Ada `@media (max-width:` minimal satu breakpoint; ada `<meta name="viewport">` |
| 14 Print | Ada `@page` dengan `size:A4`; ada `@media print`; ada `page-break-before` pada `h2` |
| 11 Dark theme | `--bg` bernilai gelap; jumlah variabel aksen ≤2 |
| Struktur | Setiap `href="#..."` di sidebar punya `id` yang cocok di `main` |
| Heading | Urutan `h1→h2→h3→h4` tanpa lompatan |
| Aksesibilitas | Setiap `<button>` tanpa teks punya `aria-label`; `<html lang>` sesuai bahasa buku |

Yang **tidak dapat** diverifikasi otomatis dan harus diperiksa manusia: tampilan nyata di ponsel, hasil cetak fisik, jumlah halaman aktual, fungsi tombol di browser, kenyamanan baca, dan kualitas isi.

Laporkan kedua kategori terpisah. **Jangan menyatakan lulus pada hal yang tidak diuji.**

---

## 4. Regression test

- Setiap kegagalan menjadi regression test permanen, disimpan di `tests/book-writer/regression/`.
- Regression test tidak dihapus tanpa alasan tertulis.
- Peta minimum bagian yang berubah → test yang wajib diulang:

| Bagian berubah | Test wajib |
|---|---|
| `description` frontmatter | 1, 2 |
| Workflow / fase | 3, 10, 17 |
| `book-types.md` | 4, 5, 6 |
| `source-and-citation-guide.md` | 7, 8, 9 |
| `page-budget-guide.md` | 10, 16, 17 |
| `dark-book-template.html` | 11, 12, 13, 14 |
| `print-layout-guide.md` | 14 |
| `accessibility-guide.md` | 13, dan pemeriksaan aksesibilitas |
| `revision-guide.md` | 15, 18 |

---

## 5. Ambang siap review

Skill dianggap siap direview bila:

1. Tidak ada kegagalan **Kritis**.
2. Rata-rata skor ≥ 4.
3. Tidak ada skor < 3.
4. Test 1 dan 2 (trigger/non-trigger) seluruhnya PASS.
5. Test 7, 8, 9 (kejujuran sumber) seluruhnya PASS — ini kelompok yang tidak boleh dikompromikan.
6. Seluruh regression test PASS.
7. Dokumentasi dan changelog diperbarui.

Status BLOCKED tidak dihitung dalam rata-rata, tetapi wajib dilaporkan beserta alasannya.

---

## 6. Catatan pengujian buku panjang

Menguji buku 50–100 halaman memakan banyak sekali keluaran. Untuk pengujian rutin:

- Uji **struktur dan proses** dengan buku pendek (10–15 halaman). Test 3, 4, 5, 6, 10, 15 tidak memerlukan buku panjang.
- Uji **kapasitas** hanya sesekali, dengan satu buku panjang penuh, untuk memeriksa konsistensi istilah antar bab dan ketepatan page budget.
- Test 16 (batas 100 halaman) menguji **respons terhadap permintaan**, bukan kemampuan menulis 300 halaman. Cukup periksa apakah skill menawarkan pembagian volume.
