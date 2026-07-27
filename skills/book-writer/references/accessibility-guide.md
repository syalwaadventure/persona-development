# Accessibility Guide

> **Catatan gaya:** Tulis hasil dengan bahasa yang langsung, natural, dan sesuai konteks. Gunakan struktur ini sebagai panduan, bukan formulir yang harus diisi secara kaku.


Aksesibilitas di sini bukan formalitas kepatuhan, melainkan syarat agar buku benar-benar terbaca oleh semua pembacanya — termasuk yang memakai layar kecil, pembaca layar, atau tanpa tetikus.

---

## 1. Kontras warna

Target minimum: **4,5:1** untuk teks biasa, **3:1** untuk teks besar (≥18,66 px tebal atau ≥24 px).

Palet bawaan template terhadap latar `--bg:#12141a`:

| Variabel | Warna | Rasio | Pemakaian |
|---|---|---|---|
| `--ink` | `#eceff4` | ±15:1 | Teks utama — aman |
| `--ink-2` | `#a8b1c2` | ±8:1 | Teks sekunder — aman |
| `--ink-3` | `#7b8598` | ±4,6:1 | Teks tersier — **batas minimum**, jangan dipakai untuk isi utama |
| `--accent` | `#4da3ff` | ±6:1 | Heading h3, tautan — aman |
| `--warn` | `#f0a742` | ±8:1 | Peringatan — aman |

**Aturan saat mengganti `--accent`:** warna aksen baru harus tetap ≥4,5:1 terhadap `--bg`. Warna jenuh gelap (biru tua, ungu tua, merah tua) hampir selalu gagal di latar gelap. Pilih nada yang lebih terang dari yang terasa alami.

Jangan menyampaikan informasi **hanya** lewat warna. Callout peringatan tetap diberi judul "Peringatan", bukan sekadar garis oranye.

---

## 2. Hierarki heading

- Satu `h1` per buku, yaitu judul di cover.
- `h2` untuk bab, `h3` untuk subbab, `h4` untuk sub-subbab.
- **Tanpa lompatan tingkat.** `h2` langsung ke `h4` membuat pembaca layar kehilangan struktur.
- Jangan memakai heading hanya untuk memperbesar teks. Gunakan `strong` atau kelas komponen.
- Heading harus deskriptif. "Bab 3" saja tidak cukup; "Bab 3 — Menyusun Anggaran" memberi konteks saat daftar heading dibacakan.

Hierarki yang benar juga menentukan kualitas daftar isi dan pencarian.

---

## 3. Navigasi keyboard

Template menyediakan:

| Tombol | Fungsi |
|---|---|
| `/` | Fokus ke kotak pencarian |
| `Esc` | Bersihkan pencarian |
| `j` atau `PageDown` | Bab berikutnya |
| `k` atau `PageUp` | Bab sebelumnya |
| `Home` | Kembali ke awal buku |

Ketentuan:
- Pintasan **tidak aktif** saat pengguna sedang mengetik di kolom input.
- Setelah berpindah bab, fokus dipindahkan ke heading bab tersebut agar pembaca layar mengumumkannya.
- Semua tombol (`button`) dapat dijangkau dengan `Tab` dan diaktifkan dengan `Enter`/`Spasi` — gunakan elemen `<button>`, jangan `<div onclick>`.
- Sediakan **skip link** (`.skip-link`) di paling atas agar pengguna keyboard dapat melompati sidebar.

Dokumentasikan pintasan ini di bagian "Cara menggunakan buku" bila bukunya panjang.

---

## 4. Semantik dan label

- Gunakan elemen semantik: `<aside>` untuk sidebar, `<nav>` untuk daftar isi, `<main>` untuk isi, `<section>` per bab, `<header>` untuk cover.
- `<nav aria-label="Daftar Isi">` — beri label karena bisa ada lebih dari satu area navigasi.
- Tombol ikon **wajib** punya `aria-label`: tombol menu (`☰`) dan tombol kembali ke atas (`↑`) tidak punya teks yang terbaca.
- Kotak pencarian memakai `<input type="search">` dengan `aria-label`.
- Tabel data memakai `<th>` untuk baris header, bukan `<td>` yang ditebalkan.
- Diagram SVG diberi `<title>` di dalam `<svg>`, dan `<figcaption>` yang menjelaskan isinya dalam kalimat lengkap.

**Uji cepat:** bila semua gambar dan warna dihapus, apakah isi buku masih dapat dipahami? Bila tidak, ada informasi yang hanya tersimpan di elemen visual.

---

## 5. Ukuran dan jarak

- Ukuran dasar 17 px di layar, turun ke 16 px di bawah 820 px lebar. Jangan turun di bawah 15 px.
- Tinggi baris 1,7 untuk teks isi — latar gelap membutuhkan jarak baris lebih longgar daripada latar terang agar tidak menyilaukan.
- Lebar kolom baca dibatasi `--maxw:820px`. Baris yang lebih panjang dari ±90 karakter melelahkan mata.
- Target sentuh minimal **44 × 44 px** untuk tombol di layar sentuh. Tombol `#toTop` dan `#menuBtn` di template sudah memenuhi.
- Jarak antar tautan di daftar isi cukup agar tidak salah sentuh.

---

## 6. Gerak dan animasi

- Tidak ada animasi dekoratif. Satu-satunya transisi adalah geser sidebar dan progress bar.
- `scroll-behavior:smooth` boleh dipertahankan, tetapi jangan menambah animasi masuk per elemen.
- Bila menambahkan animasi apa pun, hormati preferensi pengguna:

```css
@media (prefers-reduced-motion:reduce){
  *{animation:none !important;transition:none !important;}
  html{scroll-behavior:auto;}
}
```

---

## 7. Bahasa

- Atribut `lang` pada `<html>` **wajib disesuaikan dengan bahasa buku** — `id` untuk Indonesia, `en` untuk Inggris. Ini menentukan cara pembaca layar melafalkan teks.
- Bila ada kutipan dalam bahasa berbeda, beri `lang` pada elemennya.

---

## 8. Pemeriksaan aksesibilitas

Dapat diperiksa otomatis:
- [ ] Hierarki heading tanpa lompatan.
- [ ] Setiap tombol ikon punya `aria-label`.
- [ ] `<html lang>` sesuai bahasa buku.
- [ ] Tabel memakai `<th>`.
- [ ] Setiap `<svg>` dalam `<figure>` punya `<title>` atau `<figcaption>`.
- [ ] Ada `.skip-link`.

Perlu verifikasi manusia:
- [ ] Kontras aksen kustom terhadap latar.
- [ ] Navigasi `Tab` berurutan wajar dan fokus terlihat.
- [ ] Terbaca dengan pembaca layar.
- [ ] Nyaman dipakai di layar sentuh.
