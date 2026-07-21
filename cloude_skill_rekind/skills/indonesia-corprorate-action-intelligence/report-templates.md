# Report Templates

Enam mode laporan: Daily Brief (A), Weekly Digest (B), Company Deep Dive (C), Sector Watch (D), Event Verification (E), Executive One-Pager (I).

Seluruh laporan:
- Mencantumkan **tanggal penyusunan dan periode cakupan**.
- Mencantumkan **disclaimer** bila memuat analisis.
- Memakai kartu dari `intelligence-card-template.md`.
- Menyebut **cakupan pencarian** — sumber apa saja yang diperiksa.

---

## A. Daily Brief

Periode default: 24 jam terakhir. Panjang: 1–2 halaman.

```markdown
# Daily Brief — Aksi Korporasi Indonesia
**[Tanggal]** · Periode: [24 jam terakhir / rentang]
Diperiksa pada: [tanggal dan waktu]

## Ringkasan
[2–3 kalimat: berapa event, mana yang paling perlu diperhatikan, dan mengapa.]

## Perlu Perhatian
[Kartu ringkas untuk event dengan materiality ≥4 atau urgency HIGH/CRITICAL.
Maksimal 3 event.]

## Event Lain
[Kartu ringkas, dikelompokkan per sektor bila lebih dari 5.]

## Perkembangan Event Sebelumnya
[Event lama yang statusnya berubah hari ini. Sebutkan status lama → status baru.]

## Belum Terkonfirmasi
[Rumor atau berita yang belum terverifikasi. Tandai jelas.]

## Cakupan Pencarian
Sumber yang diperiksa: [daftar]
Tidak dapat diakses: [daftar, atau "tidak ada"]

---
*Analisis ini merupakan ringkasan informasi publik dan bukan rekomendasi investasi.*
```

Aturan: bila tidak ada aksi korporasi yang memenuhi kriteria, **katakan demikian**. Jangan mengisi dengan berita yang bukan aksi korporasi.

---

## B. Weekly Digest

Periode default: 7 hari. Panjang: 3–5 halaman.

```markdown
# Weekly Digest — Aksi Korporasi Indonesia
**Periode [tanggal] – [tanggal]** · Disusun [tanggal]

## Ringkasan Minggu Ini
[3–5 kalimat: tema utama, jumlah event per kategori, hal yang menonjol.]

## Sorotan
[2–4 kartu penuh untuk event paling material.]

## Tabel Seluruh Event
| Perusahaan | Kategori | Status | Mat. | Conf. | Perkembangan |
|---|---|---|---|---|---|

## Perkembangan Event Sebelumnya
[Event dari minggu-minggu lalu yang bergerak. Sebutkan perubahan statusnya.]

## Pola yang Terlihat
[Bila ada: sektor yang aktif, jenis aksi yang berulang. Tandai sebagai analisis.]

## Agenda Pekan Depan
[Kalender ringkas: RUPS, cum date, tenggat. Bedakan confirmed/planned/estimated.]

## Belum Terkonfirmasi
[Rumor dan berita belum terverifikasi.]

## Cakupan Pencarian
[—]

---
*Analisis ini merupakan ringkasan informasi publik dan bukan rekomendasi investasi.*
```

Yang membedakan dari daily brief: **wajib memuat perkembangan event lama**, bukan hanya yang baru muncul.

---

## C. Company Deep Dive

Satu perusahaan, periode tertentu. Panjang: 3–6 halaman.

```markdown
# Company Deep Dive — [Nama Perusahaan] ([TICKER])
**Periode [tanggal] – [tanggal]** · Disusun [tanggal]

## Profil Singkat
[Sektor, kegiatan usaha utama, status kepemilikan. Dari sumber resmi.
2–4 kalimat, tanpa penilaian.]

## Ringkasan Periode
[Berapa aksi korporasi, jenis apa saja, arah umumnya.]

## Event
[Kartu penuh untuk setiap event material. Kartu ringkas untuk sisanya.]

## Timeline Gabungan
[Seluruh event dalam satu garis waktu, agar terlihat urutan dan keterkaitannya.]

## Pola dan Keterkaitan
**Analisis:** [Apakah event-event ini membentuk arah tertentu? Berpijak pada
fakta yang sudah disebut. Tandai sebagai analisis.]

## Information Gaps
[Hal yang belum diketahui dan mengapa penting.]

## Agenda Mendatang
[Kalender perusahaan ini.]

## Sources
[Official / News / Supporting]

---
*Analisis ini merupakan ringkasan informasi publik dan bukan rekomendasi investasi.*
```

Aturan: deep dive **wajib memuat timeline gabungan**. Tanpa itu, laporan hanya menjadi kumpulan berita.

---

## D. Sector Watch

Satu sektor. Panjang: 3–5 halaman.

```markdown
# Sector Watch — [Sektor]
**Periode [tanggal] – [tanggal]** · Disusun [tanggal]

## Ringkasan Sektor
[Apa yang sedang terjadi di sektor ini menurut temuan. 3–5 kalimat.]

## Event per Perusahaan
| Perusahaan | Ticker | Kategori | Status | Mat. | Ringkasan |
|---|---|---|---|---|---|

## Sorotan
[Kartu penuh untuk 2–3 event paling material di sektor ini.]

## Pola Sektor
**Analisis:** [Konsolidasi? Ekspansi kapasitas? Divestasi aset? Berpijak pada
event yang ditemukan, bukan pada pengetahuan umum industri.]

## Perusahaan yang Tidak Menunjukkan Aksi
[Bila relevan: perusahaan besar di sektor ini yang tidak ditemukan aksinya
pada periode tersebut. Nyatakan bahwa ini hasil pencarian, bukan kepastian.]

## Agenda Sektor
[Kalender.]

## Cakupan Pencarian
[Perusahaan dan sumber apa saja yang diperiksa.]

---
*Analisis ini merupakan ringkasan informasi publik dan bukan rekomendasi investasi.*
```

Aturan: sector watch harus mencakup **beberapa perusahaan**. Laporan yang hanya membahas satu perusahaan adalah deep dive, bukan sector watch.

---

## E. Event Verification

Satu pertanyaan: sudah resmi atau belum. Panjang: ≤1 halaman.

```markdown
# Event Verification — [Ringkasan klaim yang diperiksa]
Diperiksa pada [tanggal]

## Klaim yang Diperiksa
"[Kutip atau parafrase klaim/rumor yang ditanyakan pengguna]"

## Jawaban Singkat
[Satu-dua kalimat langsung. Contoh: "Belum resmi. Rencana sudah diumumkan
perusahaan, tetapi persetujuan pemegang saham dan regulator belum ditemukan."]

## Status
**[STATUS]**

Dasar:
[Bukti ditemukan + bukti belum ditemukan + tanggal pemeriksaan]

## Apa yang Ditemukan
| Sumber | Tanggal | Isi |
|---|---|---|

## Apa yang Tidak Ditemukan
- [keterbukaan informasi / persetujuan / pernyataan resmi / dll.]

## Confidence
**[1–5]** — [alasan]

## Sumber yang Diperiksa
[Daftar, termasuk yang tidak dapat diakses.]

---
*Analisis ini merupakan ringkasan informasi publik dan bukan rekomendasi investasi.*
```

Mode ini paling sering dipakai. Jawaban singkat di awal wajib — pengguna bertanya untuk mendapat kepastian, bukan uraian panjang.

---

## I. Executive One-Pager

Untuk pimpinan. Maksimal satu halaman. Tanpa jargon.

```markdown
# [Judul: apa yang terjadi, dalam satu baris]
[Tanggal] · [Perusahaan/sektor]

**Intinya.** [2–3 kalimat. Apa yang terjadi, sejauh mana kepastiannya,
dan mengapa ini relevan bagi pembaca.]

**Angka kunci.**
- [item]: [nilai] ([sumber])
- [item]: [nilai] ([sumber])

**Status:** [STATUS] — [dasar dalam satu kalimat]

**Tingkat kepentingan:** Materiality [n]/5 · Confidence [n]/5 · Urgency [level]

**Yang perlu diperhatikan.**
- [1–3 butir: risiko atau tenggat, bukan saran tindakan]

**Yang belum diketahui.**
- [1–3 butir]

**Agenda terdekat:** [tanggal] — [agenda]

*Ringkasan informasi publik; bukan rekomendasi investasi. Rincian tersedia
bila diperlukan.*
```

Aturan: one-pager **tidak boleh memuat saran tindakan**. "Yang perlu diperhatikan" berisi fakta dan risiko, bukan anjuran.

---

## Aturan umum seluruh mode

1. **Selalu cantumkan tanggal penyusunan dan periode cakupan.** Laporan intelijen adalah potret waktu.
2. **Selalu sebutkan cakupan pencarian** — pengguna perlu tahu apa yang tidak diperiksa.
3. **Jangan mengisi laporan demi kelengkapan format.** Bagian yang kosong dinyatakan kosong.
4. **Deduplikasi sebelum menyusun laporan**, bukan sesudah.
5. **Rumor dipisahkan** ke bagian tersendiri, tidak dicampur dengan event terverifikasi.
6. **Disclaimer wajib** pada laporan yang memuat analisis.
7. Keluaran berupa markdown di dalam percakapan — skill ini tidak menghasilkan file.
