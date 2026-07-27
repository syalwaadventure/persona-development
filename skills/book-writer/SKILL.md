---
name: book-writer
description: >-
  Merancang, menulis, merevisi, mengaudit, dan memublikasikan buku, handbook,
  modul, manual, serta dokumentasi sebagai HTML mandiri yang terstruktur,
  source-traceable, accessible, dan siap dibaca atau dicetak.
---

# Book Writer

Skill serbaguna untuk menghasilkan **buku utuh** dan mengemasnya sebagai **satu file HTML mandiri** bertema gelap: nyaman dibaca di layar, isinya dapat dicari, dan rapi saat dicetak A4.

Skill ini **netral topik**. Tidak terikat pada organisasi, perusahaan, atau bidang tertentu — semua konteks berasal dari permintaan dan dokumen pengguna.

Penggunanya **nonteknis**. Jangan menuntut mereka menyiapkan berkas, menulis kode, atau memahami istilah teknis.

Tiga prinsip yang membedakan skill ini:

1. **Struktur mengikuti jenis buku** — bukan satu template untuk semua.
2. **Panjang dikendalikan page budget** — dihitung, bukan ditebak.
3. **Fakta terikat pada sumber** — yang belum ada menjadi placeholder, bukan karangan.
4. **Setiap bab dapat ditelusuri** — klaim material, tabel, gambar, dan contoh
   memiliki source/assumption status.
5. **Publikasi bukan sekadar menulis HTML** — struktur, aksesibilitas, print,
   navigation, dan QA harus diperiksa.

## Standar gaya penulisan

Buku harus terdengar seperti ditulis editor atau praktisi yang memahami pembacanya. Struktur tetap rapi, tetapi naskah tidak boleh terasa seperti susunan poin yang diperpanjang.

- Buka bab dengan masalah, situasi, atau pertanyaan yang dekat dengan pembaca.
- Jelaskan ide dengan alur sebab-akibat, bukan definisi berturut-turut.
- Pakai contoh konkret setelah konsep penting.
- Variasikan panjang kalimat dan paragraf.
- Gunakan daftar hanya ketika pembaca memang perlu memindai langkah atau pilihan.
- Hindari pengulangan isi dengan kata yang berbeda demi menambah halaman.
- Jangan memakai frasa generik seperti “di era digital”, “sangat penting”, atau “secara keseluruhan” tanpa alasan yang jelas.
- Transisi antarbab harus menyambung gagasan, bukan sekadar “pada bab berikutnya”.

Sebelum publikasi, baca `references/natural-language-guide.md` dan lakukan natural-language review selain editorial review.


---

## 1. Mode Kerja

Tentukan mode secara internal. Jangan mengumumkan nama mode pada baris pertama kecuali pengguna memang meminta penjelasan proses.

| Mode | Fungsi | Pemicu |
|---|---|---|
| **Create** | Buku baru, workflow 7 fase penuh | Permintaan buku baru |
| **Fast Draft** | Draft langsung tanpa menunggu persetujuan | Pengguna minta draft cepat, **atau** input penting sudah lengkap |
| **Revise** | Mengubah bab/bagian tertentu | "ubah bab 3", "perbaiki bagian X" |
| **Expand** | Menambah bab atau memperdalam isi | "tambah bab tentang Y" |
| **Condense** | Memadatkan tanpa membuang informasi kritis | "terlalu panjang", "ringkas jadi 40 halaman" |
| **Audit** | Menilai buku yang ada tanpa mengubahnya | "periksa buku ini", "apa yang kurang" |
| **Publication** | Membangun keluaran final + QA Report | "jadikan HTML", "siapkan untuk cetak" |

Perpindahan mode cukup dijelaskan bila berdampak pada pekerjaan pengguna. Mode Revise, Expand, dan Condense mengikuti `references/revision-guide.md`.

---

## 2. Input yang Perlu Dipahami

**Wajib — tanpa ini jangan mulai:**
1. Topik utama
2. Tujuan buku
3. Target pembaca

**Penting — tanyakan bila belum ada, maksimal 3 pertanyaan sekali putaran:**
4. Jenis buku
5. Sumber atau dokumen referensi
6. Panjang yang diinginkan
7. **Bahasa buku — SELALU tanyakan secara eksplisit. Jangan pernah diasumsikan**, termasuk ketika pengguna menulis dalam bahasa tertentu. Bahasa percakapan tidak selalu sama dengan bahasa buku.

**Diturunkan otomatis bila tidak disebut, dan ditandai sebagai asumsi:**

| # | Input | Default bila kosong |
|---|---|---|
| 8 | Tingkat pengetahuan pembaca | Diturunkan dari target pembaca; bila tetap tidak jelas: pemula |
| 9 | Gaya penulisan dan formalitas | Profesional, natural, ramah, tidak kaku |
| 10 | Struktur wajib | Blueprint jenis buku di `references/book-types.md` |
| 11 | Elemen visual | Dipilih dari jenis buku dan isi |
| 12 | Format akhir | Satu file HTML mandiri, tema gelap |
| 13 | Status publikasi | Draft |
| 14 | Hasil yang diharapkan pembaca | Diturunkan dari tujuan buku |
| 15 | Judul | Working title diusulkan skill |
| 16 | Klasifikasi kerahasiaan | Tidak dicantumkan; ditanya hanya bila sumber tampak internal |

**Jangan menginterogasi.** Jangan menanyakan ulang hal yang sudah jelas dari permintaan. Bila input wajib lengkap, lanjutkan dengan asumsi bertanda daripada menahan pekerjaan.

---

## 3. Workflow Tujuh Fase

```
PHASE 1  Requirement Analysis  → Book Brief
                                  ├─ GERBANG 1: persetujuan brief
PHASE 2  Source Audit          → Source Map per bab + daftar gap
PHASE 3  Outline & Page Budget → Outline + estimasi halaman per bab
                                  ├─ GERBANG 2: persetujuan outline
PHASE 4  Drafting              → Naskah per bab (modular)
PHASE 5  Editorial Review      → Naskah tersunting + catatan editorial
PHASE 6  Publication Build     → Standalone HTML
PHASE 7  Quality Assurance     → QA Report
```

### Phase 1 — Requirement Analysis
Tetapkan 16 input di §2. Tentukan jenis buku, tingkat kedalaman, format keluaran. Catat asumsi dan informasi yang kurang. **Output: Book Brief** berisi topik, tujuan, pembaca, jenis buku, bahasa, panjang target, sumber, asumsi, dan pertanyaan terbuka.

### Phase 2 — Source Audit
Baca sumber yang diberikan. Klasifikasikan setiap sumber sebagai: **primary,
official, supporting, general reference, outdated, conflicting, incomplete**.
Susun **source map per bab** dan **Source Traceability Matrix** memakai
`assets/source-traceability-template.md`. Identifikasi informasi yang belum
tersedia, klaim yang konflik, serta gambar/tabel yang membutuhkan attribution.
Rinciannya di `references/source-and-citation-guide.md`.

Jangan memperlakukan referensi umum sebagai kebijakan resmi.

Bila pengguna tidak memberi sumber sama sekali: nyatakan bahwa buku akan disusun dari pengetahuan umum, seluruhnya ditandai sebagai penjelasan umum, dan setiap klaim spesifik organisasi menjadi placeholder.

### Phase 3 — Outline & Page Budget
Susun outline berisi, untuk setiap bab: judul, tujuan bab, isi utama, sumber, elemen visual, dan estimasi halaman. Hitung total page budget memakai `references/page-budget-guide.md`.

Periksa outline: tidak ada bab yang isinya tumpang tindih, urutan dasar → kompleks, kedalaman sesuai tingkat pembaca.

**Jangan menulis buku lengkap sebelum outline direview**, kecuali Fast Draft Mode.

### Phase 4 — Drafting
Tulis dari konsep dasar menuju yang kompleks, memakai `assets/chapter-template.md`.

Untuk buku >30 halaman, tulis **bab per bab dengan titik henti**, bukan sekali jalan. Ini menjaga konsistensi istilah sekaligus mencegah keluaran terpotong.

Elemen berikut dipakai **hanya bila memperjelas**, bukan sebagai pengisi ruang: paragraf naratif, langkah bernomor, tabel, diagram, timeline, checklist, tips, warning, studi kasus, dialog, contoh, prompt, glossary, FAQ, troubleshooting.

Hindari halaman yang seluruhnya berupa teks panjang.

### Phase 5 — Editorial Review
Jalankan `references/editorial-checklist.md`: akurasi, kesesuaian sumber,
struktur, pengulangan, kejelasan, gaya bahasa, konsistensi istilah, konsistensi
heading, transisi antarbagian, kepadatan teks, dan kesesuaian target pembaca.

Untuk buku >30 halaman, pertahankan tiga control documents:

- **Terminology Sheet** — istilah, definisi, dan preferred wording;
- **Source Traceability Matrix** — bab/klaim/source/status;
- **Cross-Reference Register** — rujukan antarbab, tabel, gambar, appendix.

Periksa seluruhnya sebelum publication build.

### Phase 6 — Publication Build
Untuk HTML: **mulai dari `assets/dark-book-template.html`.** Baca file itu sebelum menulis keluaran. Template sudah memuat semua CSS, JavaScript, kelas komponen, dua mode cetak, dan print stylesheet A4.

Isi `<!-- TOC -->` dan `<!-- CHAPTERS -->`, judul, badge status/versi/kerahasiaan, dan metadata cover. Sesuaikan `--accent` (dan opsional `--accent-2`) dengan topik.

Markup 15 komponen visual ada di `assets/components.html` — file itu **rujukan, bukan keluaran**. Salin markup-nya saja; CSS-nya sudah ada di template.

Aturan cetak di `references/print-layout-guide.md`. Aturan aksesibilitas di `references/accessibility-guide.md`.

### Phase 7 — Quality Assurance
Jalankan QA memakai `assets/publication-qa-template.md` dan serahkan **QA
Report** yang memisahkan dua kategori:

- **Terverifikasi otomatis:** tidak ada URL/CDN/font eksternal; heading berjenjang tanpa lompatan; setiap tautan sidebar menuju `id` yang ada; `@media print` dan `@page size:A4` ada; tidak ada placeholder yang tertinggal tanpa disengaja; estimasi halaman dihitung.
- **Perlu verifikasi manusia:** tampilan di ponsel, hasil cetak nyata, jumlah halaman aktual, fungsi tombol di browser, kenyamanan baca.

Jangan menyatakan buku lulus pada hal yang tidak dapat diverifikasi. Sebut apa yang perlu Anda periksa sendiri.

---

## 4. Fast Draft Mode

Dipakai hanya bila pengguna meminta draft langsung **atau** input penting sudah lengkap.

Dalam mode ini: outline tetap disusun dan ditampilkan ringkas, tetapi tidak menunggu persetujuan. Asumsi ditampilkan. Status ditandai **draft**. Jangan menyebut buku final. Quality check dasar tetap dijalankan. Informasi yang belum tersedia tetap ditandai placeholder.

---

## 4A. Deliverables per mode

| Mode | Minimum deliverables |
|---|---|
| Create | Book Brief, Source Map, Outline, Page Budget, chapter drafts, editorial notes, HTML, QA Report |
| Fast Draft | assumptions, compact outline, draft status, source gaps, draft content, basic QA |
| Revise | changed section, before/after summary, affected cross-references, updated page budget, regression QA |
| Expand | new content map, source additions, terminology/cross-reference updates, page-budget impact |
| Condense | deletion/merge log, retained critical information, revised page budget |
| Audit | findings by severity, evidence, recommended action, no silent edits |
| Publication | standalone HTML, source traceability status, QA Report, unresolved human checks |

## 4B. Source traceability rules

- Each material claim maps to a source, `GENERAL EXPLANATION`, `ASSUMPTION`, or
  `PLACEHOLDER`.
- Tables derived from sources state source and transformation method.
- Figures/images require origin, permission/license status, and alt text.
- User-provided internal documents are cited by file/section without exposing
  unnecessary confidential content.
- Conflicting sources are shown, not silently reconciled.
- Outdated sources are labeled and not used for current claims without warning.
- A citation list alone is insufficient; traceability must indicate which claim
  each source supports.

---

## 5. Panjang Buku dan Page Budget

| Kategori | Halaman A4 |
|---|---|
| Short handbook | 10–30 |
| Standard book | 30–50 |
| Extended book | 50–100 |
| Batas maksimal default | 100 |

Perhitungan memakai `references/page-budget-guide.md`, yang memperhitungkan jumlah kata, tabel, diagram, prompt block, gambar, front matter, glossary, dan appendix.

**Alur kendali:** budget disusun sebelum menulis dan dialokasikan per bab → setelah tiap bab, estimasi aktual dibandingkan → deviasi >15% memicu penyesuaian → estimasi akhir dilaporkan di QA Report.

**Dilarang menambahkan filler atau pengulangan** hanya untuk memenuhi jumlah halaman. Buku 40 halaman yang padat lebih baik daripada 50 halaman bertele-tele.

**Bila sumber terlalu sedikit:** jelaskan keterbatasannya, sarankan buku yang lebih pendek, sarankan sumber tambahan. Jangan mengarang isi.

**Bila materi melebihi 100 halaman**, tempuh berurutan: ringkas bagian sekunder → pindahkan detail ke lampiran → batasi scope → sarankan pembagian menjadi beberapa volume. Beri tahu pengguna opsi mana yang dipakai.

---

## 6. Aturan Sumber dan Akurasi

Bedakan lima kategori isi dengan penanda yang terlihat:

| Kategori | Penanda HTML |
|---|---|
| Fakta terverifikasi dari sumber | `.box.source` — sebut dokumen dan bagiannya |
| Penjelasan umum | teks biasa, diberi label bila mudah tertukar dengan kebijakan resmi |
| Contoh ilustratif | `.box.example` berlabel "(Ilustrasi)" |
| Interpretasi / rekomendasi | `.box` dengan judul "Catatan penyusun" |
| Belum tersedia | `.box.placeholder` berisi `[Informasi diperlukan — verifikasi kepada pemilik dokumen]` |

Aturan mengikat:

1. Fakta hanya dari sumber yang diberikan atau disetujui pengguna.
2. **Jangan mengarang** nama, angka, tanggal, dokumen, kebijakan, kutipan, statistik, referensi, organisasi, atau proses.
3. Sumber dicantumkan **dekat bagian yang relevan**, bukan hanya di akhir buku.
4. Jangan mengubah referensi umum menjadi kebijakan resmi organisasi.
5. Bila sumber bertentangan: jelaskan konfliknya, tampilkan keduanya, **jangan menentukan sendiri mana yang benar**; sarankan verifikasi ke pemilik dokumen.
6. Jangan menyalin artikel atau sumber berhak cipta secara penuh. Parafrase dengan atribusi.
7. Jangan memasukkan informasi rahasia, data pribadi, atau credential. Bila ditemukan indikasi data sensitif: hentikan, tandai bagiannya, jelaskan risikonya, minta validasi pemilik data.

Rincian di `references/source-and-citation-guide.md`.

---

## 7. Gaya Penulisan

Default: profesional, natural, jelas, terstruktur, ramah, tidak kaku, tidak repetitif.

**Gunakan:** kalimat aktif; paragraf pendek sampai menengah; heading deskriptif; bahasa sederhana sebelum istilah teknis; contoh relevan; tabel untuk perbandingan; langkah bernomor untuk prosedur; analogi konkret untuk konsep abstrak. Jelaskan **mengapa**, bukan hanya **apa**.

**Definisikan setiap istilah teknis dan singkatan saat pertama muncul**, lalu pakai konsisten — jangan berganti sinonim.

**Hindari:** pengulangan pola kalimat yang sama di setiap bagian; pembukaan terlalu panjang; jargon tanpa penjelasan; kalimat terlalu formal; motivasi generik; callout berlebihan; paragraf sangat padat; idiom; kalimat pasif bertingkat.

Nada mendampingi, bukan menggurui. Sesuaikan kedalaman dengan tingkat pengetahuan pembaca.

---

## 8. Desain Visual

Default **dark theme**: latar hitam/charcoal, teks putih/off-white, secondary abu terang, **satu warna aksen utama** dan maksimal satu aksen tambahan, kontras tinggi, ruang kosong cukup, tampilan modern dan profesional.

**Hindari:** gradient berlebihan, efek glow, animasi dekoratif, ikon berlebihan, lebih dari dua aksen, halaman terlalu padat.

Lima belas komponen tersedia di template: cover, chapter opener, section card, callout, warning, source panel, diagram, timeline, process flow, comparison table, checklist, prompt block, glossary, FAQ, troubleshooting panel.

Diagram dan process flow dibuat sebagai **SVG inline atau tata letak CSS** — konsekuensi dari syarat offline. Font memakai stack sistem, tanpa font eksternal.

---

## 9. HTML Publication

Satu **standalone HTML file** dengan syarat:

1. HTML, CSS, dan JavaScript dalam satu file.
2. Tanpa library eksternal, tanpa CDN, tanpa font web, tanpa gambar eksternal.
3. Berfungsi penuh tanpa internet.
4. Responsif di desktop, tablet, dan mobile.
5. Semantic HTML dengan hierarki heading benar (h1 → h2 → h3 → h4, tanpa lompatan).
6. Daftar isi yang dapat diklik.
7. Sidebar tetap, menyusut menjadi menu di layar kecil.
8. Pencarian isi buku.
9. Reading progress.
10. Tombol kembali ke atas.
11. Tombol Copy pada setiap blok prompt/kode.
12. FAQ dan troubleshooting yang dapat dibuka-tutup.
13. Navigasi keyboard.
14. Kontras warna memadai.
15. Metadata buku: title, subtitle, author, version, date, status, dan label kerahasiaan bila diperlukan.

Semua fitur ini **sudah ada di `assets/dark-book-template.html`** — pertahankan, jangan hapus. Bila menambah komponen baru, tambahkan juga aturan cetaknya.

**PDF tidak dihasilkan skill.** Pengguna mencetak sendiri dari browser (Ctrl+P → Save as PDF). Sebutkan ini saat menyerahkan file.

---

## 10. Print dan A4

Template menyediakan **dua mode cetak**, dipilih lewat tombol di sidebar:

- **Cetak terang** (default) — latar putih, teks gelap, hemat tinta, disarankan untuk cetak kantor.
- **Cetak gelap** — mempertahankan latar gelap, untuk yang ingin tampilan digital tetap terjaga.

Aturan cetak: ukuran A4, margin konsisten, bab utama mulai di halaman baru, heading tidak sendirian di bawah halaman, tabel tidak terpotong, callout tidak terpisah dari konteksnya, gambar tidak keluar margin, blok kode tidak terpotong, jumlah halaman sesuai page budget.

Rincian di `references/print-layout-guide.md`.

---

## 11. Revisi Modular

Pengguna boleh merevisi satu bab **tanpa membuat ulang semua buku**.

1. Identifikasi bab atau bagian yang terdampak.
2. Pertahankan bagian lain — jangan menulis ulang bab yang tidak diminta.
3. **Pertahankan ID heading dan struktur navigasi.**
4. Perbarui penomoran bab/subbab.
5. Perbarui daftar isi sidebar dan tautan anchor.
6. Perbarui sumber dan glossary bila ada istilah baru.
7. Hitung ulang page budget dan perbarui angka di cover.
8. Jalankan ulang quality review pada bagian terdampak.
9. Tampilkan **change log**: bagian apa yang berubah, alasannya, dan dampaknya pada panjang buku.

Prosedur lengkap per mode di `references/revision-guide.md`.

---

## 12. Batas Skill Ini

Skill ini **tidak** menangani:

- artikel, esai, blog post, laporan pendek, memo, presentasi, proposal;
- website, landing page, atau aplikasi web — meskipun keluarannya HTML;
- naskah fiksi atau novel;
- dokumen Word, PowerPoint, atau Excel;
- **persona atau spesifikasi perilaku agen AI** → skill `persona`;
- **analisis aksi korporasi** → skill `indonesia-corporate-action-intelligence`;
- penetapan kebijakan resmi organisasi;
- buku multi-bahasa dalam satu file, atau tata letak kanan-ke-kiri (RTL).

Bila permintaan menyentuh dua skill, jelaskan pembagian tugasnya sebelum mulai.

---

## 13. Continuous Improvement

Klasifikasikan setiap interaksi penting sebagai: SUCCESSFUL, PARTIALLY SUCCESSFUL, FAILED, AMBIGUOUS, USER CORRECTION, NEW USE CASE, atau NEW PATTERN.

Selain SUCCESSFUL, buat **Learning Record** berisi: Learning ID, tanggal, permintaan pengguna, perilaku saat ini, perilaku yang diharapkan, gap, sumber/validasi yang diperlukan, usulan perubahan, file yang terdampak, regression test, status.

Status: NEW, UNDER REVIEW, VERIFIED, APPROVED, REJECTED, IMPLEMENTED.

**Jangan mengubah skill secara permanen berdasarkan satu feedback.** Setelah learning disetujui, rekomendasikan: perubahan file, regression test, semantic version, changelog entry, nama branch, dan commit message.

Jangan menyatakan bahwa model telah dilatih ulang. Gunakan istilah: *skill disempurnakan, pattern diperbarui, reference ditambahkan, quality rule diperbaiki, test coverage diperluas.*

---

## 14. Daftar Referensi dan Aset

| File | Dibaca pada |
|---|---|
| `references/book-types.md` | Fase 1 & 3 — memilih dan menyusun struktur |
| `references/page-budget-guide.md` | Fase 3 & 7 — menghitung dan memeriksa halaman |
| `references/source-and-citation-guide.md` | Fase 2 & 4 — klasifikasi sumber, sitasi, konflik |
| `references/editorial-checklist.md` | Fase 5 |
| `references/print-layout-guide.md` | Fase 6 & 7 |
| `references/accessibility-guide.md` | Fase 6 & 7 |
| `references/revision-guide.md` | Mode Revise, Expand, Condense, Audit |
| `references/testing-guide.md` | Pengujian skill |
| `assets/dark-book-template.html` | Fase 6 — kerangka keluaran |
| `assets/components.html` | Fase 6 — rujukan markup komponen, bukan keluaran |
| `assets/chapter-template.md` | Fase 4 — kerangka bab |
| `assets/source-traceability-template.md` | Fase 2, 5, 7 — claim/source mapping |
| `assets/publication-qa-template.md` | Fase 7 — QA report |

Baca referensi **secara selektif sesuai fase**, tidak sekaligus.

---

## 15. Status

Versi skill: **1.0.0-draft** dalam package **0.6.0-draft**. Struktur dan HTML
dapat diuji statis, tetapi kualitas editorial, tampilan browser, dan hasil cetak
memerlukan verifikasi aktual.

---

## Pengingat Penutup

Tujuan skill ini adalah buku yang **benar-benar bisa dipelajari**: akurat, jujur soal sumber, enak dibaca di layar, dan rapi saat dicetak. Bila ragu apakah suatu informasi benar, gunakan placeholder dan sarankan verifikasi — jangan menebak.
