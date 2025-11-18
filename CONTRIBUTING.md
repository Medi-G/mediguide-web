# 🏥 Panduan Kontribusi Proyek MediGuide

Selamat datang di MediGuide Developer Handbook! 👋 Dokumen ini adalah acuan utama ("Kitab Suci") bagi tim pengembang MediGuide. Tujuannya agar kode kita rapi, konflik terminimalkan, dan kolaborasi antara tim FE (Frontend) dan tim lainnya berjalan mulus.


## 0. Persiapan Awal (Setup Environment)

Lakukan langkah ini hanya sekali saat pertama kali bergabung di proyek.

**Prasyarat:**

    Node.js: (Gunakan versi LTS terbaru)

    Git: Pastikan sudah terinstall.

    VS Code: Editor yang disarankan.

**Langkah Installasi:**

    Clone Repository: Masuk ke terminal dan jalankan:
    
    - git clone <link-repo-github-mediguide-kalian>
    
    - cd mediguide

**Install Dependencies: Download semua library yang dibutuhkan proyek.**
    
    - npm install


**Setup Environment Variable: Duplikat file .env.example menjadi .env.local dan isi variabel yang diperlukan (minta API Key ke Lead jika ada).**
    
    cp .env.example .env.local

**Jalankan Project:**

    npm run dev

    Buka http://localhost:3000. Jika halaman muncul, setup berhasil! 🚀

## 1. Alur Kerja Harian (The Workflow)

Ikuti Flow ini untuk setiap kali kamu mengerjakan tugas baru.

**A. Sebelum Coding (Sync & Branching)**

Selalu pastikan kodemu up-to-date sebelum membuat branch baru agar tidak bentrok.

    Pindah ke branch utama (misal develop atau main):
    
    git checkout develop

Ambil kode terbaru dari server:

   ```bash
    git pull origin develop
   ```

Buat Branch Baru (Lihat aturan penamaan di bawah):
Bash

    git checkout -b <nama-branch-sesuai-aturan>

**B. Saat Coding**

    Fokus kerjakan satu fitur/tugas per branch.

    Jangan mencampur-aduk fitur (misal: mengerjakan Login dan Footer dalam satu branch).

    Lakukan commit secara berkala (Save points).

**C. Setelah Selesai (Push & PR)**

    - Push branch kamu ke GitHub:
    git push origin <nama-branch-kamu>

    - Buka GitHub dan buat Pull Request (PR) ke branch develop.

    - Code Review: Minta teman tim lain untuk mengecek kodemu.

    - Merge: Setelah diapprove, merge PR tersebut.

## 2. "Kamus" Tim (Aturan Penamaan)

Konsistensi adalah kunci kerapian kode.

**A. Penamaan Branch**

Format: tipe/kategori-deskripsi-singkat

    Tipe:

        feature: Fitur baru (e.g., bikin halaman baru, tombol baru).

        bugfix: Memperbaiki error/bug.

        hotfix: Perbaikan urgent di production.

        chore: Setup, config, update library (bukan kode fitur).

    Kategori:

        fe: Frontend (UI, React Component, CSS).

        be: Backend (API, Database).

        assets: Gambar, Font, Icon.

    Deskripsi: Menggunakan kebab-case (huruf kecil dipisah strip).

**Contoh Benar:**

    ✅ feature/fe-landing-page

    ✅ bugfix/fe-navbar-responsive

    ✅ chore/setup-tailwind

**Contoh Salah:**

    ❌ bikin-halaman-login (Kurang tipe & kategori)

    ❌ feature/halaman login (Ada spasi)

**B. Pesan Commit (Conventional Commits)**

Gunakan Bahasa Indonesia/Inggris (sepakati tim), format: <tipe>: <pesan singkat jelas>

Daftar Tipe:

    feat: Fitur baru.

    fix: Perbaikan bug.

    style: Perubahan visual (CSS/SCSS) tanpa mengubah logika.

    refactor: Merapikan kode tanpa mengubah fitur (optimasi).

    docs: Update dokumentasi/readme.

Contoh:

    feat: membuat komponen card dokter

    style: memperbaiki margin pada tombol register

    fix: memperbaiki error saat input tanggal lahir

## C. Judul Pull Request (PR)

Format: [KATEGORI] Judul Tugas

    [FE] : Frontend focus.

    [BE] : Backend focus.

    [UI] : Styling focus.

    [SETUP] : Konfigurasi awal.

Contoh:

    [FE] Implementasi Integrasi API List Dokter

    [UI] Redesign Halaman Profile Pasien

## 3. Do's and Don'ts

    - Jangan Push ke Main/Develop Langsung: Selalu gunakan Pull Request. Branch develop adalah zona suci yang kodenya harus bersih dan tidak error.

    - Jaga Rahasia: Jangan pernah commit file .env atau API Key ke GitHub. Pastikan .gitignore sudah benar.

    - Satu PR = Satu Fitur: Jangan menggabungkan perbaikan bug navbar dengan pembuatan halaman dashboard dalam satu PR. Pecah menjadi dua.

    - Hapus Branch: Setelah PR di-merge, hapus branch lokalmu agar tidak menumpuk:
     git branch -d feature/fe-nama-branch-lama
