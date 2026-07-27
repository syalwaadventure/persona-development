# Panduan Instalasi dan Setup Project

Dokumen ini adalah panduan resmi instalasi dan konfigurasi awal (*setup*) repository, agar setiap developer dapat menjalankan project dengan benar sejak penggunaan pertama.

| Atribut | Keterangan |
|---|---|
| Jenis dokumen | Panduan instalasi dan setup |
| Ruang lingkup | Persiapan lingkungan kerja lokal untuk pengembangan project Agen AI |
| Pembaca | AI Engineer, Developer, Business Excellence Center, Repository Maintainer, mahasiswa magang |
| Dokumen terkait | `development-workflow.md` (standar alur pengembangan) |
| Status dokumen | `[Perlu dilengkapi: status pengesahan]` |
| Versi dan tanggal berlaku | `[Perlu dilengkapi: nomor versi dan tanggal berlaku]` |
| Pemilik dokumen | `[Perlu dilengkapi: unit atau jabatan pemilik dokumen]` |

> **Catatan mengenai placeholder.** Bagian yang ditandai `[Perlu dilengkapi: ...]` adalah informasi khusus organisasi yang belum tersedia pada saat dokumen ini disusun. Bagian tersebut wajib dilengkapi oleh pemilik dokumen dan **tidak boleh diisi dengan asumsi**.

> **Catatan mengenai versi perangkat lunak.** Tampilan antarmuka dan tautan unduhan perangkat lunak pihak ketiga dapat berubah sewaktu-waktu. Jika ada perbedaan antara dokumen ini dan tampilan sebenarnya, ikuti dokumentasi resmi perangkat lunak yang bersangkutan, kemudian laporkan perbedaan tersebut kepada pemilik dokumen.

---

## Daftar Isi

1. [Tujuan Instalasi](#1-tujuan-instalasi)
2. [Kebutuhan Sistem](#2-kebutuhan-sistem)
3. [Daftar Perangkat Lunak yang Diperlukan](#3-daftar-perangkat-lunak-yang-diperlukan)
4. [Langkah Instalasi Setiap Perangkat Lunak](#4-langkah-instalasi-setiap-perangkat-lunak)
5. [Konfigurasi Awal Git](#5-konfigurasi-awal-git)
6. [Cara Melakukan Clone Repository](#6-cara-melakukan-clone-repository)
7. [Struktur Folder Setelah Clone](#7-struktur-folder-setelah-clone)
8. [Proses Setup Awal Project](#8-proses-setup-awal-project)
9. [Cara Mengimpor Hasil ZIP dari Claude ke Repository](#9-cara-mengimpor-hasil-zip-dari-claude-ke-repository)
10. [Verifikasi Keberhasilan Instalasi](#10-verifikasi-keberhasilan-instalasi)
11. [Troubleshooting Instalasi](#11-troubleshooting-instalasi)
12. [Checklist Sebelum Mulai Mengembangkan](#12-checklist-sebelum-mulai-mengembangkan)
13. [Glosarium](#13-glosarium)

---

## 1. Tujuan Instalasi

Instalasi dan setup dilakukan untuk mencapai lima tujuan berikut.

| No | Tujuan | Penjelasan |
|---:|---|---|
| 1 | Kesetaraan lingkungan kerja | Semua kontributor bekerja pada lingkungan yang setara sehingga hasil pekerjaan dapat direproduksi. |
| 2 | Kesiapan alat kerja | Perangkat lunak yang diperlukan telah terpasang dan terkonfigurasi dengan benar sebelum pengembangan dimulai. |
| 3 | Keterhubungan dengan repository | Developer dapat mengambil, menyunting, dan mengirim perubahan melalui Git dan GitHub. |
| 4 | Kesiapan alur generasi | Hasil generasi Claude dapat diimpor ke repository melalui prosedur yang baku dan aman. |
| 5 | Pencegahan kesalahan awal | Kesalahan konfigurasi terdeteksi pada tahap verifikasi, bukan setelah pekerjaan berjalan. |

> **Note.** Panduan ini hanya mencakup penyiapan lingkungan kerja. Standar alur pengembangan, penulisan *commit*, dan pengiriman perubahan diuraikan pada dokumen `development-workflow.md`.

---

## 2. Kebutuhan Sistem

### 2.1 Kebutuhan Perangkat Keras

| Komponen | Minimum | Dianjurkan |
|---|---|---|
| Prosesor | Dua inti, arsitektur 64-bit | Empat inti atau lebih |
| Memori (RAM) | 8 GB | 16 GB |
| Ruang penyimpanan kosong | 10 GB | 20 GB atau lebih |
| Resolusi layar | 1366 × 768 piksel | 1920 × 1080 piksel |
| Koneksi internet | Diperlukan untuk instalasi, *clone*, dan sinkronisasi | Koneksi stabil |

> **Note.** Kebutuhan memori sebesar 16 GB dianjurkan jika developer menjalankan VS Code, Claude Desktop, dan peramban secara bersamaan.

### 2.2 Kebutuhan Sistem Operasi

| Sistem operasi | Versi minimum | Keterangan |
|---|---|---|
| Windows | Windows 10 versi 64-bit | Windows 11 dianjurkan |
| macOS | macOS 12 (Monterey) | Mendukung prosesor Intel dan Apple Silicon |
| Linux | Distribusi 64-bit yang masih didukung, misalnya Ubuntu 22.04 LTS | Ketersediaan Claude Desktop pada Linux perlu diperiksa pada situs resmi |

> **Warning.** Sistem operasi yang telah melewati masa dukungan keamanan tidak boleh digunakan untuk mengakses repository maupun dokumen internal, karena berisiko terhadap keamanan informasi perusahaan.

### 2.3 Kebutuhan Akun dan Hak Akses

| Kebutuhan | Keterangan |
|---|---|
| Akun GitHub | Diperlukan untuk mengakses repository |
| Hak akses repository | Diberikan oleh Repository Maintainer |
| Akun Claude | Diperlukan untuk menggunakan Claude sebagai generator draf |
| Hak administratif pada komputer | Diperlukan pada saat instalasi perangkat lunak |

`[Perlu dilengkapi: prosedur resmi pengajuan akun dan hak akses repository, termasuk pihak yang berwenang menyetujui]`

> **Warning.** Akun perusahaan tidak boleh digunakan bersama oleh lebih dari satu orang. Setiap kontribusi harus dapat ditelusuri kepada satu individu yang bertanggung jawab.

---

## 3. Daftar Perangkat Lunak yang Diperlukan

### 3.1 Perangkat Lunak Wajib

| Perangkat lunak | Fungsi dalam alur kerja | Sifat |
|---|---|---|
| Git | Mengelola versi dan riwayat perubahan | Wajib |
| Visual Studio Code | Menyunting berkas dan meninjau perubahan | Wajib |
| Claude Desktop | Menghasilkan draf project dan berkas ZIP | Wajib |
| Peramban web modern | Mengakses GitHub dan dokumentasi | Wajib |
| Utilitas ekstraksi arsip | Mengekstrak berkas ZIP hasil generasi | Wajib (umumnya telah tersedia bawaan) |

### 3.2 Perangkat Lunak Pendukung

| Perangkat lunak | Fungsi | Sifat |
|---|---|---|
| GitHub CLI (`gh`) | Mempermudah autentikasi dan pengelolaan *pull request* | Dianjurkan |
| Git Credential Manager | Menyimpan kredensial Git secara aman | Dianjurkan |
| Ekstensi VS Code: Markdown All in One | Membantu penulisan dokumentasi Markdown | Dianjurkan |
| Ekstensi VS Code: markdownlint | Memeriksa konsistensi format Markdown | Dianjurkan |
| Ekstensi VS Code: Mermaid Preview | Melihat pratinjau diagram Mermaid | Dianjurkan |
| Ekstensi VS Code: GitLens | Menampilkan riwayat perubahan secara rinci | Opsional |

> **Note.** Perangkat lunak berstatus opsional tidak memengaruhi keberhasilan instalasi. Perangkat tersebut hanya mempermudah pekerjaan sehari-hari.

`[Perlu dilengkapi: daftar perangkat lunak yang telah disetujui oleh unit teknologi informasi perusahaan beserta ketentuan lisensinya]`

---

## 4. Langkah Instalasi Setiap Perangkat Lunak

> **Warning.** Semua perangkat lunak wajib diunduh dari situs resmi masing-masing. Pengunduhan dari sumber tidak resmi berisiko menyisipkan perangkat berbahaya ke dalam komputer kerja.

### 4.1 Instalasi Git

**Windows**

1. Unduh pemasang Git dari situs resmi `https://git-scm.com`.
2. Jalankan berkas pemasang.
3. Pada tahap pemilihan editor, pilih Visual Studio Code jika telah terpasang.
4. Pada tahap penyesuaian `PATH`, pilih opsi yang memungkinkan Git dijalankan dari Command Prompt.
5. Selesaikan proses instalasi dengan pengaturan bawaan untuk opsi lainnya.

**macOS**

1. Buka aplikasi Terminal.
2. Jalankan perintah `git --version`. Jika Git belum terpasang, sistem akan menawarkan pemasangan Command Line Tools.
3. Sebagai alternatif, gunakan Homebrew dengan perintah `brew install git`.

**Linux (Ubuntu atau Debian)**

```bash
sudo apt update
sudo apt install git
```

**Verifikasi**

```bash
git --version
```

Perintah tersebut harus menampilkan nomor versi Git.

### 4.2 Instalasi Visual Studio Code

1. Unduh pemasang dari situs resmi `https://code.visualstudio.com`.
2. Jalankan pemasang dan ikuti petunjuk yang ditampilkan.
3. Khusus Windows, aktifkan opsi penambahan VS Code ke `PATH` jika tersedia, agar perintah `code` dapat dijalankan dari terminal.
4. Setelah instalasi selesai, pasang ekstensi yang dianjurkan melalui menu Extensions.

**Verifikasi**

```bash
code --version
```

> **Note.** Jika perintah `code` belum dikenali pada macOS, buka VS Code, tekan `Cmd + Shift + P`, lalu jalankan perintah "Shell Command: Install 'code' command in PATH".

### 4.3 Instalasi Claude Desktop

1. Buka situs resmi Anthropic pada `https://claude.ai/download`.
2. Pilih paket pemasang yang sesuai dengan sistem operasi yang digunakan.
3. Jalankan pemasang dan ikuti petunjuk yang ditampilkan.
4. Masuk menggunakan akun Claude yang telah diberikan.
5. Pastikan aplikasi dapat membuka percakapan baru tanpa galat.

> **Note.** Ketersediaan Claude Desktop untuk setiap sistem operasi dapat berubah. Jika paket pemasang untuk sistem operasi yang digunakan tidak tersedia, gunakan Claude melalui peramban web dan laporkan kondisi tersebut kepada Repository Maintainer.

> **Warning.** Dokumen internal hanya boleh diunggah ke Claude sepanjang kontributor memiliki kewenangan yang sah atas dokumen tersebut. Kredensial, token, dan kunci akses dilarang dimasukkan ke dalam percakapan dalam kondisi apa pun.

`[Perlu dilengkapi: jenis akun Claude yang digunakan perusahaan dan prosedur permohonan akses]`

### 4.4 Instalasi GitHub CLI (Dianjurkan)

| Sistem operasi | Perintah atau cara instalasi |
|---|---|
| Windows | Unduh pemasang dari `https://cli.github.com` |
| macOS | `brew install gh` |
| Linux (Ubuntu/Debian) | Ikuti petunjuk resmi pada `https://cli.github.com` |

**Autentikasi**

```bash
gh auth login
```

Ikuti petunjuk yang ditampilkan untuk menautkan GitHub CLI dengan akun GitHub.

### 4.5 Ringkasan Verifikasi Instalasi

| Perangkat lunak | Perintah verifikasi | Hasil yang diharapkan |
|---|---|---|
| Git | `git --version` | Menampilkan nomor versi |
| VS Code | `code --version` | Menampilkan nomor versi |
| GitHub CLI | `gh --version` | Menampilkan nomor versi |
| Claude Desktop | Membuka aplikasi | Aplikasi terbuka dan pengguna dapat masuk |

---

## 5. Konfigurasi Awal Git

Konfigurasi ini menentukan identitas yang tercatat pada setiap *commit*.

```bash
git config --global user.name "Nama Lengkap"
git config --global user.email "alamat.email@perusahaan.co.id"
git config --global init.defaultBranch main
git config --global core.autocrlf input   # macOS dan Linux
git config --global core.autocrlf true    # Windows
```

**Verifikasi konfigurasi**

```bash
git config --global --list
```

| Parameter | Fungsi |
|---|---|
| `user.name` | Nama yang tercatat pada riwayat *commit* |
| `user.email` | Alamat surel yang tercatat pada riwayat *commit* |
| `init.defaultBranch` | Nama *branch* bawaan saat membuat repository baru |
| `core.autocrlf` | Penyeragaman penanda akhir baris antar sistem operasi |

> **Warning.** Alamat surel yang digunakan harus sesuai dengan ketentuan perusahaan. Alamat surel yang tercatat pada riwayat *commit* bersifat permanen dan sulit diubah setelah perubahan dikirim ke *remote*.

`[Perlu dilengkapi: ketentuan penggunaan alamat surel perusahaan pada konfigurasi Git]`

---

## 6. Cara Melakukan Clone Repository

### 6.1 Persiapan

1. Pastikan akun GitHub telah memperoleh hak akses terhadap repository.
2. Pastikan Git telah terpasang dan terkonfigurasi sebagaimana Bagian 5.
3. Tentukan direktori kerja pada komputer lokal, misalnya `~/projects` atau `D:\projects`.

### 6.2 Langkah Clone

```bash
cd ~/projects
git clone <URL-REPOSITORY>
cd <NAMA-FOLDER-REPOSITORY>
```

`[Perlu dilengkapi: URL resmi repository dan nama folder hasil clone]`

**Alternatif menggunakan GitHub CLI**

```bash
gh repo clone <ORGANISASI>/<NAMA-REPOSITORY>
```

### 6.3 Metode Autentikasi

| Metode | Keterangan | Kesesuaian |
|---|---|---|
| HTTPS dengan Git Credential Manager | Kredensial disimpan oleh sistem | Dianjurkan bagi sebagian besar pengguna |
| HTTPS dengan *personal access token* | Token digunakan sebagai pengganti kata sandi | Digunakan bila diperlukan |
| SSH | Menggunakan pasangan kunci publik dan privat | Dianjurkan bagi pengguna tingkat lanjut |

> **Warning.** *Personal access token* dan kunci privat SSH bersifat rahasia. Kedua hal tersebut dilarang disimpan di dalam repository, dibagikan melalui percakapan, atau dimasukkan ke dalam prompt Claude.

### 6.4 Verifikasi Hasil Clone

```bash
git status
git remote -v
git branch -a
```

| Perintah | Hasil yang diharapkan |
|---|---|
| `git status` | Menampilkan status bersih tanpa perubahan tertunda |
| `git remote -v` | Menampilkan alamat repository *remote* |
| `git branch -a` | Menampilkan daftar *branch* lokal dan *remote* |

---

## 7. Struktur Folder Setelah Clone

### 7.1 Gambaran Umum

Struktur berikut adalah pola umum repository kumpulan skill dan agent.

```text
<nama-repository>/
├── .git/                      # data internal Git, tidak disunting manual
├── .gitignore                 # daftar berkas yang tidak dilacak Git
├── README.md                  # penjelasan singkat repository
├── docs/                      # dokumentasi repository
│   ├── development-workflow.md
│   └── installation-and-setup.md
├── skills/                    # kumpulan skill atau agent
│   └── <nama-skill>/
│       ├── SKILL.md           # instruksi utama skill
│       ├── references/        # bahan rujukan pendukung
│       └── assets/            # template dan berkas pendukung
└── prompts/                   # arsip prompt final
```

> **Note.** Struktur di atas adalah pola umum. Struktur resmi repository dapat berbeda dan mengikuti ketetapan Repository Maintainer.

`[Perlu dilengkapi: struktur folder resmi repository beserta ketentuan penamaannya]`

### 7.2 Penjelasan Setiap Direktori

| Direktori atau berkas | Fungsi | Boleh disunting manual |
|---|---|---|
| `.git/` | Menyimpan riwayat dan konfigurasi Git | Tidak |
| `.gitignore` | Menentukan berkas yang tidak dilacak | Ya, melalui *pull request* |
| `README.md` | Penjelasan singkat dan titik masuk repository | Ya |
| `docs/` | Dokumentasi standar kerja | Ya |
| `skills/` | Kumpulan skill atau agent | Ya |
| `prompts/` | Arsip prompt final agar hasil dapat direproduksi | Ya |

> **Warning.** Direktori `.git/` tidak boleh disunting, dipindahkan, atau dihapus secara manual. Tindakan tersebut dapat merusak semua riwayat repository pada komputer lokal.

---

## 8. Proses Setup Awal Project

### 8.1 Langkah Setup

1. **Buka repository di VS Code.**
   ```bash
   cd <NAMA-FOLDER-REPOSITORY>
   code .
   ```
2. **Pasang ekstensi yang dianjurkan** melalui menu Extensions, sebagaimana tercantum pada Bagian 3.2.
3. **Baca dokumentasi wajib**, yaitu `README.md` dan `docs/development-workflow.md`.
4. **Periksa isi `.gitignore`** untuk memahami berkas yang tidak dilacak.
5. **Buat *branch* kerja** sebelum melakukan perubahan apa pun.
   ```bash
   git checkout -b docs/setup-awal
   ```

> **Warning.** Pengembangan tidak boleh dilakukan langsung pada *branch* utama. Semua perubahan dikerjakan pada *branch* kerja dan digabungkan melalui *pull request*.

### 8.2 Ketentuan `.gitignore`

Berkas berikut umumnya tidak dilacak oleh Git.

| Jenis berkas | Alasan |
|---|---|
| Berkas ZIP hasil generasi | Adalah berkas sementara, bukan hasil akhir |
| Direktori kerja sementara | Tidak relevan bagi kontributor lain |
| Berkas konfigurasi lokal | Bersifat khusus pada komputer masing-masing |
| Berkas yang memuat kredensial | Berisiko terhadap keamanan informasi |

> **Warning.** Berkas yang memuat kredensial tidak boleh dimasukkan ke dalam repository meskipun telah dicantumkan pada `.gitignore`. Kesalahan konfigurasi dapat menyebabkan berkas tersebut ikut terkirim.

---

## 9. Cara Mengimpor Hasil ZIP dari Claude ke Repository

### 9.1 Prinsip

Hasil generasi Claude berkedudukan sebagai **draf**. Berkas ZIP adalah sarana pemindahan, bukan berkas yang disimpan di dalam repository.

### 9.2 Langkah Impor

1. **Unduh berkas ZIP** dari Claude Desktop ke direktori unduhan lokal.
2. **Periksa isi ZIP sebelum diekstrak**, untuk memastikan strukturnya sesuai rancangan.
   ```bash
   unzip -l ~/Downloads/<nama-berkas>.zip
   ```
   Pada Windows, isi arsip dapat diperiksa melalui File Explorer.
3. **Ekstrak ke direktori sementara**, bukan langsung ke dalam repository.
   ```bash
   mkdir -p ~/tmp/import
   unzip ~/Downloads/<nama-berkas>.zip -d ~/tmp/import
   ```
4. **Periksa hasil ekstraksi**, meliputi kelengkapan berkas dan ketepatan struktur folder.
5. **Salin folder hasil ke lokasi yang tepat** di dalam repository.
   ```bash
   cp -r ~/tmp/import/<nama-skill> <NAMA-FOLDER-REPOSITORY>/skills/
   ```
6. **Periksa perubahan yang terdeteksi Git.**
   ```bash
   git status
   ```
7. **Tinjau isi berkas di VS Code** sebelum dilanjutkan ke tahap *commit*.
8. **Hapus berkas ZIP dan direktori sementara** setelah proses impor selesai.

> **Warning.** Berkas ZIP dilarang diekstrak langsung ke akar repository. Tindakan tersebut berisiko menimpa berkas yang sudah ada dan memasukkan berkas yang tidak dikehendaki ke dalam riwayat Git.

> **Warning.** Hasil impor dilarang di-*commit* sebelum ditinjau. Ketentuan tinjauan diuraikan pada dokumen `development-workflow.md`.

### 9.3 Pemeriksaan Setelah Impor

- [ ] Struktur folder sesuai rancangan.
- [ ] Berkas instruksi utama berada pada lokasi yang benar.
- [ ] Tidak ada berkas sementara yang ikut tersalin.
- [ ] Tidak ada kredensial atau data rahasia di dalam berkas.
- [ ] `git status` hanya menampilkan berkas yang dikehendaki.

---

## 10. Verifikasi Keberhasilan Instalasi

Instalasi dinyatakan berhasil jika semua pemeriksaan berikut memberikan hasil yang diharapkan.

### 10.1 Pemeriksaan Perangkat Lunak

| No | Pemeriksaan | Perintah | Hasil yang diharapkan |
|---:|---|---|---|
| 1 | Git terpasang | `git --version` | Nomor versi ditampilkan |
| 2 | Identitas Git terkonfigurasi | `git config --global --list` | `user.name` dan `user.email` sesuai |
| 3 | VS Code terpasang | `code --version` | Nomor versi ditampilkan |
| 4 | Claude Desktop terpasang | Membuka aplikasi | Aplikasi terbuka dan dapat digunakan |
| 5 | GitHub CLI terpasang | `gh --version` | Nomor versi ditampilkan |

### 10.2 Pemeriksaan Repository

| No | Pemeriksaan | Perintah | Hasil yang diharapkan |
|---:|---|---|---|
| 1 | Repository berhasil di-*clone* | `git status` | Status bersih tanpa galat |
| 2 | Alamat *remote* benar | `git remote -v` | Menampilkan alamat repository resmi |
| 3 | Daftar *branch* terbaca | `git branch -a` | Menampilkan *branch* lokal dan *remote* |
| 4 | Repository terbuka di VS Code | `code .` | Struktur folder tampil pada panel Explorer |

### 10.3 Uji Fungsional Ringkas

Uji berikut memastikan alur kerja dasar telah berfungsi, tanpa mengubah isi repository.

```bash
git checkout -b test/verifikasi-instalasi
echo "verifikasi instalasi" > verifikasi.txt
git add verifikasi.txt
git commit -m "chore(setup): uji verifikasi instalasi"
git log --oneline -1
```

Setelah hasil uji dipastikan benar, kembalikan kondisi repository seperti semula.

```bash
git reset --hard HEAD~1
git checkout <BRANCH-UTAMA>
git branch -D test/verifikasi-instalasi
```

> **Warning.** Perintah `git reset --hard` menghapus perubahan yang belum dikirim secara permanen. Perintah tersebut hanya boleh dijalankan pada *branch* uji sebagaimana contoh di atas, dan tidak boleh dijalankan pada *branch* yang memuat pekerjaan yang belum disimpan.

> **Note.** Berkas `verifikasi.txt` dan *branch* uji tidak boleh dikirim ke *remote*.

---

## 11. Troubleshooting Instalasi

### 11.1 Permasalahan pada Git

| Gejala | Kemungkinan penyebab | Solusi |
|---|---|---|
| Perintah `git` tidak dikenali | Git belum terpasang atau belum masuk `PATH` | Pasang ulang Git dan aktifkan opsi penambahan ke `PATH`, lalu buka terminal baru |
| Autentikasi gagal saat *clone* | Kredensial keliru atau hak akses belum diberikan | Periksa hak akses kepada Repository Maintainer, lalu ulangi autentikasi |
| Nama pembuat *commit* keliru | `user.name` atau `user.email` belum dikonfigurasi | Jalankan konfigurasi sebagaimana Bagian 5 |
| Muncul galat penanda akhir baris | Perbedaan konvensi antar sistem operasi | Atur `core.autocrlf` sesuai sistem operasi |
| Gagal *push* karena riwayat tertinggal | Ada perubahan baru pada *remote* | Jalankan `git pull --rebase`, selesaikan konflik, lalu ulangi *push* |

### 11.2 Permasalahan pada VS Code

| Gejala | Kemungkinan penyebab | Solusi |
|---|---|---|
| Perintah `code` tidak dikenali | VS Code belum masuk `PATH` | Jalankan "Shell Command: Install 'code' command in PATH" melalui Command Palette |
| Ekstensi gagal dipasang | Koneksi internet terbatas atau kebijakan jaringan | Periksa koneksi, lalu hubungi unit teknologi informasi jika akses diblokir |
| Diagram Mermaid tidak tampil | Ekstensi pratinjau belum terpasang | Pasang ekstensi Mermaid Preview |

### 11.3 Permasalahan pada Claude Desktop

| Gejala | Kemungkinan penyebab | Solusi |
|---|---|---|
| Tidak dapat masuk ke aplikasi | Akun belum aktif atau kredensial keliru | Periksa status akun kepada pihak yang berwenang |
| Paket pemasang tidak tersedia untuk sistem operasi | Dukungan sistem operasi terbatas | Gunakan Claude melalui peramban web dan laporkan kepada Repository Maintainer |
| Berkas ZIP gagal diunduh | Pengaturan peramban atau kebijakan jaringan | Periksa direktori unduhan dan kebijakan jaringan perusahaan |

### 11.4 Permasalahan pada Proses Impor ZIP

| Gejala | Kemungkinan penyebab | Solusi |
|---|---|---|
| Struktur folder tidak sesuai setelah ekstraksi | Struktur di dalam ZIP keliru | Perbaiki prompt, lalu lakukan generasi ulang |
| Berkas tidak terbaca oleh Git | Berkas berada di luar direktori repository | Pindahkan berkas ke lokasi yang benar, lalu periksa `git status` |
| Berkas ZIP ikut terdeteksi Git | Berkas ZIP berada di dalam repository | Pindahkan berkas ke luar repository dan pastikan tercantum pada `.gitignore` |
| Berkas lama tertimpa | Ekstraksi dilakukan langsung ke akar repository | Kembalikan berkas menggunakan `git checkout -- <berkas>`, lalu ulangi prosedur pada Bagian 9 |

### 11.5 Eskalasi

Jika permasalahan tidak dapat diselesaikan melalui tabel di atas, kontributor menyampaikan laporan yang memuat gejala, langkah yang telah dilakukan, pesan galat, serta sistem operasi dan versi perangkat lunak yang digunakan.

`[Perlu dilengkapi: kanal resmi pelaporan kendala teknis dan pihak yang bertanggung jawab menanganinya]`

---

## 12. Checklist Sebelum Mulai Mengembangkan

Semua butir berikut wajib terpenuhi sebelum pengembangan dimulai.

**Perangkat lunak**

- [ ] Git telah terpasang dan menampilkan nomor versi.
- [ ] Visual Studio Code telah terpasang.
- [ ] Claude Desktop telah terpasang atau akses melalui peramban telah tersedia.
- [ ] Ekstensi VS Code yang dianjurkan telah terpasang.
- [ ] GitHub CLI telah terpasang, jika digunakan.

**Konfigurasi**

- [ ] `user.name` dan `user.email` telah dikonfigurasi sesuai ketentuan perusahaan.
- [ ] `core.autocrlf` telah disesuaikan dengan sistem operasi.
- [ ] Metode autentikasi ke GitHub telah berfungsi.

**Repository**

- [ ] Repository berhasil di-*clone* tanpa galat.
- [ ] `git status` menampilkan status bersih.
- [ ] Alamat *remote* telah diperiksa dan sesuai.
- [ ] Struktur folder repository telah dipahami.
- [ ] Isi `.gitignore` telah diperiksa.

**Pemahaman standar kerja**

- [ ] `README.md` telah dibaca.
- [ ] `docs/development-workflow.md` telah dibaca dan dipahami.
- [ ] Ketentuan bahwa hasil generasi Claude adalah draf yang wajib ditinjau telah dipahami.
- [ ] Ketentuan larangan menyertakan kredensial dan dokumen rahasia telah dipahami.

**Kesiapan bekerja**

- [ ] *Branch* kerja telah dibuat dan tidak bekerja pada *branch* utama.
- [ ] Hasil uji verifikasi instalasi telah berhasil dan kondisi repository telah dikembalikan.
- [ ] Berkas dan *branch* uji telah dihapus.

> **Note.** Bagi mahasiswa magang, semua butir di atas diverifikasi bersama pembimbing sebelum kontribusi pertama diajukan.

---

## 13. Glosarium

| Istilah | Penjelasan |
|---|---|
| **Branch** | Jalur pengembangan terpisah di dalam Git yang memungkinkan pekerjaan berjalan tanpa mengganggu jalur utama. |
| **Clone** | Proses menyalin repository dari server ke komputer lokal beserta riwayatnya. |
| **Commit** | Rekaman satu satuan perubahan pada riwayat Git. |
| **Ekstensi** | Komponen tambahan yang memperluas kemampuan VS Code. |
| **Kredensial** | Data rahasia yang digunakan untuk autentikasi, misalnya kata sandi, token, dan kunci akses. |
| **PATH** | Daftar direktori yang dirujuk sistem operasi ketika mencari program yang dijalankan dari terminal. |
| **Personal access token** | Token yang digunakan sebagai pengganti kata sandi pada autentikasi GitHub. |
| **Placeholder** | Penanda `[Perlu dilengkapi: ...]` untuk informasi yang belum tersedia. |
| **Pull request** | Usulan penggabungan perubahan dari satu *branch* ke *branch* lain, disertai proses tinjauan. |
| **Push** | Pengiriman *commit* dari repository lokal ke repository *remote*. |
| **Rebase** | Penyelarasan riwayat lokal terhadap riwayat *remote*. |
| **Remote** | Repository yang tersimpan di server, dalam hal ini GitHub. |
| **Repository** | Tempat penyimpanan berkas project beserta semua riwayat perubahannya. |
| **Terminal** | Antarmuka berbasis teks untuk menjalankan perintah pada sistem operasi. |

---

**Pemeliharaan dokumen.** Dokumen ini diperbarui setiap kali terjadi perubahan pada kebutuhan sistem, perangkat lunak yang digunakan, atau prosedur setup. Usulan perubahan diajukan melalui mekanisme yang berlaku pada repository.

`[Perlu dilengkapi: pemilik dokumen, peninjau, dan jadwal peninjauan berkala]`
