# Continuous Improvement Guide

Skill ini menerapkan human-in-the-loop continuous improvement. Interaksi
pengguna tidak secara otomatis melatih ulang model; peningkatan dilakukan
melalui pembaruan skill, references, assets, dan test case yang telah
divalidasi.

## Klasifikasi Interaksi

- `SUCCESSFUL`
- `PARTIALLY SUCCESSFUL`
- `FAILED`
- `AMBIGUOUS`
- `USER CORRECTION`
- `NEW USE CASE`
- `NEW INDUSTRY`
- `NEW BUSINESS MODEL PATTERN`
- `NEW PROCESS PATTERN`
- `NEW REVENUE MODEL`

Untuk kategori selain `SUCCESSFUL`, susun Learning Record menggunakan
`assets/learning-record-template.md`.

## Isi Learning Record

- Learning ID
- Tanggal
- Perusahaan atau industri terkait
- Pertanyaan/kasus
- Current behavior
- Expected behavior
- Gap yang ditemukan
- Source required (sumber yang perlu diperiksa untuk validasi)
- Proposed change
- Affected file
- Regression test yang perlu ditambahkan
- Status

## Status Learning Record

- `NEW`
- `UNDER REVIEW`
- `VERIFIED`
- `APPROVED`
- `REJECTED`
- `IMPLEMENTED`

## Prinsip

1. Jangan menganggap satu pertanyaan atau koreksi pengguna sebagai fakta
   resmi tanpa validasi.
2. Jangan langsung mengubah skill berdasarkan satu masukan.
3. Perubahan permanen hanya direkomendasikan setelah: sumber diperiksa,
   informasi divalidasi, tidak bertentangan dengan aturan lain, data
   sensitif diperiksa, test case dibuat, dan persetujuan pengguna atau
   pembimbing diperoleh.
4. Setelah disetujui, tentukan file yang relevan untuk diperbarui
   (SKILL.md, references, assets, test-cases.md), perbarui hanya file
   tersebut, tambahkan regression test, rekomendasikan versi baru, dan
   buat changelog entry.
5. Gunakan istilah "skill disempurnakan", "knowledge diperbarui",
   "reference ditambahkan", "pola jawaban ditingkatkan", atau
   "test coverage diperluas" — jangan menyatakan "agent telah melatih
   dirinya sendiri".
