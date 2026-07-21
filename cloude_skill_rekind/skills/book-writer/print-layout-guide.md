# Print Layout Guide

Aturan cetak A4 untuk keluaran HTML. Seluruh aturan di bawah **sudah terpasang** di `assets/dark-book-template.html`. Referensi ini menjelaskan alasannya, agar aturan tidak terhapus saat template dimodifikasi.

---

## 1. Ukuran dan margin

```css
@page{ size:A4; margin:18mm 16mm; }
```

- A4 = 210 × 297 mm. Area cetak menjadi ±178 × 261 mm.
- Margin 18 mm atas-bawah, 16 mm kiri-kanan: cukup untuk dijilid ringan, tidak boros kertas.
- Ukuran font cetak diturunkan ke 10,5 pt — ukuran layar 17 px terlalu besar di kertas dan membengkakkan jumlah halaman hingga 40%.

Jangan mengubah margin per bab. Margin yang tidak konsisten membuat buku terlihat amatir saat dijilid.

---

## 2. Dua mode cetak

| Mode | Tombol | Karakter | Untuk |
|---|---|---|---|
| **Cetak terang** | `#printLight` | Latar putih, teks gelap | Cetak kantor, hemat tinta — **default dan disarankan** |
| **Cetak gelap** | `#printDark` | Mempertahankan latar gelap | Ketika tampilan digital ingin dipertahankan |

Mode gelap bekerja lewat kelas `body.print-dark` dan memerlukan `print-color-adjust:exact`. Peringatkan pengguna bahwa mode ini memakai tinta sangat banyak dan sebagian printer kantor mengabaikan latar belakang.

---

## 3. Elemen yang disembunyikan saat cetak

`#sidebar`, `#menuBtn`, `#toTop`, `#progress`, `.copy-btn`, `#search`, `#searchInfo`, `.printbar`, `.skip-link`.

Alasannya: elemen navigasi layar tidak berfungsi di kertas dan hanya memakan ruang. Daftar isi cetak, bila diperlukan, dibuat sebagai section tersendiri di badan buku — bukan dari sidebar.

---

## 4. Page break

| Aturan | CSS | Alasan |
|---|---|---|
| Bab mulai di halaman baru | `h2{page-break-before:always}` | Batas bab terlihat jelas |
| Bab pertama tidak memulai halaman kosong | `section:first-of-type h2{page-break-before:auto}` | Mencegah halaman kosong setelah cover |
| Heading tidak sendirian di bawah halaman | `h2,h3,h4{page-break-after:avoid}` | Heading yatim membingungkan |
| Baris yatim/janda | `p,li{orphans:3;widows:3}` | Minimal 3 baris tersisa bersama paragrafnya |
| Blok tidak terpotong | `page-break-inside:avoid` pada `.box`, `.snippet`, `.goal`, `table`, `figure`, `details`, `.card`, `.flow .step`, `.timeline li` | Callout dan tabel kehilangan makna bila terpotong |

**Batas praktis:** tabel yang lebih tinggi dari satu halaman tetap akan terpotong meskipun ada `page-break-inside:avoid`. Untuk tabel panjang, pecah menjadi beberapa tabel bertema atau pindahkan ke lampiran.

---

## 5. Perubahan tampilan saat cetak

- Tata letak grid (`.cards`) dan flex (`.flow`) diubah menjadi blok bertumpuk. Kolom sempit yang terlihat rapi di layar menjadi tidak terbaca di kertas.
- Warna latar box diganti abu muda (`#f4f6f8`) dengan garis `#bbb` pada mode terang — cukup terlihat tanpa memboroskan tinta.
- Tautan kehilangan warna dan garis bawah; alamat URL tidak dicetak karena tidak dapat diklik di kertas.
- `mark` (highlight pencarian) dinetralkan.
- `section.dimmed` dikembalikan ke opasitas penuh — jangan sampai hasil pencarian membuat sebagian buku tercetak pudar.
- Isi `details` yang tertutup **tetap tercetak**. Pembaca kertas tidak bisa mengklik.

Skrip `beforeprint` membuka seluruh `details` dan membersihkan kotak pencarian sebelum dialog cetak muncul; `afterprint` mengembalikannya.

---

## 6. Memeriksa hasil cetak

Yang dapat diperiksa otomatis:
- [ ] `@page` dengan `size:A4` ada.
- [ ] `@media print` ada dan memuat aturan page break.
- [ ] Elemen layar disembunyikan.
- [ ] Tidak ada aset eksternal yang gagal dimuat saat offline.

Yang **harus diperiksa manusia** di browser (Ctrl+P → pratinjau):
- [ ] Jumlah halaman aktual dan selisihnya terhadap page budget.
- [ ] Tidak ada halaman kosong yang tidak disengaja.
- [ ] Tidak ada heading sendirian di bawah halaman.
- [ ] Tabel, callout, dan blok kode utuh.
- [ ] Diagram SVG tidak keluar margin.
- [ ] Kontras cukup pada hasil cetak nyata, bukan hanya di pratinjau layar.

Laporkan kedua kategori ini secara terpisah di QA Report. Jangan menyatakan lulus pada hal yang tidak dapat diverifikasi.

---

## 7. Menghasilkan PDF

Skill tidak menghasilkan PDF. Pengguna mencetak sendiri:

1. Buka file HTML di browser (Chrome atau Edge disarankan).
2. Pilih tombol **Cetak terang** atau **Cetak gelap** di sidebar.
3. Pada dialog cetak, pilih **Save as PDF**.
4. Untuk mode gelap, aktifkan **Background graphics** di opsi lanjutan.
5. Pastikan ukuran kertas **A4**, skala **100%** (bukan "Fit to page").

Sebutkan langkah ini saat menyerahkan file. Pengguna nonteknis sering terhenti di langkah 4 dan 5.

---

## 8. Bila menambah komponen baru

Setiap komponen visual baru **wajib** disertai aturan cetaknya:

1. Apakah perlu `page-break-inside:avoid`?
2. Bagaimana tampilannya pada mode cetak terang (warna latar dan garis)?
3. Bagaimana pada mode cetak gelap (`body.print-dark`)?
4. Apakah tata letaknya perlu berubah menjadi blok bertumpuk?

Komponen tanpa aturan cetak akan tampil rusak di kertas dan biasanya baru ketahuan setelah buku dicetak.
