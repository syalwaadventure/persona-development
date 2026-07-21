# Corporate-Action Calendar Template

Mode H. Menyusun agenda aksi korporasi yang akan datang.

---

## 1. Empat jenis tanggal — wajib dibedakan

| Penanda | Arti |
|---|---|
| `[Confirmed]` | Ditetapkan resmi dan diumumkan |
| `[Planned]` | Direncanakan perusahaan, belum resmi ditetapkan |
| `[Estimated]` | Perkiraan berdasarkan pernyataan umum atau pola; **wajib menyebut dasarnya** |
| `[Unknown]` | Diketahui akan terjadi, tanggalnya belum ada |

**Tanggal `[Estimated]` tanpa penanda adalah kegagalan.** Pengguna dapat mengambil keputusan berdasarkan tanggal yang ternyata hanya perkiraan.

---

## 2. Template

```markdown
# Corporate-Action Calendar — [cakupan]
Periode [rentang] · Disusun [tanggal]

## Agenda Terjadwal

| Tanggal | Jenis | Perusahaan | Ticker | Agenda | Status Tanggal | Sumber |
|---|---|---|---|---|---|---|
| 28 Jul 2026 | Cum date | [—] | [—] | Dividen tunai Rp45/saham | Confirmed | IDX, 10 Jul 2026 |
| 05 Agu 2026 | RUPSLB | [—] | [—] | Persetujuan akuisisi | Confirmed | Pemanggilan RUPS, 21 Jul 2026 |
| Sep 2026 | Closing | [—] | — | Penyelesaian divestasi | Estimated | Siaran pers 12 Jun 2026 ("kuartal III") |

## Tanggal Belum Ditentukan

| Jenis | Perusahaan | Agenda | Keterangan | Sumber |
|---|---|---|---|---|
| Persetujuan | [—] | Keputusan KPPU | Notifikasi diajukan 20 Jun 2026 | [—] |

## Catatan Istilah
[Jelaskan istilah yang muncul dalam kalender ini.]

## Cakupan
Perusahaan yang diperiksa: [daftar]
Sumber: [daftar]
Tidak dapat diakses: [daftar, atau "tidak ada"]

---
*Jadwal dapat berubah. Kalender ini merupakan potret pada tanggal penyusunan
dan bukan rekomendasi investasi.*
```

Urutkan menaik berdasarkan tanggal. Agenda bertanggal `[Unknown]` diletakkan pada tabel terpisah di bawah.

---

## 3. Jenis agenda

| Agenda | Keterangan |
|---|---|
| RUPS Tahunan (RUPST) | Rapat umum pemegang saham tahunan |
| RUPS Luar Biasa (RUPSLB) | Rapat untuk agenda khusus, misalnya persetujuan transaksi |
| Cum date | Tanggal terakhir memiliki saham untuk berhak atas aksi korporasi |
| Ex date | Tanggal saham diperdagangkan tanpa hak tersebut |
| Recording date | Tanggal pencatatan pemegang saham yang berhak |
| Payment date | Tanggal pembayaran dividen |
| Periode perdagangan HMETD | Masa perdagangan hak dalam rights issue |
| Batas waktu penawaran | Untuk tender offer atau buyback |
| Closing transaksi | Penyelesaian M&A |
| Tenggat regulator | Batas waktu keputusan atau pemenuhan syarat |
| Listing date | Pencatatan saham baru di bursa |

---

## 4. Penjelasan istilah untuk pengguna nonteknis

Sertakan bila istilahnya muncul. Rumusan yang disarankan:

- **Cum date** — batas akhir untuk tercatat sebagai pemegang saham yang berhak atas dividen atau aksi korporasi tersebut.
- **Ex date** — mulai tanggal ini, pembeli saham tidak lagi memperoleh hak tersebut.
- **Recording date** — tanggal perusahaan mencatat siapa saja pemegang saham yang berhak.
- **HMETD** — Hak Memesan Efek Terlebih Dahulu; hak pemegang saham lama untuk membeli saham baru dalam rights issue.
- **RUPSLB** — rapat pemegang saham di luar jadwal tahunan, biasanya untuk memutuskan hal khusus.
- **Tender offer** — penawaran untuk membeli saham dari pemegang saham publik, dalam kondisi tertentu diwajibkan aturan.

Penjelasan diberikan **satu kali** saat istilah pertama muncul.

---

## 5. Aturan

1. **Jangan mengarang tanggal.** Yang tidak ditemukan ditulis `[Unknown]`.
2. **Setiap tanggal menyebut sumber dan tanggal sumbernya.**
3. **Cantumkan tanggal penyusunan.** Jadwal berubah.
4. **Perbarui status tanggal** bila berubah dari *planned* menjadi *confirmed*.
5. **Tidak ada saran tindakan.** Kalimat seperti "sebaiknya membeli sebelum cum date" dilarang — itu rekomendasi investasi.
6. Bila kalender disusun untuk watchlist, sebutkan bahwa cakupannya terbatas pada daftar tersebut.
7. Agenda yang tanggalnya sudah lewat tanpa kabar dipindahkan ke catatan dengan keterangan "tenggat lewat, belum ada pengumuman" — jangan dihapus diam-diam.

---

## 6. Bila tidak ada agenda ditemukan

Katakan apa adanya:

> Tidak ditemukan agenda aksi korporasi terjadwal untuk [cakupan] pada periode
> [rentang] berdasarkan sumber yang diperiksa hingga [tanggal]. Ini tidak
> berarti tidak ada agenda; pengumuman dapat terbit setelah tanggal pemeriksaan.

Jangan mengisi kalender dengan perkiraan agar terlihat lengkap.
