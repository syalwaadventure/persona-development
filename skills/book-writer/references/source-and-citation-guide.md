# Source and Citation Guide

> **Catatan gaya:** Tulis hasil dengan bahasa yang langsung, natural, dan sesuai konteks. Gunakan struktur ini sebagai panduan, bukan formulir yang harus diisi secara kaku.


Dipakai pada Fase 2 (Source Audit) dan Fase 4 (Drafting).

---

## 1. Klasifikasi sumber

Setiap sumber yang diberikan pengguna diklasifikasikan ke salah satu dari tujuh kategori.

| Kategori | Ciri | Boleh dipakai sebagai |
|---|---|---|
| **Primary** | Dokumen asli yang menjadi subjek buku: SOP, kontrak, data mentah, hasil pengukuran, notulen | Dasar fakta utama |
| **Official** | Dokumen resmi yang mengikat: kebijakan, pedoman, peraturan, standar terbit | Dasar pernyataan kebijakan |
| **Supporting** | Materi pendukung: presentasi internal, catatan pelatihan, email penjelasan | Konteks dan contoh, bukan dasar kebijakan |
| **General reference** | Pengetahuan umum, buku teks, praktik industri | Penjelasan umum — **wajib ditandai** |
| **Outdated** | Versi lama yang sudah digantikan | Konteks historis saja; sebutkan bahwa sudah tidak berlaku |
| **Conflicting** | Bertentangan dengan sumber lain | Ditampilkan bersama pembandingnya, tidak dipilih sendiri |
| **Incomplete** | Terpotong, sebagian hilang, atau tidak terbaca | Ditandai; bagian yang hilang menjadi placeholder |

**Aturan pokok:** *general reference* tidak boleh naik pangkat menjadi *official*. Praktik umum industri bukan kebijakan organisasi pengguna.

---

## 2. Source map per bab

Disusun pada Fase 2, dipakai sepanjang Fase 4.

| Bab | Sumber utama | Kategori | Bagian yang dipakai | Gap |
|---|---|---|---|---|
| 1 | [dokumen] | official | [bab/halaman] | — |
| 2 | [dokumen] | supporting | [bagian] | Angka target belum ada |
| 3 | — | general reference | — | Semua bab perlu validasi |

Kolom **Gap** menjadi daftar placeholder yang akan muncul di buku. Laporkan daftar ini kepada pengguna sebelum menulis, bukan setelah buku jadi.

---

## 3. Lima kategori isi dan penandanya

Setiap paragraf dalam buku termasuk salah satu kategori berikut. Kategori yang tidak jelas adalah sumber utama kesalahan pembaca.

| Kategori | Penanda HTML | Penanda Markdown |
|---|---|---|
| Fakta terverifikasi | `.box.source` | `> **Sumber:** [dokumen, bagian]` |
| Penjelasan umum | teks biasa / `.box` | `> **Penjelasan umum:** ...` |
| Contoh ilustratif | `.box.example` berlabel "(Ilustrasi)" | `> **Contoh (Ilustrasi):** ...` |
| Interpretasi / rekomendasi | `.box` "Catatan penyusun" | `> **Catatan penyusun:** ...` |
| Belum tersedia | `.box.placeholder` | `> **[Informasi diperlukan — verifikasi kepada pemilik dokumen]**` |

---

## 4. Cara mencantumkan sumber

1. Sumber diletakkan **dekat klaimnya**, di akhir subbagian yang relevan — bukan hanya di daftar pustaka.
2. Format minimum: nama dokumen + bagian/halaman + tanggal atau versi bila ada.
3. Bila satu bab bersandar pada satu dokumen, cukup satu panel sumber di awal bab, lalu sebut ulang hanya untuk klaim spesifik (angka, tanggal, nama).
4. Bagian **Sumber** di akhir buku memuat daftar lengkap semua dokumen beserta kategorinya.
5. Untuk sumber web: judul + penerbit + tanggal akses. Jangan menyalin isinya secara penuh.

**Contoh panel sumber:**

> **Sumber:** Pedoman Pengadaan Barang dan Jasa, Bab IV bagian 4.2, versi 3 (2024).

---

## 5. Menangani sumber yang bertentangan

Langkah wajib:

1. **Tampilkan keduanya.** Sebut isi masing-masing beserta dokumen dan tanggalnya.
2. **Jelaskan konfliknya** dalam satu-dua kalimat: apa persisnya yang berbeda.
3. **Jangan memilih sendiri** mana yang benar, meskipun salah satu tampak lebih baru atau lebih resmi.
4. **Sarankan verifikasi** kepada pemilik dokumen.
5. Tandai bagian itu dengan `.box.warn`.

**Pola kalimat:**

> **Perlu verifikasi.** Dokumen A (versi 2023) menyebut batas waktu 14 hari kerja, sedangkan Dokumen B (versi 2024) menyebut 10 hari kerja. Kedua dokumen masih beredar dan tidak ada keterangan pencabutan. Silakan konfirmasi ke pemilik dokumen sebelum angka ini dipakai.

Kekeliruan yang harus dihindari: memilih angka yang lebih baru "karena logikanya begitu", menggabungkan keduanya menjadi rentang, atau menyembunyikan konflik.

---

## 6. Aturan placeholder

Format baku:

```
[Informasi diperlukan — verifikasi kepada pemilik dokumen]
```

Diperjelas dengan konteks:

```
[Informasi diperlukan — nama unit pemilik proses; verifikasi kepada pemilik dokumen]
```

Aturan:
- Placeholder **lebih baik daripada tebakan yang masuk akal**. Tebakan yang masuk akal adalah bentuk kesalahan yang paling sulit dideteksi pembaca.
- Jangan mengisi placeholder dengan contoh yang tampak nyata (nama orang, nomor dokumen, angka).
- Kumpulkan semua placeholder ke dalam satu lampiran "Daftar Informasi yang Perlu Dilengkapi" agar mudah ditindaklanjuti.
- Laporkan jumlah placeholder di QA Report.

---

## 7. Hak cipta dan kerahasiaan

1. Jangan menyalin artikel, bab buku, atau materi berhak cipta secara penuh. Parafrase dengan atribusi.
2. Kutipan langsung dibatasi seperlunya, diberi tanda kutip dan sumber.
3. Jangan menyalin isi artikel berbayar.
4. Jangan memuat data pribadi (nama pegawai, nomor identitas, kontak pribadi), credential, atau tautan internal sensitif.
5. Bila sumber pengguna tampak rahasia atau internal: tanyakan status kerahasiaannya, dan tawarkan label kerahasiaan pada cover.
6. Bila ditemukan indikasi data sensitif: **hentikan proses**, tandai bagiannya, jelaskan risikonya, sarankan sanitasi, minta validasi pemilik data.

---

## 8. Buku tanpa sumber

Bila pengguna tidak memberi dokumen apa pun:

1. Nyatakan sejak awal bahwa buku akan disusun dari pengetahuan umum.
2. Semua isi ditandai sebagai **penjelasan umum**, bukan kebijakan.
3. Setiap hal yang spesifik pada organisasi pengguna (angka, nama unit, alur internal, tenggat) menjadi **placeholder**.
4. Tambahkan catatan keterbatasan di bagian depan buku.
5. Sarankan dokumen apa yang sebaiknya disediakan agar buku menjadi akurat.

Jangan menolak permintaan hanya karena tidak ada sumber — tetapi jangan pula menyajikan pengetahuan umum seolah-olah hasil pemeriksaan dokumen.

---

## Source Traceability Matrix — v1.0 addition

For books with material factual claims, use
`assets/source-traceability-template.md` in addition to a bibliography.

A bibliography answers “what sources were consulted”; a traceability matrix
answers “which source supports which claim, table, or figure.”

Minimum fields:

- chapter/section;
- claim/table/figure;
- source;
- source type;
- status;
- transformation or interpretation;
- limitation.

Tables calculated from source data must explain the transformation. Figures and
images must include origin, permission/license status where relevant, and alt
text. Internal documents should be cited minimally without exposing unnecessary
confidential content.
