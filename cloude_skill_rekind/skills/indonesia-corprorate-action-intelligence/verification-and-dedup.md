# Verification and Deduplication Guide

Dipakai pada Fase 3 (deduplikasi) dan Fase 4 (verifikasi). Dua fase ini berurutan dan saling bergantung: deduplikasi menentukan apa yang diverifikasi, verifikasi kadang mengungkap bahwa dua "event" sebenarnya satu.

---

# BAGIAN A — DEDUPLIKASI DAN EVENT CLUSTERING

## A1. Prinsip

Satu peristiwa yang diberitakan sepuluh portal adalah **satu event dengan sepuluh sumber**, bukan sepuluh event.

Menampilkannya sebagai sepuluh entri membuat laporan terlihat penuh tetapi menyesatkan: pengguna mengira ada banyak peristiwa.

## A2. Kriteria clustering

Dua berita digabungkan bila **sebagian besar** dimensi berikut cocok:

| Dimensi | Bobot | Catatan |
|---|---|---|
| Perusahaan utama | Tinggi | Harus sama |
| Pihak terkait (lawan transaksi) | Tinggi | Nama bisa ditulis berbeda; periksa entitas sebenarnya |
| Jenis aksi korporasi | Tinggi | Harus sama atau setara |
| Aset atau objek transaksi | Tinggi | Blok, pabrik, anak usaha, lini bisnis |
| Periode | Sedang | Berita bisa terbit selang beberapa hari |
| Nilai transaksi | Sedang | Angka bisa berbeda antar media — itu konflik, bukan event berbeda |

**Aturan keputusan:** empat dimensi berbobot tinggi cocok → satu event. Bila ragu, **pisahkan dan tandai** bahwa keduanya mungkin peristiwa yang sama. Menggabungkan dua transaksi berbeda lebih merugikan daripada memisahkan satu transaksi menjadi dua.

## A3. Langkah penggabungan

1. **Buat satu event.**
2. **Gabungkan seluruh sumber** ke dalam daftar sumber event tersebut.
3. **Gunakan sumber resmi sebagai dasar utama** untuk fakta yang bertentangan.
4. **Catat perbedaan informasi antar media** — jangan dihapus (lihat Bagian C).
5. **Gunakan informasi terbaru yang sudah terverifikasi**, bukan sekadar yang paling baru terbit.
6. **Pertahankan timeline perubahan** — perkembangan lama tetap tercatat.

## A4. Yang tidak boleh digabung

| Situasi | Alasan |
|---|---|
| Dua transaksi berbeda dengan pihak berbeda | Peristiwa berbeda meskipun jenisnya sama |
| Rencana lama yang batal dan rencana baru yang serupa | Riwayatnya berbeda; hubungkan lewat timeline, jangan lebur |
| Aksi induk dan aksi anak usaha yang terpisah | Entitas berbeda; sebutkan keterkaitannya |
| Transaksi bertahap yang diumumkan terpisah | Bila masing-masing memiliki persetujuan sendiri, perlakukan sebagai event terkait, bukan satu event |

Untuk event yang berkaitan tetapi tidak sama, gunakan penanda: **"Terkait dengan: [event lain]"**.

## A5. Rangkaian transaksi

Akuisisi yang dibiayai rights issue adalah **satu rangkaian**, bukan dua event terpisah — lihat `corporate-action-taxonomy.md` §8. Tetapkan kategori utama, cantumkan kategori terkait.

Namun bila rights issue tersebut juga membiayai hal lain dan punya jadwal serta persetujuan sendiri, laporkan sebagai dua event yang saling dirujuk.

---

# BAGIAN B — VERIFIKASI

## B1. Yang diperiksa

| Sumber | Untuk memastikan |
|---|---|
| Keterbukaan informasi IDX | Adanya transaksi, nilai, pihak, jadwal |
| Pengumuman OJK | Persetujuan, pernyataan efektif |
| Website perusahaan & siaran pers | Pernyataan resmi perusahaan |
| Investor relations | Presentasi, materi RUPS, laporan |
| Regulator sektoral | Persetujuan khusus (KPPU, kementerian terkait) |
| Sumber pembanding | Konsistensi antar pemberitaan |

## B2. Lima status verifikasi

| Status | Arti | Tindakan |
|---|---|---|
| **Terverifikasi** | Fakta material dikonfirmasi sumber resmi | Confidence 4–5 |
| **Sebagian terverifikasi** | Sebagian fakta dikonfirmasi, sebagian belum | Sebutkan bagian mana yang mana |
| **Belum terverifikasi** | Belum ditemukan konfirmasi resmi | Confidence maksimal 3 |
| **Bertentangan** | Sumber saling berbeda | Terapkan Bagian C |
| **Kedaluwarsa** | Informasi resmi ada tetapi sudah lama dan mungkin berubah | Cari perkembangan terbaru; turunkan confidence |

## B3. Cara menulis hasil verifikasi

```
VERIFICATION
- Sumber resmi ditemukan: Ya — keterbukaan informasi IDX, 18 Juni 2026
- Pernyataan perusahaan: Ya — siaran pers 12 Juni 2026
- Jumlah media kredibel: 4 (Kontan, CNBC Indonesia, Bisnis Indonesia, Katadata)
- Belum terverifikasi: sumber pendanaan, jadwal closing, persetujuan KPPU
- Keterbatasan akses: artikel Bloomberg 14 Juni 2026 berbayar, tidak dapat diperiksa
```

Bagian **"belum terverifikasi"** wajib diisi. Bila semuanya terverifikasi, tulis "tidak ada" — jangan dihilangkan.

## B4. Aturan verifikasi

1. **Ketiadaan bukti bukan bukti ketiadaan.** Tidak menemukan keterbukaan informasi tidak berarti transaksinya tidak ada. Tulis "belum ditemukan pada sumber yang diperiksa", bukan "tidak ada".
2. **Sebutkan apa yang diperiksa.** Verifikasi yang tidak menyebut sumber apa yang dicek tidak dapat dinilai pengguna.
3. **Diam bukan konfirmasi.** Perusahaan yang tidak membantah bukan berarti membenarkan.
4. **Verifikasi bersifat per fakta**, bukan per event. Nilai transaksi bisa terverifikasi sementara jadwal belum.
5. **Cantumkan tanggal pemeriksaan.**

---

# BAGIAN C — KONFLIK SUMBER

## C1. Kapan terjadi

Sumber berbeda mengenai: nilai transaksi · tanggal · status · persentase saham · pihak terkait · tujuan · jadwal.

## C2. Enam langkah wajib

1. **Tampilkan perbedaannya** secara eksplisit.
2. **Sebutkan masing-masing sumber** beserta tanggalnya.
3. **Prioritaskan sumber resmi** bila ada.
4. **Jangan menghapus konflik** demi laporan yang terlihat rapi.
5. **Jangan menentukan sendiri** mana yang benar tanpa bukti.
6. **Tandai sebagai information gap** bila belum terselesaikan, dan turunkan confidence.

## C3. Format

```
⚠ Perbedaan informasi — nilai transaksi

- Kontan (12 Juni 2026): Rp2,4 triliun
- CNBC Indonesia (12 Juni 2026): "sekitar Rp2 triliun"
- Keterbukaan informasi IDX (18 Juni 2026): Rp2.380.000.000.000

Angka pada keterbukaan informasi dipakai sebagai acuan karena berasal
dari sumber resmi. Perbedaan pemberitaan awal kemungkinan karena
pembulatan, tetapi hal itu tidak dikonfirmasi.
```

Perhatikan kalimat terakhir: dugaan penyebab boleh disampaikan, **asalkan ditandai sebagai dugaan**.

## C4. Bila tidak ada sumber resmi

Jangan memilih. Tampilkan keduanya dan nyatakan bahwa perbedaan belum terselesaikan:

```
⚠ Perbedaan informasi — persentase kepemilikan

- Bisnis Indonesia (10 Juni 2026): 51%
- Katadata (11 Juni 2026): 55%

Belum ditemukan keterbukaan informasi yang memuat angka resmi.
Perbedaan ini dicatat sebagai information gap. Confidence: 2.
```

## C5. Kesalahan yang sering terjadi

| Kesalahan | Mengapa salah |
|---|---|
| Memilih angka terbaru | Terbit belakangan tidak berarti lebih akurat |
| Menggabungkan menjadi rentang ("Rp2–2,4 triliun") | Menciptakan angka yang tidak dinyatakan sumber mana pun |
| Mengambil rata-rata | Sama saja mengarang |
| Memilih sumber yang lebih terkenal | Reputasi bukan bukti |
| Menyembunyikan konflik | Menghilangkan informasi yang justru paling berguna bagi pengguna |
