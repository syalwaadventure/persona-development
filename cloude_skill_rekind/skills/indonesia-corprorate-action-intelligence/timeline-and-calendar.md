# Timeline and Calendar Guide

Dipakai pada Fase 6 dan Fase 8. Timeline melihat ke belakang; kalender melihat ke depan.

---

# BAGIAN A — TIMELINE

## A1. Fungsi

Timeline menunjukkan **bagaimana suatu event berkembang**, bukan sekadar kapan diberitakan. Ini yang membedakan laporan intelijen dari kumpulan berita: pengguna dapat melihat apakah transaksi bergerak maju, melambat, atau berubah arah.

## A2. Sepuluh titik yang dicatat

| Titik | Keterangan |
|---|---|
| Rumor pertama | Kapan isu mulai beredar dan di mana |
| Laporan media | Pemberitaan media kredibel pertama dan berikutnya yang membawa informasi baru |
| Pernyataan manajemen | Kutipan atau konfirmasi dari pengurus |
| Pengumuman resmi | Siaran pers perusahaan |
| Keterbukaan informasi | Pelaporan ke IDX/OJK |
| Agenda RUPS | Pemanggilan dan tanggal pelaksanaan |
| Persetujuan | Pemegang saham, regulator, atau keduanya |
| Closing | Penyelesaian transaksi |
| Realisasi | Efek nyata: pengalihan saham, operasi dimulai |
| Pembatalan atau penundaan | Termasuk alasannya bila disebut |

Tidak semua event memiliki seluruh titik. Catat yang ada; jangan mengarang tahap yang tidak ditemukan.

## A3. Format

```
TIMELINE

12 Mei 2026   — Isu beredar di kalangan pelaku pasar tanpa sumber jelas
                (status: RUMOR)
02 Jun 2026   — Kontan memberitakan rencana akuisisi, mengutip "sumber
                yang mengetahui" (status: MEDIA REPORT)
12 Jun 2026   — Siaran pers perusahaan mengonfirmasi rencana; nilai belum
                disebut (status: PLANNED)
18 Jun 2026   — Keterbukaan informasi IDX; nilai Rp2,38 triliun
20 Jun 2026   — Notifikasi ke KPPU diajukan (status: REGULATORY SUBMISSION)
05 Agu 2026   — RUPS Luar Biasa dijadwalkan (belum berlangsung)

Diperiksa pada: 20 Juli 2026
```

Aturan:
- Urut menaik berdasarkan tanggal.
- Setiap butir menyebut **sumbernya**.
- Perubahan status dicantumkan di titik terjadinya.
- Peristiwa yang belum terjadi ditandai jelas ("dijadwalkan", "belum berlangsung").
- Cantumkan tanggal pemeriksaan di akhir.

## A4. Aturan penting

1. **Jangan menghapus tahap yang sudah lewat**, termasuk rumor yang ternyata keliru. Riwayat itu informasi.
2. **Bedakan tanggal berita dan tanggal peristiwa.** Berita 15 Juni tentang persetujuan 10 Juni dicatat pada 10 Juni, dengan keterangan sumbernya terbit 15 Juni.
3. **Bila tanggal tidak diketahui**, tulis perkiraan periodenya dan tandai: "sekitar Mei 2026 (tanggal pasti belum ditemukan)".
4. **Bila event mundur** (PLANNED → DELAYED), timeline menunjukkan keduanya. Ini justru sinyal penting.
5. Untuk event lama yang kembali aktif, tampilkan riwayat lamanya secara ringkas agar konteksnya utuh.

---

# BAGIAN B — CORPORATE-ACTION CALENDAR

## B1. Fungsi

Kalender menyusun **tanggal-tanggal yang akan datang** yang perlu diperhatikan pengguna.

## B2. Empat jenis tanggal — wajib dibedakan

| Jenis | Arti | Penanda |
|---|---|---|
| **Confirmed** | Ditetapkan resmi dan diumumkan | `[Confirmed]` |
| **Planned** | Direncanakan perusahaan, belum resmi ditetapkan | `[Planned]` |
| **Estimated** | Perkiraan berdasarkan pola atau pernyataan umum | `[Estimated]` |
| **Unknown** | Diketahui akan terjadi, tanggalnya belum ada | `[Unknown]` |

**Jangan menampilkan tanggal *estimated* tanpa penanda.** Pengguna bisa membuat keputusan berdasarkan tanggal yang ternyata hanya perkiraan.

Untuk *estimated*, sebutkan dasarnya:

> 15 Sep 2026 `[Estimated]` — perkiraan closing; perusahaan menyatakan "kuartal ketiga 2026" tanpa tanggal pasti.

## B3. Jenis agenda yang dicatat

| Agenda | Keterangan |
|---|---|
| RUPS Tahunan / Luar Biasa | Tanggal pemanggilan dan pelaksanaan |
| Cum date | Tanggal terakhir memiliki saham untuk berhak atas aksi korporasi |
| Ex date | Tanggal saham diperdagangkan tanpa hak tersebut |
| Recording date | Tanggal pencatatan pemegang saham yang berhak |
| Payment date | Tanggal pembayaran dividen |
| Periode perdagangan HMETD | Untuk rights issue |
| Batas waktu penawaran | Untuk tender offer atau buyback |
| Closing transaksi | Penyelesaian M&A |
| Tenggat regulator | Batas waktu keputusan atau pemenuhan syarat |
| Pencatatan saham baru | Listing date |

Istilah *cum date*, *ex date*, dan *HMETD* dijelaskan saat pertama muncul — pengguna skill ini belum tentu memahami istilah pasar modal.

## B4. Format

```
CORPORATE-ACTION CALENDAR — Juli–September 2026
Disusun pada 20 Juli 2026

| Tanggal | Jenis | Perusahaan | Agenda | Status tanggal | Sumber |
|---|---|---|---|---|---|
| 28 Jul 2026 | Cum date | PT A (AAAA) | Dividen tunai Rp45/saham | Confirmed | IDX, 10 Jul 2026 |
| 05 Agu 2026 | RUPSLB | PT B (BBBB) | Persetujuan akuisisi | Confirmed | Pemanggilan RUPS, 21 Jul 2026 |
| Sep 2026 | Closing | PT C | Penyelesaian divestasi | Estimated | Siaran pers 12 Jun 2026 ("kuartal III") |
| — | Persetujuan | PT D | Keputusan KPPU | Unknown | Notifikasi 20 Jun 2026 |
```

Urutkan berdasarkan tanggal. Tanggal *unknown* diletakkan di bagian akhir.

## B5. Aturan

1. **Jangan mengarang tanggal.** Tanggal yang tidak ditemukan ditulis `[Unknown]`, bukan diperkirakan diam-diam.
2. **Setiap tanggal menyebut sumber dan tanggal sumbernya.**
3. **Cantumkan tanggal penyusunan kalender.** Jadwal berubah; kalender adalah potret.
4. **Perbarui status tanggal** bila berubah dari *planned* menjadi *confirmed*.
5. Untuk cum date dan ex date, cukup sajikan tanggalnya — **jangan menyertakan saran tindakan apa pun**, karena itu masuk wilayah rekomendasi investasi.
6. Bila kalender disusun untuk watchlist, sebutkan bahwa cakupannya terbatas pada perusahaan dalam daftar tersebut.

## B6. Batas

Kalender ini menyajikan **jadwal**, bukan anjuran. Kalimat seperti "sebaiknya membeli sebelum cum date" dilarang. Bila pengguna menanyakan implikasi tanggal terhadap keputusan investasi, jelaskan batas kewenangan dan tawarkan penjelasan mekanismenya saja.
