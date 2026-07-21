# Event Status Guide

Dipakai pada Fase 5. Lima belas status. **Setiap penetapan status wajib disertai dasar.**

---

## 1. Progresi status

```
RUMOR → MEDIA REPORT → MANAGEMENT STATEMENT → UNDER REVIEW → PLANNED
      → REGULATORY SUBMISSION → AWAITING APPROVAL
      → SHAREHOLDER APPROVED / REGULATOR APPROVED
      → IN PROGRESS → COMPLETED

Jalur keluar kapan saja: CANCELLED · REJECTED · DELAYED
Status khusus: UNCONFIRMED
```

Event tidak selalu melewati seluruh tahap. Yang penting bukan urutannya, melainkan **bukti apa yang ditemukan**.

---

## 2. Definisi dan bukti yang diperlukan

| Status | Arti | Bukti minimum |
|---|---|---|
| **RUMOR** | Beredar tanpa sumber yang dapat dipertanggungjawabkan | Sumber tidak jelas, "menurut sumber", media sosial |
| **MEDIA REPORT** | Diberitakan media kredibel, belum ada konfirmasi perusahaan | Satu atau lebih media Tier 2 |
| **MANAGEMENT STATEMENT** | Manajemen menyatakan sesuatu secara publik | Kutipan direksi, wawancara, konferensi pers |
| **UNDER REVIEW** | Sedang dikaji, belum diputuskan | Pernyataan "sedang dikaji", "masih dievaluasi" |
| **PLANNED** | Rencana diumumkan resmi, belum ada persetujuan | Siaran pers atau keterbukaan informasi berisi rencana |
| **REGULATORY SUBMISSION** | Dokumen diajukan ke regulator | Pernyataan pendaftaran, pengajuan ke OJK/KPPU |
| **AWAITING APPROVAL** | Menunggu keputusan pemegang saham atau regulator | Agenda RUPS terbit, permohonan tercatat |
| **SHAREHOLDER APPROVED** | Disetujui RUPS | Hasil RUPS |
| **REGULATOR APPROVED** | Disetujui regulator | Pernyataan efektif, persetujuan KPPU/OJK/kementerian |
| **IN PROGRESS** | Sedang dieksekusi | Pembayaran berjalan, pengalihan bertahap, konstruksi dimulai |
| **COMPLETED** | Selesai dan terealisasi | Pengumuman penyelesaian, perubahan kepemilikan tercatat |
| **CANCELLED** | Dibatalkan oleh para pihak | Pengumuman pembatalan |
| **REJECTED** | Ditolak regulator atau pemegang saham | Keputusan penolakan |
| **DELAYED** | Ditunda, belum batal | Pengumuman penundaan, tenggat lewat tanpa penjelasan |
| **UNCONFIRMED** | Ada indikasi, tetapi tidak cukup untuk status lain | Informasi terlalu tipis atau bertentangan |

---

## 3. Format wajib penetapan status

```
Status: PLANNED

Dasar:
Manajemen mengumumkan rencana melalui siaran pers 12 Juni 2026 dan
keterbukaan informasi IDX 13 Juni 2026. Belum ditemukan agenda RUPS
maupun pengajuan ke regulator pada sumber yang diperiksa hingga
20 Juli 2026.
```

Dasar memuat tiga unsur:
1. **Bukti yang ditemukan** — sumber dan tanggalnya.
2. **Bukti yang belum ditemukan** — yang seharusnya ada untuk status berikutnya.
3. **Tanggal pemeriksaan.**

Status tanpa dasar adalah **kegagalan kritis** dalam testing.

---

## 4. Aturan penetapan

1. **Status ditentukan oleh bukti tertinggi yang ditemukan**, bukan oleh nada pemberitaan. Sepuluh berita yang menyebut "hampir pasti" tetap menghasilkan MEDIA REPORT bila tidak ada keterbukaan informasi.
2. **Jumlah media tidak menaikkan status.** Lima portal memberitakan hal yang sama tetap MEDIA REPORT — itu satu event dengan lima sumber, bukan bukti yang lebih kuat.
3. **Jangan menaikkan status karena logis.** Fakta bahwa RUPS "biasanya menyetujui" tidak menjadikan status SHAREHOLDER APPROVED.
4. **Persetujuan bersifat spesifik.** Persetujuan RUPS bukan persetujuan regulator, dan sebaliknya. Bila keduanya diperlukan, sebutkan mana yang sudah dan mana yang belum.
5. **Status dapat mundur.** Event yang tadinya PLANNED bisa menjadi DELAYED atau CANCELLED. Perbarui, dan pertahankan riwayatnya di timeline.
6. **Tanggal pemeriksaan wajib disebut.** Status adalah potret pada suatu tanggal, bukan keadaan abadi.

---

## 5. Membedakan status yang mirip

| Sering tertukar | Pembeda |
|---|---|
| RUMOR vs MEDIA REPORT | Apakah media kredibel memberitakan dengan atribusi jelas |
| MEDIA REPORT vs MANAGEMENT STATEMENT | Apakah ada pernyataan yang dapat diatribusikan ke manajemen |
| MANAGEMENT STATEMENT vs PLANNED | Apakah rencananya sudah resmi diumumkan atau baru disinggung |
| UNDER REVIEW vs PLANNED | Sudah diputuskan untuk dilakukan, atau masih dikaji |
| AWAITING APPROVAL vs IN PROGRESS | Menunggu keputusan, atau keputusan sudah ada dan sedang dijalankan |
| IN PROGRESS vs COMPLETED | Apakah ada pengumuman penyelesaian |
| DELAYED vs CANCELLED | Apakah ada pernyataan pembatalan, atau sekadar mundur |
| UNCONFIRMED vs RUMOR | UNCONFIRMED: ada indikasi tetapi tidak jelas. RUMOR: beredar tanpa dasar |

---

## 6. Event dengan status majemuk

Transaksi besar sering memerlukan beberapa persetujuan. Tampilkan rinciannya:

```
Status: AWAITING APPROVAL

Dasar:
- RUPS Luar Biasa: dijadwalkan 5 Agustus 2026 (belum berlangsung)
- KPPU: notifikasi diajukan 20 Juni 2026, belum ada keputusan
- OJK: belum ditemukan pengajuan pada sumber yang diperiksa

Status keseluruhan mengikuti tahap terendah yang belum terpenuhi.
```

**Aturan:** status keseluruhan mengikuti **tahap terendah yang belum terpenuhi**, bukan yang tertinggi yang sudah tercapai.

---

## 7. Status dan confidence

Keduanya berbeda dan tidak boleh dicampur.

- **Status** menjawab: sejauh mana peristiwanya berkembang.
- **Confidence** menjawab: seberapa kuat dasar informasi kita.

Contoh: event berstatus COMPLETED yang hanya bersumber dari satu media tanpa konfirmasi resmi tetap berconfidence rendah. Sebaliknya, event berstatus RUMOR bisa saja diberitakan banyak media kredibel — tetap confidence 1–2 karena tidak ada konfirmasi.

Panduan skor: `scoring-guide.md`.
