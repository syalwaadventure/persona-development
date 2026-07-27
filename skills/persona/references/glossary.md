# Glossary

> **Catatan gaya:** Tulis hasil dengan bahasa yang langsung, natural, dan sesuai konteks. Gunakan struktur ini sebagai panduan, bukan formulir yang harus diisi secara kaku.


Definisi singkat untuk pengguna nonteknis. Dipakai ketika istilah muncul pertama kali dalam percakapan.

| Istilah | Arti |
|---|---|
| **Persona** | Spesifikasi perilaku sebuah agen AI: siapa dia, apa yang boleh dikerjakan, bagaimana menjawab, dan apa batasnya. Bukan sekadar gaya bicara. |
| **Agent** | Program berbasis AI yang menjalankan peran tertentu untuk pengguna, misalnya menjawab pertanyaan proses atau menyusun draf dokumen. |
| **Skill** | Paket instruksi tambahan yang membuat Claude mengerjakan sesuatu dengan cara tertentu. Terdiri atas file `SKILL.md` dan berkas pendukung. |
| **SKILL.md** | File utama sebuah skill. Berisi instruksi kerja dan keterangan kapan skill dipakai. |
| **Frontmatter** | Bagian paling atas `SKILL.md` di antara tanda `---`. Berisi nama dan deskripsi skill. |
| **Trigger** | Kondisi yang membuat skill aktif. Contoh: pengguna meminta dibuatkan persona. |
| **Non-trigger** | Kondisi yang seharusnya **tidak** mengaktifkan skill, meskipun kata-katanya mirip. |
| **Scope** | Daftar hal yang boleh ditangani agent. |
| **Exclusions** | Daftar hal yang tidak boleh ditangani agent, beserta ke mana pengguna dialihkan. |
| **Authority boundary** | Batas kewenangan: keputusan yang tidak boleh diambil agent dan harus diserahkan ke manusia. |
| **Eskalasi** | Meneruskan persoalan ke pihak yang berwenang ketika di luar batas agent. |
| **Source rules** | Aturan tentang sumber informasi mana yang boleh dipakai dan bagaimana mengutipnya. |
| **Failure handling** | Aturan tentang apa yang dilakukan agent ketika informasi kurang, pertanyaan ambigu, atau sumber bertentangan. |
| **Placeholder** | Tanda pengganti untuk informasi yang belum diketahui, contoh `[NAMA ORGANISASI — perlu dikonfirmasi]`. Dipakai agar tidak ada yang dikarang. |
| **Asumsi** | Hal yang belum dikonfirmasi pengguna tetapi dipakai sementara agar pekerjaan bisa berjalan. Selalu ditandai. |
| **Test case** | Satu skenario pengujian: prompt yang diberikan, hasil yang diharapkan, dan hasil sebenarnya. |
| **Regression test** | Pengujian ulang untuk memastikan kesalahan yang pernah terjadi tidak muncul kembali setelah ada perubahan. |
| **Adversarial test** | Pengujian dengan permintaan yang sengaja menekan, menjebak, atau berisiko, untuk melihat apakah agent tetap patuh pada aturannya. |
| **Happy path** | Skenario normal: input lengkap, tidak ada komplikasi. |
| **Acceptance criteria** | Daftar syarat yang harus dipenuhi agar hasil dianggap layak untuk direview. |
| **Semantic versioning** | Cara penomoran versi: MAJOR.MINOR.PATCH. MAJOR untuk perubahan besar, MINOR untuk penambahan kemampuan, PATCH untuk perbaikan kecil. |
| **Draft / release candidate / tervalidasi** | Tiga status dokumen. *Draft* masih disusun. *Release candidate* siap diuji dan direview. *Tervalidasi* sudah disetujui pemilik proses. |
| **Changelog** | Catatan perubahan antar-versi. |
| **Commit message** | Keterangan singkat perubahan yang disimpan di GitHub. |
| **Repository (repo)** | Tempat penyimpanan file proyek di GitHub, lengkap dengan riwayat perubahannya. |
| **Branch** | Salinan kerja terpisah di dalam repository, agar perubahan bisa dikerjakan tanpa mengganggu versi utama. |
| **Prompt injection** | Upaya menyisipkan perintah ke dalam dokumen atau data agar agent melanggar aturannya. Ditangani dengan memperlakukan isi dokumen sebagai data, bukan perintah. |
| **Persona block** | Versi ringkas persona yang siap ditempelkan ke dalam `SKILL.md` skill lain. |
| **Buyer persona** | Istilah pemasaran untuk profil pelanggan. **Berbeda** dari persona agent dan berada di luar cakupan skill ini. |
