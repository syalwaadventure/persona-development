# Review Checklist

> **Catatan gaya:** Tulis hasil dengan bahasa yang langsung, natural, dan sesuai konteks. Gunakan struktur ini sebagai panduan, bukan formulir yang harus diisi secara kaku.


Dipakai pada langkah A9 (self-review) dan Mode C (audit persona pihak lain).

---

## Bagian 1 — Kelengkapan struktur

- [ ] Kedua belas blok ada dan tidak kosong.
- [ ] Blok yang belum diketahui memakai placeholder bertanda, bukan diisi karangan.
- [ ] Metadata lengkap: nama, versi, status, tanggal, pemilik proses, tipe agent, tingkat risiko.
- [ ] Minimal 3 pasang contoh input–output tersedia.
- [ ] Test scenarios dan acceptance criteria tersedia.
- [ ] Daftar asumsi tercantum.
- [ ] Riwayat versi tercantum.

## Bagian 2 — Kejelasan dan keteruji-an

- [ ] Setiap aturan dapat diturunkan menjadi test case.
- [ ] Tidak ada frasa kabur tanpa penjelasan operasional ("profesional", "cerdas", "gunakan penilaian terbaik").
- [ ] Scope disebut dalam bentuk daftar topik dan jenis tugas, bukan kalimat umum.
- [ ] Gaya komunikasi menyebut bahasa, formalitas, panjang, dan kedalaman secara konkret.
- [ ] Response format menyebut struktur, bukan hanya "rapi dan jelas".

## Bagian 3 — Konsistensi internal

- [ ] Scope dan Exclusions tidak tumpang tindih.
- [ ] Authority Boundaries tidak bertentangan dengan Purpose.
- [ ] Level kewenangan konsisten dengan tingkat risiko domain.
- [ ] Source Rules dapat dipenuhi dengan sumber yang benar-benar tersedia.
- [ ] Response Format tidak bertentangan dengan Behavior & Communication Style.
- [ ] Failure Handling mencakup semua jenis kegagalan yang mungkin timbul dari Scope.
- [ ] Tidak ada aturan yang sama diulang di dua blok dengan rumusan berbeda.

## Bagian 4 — Keamanan

- [ ] Tidak ada credential, token, password, atau data pribadi.
- [ ] Tidak ada dokumen rahasia atau tautan internal sensitif.
- [ ] Agent tidak diminta menyamar sebagai manusia.
- [ ] Aturan anti-manipulasi instruksi tercantum.
- [ ] Jalur eskalasi terisi bila risiko sedang atau tinggi.
- [ ] Larangan mengarang fakta tercantum di blok Source Rules.

## Bagian 5 — Netralitas skill

- [ ] Tidak ada aturan domain tertentu yang masuk sebagai default skill `persona`.
- [ ] Metodologi kerja domain tetap berada di skill domainnya, bukan di persona.
- [ ] Persona dapat dipakai ulang untuk agent lain dengan mengganti isinya, bukan strukturnya.

---

## Skoring per blok (Mode C — audit)

| Skor | Kriteria |
|---|---|
| **5** | Lengkap, konkret, dapat diuji, konsisten dengan blok lain |
| **4** | Lengkap dan konsisten, ada satu-dua rumusan yang masih kabur |
| **3** | Isi ada tetapi terlalu umum; perlu revisi agar dapat diuji |
| **2** | Sebagian besar kabur, atau bertentangan dengan blok lain |
| **1** | Tidak ada, kosong, atau menimbulkan risiko (mengarang, melampaui kewenangan, tidak aman) |

**Ambang siap review:** rata-rata ≥ 4, tidak ada blok < 3, tidak ada temuan kategori kritis.

---

## Kategori temuan audit

| Kategori | Definisi | Contoh |
|---|---|---|
| **Kritis** | Menimbulkan risiko keamanan, hukum, atau kebocoran data; harus diperbaiki sebelum dipakai | Credential di dalam dokumen; agent diberi kewenangan `deciding` pada domain berisiko tinggi tanpa kriteria tertulis |
| **Penting** | Membuat perilaku agent tidak dapat diprediksi | Blok Failure Handling hanya mencakup satu situasi; Scope tumpang tindih dengan Exclusions |
| **Opsional** | Meningkatkan kualitas tetapi tidak menghalangi pemakaian | Contoh input–output kurang variatif; format tabel belum konsisten |

---

## Format laporan audit

```markdown
# Audit Persona: [Nama] v[versi]
Tanggal: [—] | Auditor: skill `persona` Mode C

## Skor per blok
| # | Blok | Skor | Catatan |
|---|---|---|---|
| 1 | Identity | [1–5] | [—] |
| ... | | | |
| **Rata-rata** | | **[—]** | |

## Temuan
### Kritis
1. [temuan] — dampak: [—] — perbaikan: [—]
### Penting
### Opsional

## Blok yang hilang
[daftar]

## Rekomendasi prioritas
1. [—]

## Catatan
Audit ini bukan persetujuan. Keputusan kelayakan pakai ada pada pemilik proses.
```
