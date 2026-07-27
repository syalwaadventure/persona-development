# Scoring Guide

> **Catatan gaya:** Tulis hasil dengan bahasa yang langsung, natural, dan sesuai konteks. Gunakan struktur ini sebagai panduan, bukan formulir yang harus diisi secara kaku.


Dipakai pada Fase 7. Tiga skor: materiality, confidence, urgency.

**Aturan mengikat: setiap skor wajib disertai alasan satu–dua kalimat.** Skor tanpa alasan adalah kegagalan kritis.

---

## 1. Materiality Score (1–5)

Menjawab: **seberapa penting event ini bagi perusahaan dan pemangku kepentingannya?**

| Skor | Arti | Indikator |
|---|---|---|
| **1** | Sangat rendah | Rutin, tidak mengubah apa pun yang berarti |
| **2** | Terbatas | Berdampak pada satu unit kecil atau satu lini pendukung |
| **3** | Cukup material | Mempengaruhi lini bisnis atau posisi keuangan secara terlihat |
| **4** | Material | Mengubah struktur, kapasitas, atau posisi keuangan secara signifikan |
| **5** | Sangat material / strategis | Mengubah pengendali, arah usaha, atau struktur industri |

### Faktor penilaian

| Faktor | Pertanyaan |
|---|---|
| Nilai relatif | Berapa nilainya dibanding aset, ekuitas, atau pendapatan perusahaan? |
| Dampak kepemilikan | Apakah mengubah pemegang saham pengendali? |
| Dampak usaha | Apakah mengubah kegiatan usaha utama atau kapasitas? |
| Dampak keuangan | Apakah mengubah struktur utang, arus kas, atau kemampuan bayar? |
| Dampak industri | Apakah mengubah peta persaingan atau rantai pasok sektor? |
| Ketentuan regulasi | Apakah tergolong transaksi material yang wajib dilaporkan? |

### Contoh penulisan

> **Materiality: 4**
> Nilai transaksi Rp2,4 triliun setara sekitar 18% total aset perusahaan dan menambah kapasitas produksi sekitar sepertiga. Tidak mengubah pemegang saham pengendali, sehingga belum mencapai skor 5.

### Kesalahan yang harus dihindari
- **Menurunkan materialitas karena belum terverifikasi.** Itu urusan confidence, bukan materiality.
- Menilai dari besar angka absolut tanpa membandingkan ukuran perusahaan.
- Memberi skor 3 sebagai jalan aman ketika ragu. Bila data tidak cukup, katakan demikian dan beri rentang.

---

## 2. Confidence Score (1–5)

Menjawab: **seberapa kuat dasar informasi kita?**

| Skor | Dasar |
|---|---|
| **1** | Rumor atau satu sumber tidak resmi |
| **2** | Beberapa media kredibel, belum ada konfirmasi resmi |
| **3** | Ada pernyataan manajemen |
| **4** | Ada keterbukaan informasi resmi |
| **5** | Telah disetujui atau diselesaikan, dan terverifikasi dari sumber resmi |

### Penyesuaian

**Turunkan satu tingkat bila:**
- Sumber utama tidak dapat diakses (paywall, halaman dihapus).
- Ada konflik antar sumber yang belum terselesaikan.
- Informasi berasal dari sumber resmi tetapi sudah lama dan mungkin berubah.

**Jangan naikkan karena:**
- Banyak media memberitakan hal yang sama. Jumlah media bukan pengganti konfirmasi resmi.
- Beritanya terdengar meyakinkan atau rinci.
- Perusahaan tidak membantah. Diam bukan konfirmasi.

### Contoh penulisan

> **Confidence: 2**
> Diberitakan Kontan dan CNBC Indonesia pada 12–13 Juni 2026, tetapi belum ditemukan keterbukaan informasi maupun pernyataan manajemen. Artikel Bloomberg tidak dapat diakses karena berbayar.

---

## 3. Materiality dan confidence bersifat independen

Ini rancangan yang disengaja dan penting untuk fungsi *early warning*.

| Kombinasi | Arti | Contoh |
|---|---|---|
| Materiality 5, Confidence 1 | **Paling berguna sebagai peringatan dini** — bila benar, dampaknya besar | Rumor akuisisi pengendali |
| Materiality 5, Confidence 5 | Peristiwa besar yang sudah pasti | Merger yang telah disetujui dan selesai |
| Materiality 2, Confidence 5 | Terverifikasi tetapi tidak penting | Perubahan komisaris independen |
| Materiality 2, Confidence 1 | Dapat diabaikan | Rumor kecil tanpa dasar |

Jangan menurunkan materialitas hanya karena confidence rendah. Justru kombinasi materialitas tinggi–confidence rendah yang paling perlu diperhatikan pengguna.

---

## 4. Urgency

Menjawab: **seberapa cepat pengguna perlu memperhatikan?**

| Level | Kriteria |
|---|---|
| **LOW** | Tidak ada tenggat dekat; perkembangan lambat; tidak memerlukan respons |
| **MEDIUM** | Ada tenggat dalam beberapa minggu, atau perkembangan berjalan aktif |
| **HIGH** | Tenggat dalam hitungan hari (RUPS, cum date, batas penawaran), atau perkembangan cepat |
| **CRITICAL** | Memerlukan perhatian segera: tenggat sangat dekat, perubahan pengendali berlangsung, atau menyentuh kepentingan langsung pengguna |

Faktor: kedekatan tenggat · kecepatan perkembangan · kebutuhan respons pengguna · keterkaitan dengan watchlist pengguna.

Urgency **bukan** turunan dari materiality. Event bermaterialitas 5 yang sudah selesai berurgensi LOW; event bermaterialitas 3 dengan cum date tiga hari lagi berurgensi HIGH.

### Contoh penulisan

> **Urgency: HIGH**
> RUPS Luar Biasa dijadwalkan 5 Agustus 2026, sembilan hari dari tanggal laporan. Keputusan pada RUPS menentukan kelanjutan transaksi.

---

## 5. Menyusun ketiga skor sekaligus

Urutan penilaian yang disarankan:

1. Tetapkan **status** lebih dulu (`event-status-guide.md`) — status membantu menentukan confidence.
2. Nilai **materiality** dari isi transaksi, tanpa memandang tingkat verifikasi.
3. Nilai **confidence** dari kualitas sumber, tanpa memandang besarnya transaksi.
4. Nilai **urgency** dari tenggat dan kecepatan perkembangan.
5. Tulis alasan masing-masing.

Blok skor lengkap:

```
MATERIALITY: 4
Nilai transaksi setara ±18% total aset dan menambah kapasitas sekitar
sepertiga. Tidak mengubah pengendali.

CONFIDENCE: 2
Dua media kredibel (12–13 Juni 2026). Belum ditemukan keterbukaan
informasi maupun pernyataan manajemen.

URGENCY: MEDIUM
Belum ada tenggat resmi. Perkembangan diperkirakan berlanjut bila
manajemen memberikan konfirmasi.
```

---

## 6. Ketika data tidak cukup untuk memberi skor

Jangan memberi skor asal. Tulis:

> **Materiality: belum dapat dinilai** — nilai transaksi belum ditemukan pada sumber yang diperiksa, sehingga proporsinya terhadap ukuran perusahaan tidak dapat dihitung. Bila nilai yang beredar di media (Rp2 triliun) benar, materialitas diperkirakan berada di kisaran 4, tetapi angka tersebut belum terkonfirmasi.

Perkiraan bersyarat seperti ini boleh, asalkan syaratnya dinyatakan terbuka dan angkanya diberi atribusi.

---

## 7. Rekind Relevance — Mode K only

Rekind relevance is separate from general news materiality.

| Level | Criteria |
|---|---|
| **HIGH** | Direct effect on Indonesian EPC/project pipeline, tender/contract, Pupuk Indonesia Group, Rekind client/partner, O&M/commissioning, utilities, industrial trading, major feedstock cost, or sector regulation |
| **MEDIUM** | Credible indirect effect through regional supply-demand, commodity/input price, equipment lead time, technology, financing, or competitor investment |
| **LOW** | Background context with no clear near-term project, client, operational, or commercial pathway |

Each relevance label must state the mechanism. “Important for Rekind” without a
mechanism is not acceptable.

For international stories, HIGH or MEDIUM relevance requires a complete
transmission path:

`global event → sector mechanism → Indonesia channel → potential Rekind relevance`.

If the path is missing, exclude the item rather than assigning LOW by default.

## 8. Do not create one composite score

Do not average materiality, confidence, urgency, and Rekind relevance into one
number. They answer different questions and must remain visible separately.
