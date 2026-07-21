# Revision Guide

Prosedur untuk mode Revise, Expand, Condense, dan Audit. Prinsip utama: **ubah sekecil mungkin, laporkan sejelas mungkin.**

---

## 1. Aturan yang berlaku di semua mode revisi

1. **Jangan menulis ulang buku** ketika hanya sebagian diminta berubah.
2. **Pertahankan ID heading** (`id="bab-3"`). ID yang berubah merusak tautan sidebar, bookmark pembaca, dan rujukan silang antar bab.
3. **Pertahankan gaya, istilah, dan pola penomoran** yang sudah dipakai. Revisi yang gayanya berbeda dari bab lain akan terlihat.
4. Perbarui hal-hal turunan: daftar isi, penomoran, tautan anchor, glossary, daftar sumber, estimasi halaman di cover.
5. Jalankan ulang quality review **pada bagian terdampak saja**, kecuali perubahan menyentuh struktur seluruh buku.
6. Selalu serahkan **change log**.

---

## 2. Mode Revise — mengubah isi yang ada

Untuk perbaikan fakta, penyesuaian gaya, penajaman penjelasan, atau koreksi kesalahan.

**Langkah:**
1. Identifikasi bab dan subbagian yang terdampak.
2. Periksa apakah perubahan berdampak ke bab lain (istilah, angka, rujukan silang). Bila ya, sebutkan — jangan diam-diam mengubah bab lain.
3. Ubah hanya bagian tersebut.
4. Bila menyangkut fakta, periksa terhadap source map. Fakta baru tanpa sumber menjadi placeholder, bukan tulisan baru.
5. Hitung ulang halaman bab tersebut; perbarui total.
6. Susun change log.

**Sering terlewat:** istilah yang diubah di satu bab tetapi masih dipakai versi lama di bab lain, dan glossary yang tidak ikut diperbarui.

---

## 3. Mode Expand — menambah isi

Untuk menambah bab, subbab, contoh, atau memperdalam pembahasan.

**Langkah:**
1. Tentukan letak penambahan dalam struktur yang ada.
2. **Periksa page budget lebih dulu.** Bila penambahan membuat total melewati batas yang disepakati, laporkan sebelum menulis, dan tawarkan: menambah batas, memadatkan bagian lain, atau memindahkan detail ke lampiran.
3. Periksa tumpang tindih dengan bab yang sudah ada. Materi yang sudah dibahas cukup jangan dibahas ulang di bab baru.
4. Tulis bagian baru dengan `assets/chapter-template.md`, mengikuti gaya dan tingkat kedalaman yang sudah berjalan.
5. Sisipkan ke urutan yang benar; perbarui penomoran bab **berikutnya** dan seluruh tautan.
6. Bila bab baru disisipkan di tengah, ID bab sesudahnya ikut bergeser — laporkan ini karena berdampak pada tautan lama.

**Alternatif yang lebih aman:** beri ID baru yang tidak bergeser (`id="bab-3a"`) bila pengguna sudah menyebarkan tautan ke versi sebelumnya.

---

## 4. Mode Condense — memadatkan

Untuk buku yang terlalu panjang atau terasa bertele-tele.

**Urutan pemadatan** (tempuh berurutan, hentikan begitu target tercapai):

1. **Hapus pengulangan.** Ini hampir selalu menyumbang paling banyak dan tidak menghilangkan informasi.
2. **Rapatkan kalimat.** Buang basa-basi pembuka, kalimat transisi berlebihan, dan penegasan ganda.
3. **Ubah prosa menjadi tabel atau daftar** untuk bagian yang berupa enumerasi.
4. **Pindahkan detail ke lampiran.** Prosedur rinci, tabel panjang, dan rujukan teknis cocok di lampiran.
5. **Gabungkan bab** yang isinya tipis dan bertema dekat.
6. **Persempit scope** — hanya dengan persetujuan pengguna.

**Yang tidak boleh dipadatkan:** peringatan keselamatan, batasan, penanda sumber, placeholder, dan definisi istilah. Memadatkan ini menghemat halaman tetapi merusak kegunaan buku.

Laporkan berapa halaman yang dihemat di setiap langkah.

---

## 5. Mode Audit — menilai tanpa mengubah

Untuk memeriksa buku yang sudah ada.

**Langkah:**
1. Petakan isi ke struktur jenis bukunya (`references/book-types.md`). Tandai bagian yang hilang.
2. Nilai per aspek dengan skor 1–5.
3. Susun daftar temuan berprioritas.
4. **Jangan mengubah apa pun** kecuali diminta.

**Aspek yang dinilai:**

| Aspek | Yang diperiksa |
|---|---|
| Struktur | Kelengkapan, urutan, kesesuaian jenis buku |
| Akurasi & sumber | Penanda sumber, placeholder, konflik, indikasi karangan |
| Kejelasan | Kalimat, istilah, contoh, kedalaman |
| Kepadatan | Keseimbangan teks dan elemen pendukung |
| Konsistensi | Istilah, heading, penomoran, gaya |
| Teknis HTML | Tautan, hierarki heading, aset eksternal, fitur |
| Cetak | Page break, tabel terpotong, jumlah halaman |
| Aksesibilitas | Kontras, label, navigasi keyboard |

**Skor:** 5 sangat baik; 4 baik dengan kekurangan kecil; 3 cukup, perlu revisi; 2 banyak masalah; 1 gagal atau berisiko.

**Prioritas temuan:** Kritis (fakta salah, data sensitif, klaim tanpa sumber) / Penting (struktur, kejelasan, konsistensi) / Opsional (gaya, estetika).

Audit bukan persetujuan. Kelayakan terbit diputuskan pemilik dokumen.

---

## 6. Mode Publication — merakit ulang keluaran

Dipakai setelah revisi selesai atau ketika pengguna meminta format akhir.

1. Rakit naskah ke `assets/dark-book-template.html`.
2. Perbarui metadata cover: versi, status, tanggal, estimasi halaman.
3. Periksa seluruh tautan sidebar menuju `id` yang ada.
4. Jalankan QA (Fase 7) dan serahkan QA Report.

---

## 7. Format change log

Wajib disertakan pada setiap penyerahan hasil revisi.

```markdown
## Change Log — [Judul Buku] v[lama] → v[baru]
Tanggal: [—] | Mode: [Revise/Expand/Condense]

| Bagian | Perubahan | Alasan | Dampak halaman |
|---|---|---|---|
| Bab 3.2 | Angka tenggat diganti placeholder | Tidak ada di source map | −0,1 |
| Bab 6 (baru) | Bab ditambahkan | Permintaan pengguna | +4,5 |
| Glossary | 3 istilah baru | Mengikuti Bab 6 | +0,1 |

**Total halaman:** [lama] → [baru] (budget: [target])
**Bagian yang tidak diubah:** [daftar bab]
**ID heading yang bergeser:** [daftar, atau: tidak ada]
**Perlu diperiksa pengguna:** [daftar]
**Rekomendasi versi:** v[x.y.z] — [alasan]
```

---

## 8. Penomoran versi buku

Versi **buku** terpisah dari versi **skill**.

| Perubahan | Kenaikan |
|---|---|
| Penambahan atau penghapusan bab, perubahan struktur | MINOR (0.2.0 → 0.3.0) |
| Perbaikan isi, koreksi fakta, penyuntingan | PATCH (0.2.0 → 0.2.1) |
| Perubahan scope atau audiens buku | MAJOR (0.2.0 → 1.0.0) |
| Buku dinyatakan final oleh pemilik dokumen | 1.0.0 |

Status buku: **draft** → **review** → **final**. Skill tidak menetapkan status final sendiri; itu keputusan pemilik dokumen.
