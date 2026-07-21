# Chapter Template

Kerangka satu bab, dipakai pada Fase 4 (Drafting). Tulis dalam Markdown lebih dulu,
baru rakit ke HTML pada Fase 6. Hapus bagian yang tidak relevan — jangan mengisi
paksa setiap slot.

---

## Kepala bab (wajib)

```markdown
# Bab [N] — [Judul Bab]

**Tujuan bab:** [satu kalimat: apa yang akan dipahami atau bisa dilakukan pembaca]

**Kaitan:** [satu–dua kalimat menghubungkan dengan bab sebelumnya]

**Sumber utama bab ini:** [dokumen/rujukan, atau: pengetahuan umum — ditandai]

**Alokasi halaman:** [N] halaman  |  **Estimasi aktual:** [diisi setelah selesai]
```

---

## Badan bab

Pola dasar tiap subbagian:

```markdown
## [N.1] [Subjudul deskriptif]

[Paragraf pembuka: apa dan mengapa, 2–4 kalimat]

[Isi utama: paragraf, langkah bernomor, atau tabel — pilih yang paling jelas]

[Elemen pendukung bila memperjelas: contoh, diagram, callout, checklist]
```

Aturan:
- Satu ide per subbagian.
- Urutan dasar → kompleks. Jangan mengandaikan materi bab berikutnya.
- Istilah teknis didefinisikan saat pertama muncul, lalu konsisten.
- Jelaskan **mengapa**, bukan hanya **apa**.
- Pecah blok teks yang lebih dari 5–6 kalimat.
- Elemen pendukung dipakai hanya bila memperjelas.

---

## Penanda jenis isi (wajib dipakai)

| Jenis isi | Penanda Markdown | Kelas HTML |
|---|---|---|
| Fakta dari sumber | `> **Sumber:** [dokumen, bagian]` | `.box.source` |
| Penjelasan umum | `> **Penjelasan umum:** ...` | `.box` |
| Contoh ilustratif | `> **Contoh (Ilustrasi):** ...` | `.box.example` |
| Interpretasi / rekomendasi | `> **Catatan penyusun:** ...` | `.box` |
| Belum tersedia | `> **[Informasi diperlukan — verifikasi kepada pemilik dokumen]**` | `.box.placeholder` |
| Peringatan | `> **Peringatan:** ...` | `.box.warn` |
| Tips | `> **Tips:** ...` | `.box.tip` |

---

## Ekor bab (pilih yang sesuai jenis buku)

| Jenis buku | Ekor bab yang lazim |
|---|---|
| Handbook | Checklist, rujukan cepat |
| Modul pembelajaran | Rangkuman, latihan, refleksi, evaluasi |
| Buku teknis | Batasan, troubleshooting, rujukan lanjutan |
| Onboarding | Checklist, pertanyaan umum, jalur eskalasi |
| Dokumentasi proses | Kontrol, risiko, pengecualian, dokumen terkait |

```markdown
### Rangkuman
- [3–5 butir inti bab]

### Checklist
- [ ] [butir periksa]

### Sumber bab ini
- [dokumen, bagian, tanggal]
```

---

## Pemeriksaan sebelum bab dinyatakan selesai

- [ ] Tujuan bab terpenuhi oleh isinya.
- [ ] Tidak mengulang materi bab lain.
- [ ] Semua istilah baru sudah didefinisikan.
- [ ] Setiap klaim faktual punya penanda sumber.
- [ ] Tidak ada angka, nama, tanggal, atau kebijakan yang dikarang.
- [ ] Informasi yang belum ada memakai placeholder, bukan tebakan.
- [ ] Estimasi halaman dihitung dan dibandingkan dengan alokasi.
- [ ] Deviasi >15% terhadap alokasi sudah ditangani atau dilaporkan.
- [ ] ID heading akan stabil (tidak berubah bila bab lain direvisi).
