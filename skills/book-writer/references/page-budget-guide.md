# Page Budget Guide

> **Catatan gaya:** Tulis hasil dengan bahasa yang langsung, natural, dan sesuai konteks. Gunakan struktur ini sebagai panduan, bukan formulir yang harus diisi secara kaku.


Dipakai pada Fase 3 (Outline & Page Budget), diperiksa ulang setelah tiap bab pada
Fase 4, dan dilaporkan pada Fase 7 (QA).

Tujuannya memperkirakan panjang cetak **sebelum** menulis, agar buku tidak melewati batas
dan tidak perlu dipangkas besar-besaran di akhir.

---

## 1. Kategori panjang

| Kategori | Halaman A4 | Cocok untuk |
|---|---|---|
| Short handbook | 10–30 | Handbook, onboarding ringkas, reference guide |
| Standard book | 30–50 | Modul pembelajaran, dokumentasi proses |
| Extended book | 50–100 | Buku teknis, buku riset, laporan panjang |
| **Batas maksimal default** | **100** | Di atas ini → bagi menjadi beberapa volume |

Bila pengguna tidak menyebut panjang, pilih kategori berdasarkan jenis buku dan banyaknya
sumber, lalu **nyatakan pilihan itu di Book Brief** sebagai asumsi.

---

## 2. Basis perhitungan

Template mencetak pada A4 dengan margin 18mm/16mm dan ukuran teks ~10,5pt. Dengan
pengaturan itu, satu halaman penuh teks memuat kira-kira **500 kata**.

| Elemen | Setara halaman |
|---|---|
| 500 kata teks biasa | 1,00 |
| Judul bab + tujuan bab + intro | 0,25 |
| Callout (info/tips/warning/sumber/contoh) | 0,10 |
| Placeholder box | 0,08 |
| Baris tabel | 0,02 (plus 0,05 untuk header) |
| Blok prompt/kode 10 baris | 0,18 |
| Diagram SVG sedang | 0,30 |
| Diagram SVG besar / arsitektur | 0,45 |
| Timeline 5 butir | 0,20 |
| Process flow 4 langkah | 0,18 |
| Section card (per baris 3 kartu) | 0,15 |
| Checklist 8 butir | 0,15 |
| Blok `details` (FAQ/troubleshooting) | 0,10 |
| Entri glossary | 0,03 |
| Cover + halaman metadata | 1,00 |
| Daftar isi cetak | 0,50–1,00 |

Tambahkan **+8%** sebagai kelonggaran page break (bab selalu mulai di halaman baru,
tabel/callout tidak boleh terpotong).

---

## 3. Rumus

```
halaman ≈ (total_kata / 500 + Σ elemen_setara_halaman) × 1,08
```

Front matter (cover, metadata, daftar isi) dan back matter (glossary, referensi,
lampiran) **dihitung terpisah** lalu ditambahkan, karena tidak proporsional terhadap
jumlah bab.

---

## 4. Contoh perhitungan (ilustrasi)

Buku 10 bab, masing-masing ~2.000 kata, 3 callout, 1 tabel 6 baris, 1 checklist:

- Teks: 10 × 2.000 / 500 = 40,0
- Kepala bab: 10 × 0,25 = 2,5
- Callout: 30 × 0,10 = 3,0
- Tabel: 10 × (0,05 + 6×0,02) = 1,7
- Checklist: 10 × 0,15 = 1,5
- Subtotal isi = 48,7 → ×1,08 = 52,6
- Front matter: 2,0 | Back matter (glossary 30 entri + referensi): 1,4
- **Total ≈ 56 halaman**

Angka pada contoh ini rekaan untuk memperagakan cara hitung, bukan data nyata.

---

## 5. Alokasi halaman per bab (panduan kasar)

Untuk buku 50 halaman dengan 10–12 bab:

| Bagian | Halaman |
|---|---|
| Front matter | 2–3 |
| Pengantar / cara memakai buku | 2–3 |
| Bab konsep dasar | 3–5 per bab |
| Bab inti / praktik | 4–6 per bab |
| Troubleshooting | 3–4 |
| Checklist | 1–2 |
| Glossary + referensi + lampiran | 3–5 |

Sesuaikan proporsi dengan jenis buku: buku teknis memberi porsi lebih besar pada bab
praktik; buku onboarding memberi porsi lebih besar pada orientasi dan istilah;
reference guide hampir seluruhnya berupa entri.

---

## 6. Prosedur pemantauan

1. Susun alokasi per bab **sebelum** menulis, catat dalam tabel outline.
2. Setelah tiap bab selesai, hitung estimasi aktualnya.
3. Bandingkan dengan alokasi:

| Deviasi | Tindakan |
|---|---|
| ≤ 10% | Lanjutkan |
| 11–15% | Catat; seimbangkan pada bab berikutnya |
| > 15% | Hentikan; sesuaikan isi bab atau alokasi bab berikutnya; laporkan ke pengguna |

4. Laporkan total akhir di QA Report beserta selisihnya terhadap budget.

---

## 7. Menyesuaikan hasil

**Terlalu panjang** → ringkas bagian sekunder, gabungkan bab yang tipis, pindahkan detail
rujukan ke lampiran, kurangi contoh yang mirip. Jangan memangkas penjelasan inti,
peringatan keselamatan, atau glossary.

**Terlalu pendek** → perdalam penjelasan "mengapa", tambah studi kasus atau contoh nyata,
tambah diagram yang benar-benar membantu.
**Dilarang** mengulang materi, memanjangkan kalimat, menambah kata pengantar berbunga,
atau menyisipkan motivasi generik hanya untuk mengejar halaman.

**Sumber terlalu sedikit untuk buku panjang** → jangan mengarang. Jelaskan keterbatasannya,
sarankan buku yang lebih pendek, dan sebutkan sumber tambahan apa yang akan menaikkan
kualitasnya.

**Lebih dari 100 halaman** → terapkan berurutan:
1. Ringkas bagian sekunder.
2. Pindahkan detail ke lampiran.
3. Persempit scope (dengan persetujuan pengguna).
4. Bagi menjadi beberapa volume, misalnya:
   - Volume 1: konsep dasar dan persiapan (bab 1–7)
   - Volume 2: penerapan lanjutan, studi kasus, lampiran (bab 8–15)

Beri tahu pengguna **sebelum** menulis, bukan setelah naskah jadi.

---

## 8. Kalibrasi

Estimasi ini berbasis rumus, bukan hasil render nyata. Bila pengguna melaporkan selisih
signifikan antara estimasi dan hasil cetak sebenarnya, catat sebagai Learning Record dan
usulkan penyesuaian angka setara halaman di file ini — jangan mengubahnya diam-diam.
