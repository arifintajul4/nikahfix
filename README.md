# NIKAHFIX

**NIKAHFIX** adalah sebuah website undangan pernikahan yang terinspirasi dari tampilan _Netflix_, memberikan pengalaman visual menarik dan modern untuk pengguna. Proyek ini dibangun menggunakan **React** dengan bundler **Vite**, dilengkapi dengan **Supabase** untuk mengelola data undangan, serta dirancang agar mudah diakses, responsif, dan estetis.

## Demo

Anda dapat melihat demo langsung dari NIKAHFIX di sini: [NIKAHFIX - Demo](https://nikahfix-v01.vercel.app/).
Jika anda memiliki tujuan spesifik undangannya, bisa dibuat link seperti berikut [https://nikahfix-v01.vercel.app/?to=tajul+dan+gorbon](https://nikahfix-v01.vercel.app/?to=tajul+dan+gorbon)

## Teknologi yang Digunakan

- **React**: Library JavaScript untuk membangun antarmuka pengguna.
- **Vite**: Bundler modern untuk pengembangan aplikasi web cepat dengan konfigurasi minimal.
- **TailwindCSS**: Untuk mendesain tampilan visual agar lebih menarik.
- **Supabase**: Backend sebagai layanan untuk autentikasi, database, dan API real-time.
- **Vercel**: Platform hosting yang digunakan untuk menyajikan demo.

## Instalasi

Berikut adalah langkah-langkah untuk menginstal proyek ini di lingkungan lokal Anda:

1. **Clone Repository**:

   `git clone https://github.com/arifintajul4/nikahfix.git`

2. **Masuk ke Direktori Proyek**:

   `cd nikahfix`

3. **Instal Dependensi**:
   Pastikan Anda sudah menginstal Node.js. Jalankan perintah berikut untuk menginstal semua dependensi yang diperlukan.

   `npm install`

4. **Menjalankan Proyek**:
   Setelah semua dependensi terpasang, jalankan proyek dengan perintah:

   `npm run dev`

5. **Mengakses Proyek**:
   Buka browser Anda dan akses proyek di

   `http://localhost:5173`

---

# Cara Integrasi Supabase di NIKAHFIX (Untuk Pemula)

NIKAHFIX menggunakan **Supabase** untuk menyimpan data ucapan/pesan undangan. Tenang saja, pengaturan Supabase ini sangat mudah dan tidak memerlukan kemampuan memprogram. Di bawah ini adalah langkah-langkah simpelnya:

## Langkah 1: Buat Proyek Supabase

1. Kunjungi [Supabase.com](https://supabase.io) dan daftar/login.
2. Klik tombol **"New Project"**.
3. Pilih Organisasi dan beri nama proyek Anda (misalnya: `Undangan Nikah Ku`).
4. Buat **Database Password** (simpan baik-baik atau gunakan tombol _Generate a password_).
5. Pilih Region (disarankan "Singapore" agar lebih cepat).
6. Klik **"Create New Project"** dan tunggu beberapa menit hingga proyek siap (Status _Provisioning_ selesai).

## Langkah 2: Buat Tabel Supabase Otomatis

Kita perlu membuat tempat menyimpan pesan tamu (namanya 'Table'). Kami sudah menyiapkan script otomatis agar Anda tidak perlu membuatnya secara manual.

1. Di Dashboard Supabase proyek Anda, lihat menu di sebelah kiri dan pilih **"SQL Editor"** (ikon `< >`).
2. Klik tombol **"New Query"**.
3. Buka file `setup_supabase.sql` yang ada di folder proyek ini. Copy seluruh isi teks dalam file tersebut.
4. Paste (tempel) teks tersebut ke layar "SQL Editor" di Supabase.
5. Klik tombol hijau **"Run"** (atau tekan `Ctrl` + `Enter`).
6. Jika di bawah layar muncul pesan "Success", berarti tabel Anda sudah selesai dibuat dengan aman!

_(Catatan: Langkah ini membuat tabel bernama `nikahfix` dan mengatur izin keamanan agar semua tamu bisa mengisi & membaca pesan)._

## Langkah 3: Sambungkan NIKAHFIX dengan Supabase

Sekarang saatnya menghubungkan website NIKAHFIX dengan Supabase.

1. Di Dashboard Supabase Anda, masuk ke menu **"Project Settings"** (ikon roda gigi di kiri bawah).
2. Pilih menu **"API"**.
3. Di dalam proyek NIKAHFIX Anda, cari file bernama `.env.example`, lalu ubah namanya menjadi **`.env`** (atau buat file baru bernana `.env`).
4. Buka file `.env` tersebut dan isi sesuai dengan data dari Supabase Anda:

```env
VITE_APP_SUPABASE_URL=Masukkan "Project URL" dari halaman API Supabase Anda
VITE_APP_SUPABASE_ANON_KEY=Masukkan "anon" / "public" key dari halaman API Supabase Anda
VITE_APP_TABLE_NAME=nikahfix
```

**Selesai!** Sekarang NIKAHFIX sudah siap digunakan dan bisa menerima ucapan dari tamu Anda.

## Struktur Proyek

Berikut adalah struktur direktori proyek yang telah terintegrasi dengan Supabase:

- `src/` - Berisi komponen utama, logika aplikasi, dan konfigurasi Supabase.
  - `supabaseClient.js` - File konfigurasi Supabase (sudah disingkronisasi dengan `.env`).
  - `App.jsx` - Komponen utama aplikasi.
- `public/` - Berisi aset-aset statis, seperti gambar dan ikon.
- `.env` - Berisi variabel lingkungan untuk kredensial Supabase.
- `setup_supabase.sql` - Script otomatis untuk mempermudah pengaturan database Anda.

---
