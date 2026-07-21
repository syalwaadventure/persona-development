# Intelligence Card Template

Dua versi: **kartu penuh** (untuk analisis mendalam) dan **kartu ringkas** (untuk daily brief, one-pager, dan daftar).

Aturan umum:
- Blok yang datanya tidak ada **tidak dihapus**. Isi dengan "Belum ditemukan dalam sumber yang diperiksa".
- Ticker dikosongkan dengan keterangan "tidak tercatat di bursa" untuk entitas non-listed. **Jangan mengarang ticker.**
- Setiap fakta menyebut sumber dan tanggal.
- Cantumkan tanggal pencarian.

---

## A. Kartu penuh

```markdown
## [Nama Perusahaan] — [Ringkasan event dalam 5–8 kata]

| | |
|---|---|
| **Company** | [Nama lengkap entitas] |
| **Ticker** | [XXXX] / tidak tercatat di bursa |
| **Sector** | [sektor] |
| **Category** | [kategori utama] · [kategori terkait bila ada] |
| **Status** | [STATUS] |
| **Date** | Berita: [tanggal] · Event: [tanggal] · Diperiksa: [tanggal] |

### Executive Summary
[3–5 kalimat. Apa yang terjadi, sejauh mana perkembangannya, dan apa yang
belum pasti. Tanpa jargon yang belum dijelaskan.]

### Status — dasar penetapan
[Bukti yang ditemukan + bukti yang belum ditemukan + tanggal pemeriksaan]

### Key Facts
| Item | Isi | Sumber |
|---|---|---|
| Nilai transaksi | [—] | [sumber, tanggal] |
| Pihak terkait | [—] | [—] |
| Persentase kepemilikan | [—] | [—] |
| Sumber pendanaan | [—] | [—] |
| Jadwal | [—] | [—] |
| Persetujuan diperlukan | [—] | [—] |
| Aset terkait | [—] | [—] |

### 5W1H
- **What:** [aksi korporasi yang dilakukan]
- **Who:** [perusahaan dan pihak terkait]
- **When:** [tanggal berita, pengumuman, persetujuan, realisasi]
- **Where:** [lokasi, pasar, atau aset terkait]
- **Why:** [alasan menurut sumber — tandai bila dari perusahaan]
- **How:** [mekanisme transaksi atau implementasi]

### Verification
- Sumber resmi ditemukan: [Ya/Tidak — sebutkan apa dan tanggalnya]
- Pernyataan perusahaan: [Ya/Tidak — sebutkan]
- Jumlah sumber media kredibel: [n — sebutkan]
- Belum terverifikasi: [daftar; tulis "tidak ada" bila semua terverifikasi]
- Keterbatasan akses: [sumber yang tidak dapat dibuka, atau "tidak ada"]

### Scoring
**MATERIALITY: [1–5]**
[alasan 1–2 kalimat]

**CONFIDENCE: [1–5]**
[alasan 1–2 kalimat]

**URGENCY: [LOW/MEDIUM/HIGH/CRITICAL]**
[alasan 1–2 kalimat]

### Strategic Rationale
**A. Menurut perusahaan:** [dikutip/diparafrase dengan atribusi, atau
"Belum ditemukan dalam sumber yang diperiksa"]

**B. Analisis:** [interpretasi skill, ditandai jelas]

### Potential Impacts
- **Strategic:** [—]
- **Financial:** [—]
- **Operational:** [—]
- **Ownership:** [—]
- **Industry:** [—]
- **Stakeholder:** [—]

### Risk Flags
- **Regulatory:** [tingkat] — [dasar]
- **Funding:** [tingkat] — [dasar]
- **Execution:** [tingkat] — [dasar]
- **Governance:** [tingkat] — [dasar]
- **Reputational:** [tingkat] — [dasar]

### Timeline
[tanggal] — [peristiwa] ([sumber])
[tanggal] — [peristiwa] ([sumber])

### Open Questions
1. [pertanyaan yang belum terjawab dan mengapa penting]
2. [—]

### Sources
**Official**
- [nama dokumen/lembaga, tanggal]

**News**
- [media, tanggal, judul singkat]

**Supporting**
- [—]

---
*Analisis ini merupakan ringkasan informasi publik dan bukan rekomendasi
investasi. Diperiksa pada [tanggal].*
```

---

## B. Kartu ringkas

Untuk daily brief, executive one-pager, dan daftar dalam tracker.

```markdown
**[Nama Perusahaan] ([TICKER])** — [Kategori] · **[STATUS]**
[Satu kalimat: apa yang terjadi dan sejauh mana perkembangannya.]
Materiality [n] · Confidence [n] · Urgency [level]
Sumber: [sumber utama, tanggal] (+[n] media lain)
```

Contoh terisi:

```markdown
**PT Contoh Industri Tbk (CTIN)** — Akuisisi saham · **PLANNED**
Mengumumkan rencana mengambil 51% saham pemasok bahan bakunya; nilai
belum disebut dalam pengumuman resmi.
Materiality 4 · Confidence 3 · Urgency MEDIUM
Sumber: siaran pers perusahaan, 12 Jun 2026 (+3 media)
```

*Contoh di atas bersifat ilustratif — nama, ticker, dan angka bukan data nyata.*

---

## C. Aturan pengisian

| Blok | Aturan khusus |
|---|---|
| Company | Nama lengkap entitas. Bila induk dan anak usaha mirip, sebutkan keduanya |
| Ticker | Kosongkan dengan keterangan untuk non-listed. Jangan menebak |
| Category | Kategori utama + terkait. Bila bukti kurang: "Belum dapat diklasifikasikan — memerlukan informasi tambahan" |
| Status | Wajib disertai blok "dasar penetapan" |
| Executive Summary | Sebutkan juga apa yang belum pasti, bukan hanya apa yang terjadi |
| Key Facts | Setiap baris menyebut sumbernya. Baris tanpa data tetap ditampilkan |
| Verification | Bagian "belum terverifikasi" wajib diisi |
| Scoring | Ketiganya wajib beralasan |
| Strategic Rationale | Pemisahan A dan B mutlak |
| Impacts | Jangan menyebut dampak terhadap harga saham |
| Risk Flags | Bila tidak ada indikasi, tulis "tidak ditemukan indikasi" — jangan mengarang risiko |
| Timeline | Urut menaik, setiap butir bersumber |
| Sources | Tiga kelompok terpisah |
| Disclaimer | Wajib pada kartu yang memuat analisis |

---

## D. Konflik sumber di dalam kartu

Bila ada perbedaan antar sumber, sisipkan blok ini tepat di bawah Key Facts:

```markdown
> ⚠ **Perbedaan informasi — [item]**
> - [Sumber A, tanggal]: [nilai]
> - [Sumber B, tanggal]: [nilai]
>
> [Sumber resmi dipakai sebagai acuan / Belum ada sumber resmi; perbedaan
> dicatat sebagai information gap.]
```

Jangan menghapus konflik atau memilih sendiri tanpa dasar.
