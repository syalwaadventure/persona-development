# Laporan Revisi — v0.4.0-draft

## Tujuan

Menindaklanjuti dua permintaan perbaikan: (1) Skill News Anchor — yang
di repository ini diwakili oleh `indonesia-corporate-action-intelligence`
— dan (2) Skill Business Modeler (`indonesia-business-modeler`).

## Catatan penting soal permintaan #1

Repository ini tidak memiliki skill bernama "News Anchor". Setelah
dikonfirmasi, permintaan tersebut dimaksudkan untuk
`indonesia-corporate-action-intelligence`, dijadikan lebih seperti news
brief harian. Perubahan di bawah ditambahkan sebagai **mode baru (Mode
K)** di skill tersebut, bukan menggantikan fungsi corporate-action
intelligence yang sudah ada — supaya kemampuan verifikasi aksi korporasi
yang sudah teruji tetap utuh.

## Perubahan untuk permintaan #1 — Rekind Sector News Brief (Mode K)

| Permintaan | Perubahan |
|---|---|
| Output format HTML | Mode K menghasilkan satu file HTML mandiri (`assets/rekind-sector-news-brief-template.html`), bukan markdown. |
| Estimasi waktu baca 6–8 menit di header | Ditambahkan badge waktu baca di header; cara hitung (≈200 kata/menit, target isi 1.200–1.600 kata) dijelaskan di `references/rekind-sector-brief-guide.md` §3. |
| Alat bantu visual (infografis/tabel/ringkasan poin) | Ditambahkan: kotak "Poin Penting", bar CSS jumlah berita per sektor, badge relevansi warna, dan tabel ringkas semua berita. Tanpa library chart eksternal supaya file tetap mandiri. |
| Filter ke sektor Energi, Oil & Gas, Petrokimia, Fertilizer/Pupuk | Empat sektor ini jadi default otomatis Mode K, lengkap dengan kata kunci pencarian per sektor (`references/rekind-sector-brief-guide.md` §1). |
| Tambahkan CNBC Indonesia sebagai sumber | CNBC Indonesia (sudah ada di Tier 2) ditandai eksplisit sebagai sumber prioritas untuk keempat sektor tersebut (`references/source-guide.md`). |
| Berita lebih spesifik/terkurasi/tersegmentasi | Ditambahkan prinsip kurasi: saring dulu baru tulis, gabungkan duplikasi, tag relevansi LOW/MEDIUM/HIGH untuk Rekind, maksimal 3–5 butir per sektor, lewati sektor tanpa perkembangan berarti. |
| Kurangi ketergantungan pada prompt | Ditambahkan auto-deteksi Mode K dari frasa pemicu ("news brief", "sector brief", dll.) di Fase 1 `SKILL.md`, lengkap dengan parameter default (periode, sektor, sumber, format) supaya pengguna tidak perlu menuliskan semuanya setiap kali. |

## Perubahan untuk permintaan #2 — Business Modeler

| Permintaan | Perubahan |
|---|---|
| Matriks IRR | Analysis mode baru "Investment Return / IRR Matrix" — `assets/irr-matrix-template.md` + `references/irr-cashflow-guide.md`, termasuk format matriks sensitivitas skenario × discount rate. |
| Alur cash flow belum jelas | Analysis mode baru "Cash Flow Analysis" — `assets/cash-flow-template.md`, menjelaskan jembatan profit-ke-kas dan tiga bagian arus kas (operasi/investasi/pendanaan). |
| Analisis peluang bisnis | Analysis mode baru "Business Opportunity Analysis" — `assets/business-opportunity-template.md` + `references/business-opportunity-guide.md`, lima dimensi penilaian dengan skor 1–5. |
| Kurangi ketergantungan pada prompt | Ditambahkan auto-deteksi analysis mode dari kata kunci pengguna (§6a `SKILL.md`) — skill langsung menjalankan mode yang sesuai dan menyatakan asumsinya di awal jawaban, alih-alih selalu bertanya balik. |

## Batasan yang sengaja dipertahankan

- Mode K tetap tidak boleh mengarang fakta, tetap membedakan rumor dari
  fakta, dan tetap mencantumkan sumber + tanggal per butir — prinsip inti
  skill tidak dilonggarkan hanya karena formatnya berubah.
- Mode IRR/cash flow/business opportunity tetap tidak memberi rekomendasi
  investasi atau simpulan "layak/tidak layak" final; semua angka
  proyeksi wajib berlabel sumber/estimasi sesuai
  `references/source-and-confidence-guide.md`.

## Catatan

Paket masih berstatus draft. Ketiga mode baru dan Mode K belum melalui
eksekusi test case nyata — perlu diuji dengan kasus riil sebelum dipakai
sebagai proses harian yang diandalkan.
