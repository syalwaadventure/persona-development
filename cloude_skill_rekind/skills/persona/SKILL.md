---
name: persona
description: > Merancang, mengembangkan, merevisi, mengaudit, dan menguji persona untuk berbagai jenis AI agent. Gunakan saat pengguna meminta identitas, perilaku, gaya komunikasi, scope, batas kewenangan, atau aturan agent.
metadata:
  version: "0.1.0"
  status: draft
---

# Persona Skill

Skill ini **membuat artefak persona**, bukan menjalankan persona.
Persona di sini berarti **spesifikasi perilaku agent**: identitas, tujuan, scope, batas kewenangan, aturan sumber, format jawaban, dan cara menangani kegagalan — bukan sekadar gaya bicara.

Skill ini **general-purpose**. Tidak boleh memuat aturan domain tertentu (organisasi, industri, atau produk apa pun) sebagai default. Aturan domain hanya masuk bila pengguna menyediakannya.

---

## 1. Empat mode kerja

Tentukan mode di awal, lalu sebutkan mode tersebut pada baris pertama respons.

| Mode | Kapan dipakai | Referensi yang dibaca |
|---|---|---|
| **A — Persona baru** | Pengguna ingin membuat persona dari nol | `persona-components.md`, `agent-type-taxonomy.md`, `persona-templates.md`, `authority-and-safety.md` |
| **B — Revisi persona** | Persona sudah ada, ada bagian yang diubah | `persona-components.md` (blok terdampak saja), `review-checklist.md` |
| **C — Audit persona** | Menilai persona yang dibuat pihak lain | `review-checklist.md`, `persona-components.md` |
| **D — Pengujian persona** | Menyusun/menjalankan test | `testing-guide.md` |

Baca referensi **secara selektif**. Jangan memuat seluruh referensi sekaligus.
Jika pengguna nonteknis bingung dengan istilah, rujuk `references/glossary.md`.

---

## 2. Mode A — Membuat persona baru

### Langkah A1. Klasifikasi tipe agent
Cocokkan permintaan ke salah satu tipe di `references/agent-type-taxonomy.md`. Tipe menentukan default awal (gaya, kedalaman, ketatnya aturan sumber). Jika tidak cocok dengan tipe mana pun, gunakan profil generik dan katakan demikian.

### Langkah A2. Periksa input wajib
Input **wajib** (tanpa ini, jangan lanjut):
1. Tujuan agent — masalah apa yang diselesaikan.
2. Target pengguna.
3. Domain atau ruang lingkup kerja.

Input **penting** (tanya bila belum ada, tetapi boleh diasumsikan dengan penandaan):
4. Sumber informasi yang boleh dipakai.
5. Batas kewenangan.
6. **Bahasa dan tingkat formalitas — SELALU tanyakan secara eksplisit, jangan pernah diasumsikan.**
7. Format keluaran yang diharapkan.

Input **opsional**: nama agent, tingkat risiko domain, contoh pertanyaan nyata, contoh jawaban baik/buruk, persona versi sebelumnya, larangan spesifik organisasi.

**Aturan bertanya:** maksimal 3 pertanyaan per putaran, terarah, tidak menanyakan hal yang sudah jelas dari konteks. Pertanyaan bahasa/formalitas selalu termasuk. Bila input wajib sudah lengkap dan hanya opsional yang kosong, **lanjutkan** dengan asumsi bertanda.

### Langkah A3. Tentukan tingkat risiko domain
Rendah / sedang / tinggi — lihat `references/authority-and-safety.md`. Tingkat risiko menentukan ketatnya source rules, authority boundaries, dan wajib-tidaknya disclaimer.

### Langkah A4. Susun Persona Brief
Ringkasan satu halaman menggunakan template di `references/persona-templates.md`. **Selalu tampilkan brief dan minta persetujuan sebelum menulis spesifikasi penuh.** Jangan lompat langsung ke dokumen lengkap.

### Langkah A5. Susun Persona Specification (12 blok wajib)

| # | Blok | Kelompok |
|---|---|---|
| 1 | Identity | APA |
| 2 | Purpose | APA |
| 3 | Audience | APA |
| 4 | Scope | APA |
| 5 | Exclusions | APA |
| 6 | Behavior & Communication Style | BAGAIMANA |
| 7 | Reasoning Steps | BAGAIMANA |
| 8 | Source Rules | BATAS |
| 9 | Authority Boundaries | BATAS |
| 10 | Response Format | BAGAIMANA |
| 11 | Failure Handling | KETIKA GAGAL |
| 12 | Safety & Confidentiality | BATAS |

Definisi rinci, pertanyaan pemandu, dan contoh isi baik vs buruk ada di `references/persona-components.md`.

**Aturan blok:**
- Semua 12 blok wajib ada. Tidak boleh ada blok kosong.
- Blok yang informasinya belum tersedia ditulis dengan placeholder eksplisit, contoh: `[BELUM DITENTUKAN — perlu keputusan pemilik proses]`.
- Jangan mengarang isi blok.

### Langkah A6. Conflict check
Periksa minimal: Scope vs Exclusions tumpang tindih; Authority Boundaries bertentangan dengan Purpose; Source Rules tidak mungkin dipenuhi dengan sumber yang tersedia; Response Format bertentangan dengan gaya komunikasi; Failure Handling tidak mencakup semua kegagalan yang mungkin dari Scope. Laporkan setiap konflik yang ditemukan.

### Langkah A7. Buat contoh input–output
Minimal 3 pasang: (a) pertanyaan normal dalam scope, (b) pertanyaan di luar scope, (c) pertanyaan yang informasinya tidak tersedia. Tambah bila risiko domain tinggi.

### Langkah A8. Buat test case dan acceptance criteria
Turunkan dari Scope, Exclusions, dan Authority Boundaries. Ikuti `references/testing-guide.md`.

### Langkah A9. Self-review
Jalankan checklist di `references/review-checklist.md`.

### Langkah A10. Tampilkan asumsi, risiko, dan pertanyaan terbuka
Selalu. Tanpa pengecualian.

### Langkah A11. Tawarkan format keluaran
Dokumen penuh, atau **Persona Block** ringkas siap tempel ke SKILL.md skill lain.

---

## 3. Mode B — Revisi persona

1. Identifikasi nama persona dan versinya.
2. Petakan permintaan ke blok yang terdampak. **Ubah hanya blok tersebut.** Jangan menulis ulang seluruh dokumen.
3. Conflict check terhadap blok lain yang tidak diubah.
4. Tampilkan tabel perbandingan sebelum/sesudah untuk setiap blok yang berubah.
5. Perbarui atau tambahkan test case; tandai regression test yang harus dijalankan.
6. Rekomendasikan versi (semantic versioning: MAJOR perubahan tidak kompatibel, MINOR penambahan kemampuan, PATCH perbaikan kecil).
7. Buat changelog entry dan usulan commit message.

Keluaran revisi wajib memuat: alasan perubahan, blok yang berubah, dampak terhadap perilaku agent, test yang harus dijalankan, risiko tersisa, rekomendasi versi, commit message.

---

## 4. Mode C — Audit persona

1. Petakan isi persona yang ada ke 12 blok. Tandai blok yang hilang atau tidak lengkap.
2. Beri skor 1–5 per blok menggunakan kriteria di `references/review-checklist.md`.
3. Daftar temuan: ambiguitas, konflik antar-aturan, celah kewenangan, risiko keamanan, ketergantungan pada asumsi tak tertulis.
4. Rekomendasi perbaikan berprioritas (kritis / penting / opsional).
5. Jangan menyatakan persona "lulus" atau "final" — itu keputusan pemilik proses.

---

## 5. Mode D — Pengujian persona

Ikuti `references/testing-guide.md`. Sepuluh jenis test minimum: trigger, non-trigger, happy path, ambiguous input, missing information, adversarial, boundary, source accuracy, regression, output quality.

Format hasil: Test ID, versi persona, tanggal, prompt, expected result, actual result, status (PASS/PARTIAL/FAIL/BLOCKED), skor 1–5, issue, recommended action.

Ambang siap review: tidak ada kegagalan kritis, tidak mengarang fakta/sumber, rata-rata skor ≥ 4, tidak ada skor < 3, trigger dan non-trigger bekerja, regression test lulus.

---

## 6. Aturan sumber dan akurasi

1. Jangan mengarang nama organisasi, jabatan, kebijakan, dokumen, tanggal, atau angka. Gunakan placeholder bertanda, contoh `[NAMA ORGANISASI — perlu dikonfirmasi]`.
2. Bedakan secara eksplisit: **fakta dari pengguna**, **asumsi skill**, **praktik umum**, dan **rekomendasi**.
3. Praktik umum tidak boleh ditulis sebagai kebijakan resmi organisasi.
4. Bila informasi pengguna saling bertentangan, tampilkan pertentangannya dan minta keputusan. Jangan memilih sendiri.
5. Persona yang dihasilkan wajib memuat Source Rules-nya sendiri; persona tanpa aturan sumber dianggap belum lengkap.
6. Skill ini tidak memverifikasi kebenaran fakta domain. Validasi adalah tanggung jawab pemilik proses.
7. Cantumkan daftar asumsi di akhir setiap dokumen.

---

## 7. Batas kewenangan skill ini

- Tidak menyetujui, memvalidasi, atau mengesahkan persona.
- Tidak menetapkan kebijakan organisasi.
- Tidak menyatakan persona "final". Gunakan status: **draft**, **release candidate**, atau **tervalidasi** (yang terakhir hanya setelah pengguna menyatakannya).
- Tidak membuat paket ZIP atau rilis tanpa permintaan eksplisit dan pemeriksaan source terlebih dahulu.
- Tidak melakukan deployment, integrasi API, atau konfigurasi platform.

**Kewajiban terhadap persona yang dihasilkan:** setiap persona wajib memiliki blok Authority Boundaries terisi. Bila pengguna tidak menyebutkan, usulkan default konservatif dan tandai sebagai asumsi. Gunakan skala kewenangan lima tingkat (informational → advisory → drafting → recommending → deciding) dari `references/authority-and-safety.md`. Level `deciding` selalu memicu peringatan risiko eksplisit.

---

## 8. Larangan keras

Tolak, jelaskan alasannya, dan tawarkan alternatif bila diminta:

1. Persona yang menyamar sebagai manusia atau menyangkal dirinya AI ketika ditanya.
2. Persona yang meniru orang nyata yang teridentifikasi tanpa izin.
3. Menyimpan credential, API key, token, password, atau data pribadi di dalam persona. Gunakan placeholder.
4. Persona yang dirancang untuk menipu, memanipulasi, atau menekan pengguna.
5. Persona yang menyatakan kebijakan resmi organisasi tanpa dokumen sumber.
6. Persona untuk memberi nasihat hukum/medis/keuangan definitif tanpa batas kewenangan dan disclaimer eksplisit.
7. Memasukkan aturan domain-spesifik dari contoh use case sebagai default skill ini.

Bila menemukan indikasi data sensitif dalam input pengguna: hentikan proses, tandai bagiannya, jelaskan risikonya, sarankan sanitasi, minta validasi pemilik data.

---

## 9. Batas terhadap skill lain

Skill ini hanya menghasilkan **blok persona**. Aturan kerja domain tetap berada di skill domainnya masing-masing.

- Diminta menulis konten substantif (bab buku, laporan, analisis) → di luar scope; arahkan ke skill yang sesuai.
- Diminta menjalankan persona yang sudah jadi → itu pemakaian, bukan pembuatan; skill ini tidak aktif.
- Diminta membuat buyer persona / persona pelanggan pemasaran → istilah berbeda; klarifikasi maksud pengguna.

---

## 10. Format respons

Untuk pekerjaan pembuatan atau revisi persona, gunakan urutan:

1. Mode dan skill yang sedang dikerjakan
2. Ringkasan kebutuhan
3. Keputusan desain
4. Isi atau revisi dokumen
5. Contoh input–output
6. Testing plan
7. Asumsi
8. Risiko dan batasan
9. Versioning dan changelog
10. Langkah berikutnya

Untuk pertanyaan sederhana, jawab langsung tanpa struktur penuh.

---
## Continuous Improvement

Identifikasi peluang peningkatan berdasarkan pertanyaan, feedback, koreksi,
dan hasil testing.

Klasifikasikan interaksi penting sebagai:

- SUCCESSFUL;
- PARTIALLY SUCCESSFUL;
- FAILED;
- AMBIGUOUS;
- USER CORRECTION;
- NEW USE CASE;
- NEW PATTERN.

Ketika ditemukan gap, buat Learning Record yang berisi:

1. Learning ID.
2. Tanggal.
3. Permintaan pengguna.
4. Perilaku saat ini.
5. Perilaku yang diharapkan.
6. Gap yang ditemukan.
7. Sumber atau validasi yang diperlukan.
8. Usulan perubahan.
9. File yang terdampak.
10. Regression test yang diperlukan.
11. Status pembelajaran.

Jangan langsung mengubah skill berdasarkan satu masukan pengguna.

Perubahan permanen hanya diterapkan setelah divalidasi, disetujui manusia,
ditambahkan test case, dan dicatat dalam changelog.

## 11. Daftar referensi

| File | Dibaca ketika |
|---|---|
| `references/persona-components.md` | Menyusun atau menilai 12 blok |
| `references/persona-templates.md` | Membutuhkan format brief, spesifikasi, atau persona block |
| `references/agent-type-taxonomy.md` | Menentukan tipe agent dan default awal |
| `references/authority-and-safety.md` | Menentukan kewenangan, risiko domain, aturan keamanan |
| `references/failure-handling-patterns.md` | Menyusun blok 11 |
| `references/review-checklist.md` | Self-review (A9) dan audit (Mode C) |
| `references/testing-guide.md` | Mode D dan langkah A8 |
| `references/glossary.md` | Pengguna nonteknis butuh definisi istilah |
