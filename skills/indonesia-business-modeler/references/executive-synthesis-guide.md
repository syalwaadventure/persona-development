# Executive Synthesis Guide

> **Catatan gaya:** Tulis hasil dengan bahasa yang langsung, natural, dan sesuai konteks. Gunakan struktur ini sebagai panduan, bukan formulir yang harus diisi secara kaku.

Panduan ini adalah rujukan untuk **Phase 8 — Executive Decision Synthesis**
pada `SKILL.md`. Phase ini adalah **lapisan tambahan (additive layer)** yang
dijalankan setelah seluruh workflow analisis (Phase 1–7) selesai. Phase ini
tidak menggantikan Company Overview, Profit Model Analysis, Cash Flow
Analysis, Risk consolidation, atau mode lain — ia mengonsumsi hasilnya dan
mengubahnya menjadi bentuk yang siap dipakai Direksi untuk mengambil
keputusan.

Gunakan panduan ini bersama `assets/executive-management-report-template.md`.

---

## 1. Kapan Phase 8 dijalankan

Jalankan Phase 8 setelah Phase 1–7, dalam kondisi berikut:

1. Pengguna secara eksplisit meminta laporan/ringkasan **untuk Direksi**,
   **executive report**, **executive summary**, atau **management report**.
2. Pengguna mengunggah **laporan bulanan/berkala perusahaan** (laporan
   monitoring, laporan kinerja, laporan rapat direksi) dan meminta analisis
   tanpa menyebut mode tertentu — termasuk permintaan singkat seperti
   *"Analisis laporan bulanan perusahaan menggunakan Business Modeler."*
3. Analisis mencakup lebih dari satu mode (misalnya revenue + profit + cash
   flow + risk) sehingga pembaca membutuhkan satu simpulan terpadu.

Phase 8 **tidak** dijalankan otomatis ketika permintaan pengguna jelas-jelas
sempit dan teknis (misalnya "hitung BEP unit produk ini saja", "jelaskan
value proposition-nya saja") kecuali pengguna memang meminta ringkasan
eksekutif. Ini menjaga backward compatibility: prompt lama yang meminta satu
output spesifik tetap mendapat output spesifik itu saja, tidak dipaksa masuk
format 10 bagian.

Ketika ragu, tanyakan hanya jika benar-benar ambigu; bila permintaan berupa
laporan lengkap perusahaan, defaultnya adalah **menjalankan Phase 8** karena
itu adalah kasus penggunaan utama Direksi.

---

## 2. Executive Thinking Rules (internal, tidak ditampilkan)

Sebelum menulis Executive Summary, jawab lima pertanyaan berikut **secara
internal** — jangan ditampilkan ke pengguna sebagai chain-of-thought, cukup
gunakan hasilnya untuk membentuk isi laporan:

1. Jika saya adalah Direktur, apa yang **paling penting** saya ketahui dari
   laporan ini?
2. Apa **risiko terbesar** yang sedang dihadapi perusahaan saat ini?
3. Apa yang **harus diputuskan minggu ini** (tidak bisa ditunda)?
4. Apa yang **bisa ditunda** tanpa risiko material?
5. Apa **konsekuensinya** jika tidak ada tindakan sama sekali?

Jawaban ini menjadi kerangka Executive Summary dan Priority Decisions, bukan
konten yang ditampilkan apa adanya.

---

## 3. Business Interpretation Rules

Untuk **setiap indikator penting** (bukan setiap angka kecil), gunakan pola
lima langkah berikut sebelum menuliskannya ke laporan:

```
Apa yang terjadi
   ↓
Mengapa terjadi
   ↓
Dampak terhadap bisnis
   ↓
Implikasi terhadap Direksi
   ↓
Rekomendasi
```

Contoh singkat (bukan template kaku, sesuaikan bahasa):

> OCF terealisasi 783% dari RKAP (apa) — karena penerimaan besar dari dua
> proyek yang kebetulan cair bulan ini (mengapa) — sehingga kas terlihat
> sangat sehat padahal ini efek waktu, bukan perbaikan struktural (dampak) —
> Direksi perlu waspada supaya tidak salah baca kesehatan kas ke depan
> (implikasi) — sebaiknya proyeksi kas bulan berikutnya tetap dipantau
> terpisah dari windfall ini (rekomendasi).

Jangan berhenti di angka. Analisis yang hanya menampilkan "OCF 783% dari
RKAP" tanpa keempat langkah berikutnya dianggap tidak lulus QA Phase 8.

---

## 4. Root Cause Pattern (untuk Key Issues)

Untuk setiap masalah yang masuk **Key Issues**, gunakan pola yang sama namun
difokuskan ke root cause:

```
Apa yang terjadi
   ↓
Mengapa terjadi
   ↓
Apa dampaknya
   ↓
Mengapa Direksi harus peduli
```

Root cause harus berdasarkan evidence dari dokumen (termasuk bagian
"Penyebab" bila laporan sumber sudah memilikinya, seperti pada laporan
monitoring risiko). Jika evidence tidak menyebutkan penyebab, nyatakan
sebagai `INFORMATION GAP`, jangan mengarang penyebab.

---

## 5. Business Impact Dimensions

Setiap isu utama sedapat mungkin dipetakan ke dimensi berikut. Jika suatu
dimensi tidak relevan atau tidak ada datanya, lewati — jangan dipaksakan
atau diisi dengan asumsi:

- **Operasional** — proses, jadwal proyek, kualitas, kapasitas.
- **Keuangan** — laba, kas, utang, piutang, biaya.
- **Pelanggan** — kepuasan, konsentrasi pelanggan, keberlanjutan kontrak.
- **SDM** — beban kerja, retensi, produktivitas, biaya tenaga kerja.
- **Strategi** — arah bisnis, portofolio, ekspansi, aksi korporasi.
- **Sustainability** — keberlanjutan operasi, K3LH, risiko jangka panjang.

---

## 6. Prioritization Engine

Urutkan seluruh isu (Key Issues, Top Risks, dan Priority Decisions)
berdasarkan lima faktor berikut. Faktor ini dinilai kualitatif
(tinggi/sedang/rendah) berdasarkan evidence, bukan skor numerik yang
dikarang:

| Faktor | Pertanyaan panduan |
|---|---|
| Financial impact | Seberapa besar dampaknya ke laba, kas, atau neraca? |
| Business impact | Seberapa luas dampaknya ke operasional/pelanggan/SDM/strategi? |
| Urgency | Seberapa cepat ini harus ditangani (minggu ini vs kuartal ini)? |
| Strategic importance | Apakah ini memengaruhi arah bisnis jangka panjang? |
| Probability | Seberapa besar kemungkinan risiko ini benar-benar terjadi, berdasarkan evidence yang ada? |

Hasil pengurutan ditampilkan sebagai **Priority 1, Priority 2, Priority 3**
(dan seterusnya bila perlu), bukan sekadar daftar tanpa urutan. Jelaskan
singkat alasan urutan tersebut (mis. "Priority 1 karena dampak finansial
langsung ke neraca dan disebutkan eksplisit memengaruhi keputusan kreditur").

Risiko juga dikelompokkan ke **Critical / High / Medium / Low** dengan alasan
pengelompokan yang jelas — bukan hanya label.

---

## 7. Company Health Assessment

Tentukan status keseluruhan perusahaan: **Healthy / Needs Attention /
Critical**. Aturan penentuan (indikatif, gunakan judgement berbasis evidence,
bukan formula kaku):

- **Healthy** — indikator utama (laba, kas, risiko) berada dalam ambang aman
  dan tidak ada isu yang mengancam kelangsungan operasional/pendanaan.
- **Needs Attention** — ada satu atau lebih indikator di bawah target atau
  ambang toleransi, tetapi belum mengancam kelangsungan usaha; perlu
  intervensi terencana.
- **Critical** — ada indikator yang menembus batas toleransi/tolerance
  (misalnya rasio utang jauh di atas batas, kas negatif berkelanjutan, atau
  risiko yang secara eksplisit disebut memengaruhi keberlangsungan fasilitas
  pendanaan atau operasi), sehingga membutuhkan keputusan segera.

Status harus disertai **alasan berbasis evidence** — dilarang hanya
menampilkan label tanpa penjelasan. Jika entitas terdiri dari induk dan anak
usaha dengan status berbeda, jelaskan keduanya secara terpisah sebelum
menyimpulkan status gabungan.

---

## 8. Confidence pada Rekomendasi

Setiap rekomendasi di bagian Director Recommendation dan Priority Decisions
diberi catatan singkat tingkat keyakinan, mengikuti skala confidence yang
sama dengan `references/source-and-confidence-guide.md`
(`HIGH CONFIDENCE` / `MEDIUM CONFIDENCE` / `LOW CONFIDENCE` /
`NOT CALCULABLE`), dengan penjelasan singkat apakah evidence yang mendasari
sudah cukup atau masih memerlukan validasi/data tambahan.

---

## 9. Hubungan dengan Mode Analisis Lain

Phase 8 adalah **lapisan sintesis**, bukan mode baru yang berdiri sendiri
menggantikan mode lain. Urutan kerja tetap:

```
Mode analisis yang relevan (Profit / Cash Flow / Risk / Company Deep Dive / dst.)
        ↓
Phase 1–7 (Scope → Evidence → Structural → Relationship → Quantitative → Interpretation → QA)
        ↓
Phase 8 — Executive Decision Synthesis (opsional, dijalankan sesuai Bagian 1 di atas)
```

Jika pengguna hanya meminta satu mode teknis tanpa indikasi kebutuhan
ringkasan Direksi, keluarkan output mode tersebut seperti biasa (perilaku
lama tetap berlaku, tidak berubah).

---

## 10. Integrity Checks Phase 8

- Jangan mengarang angka atau fakta baru; Phase 8 hanya menyintesis apa yang
  sudah dihasilkan Phase 1–7.
- Jangan mengubah rekomendasi menjadi keputusan final atas nama Direksi.
  Gunakan kata seperti "disarankan", "perlu dipertimbangkan", bukan "telah
  diputuskan".
- Jangan mengisi Business Impact pada dimensi yang tidak punya evidence.
- Jangan memberi status Company Health tanpa alasan berbasis evidence.
- Executive Summary wajib dapat dibaca dalam waktu kurang dari dua menit
  (indikatif: maksimum 10 poin, masing-masing 1–2 kalimat).
