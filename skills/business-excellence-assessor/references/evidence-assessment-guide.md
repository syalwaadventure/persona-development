# Evidence Assessment Guide

Assessment harus dapat ditelusuri kembali ke evidence. Panduan ini membantu
membedakan keberadaan dokumen, penerapan, dan hasil.

## 1. Status evidence

| Status | Penggunaan |
|---|---|
| Available | Evidence tersedia, dapat dibaca, relevan, dan dapat digunakan |
| Partially Available | Evidence tersedia sebagian atau hanya mendukung sebagian kriteria |
| Not Available | Evidence tidak diberikan atau tidak ditemukan |
| Not Verified | Evidence disebutkan tetapi belum dapat diperiksa atau divalidasi |

## 1a. Lifecycle Evidence (Mentioned → Received → Validated → Used in Scoring)

Status pada tabel Bagian 1 menjelaskan *kualitas* evidence. Selain itu,
setiap evidence juga memiliki *lifecycle* penerimaan yang wajib dibedakan
secara eksplisit di Evidence Register:

1. **Mentioned** — pengguna hanya menyebut nama dokumen; isinya belum
   diunggah atau belum dapat dibaca.
2. **Received** — isi dokumen sudah dapat dibaca/diperiksa.
3. **Validated** — isi dokumen sudah diperiksa relevansi, kecukupan, dan
   konsistensinya terhadap kategori/subkriteria yang dinilai.
4. **Used in Scoring** — evidence yang sudah Validated dan benar-benar
   dijadikan dasar suatu skor, maturity level, atau finding tertentu.

Jangan melompati tahap ini. Evidence yang baru Mentioned tidak boleh
dianggap Received, apalagi dipakai untuk scoring atau untuk menaikkan
Assessment Confidence.

## 2. Dimensi kualitas evidence

### Relevance

Apakah evidence benar-benar menjawab kategori, unit, periode, dan pertanyaan
assessment?

### Sufficiency

Apakah jumlah dan kedalaman evidence cukup untuk menyimpulkan desain,
implementasi, dan hasil?

### Consistency

Apakah evidence dari dokumen, data, wawancara, dan praktik aktual saling
mendukung atau bertentangan?

### Recency

Apakah evidence masih berlaku untuk periode assessment?

### Verifiability

Apakah sumber, tanggal, pemilik, dan isi evidence dapat ditelusuri?

## 3. Evidence hierarchy untuk maturity

Tidak semua evidence memiliki kekuatan yang sama. Gunakan lapisan berikut:

1. **Direction/Design Evidence** — strategi, kebijakan, roadmap, SOP, desain KPI.
2. **Deployment Evidence** — record pelaksanaan, komunikasi, training, workflow,
   meeting review, dan penggunaan sistem.
3. **Evaluation Evidence** — audit, review, analisis gap, corrective action.
4. **Results Evidence** — KPI aktual, tren, outcome, benefit, dan hasil perbaikan.
5. **Learning/Integration Evidence** — standardisasi ulang, replication,
   lessons learned, dan bukti integrasi lintas unit.

Dokumen strategi hanya mendukung direction/design. Dokumen tersebut tidak
cukup untuk menyimpulkan deployment, effectiveness, atau results.

## 4. Evidence register

Gunakan `../assets/evidence-register-template.md` dan catat:

- Evidence ID;
- nama evidence;
- source/owner;
- tanggal/periode;
- kategori/subkriteria;
- status;
- relevance dan sufficiency;
- findings;
- limitations.

## 5. Label pernyataan

Gunakan label secara natural dan hanya ketika penting:

- `EVIDENCE` — langsung didukung sumber.
- `INFERENCE` — kesimpulan logis dari evidence tetapi tidak dinyatakan langsung.
- `ASSUMPTION` — parameter yang diperlukan tetapi belum diberikan.
- `RECOMMENDATION` — tindakan yang disarankan berdasarkan gap.
- `INFORMATION GAP` — informasi penting belum tersedia.

Jangan menyamarkan assumption sebagai evidence.

## 6. Konflik evidence

Jika sumber bertentangan:

1. tampilkan perbedaannya;
2. catat unit, periode, definisi, dan sumber;
3. jangan memilih sepihak tanpa dasar;
4. turunkan confidence;
5. tandai `REQUIRES ORGANIZATION VALIDATION`.

## 7. Dokumen rencana dan target

Bedakan:

- `Existing Condition` — praktik yang telah dibuktikan berjalan;
- `Planned Initiative` — aktivitas yang direncanakan;
- `Target Condition` — hasil atau maturity yang ingin dicapai;
- `Evidence Not Available` — belum ada bukti untuk menilai.

Rencana tidak boleh digunakan sebagai bukti hasil. Target tidak boleh digunakan
sebagai capaian aktual.

## 8. Evidence yang tidak cukup

Jika evidence hanya satu dokumen ringkas:

- jalankan Preliminary Document Assessment;
- jangan memberi skor pada kategori yang tidak didukung;
- gunakan skor rentang hanya bila rubric dan sebagian evidence memadai;
- tampilkan missing evidence;
- jelaskan bahwa wawancara, observasi, atau data aktual dapat mengubah hasil.

## 9. Larangan

- Jangan mengarang nama dokumen, tanggal, KPI, survei, SOP, atau hasil.
- Jangan menyimpulkan efektivitas hanya dari keberadaan dokumen.
- Jangan menganggap dokumen terbaru otomatis paling benar.
- Jangan mengutip isi sensitif lebih banyak daripada yang dibutuhkan.
- Jangan menyimpan evidence internal sebagai referensi permanen tanpa izin.
