# Continuous Improvement Guide

> **Catatan gaya:** Tulis hasil dengan bahasa yang langsung, natural, dan sesuai konteks. Gunakan struktur ini sebagai panduan, bukan formulir yang harus diisi secara kaku.


Peningkatan skill dilakukan melalui **human-in-the-loop continuous improvement**: pola yang berulang dan tervalidasi diubah menjadi pembaruan taksonomi, source registry, aturan klasifikasi, pola analisis, dan test.

Skill tidak melatih dirinya sendiri. Gunakan istilah: *taxonomy diperbarui, source registry ditambahkan, classification rule diperbaiki, analysis pattern disempurnakan, test coverage diperluas.*

---

## 1. Klasifikasi interaksi

| Kategori | Kapan dipakai |
|---|---|
| **SUCCESSFUL** | Permintaan terpenuhi, tidak ada gap |
| **PARTIALLY SUCCESSFUL** | Sebagian terpenuhi; ada bagian yang lemah |
| **FAILED** | Tidak terpenuhi, atau hasilnya keliru |
| **AMBIGUOUS** | Permintaan tidak jelas dan klarifikasi tidak menyelesaikan |
| **USER CORRECTION** | Pengguna mengoreksi keluaran skill |
| **NEW USE CASE** | Kebutuhan yang belum tercakup mode yang ada |
| **NEW PATTERN** | Pola permintaan atau analisis yang berulang |
| **NEW SOURCE** | Portal, regulator, atau kanal resmi yang belum ada di source guide |
| **NEW CORPORATE-ACTION TYPE** | Jenis aksi yang belum ada di taksonomi |

Dua kategori terakhir paling sering muncul pada skill ini.

Selain SUCCESSFUL, buat **Learning Record** memakai `assets/learning-record-template.md`.

---

## 2. Aturan pengaman khusus domain ini

1. **Satu berita bukan bukti pola.** Transaksi tidak lazim tidak membuktikan perlunya kategori baru di taksonomi.
2. **Koreksi pengguna bukan otomatis fakta.** Pengguna bisa keliru. Periksa sumbernya sebelum menerima koreksi sebagai dasar perubahan.
3. **Pola harus muncul minimal dua kali** sebelum diusulkan menjadi perubahan permanen.
4. **Sumber baru harus diperiksa kredibilitasnya** sebelum masuk registry: siapa penerbitnya, apakah ada atribusi jelas, apakah membedakan berita dan opini.
5. **Perubahan tidak boleh melonggarkan pengaman.** Usulan yang mempermudah menaikkan status, menurunkan syarat verifikasi, atau melunakkan larangan rekomendasi investasi ditolak.

---

## 3. Alur dari temuan ke perubahan

```
Temuan (gap/koreksi/pola)
   ↓
Learning Record — status NEW
   ↓
Periksa sumber & validasi        → status UNDER REVIEW → VERIFIED
   ↓
Periksa konflik dengan aturan lain
   ↓
Ajukan ke pengguna/pembimbing    → APPROVED / REJECTED
   ↓
Terapkan pada file yang relevan  → status IMPLEMENTED
   ↓
Tambahkan regression test
```

Status: **NEW · UNDER REVIEW · VERIFIED · APPROVED · REJECTED · IMPLEMENTED**

Perubahan permanen hanya boleh diterapkan setelah keenam syarat terpenuhi: sumber diperiksa · pembelajaran divalidasi · perubahan disetujui manusia · test case dibuat · changelog diperbarui · versioning dilakukan.

---

## 4. Menentukan file yang diperbarui

| Jenis temuan | File yang kemungkinan terdampak |
|---|---|
| Jenis aksi korporasi baru atau salah klasifikasi | `corporate-action-taxonomy.md` |
| Portal/regulator baru, atau sumber yang tidak lagi kredibel | `source-guide.md` |
| Status sulit ditetapkan atau definisinya ambigu | `event-status-guide.md` |
| Skor terasa tidak konsisten antar kasus | `scoring-guide.md` |
| Deduplikasi keliru, konflik sumber salah ditangani | `verification-and-dedup.md` |
| Dimensi dampak/risiko kurang atau berlebihan | `analysis-guide.md` |
| Jenis tanggal atau agenda baru | `timeline-and-calendar.md` |
| Format laporan kurang berguna | `assets/*.md` |
| Perilaku inti, batas, atau workflow | `SKILL.md` |
| Kegagalan yang tidak boleh terulang | `references/testing-guide.md` + regression test |

**Perbarui hanya file yang relevan.** Jangan menyentuh file lain "sekalian".

---

## 5. Rekomendasi setelah perubahan disetujui

Sertakan seluruhnya:

1. **File yang diperbarui** — daftar, dengan ringkasan perubahan per file.
2. **Semantic version** — MAJOR (tidak kompatibel) / MINOR (kemampuan baru) / PATCH (perbaikan kecil).
3. **Changelog entry.**
4. **Nama branch** — `feat/` `fix/` `test/` `docs/` `refactor/` `chore/`.
5. **Commit message.**
6. **Regression test** yang ditambahkan.

Contoh:

```
File: references/corporate-action-taxonomy.md
Perubahan: menambahkan kategori "tender offer wajib" dengan aturan pembeda
           terhadap akuisisi saham biasa
Versi: v0.1.0 → v0.2.0 (penambahan kemampuan klasifikasi)
Branch: feat/taxonomy-tender-offer
Commit: feat: menambahkan kategori tender offer wajib ke taksonomi
Regression test: CAI-T-006-R — klasifikasi tender offer wajib
Changelog:
  ### Added
  - Kategori "tender offer wajib" pada taksonomi aksi korporasi
```

---

## 6. Kegagalan menjadi regression test

Setiap kesalahan yang ditemukan **wajib** menjadi regression test permanen:

- Salah klasifikasi → test klasifikasi untuk kasus itu.
- Rumor disebut fakta → test kejujuran dengan kasus serupa.
- Angka dikarang → test halusinasi.
- Rekomendasi investasi lolos → test batas kewenangan.

Regression test tidak dihapus tanpa alasan tertulis. Disimpan di `tests/corporate-action/regression/`.

Catatan penting: regression test untuk skill ini harus **menguji perilaku, bukan isi berita**, karena berita berubah. Lihat `testing-guide.md` §5.

---

## 7. Yang tidak boleh dikatakan

Jangan menyatakan bahwa model dilatih ulang, belajar sendiri, atau menjadi lebih pintar dari percakapan. Yang terjadi adalah dokumen skill diperbarui oleh manusia setelah divalidasi.

Rumusan yang benar:

> Pola klasifikasi untuk tender offer wajib telah ditambahkan ke taksonomi setelah divalidasi terhadap dua kasus dan disetujui. Test coverage diperluas dengan satu regression test.
