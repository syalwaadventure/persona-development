# Testing Guide — Business Excellence Assessor

## Tujuan

Pengujian memastikan skill aktif pada permintaan maturity assessment, tidak
mengarang skor/evidence, dan tidak mengambil alih fungsi Business Modeler.

## Jenis pengujian

1. **Trigger test** — permintaan maturity mengaktifkan skill.
2. **Mode test** — full, category, preliminary, evidence gap, roadmap, dan
   comparative mode berjalan sesuai kebutuhan.
3. **Evidence test** — skor dan temuan dapat ditelusuri.
4. **Boundary test** — BMC, revenue, profit, cash flow, NPV, dan IRR diarahkan ke
   `indonesia-business-modeler`.
5. **Hallucination test** — skill tidak menciptakan evidence atau hasil.
6. **Natural-language test** — output jelas, tidak kaku, dan tidak berlebihan.
7. **Regression test** — penambahan skill tidak mengubah skill existing.

## Status hasil

Gunakan hanya:

- `PASS`
- `FAIL`
- `NOT TESTED`
- `NEEDS REVISION`

Jangan menulis PASS berdasarkan inspeksi prompt saja. Behavioral test harus
dijalankan pada Claude dengan package aktual.

## Kriteria lulus utama

- Framework dan evidence disebut sebelum scoring.
- Dokumen rencana tidak dianggap sebagai hasil implementasi.
- Kategori tanpa evidence menggunakan N/A/Not Assessable.
- Confidence terpisah dari maturity.
- Overall score tidak dipaksakan ketika coverage rendah.
- Rekomendasi terkait dengan gap.
- Permintaan finansial diarahkan ke Business Modeler.
- Tidak ada klaim sertifikasi.

## Static validation

Static validation dapat memeriksa:

- frontmatter `SKILL.md`;
- keberadaan referenced paths;
- keseimbangan code fences;
- struktur folder dan template;
- tidak adanya metadata sementara.

Static validation tidak membuktikan kualitas jawaban Claude.
