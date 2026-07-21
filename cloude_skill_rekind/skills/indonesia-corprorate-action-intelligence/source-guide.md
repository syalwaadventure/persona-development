# Source Guide

Gabungan aturan prioritas sumber dan daftar sumber. Dipakai pada Fase 2 (pencarian) dan Fase 4 (verifikasi).

---

## 1. Tiga tier sumber

### Tier 1 — Sumber resmi
**Fungsi: memastikan fakta material.** Satu-satunya dasar untuk menyatakan sesuatu resmi.

| Sumber | Dipakai untuk |
|---|---|
| Bursa Efek Indonesia (IDX) | Keterbukaan informasi, pengumuman bursa, jadwal aksi korporasi, suspensi |
| Otoritas Jasa Keuangan (OJK) | Persetujuan, pernyataan efektif, sanksi, peraturan |
| Keterbukaan informasi emiten | Dasar paling kuat untuk transaksi material |
| Website resmi perusahaan | Siaran pers, pengumuman korporasi |
| Halaman investor relations | Presentasi, materi RUPS, laporan |
| Laporan tahunan & laporan keuangan | Nilai, struktur kepemilikan, kewajiban |
| Pengumuman RUPS | Agenda, hasil, persetujuan pemegang saham |
| Siaran pers resmi | Pernyataan perusahaan yang dapat dikutip |
| Regulator & kementerian terkait | Persetujuan sektoral (KPPU, Kementerian BUMN, ESDM, Kominfo, dll.) |

### Tier 2 — Media bisnis dan keuangan kredibel
**Fungsi: menemukan isu dan memperoleh konteks.** Tidak pernah menjadi dasar status resmi.

Kontan · CNBC Indonesia · Kompas Money/Finance · Bloomberg · Reuters · Bisnis Indonesia · Katadata · media bisnis nasional kredibel lain.

Catatan akses: Bloomberg, Reuters, dan sebagian Bisnis Indonesia sering berbayar. Bila tidak dapat diakses, terapkan aturan §5.

### Tier 3 — Sumber pendukung
**Fungsi: konteks industri, latar belakang, pembanding.**

Media industri · asosiasi · wawancara · laporan riset · publikasi sektor · sumber lain yang relevan dan dapat dipertanggungjawabkan.

---

## 2. Sepuluh aturan sumber

1. Media dipakai untuk **menemukan** isu dan memperoleh konteks.
2. Sumber resmi dipakai untuk **memverifikasi** fakta material.
3. **Berita media bukan keputusan resmi**, betapapun banyak portal yang memberitakannya.
4. **Rumor tidak pernah disebut sebagai fakta.**
5. Jangan menyalin artikel secara penuh. Parafrase; kutipan sangat terbatas dengan atribusi.
6. Jangan melewati paywall, login, atau pembatasan akses.
7. Bila halaman tidak dapat diakses, **katakan dengan jujur**.
8. Cantumkan nama sumber dan tanggal publikasi untuk setiap fakta.
9. Cantumkan tanggal pencarian pada setiap laporan.
10. Prioritaskan sumber terbaru, tetapi tetap periksa perkembangan sebelumnya agar timeline utuh.

---

## 3. Strategi pencarian

### Urutan baku
```
Media (Tier 2) → temukan isu
      ↓
Sumber resmi (Tier 1) → verifikasi fakta material
      ↓
Pendukung (Tier 3) → konteks industri
```

Untuk event yang sudah diketahui pengguna, **balik urutannya**: periksa keterbukaan informasi dan siaran pers lebih dulu, baru media untuk konteks dan reaksi.

### Menyusun kueri
- Pendek dan spesifik, 3–6 kata. Mulai luas, lalu persempit.
- Sertakan **tahun berjalan** untuk perkembangan terkini. Kueri tanpa tahun sering mengembalikan berita lama.
- Setiap kueri harus berbeda bermakna dari kueri sebelumnya. Mengulang frasa yang sama tidak mengubah hasil.
- Untuk verifikasi, gunakan nama entitas lengkap + kata kunci resmi ("keterbukaan informasi", "siaran pers", "RUPS", "prospektus").
- Untuk deep dive, cari per jenis aksi secara terpisah — kueri gabungan menghasilkan hasil dangkal untuk semuanya.

### Berapa banyak pencarian
| Mode | Perkiraan |
|---|---|
| Event Verification | 3–6 |
| Daily Brief | 6–12 |
| Company Deep Dive | 8–15 |
| Sector Watch | 10–20 |
| Weekly Digest | 12–25 |

Di atas ±30, sarankan fitur Research atau pembagian permintaan.

---

## 4. Mencatat sumber

Untuk setiap temuan, catat: judul · tanggal publikasi · perusahaan · ticker · pihak terkait · jenis aksi · nilai transaksi · jadwal · status · nama sumber.

Format pencantuman di laporan:

```
Kontan, 12 Juni 2026 — rencana akuisisi diumumkan
Keterbukaan informasi IDX, 18 Juni 2026 — nilai transaksi dikonfirmasi
```

Di bagian SOURCES, pisahkan tiga kelompok: **official sources**, **news sources**, **supporting sources**.

---

## 5. Sumber tidak dapat diakses

Penyebab lazim: paywall, dinding login, halaman dihapus, pemblokiran, pembatasan robots, masalah koneksi.

Langkah:
1. **Jangan mengarang isinya.** Jangan menyimpulkan isi dari judul atau cuplikan pencarian.
2. Nyatakan sumber mana yang tidak dapat diakses.
3. Cari sumber alternatif yang memberitakan hal yang sama.
4. **Turunkan confidence score**, dan sebutkan bahwa penurunannya karena keterbatasan akses.
5. Catat keterbatasan itu di bagian Verification.

Kalimat pola:

> Artikel Bloomberg 14 Juni 2026 tidak dapat diakses karena berbayar. Informasi di bawah berasal dari Kontan dan CNBC Indonesia yang memberitakan hal serupa. Confidence diturunkan ke 2 karena konfirmasi resmi belum ditemukan.

---

## 6. Hak cipta

1. **Jangan menyalin artikel secara penuh** atau sebagian besar.
2. Parafrase dengan kata sendiri, sebutkan sumbernya.
3. Kutipan langsung hanya bila kata persisnya penting (misalnya pernyataan resmi direksi), sangat pendek, diberi tanda kutip dan atribusi.
4. Jangan menyusun ringkasan yang begitu rinci sehingga menggantikan artikel aslinya.
5. Untuk artikel berbayar, jangan menyalin isinya dari sumber sekunder yang mengutipnya penuh.

---

## 7. Sumber yang tidak dipakai

- Media sosial dan forum tanpa konfirmasi — boleh menjadi petunjuk awal, tidak boleh menjadi sumber fakta.
- Blog anonim, situs agregator tanpa atribusi.
- Situs yang menyalin berita tanpa menyebut sumber asli — telusuri ke sumber aslinya.
- Grup pesan, "bocoran", atau informasi non-publik.

Bila sebuah klaim hanya ditemukan di sumber semacam ini, statusnya **RUMOR** dengan confidence 1, dan itu harus dinyatakan.
