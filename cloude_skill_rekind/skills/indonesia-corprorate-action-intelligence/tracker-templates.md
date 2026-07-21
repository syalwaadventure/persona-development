# Tracker Templates

Tiga mode: Deal Tracker (F), Capital Market Action Tracker (G), Watchlist Mode (J).

Tracker berbeda dari laporan naratif: bentuknya tabel pemantauan, dirancang untuk **dibandingkan dan diperbarui**, bukan dibaca sekali.

---

## F. Deal Tracker

Melacak merger, akuisisi, divestasi, joint venture, spin-off, dan transaksi strategis lain.

```markdown
# Deal Tracker — [cakupan: sektor / watchlist / periode]
Disusun [tanggal] · Periode [rentang]

## Ringkasan
[Berapa deal aktif, berapa selesai, berapa batal pada periode ini.]

## Deal Aktif
| Perusahaan | Pihak Lawan | Jenis | Objek | Nilai | Status | Mat. | Conf. | Tenggat Terdekat |
|---|---|---|---|---|---|---|---|---|
| [—] | [—] | Akuisisi saham | 51% PT X | Rp2,38 T | AWAITING APPROVAL | 4 | 4 | RUPS 5 Agu |

## Deal Selesai pada Periode Ini
| Perusahaan | Jenis | Nilai | Tanggal Closing | Sumber |
|---|---|---|---|---|

## Deal Batal atau Tertunda
| Perusahaan | Jenis | Status | Alasan (bila disebut) | Sumber |
|---|---|---|---|---|

## Catatan per Deal
[Untuk deal bermaterialitas ≥4: kartu ringkas atau kartu penuh.]

## Information Gaps
[Deal yang nilainya, pihaknya, atau jadwalnya belum ditemukan.]

## Cakupan Pencarian
[—]

---
*Analisis ini merupakan ringkasan informasi publik dan bukan rekomendasi investasi.*
```

Aturan kolom:
- **Nilai** yang belum ditemukan ditulis "belum ditemukan", bukan dikosongkan atau diperkirakan.
- **Objek** menyebut apa yang berpindah: persentase saham, entitas, atau aset tertentu. Ini yang membedakan jenis akuisisi.
- **Tenggat terdekat** diisi agenda paling dekat; bila tidak ada, tulis "belum ada tenggat".

---

## G. Capital Market Action Tracker

Melacak rights issue, private placement, buyback, dividen, stock split, obligasi, sukuk, dan aksi pasar modal lainnya.

```markdown
# Capital Market Action Tracker — [cakupan]
Disusun [tanggal] · Periode [rentang]

## Aksi Ekuitas
| Perusahaan | Ticker | Jenis | Nilai/Jumlah | Harga | Periode | Status | Sumber |
|---|---|---|---|---|---|---|---|
| [—] | [—] | Rights issue | 1,2 miliar saham | Rp850 | 10–17 Agu | AWAITING APPROVAL | [—] |

## Dividen
| Perusahaan | Ticker | Per Saham | Total | Cum Date | Ex Date | Payment | Status |
|---|---|---|---|---|---|---|---|

## Buyback
| Perusahaan | Ticker | Nilai Maks. | Periode | Status | Sumber |
|---|---|---|---|---|---|

## Aksi Utang
| Perusahaan | Jenis | Nilai | Tenor | Kupon | Status | Sumber |
|---|---|---|---|---|---|---|

## Catatan Istilah
[Jelaskan istilah yang muncul: cum date, ex date, HMETD, tenor, kupon —
bila pengguna belum tentu memahaminya.]

## Information Gaps
[—]

---
*Analisis ini merupakan ringkasan informasi publik dan bukan rekomendasi investasi.*
```

**Aturan penting:** tracker ini menyajikan **jadwal dan angka**, tanpa saran tindakan. Kalimat seperti "menarik untuk dicermati sebelum cum date" dilarang — itu rekomendasi terselubung.

Bagian "Catatan Istilah" wajib diisi bila laporan memuat istilah pasar modal, karena pengguna skill ini mencakup kalangan nonteknis.

---

## J. Watchlist Mode

Pemantauan perusahaan, ticker, sektor, BUMN, konglomerasi, atau jenis event yang ditentukan pengguna.

### J1. Peringatan wajib

Setiap kali watchlist dibuat atau dipakai, sampaikan:

> Watchlist ini berlaku untuk percakapan saat ini. Skill tidak menyimpannya
> secara otomatis antar percakapan. Bila akan dipakai berulang, simpan
> daftarnya di Project Knowledge atau repository, lalu tempelkan kembali
> pada percakapan berikutnya.

### J2. Format watchlist tersimpan

Format ini dirancang agar pengguna dapat menyalin, menyimpan, dan menempelkannya kembali.

```markdown
# Watchlist — [nama daftar]
Dibuat [tanggal] · Terakhir diperbarui [tanggal]

## Perusahaan
| Nama | Ticker | Sektor | Alasan Pemantauan |
|---|---|---|---|

## Sektor
- [sektor] — [alasan]

## Jenis Event yang Dipantau
- [kategori aksi korporasi]

## Ambang Pelaporan
- Materiality minimum: [n]
- Status yang dilaporkan: [semua / hanya terverifikasi / dll.]
```

### J3. Laporan pemantauan

```markdown
# Watchlist Report — [nama daftar]
Periode [rentang] · Diperiksa [tanggal]

## Ada Perkembangan
| Perusahaan | Kategori | Status | Mat. | Conf. | Perkembangan |
|---|---|---|---|---|---|

## Kartu Detail
[Kartu ringkas atau penuh untuk yang melewati ambang pelaporan.]

## Tidak Ditemukan Perkembangan
[Daftar entri watchlist yang tidak ditemukan aksi korporasinya pada periode ini.]

> Catatan: "tidak ditemukan" berarti tidak ada pada sumber yang diperiksa
> dalam periode tersebut, bukan kepastian bahwa tidak ada peristiwa.

## Agenda Mendatang
[Kalender untuk entri watchlist.]

## Cakupan Pencarian
[Sumber dan entri yang diperiksa; sumber yang tidak dapat diakses.]

---
*Analisis ini merupakan ringkasan informasi publik dan bukan rekomendasi investasi.*
```

### J4. Aturan

1. **Bagian "Tidak Ditemukan Perkembangan" wajib ditampilkan.** Pengguna perlu tahu bahwa entri tersebut diperiksa, bukan terlewat.
2. **Nyatakan batas pencarian.** Tidak ditemukan ≠ tidak ada.
3. **Hormati ambang pelaporan** yang ditetapkan pengguna; jangan membanjiri laporan dengan event kecil.
4. **Watchlist perusahaan menengah:** bila pengguna memasukkan entitas di luar cakupan default (§2 SKILL.md), sampaikan bahwa cakupan pencarian untuk entitas tersebut mungkin lebih terbatas.

---

## Aturan umum tracker

1. Kolom yang datanya tidak ada diisi **"belum ditemukan"**, bukan dikosongkan.
2. Setiap baris dapat ditelusuri ke sumbernya — sertakan kolom sumber atau catatan kaki.
3. Cantumkan tanggal penyusunan; tracker adalah potret waktu.
4. Deduplikasi dilakukan sebelum mengisi tabel.
5. Tidak ada kolom, catatan, atau kalimat yang berisi saran tindakan investasi.
