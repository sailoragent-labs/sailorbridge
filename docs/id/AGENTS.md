[English](../../AGENTS.md) · [简体中文](../zh-CN/AGENTS.md) · [日本語](../ja/AGENTS.md) · [한국어](../ko/AGENTS.md) · [Deutsch](../de/AGENTS.md) · [Français](../fr/AGENTS.md) · [Español](../es/AGENTS.md) · [Português (BR)](../pt-BR/AGENTS.md) · [Bahasa Indonesia](AGENTS.md) · [हिन्दी](../hi/AGENTS.md)

# Panduan penyiapan SailorBridge

## 1. Siapkan komputer

Gunakan komputer yang Anda kendalikan dengan Linux x64 atau macOS pada arm64 atau x64. Pasang Git dan salah satu dari Claude Code atau Codex. Masuk dengan akun Anda sendiri dan tentukan direktori proyek tempat tim akan bekerja.

**Periksa** — `git --version` dan salah satu dari `claude --version` atau `codex --version` menampilkan versi masing-masing. Jika Claude Code atau Codex sudah terpasang tetapi Anda belum masuk, jalankan `claude login` atau `codex login` di komputer itu. Komputer bisa disandingkan lebih dulu. Masuklah sebelum memulai obrolan atau tugas.

## 2. Daftar di browser

Buka [aplikasi](https://app.sailorbridge.com) dan pilih **Daftar**. Untuk panduan ini, masukkan ID Kapten berupa angka yang masih tersedia dan ditampilkan sebagai gratis, buat kata sandi, konfirmasi usia, dan setujui ketentuan layanan.

**Periksa** — Aplikasi terbuka dan Anda dapat mengakses **Mesin**.

## 3. Jalankan perintah pemasangan

Buka **Mesin**, lalu **Pasangkan mesin baru**. Salin satu perintah pemasangan yang terlihat dan jalankan di komputer dari langkah 1. Perintah itu memasang `sail` dan otomatis memulai penyandingan.

**Periksa** — Terminal menampilkan kode penyandingan delapan karakter dan sisa waktu berlakunya. Jika kode kedaluwarsa, jalankan `sail login` untuk mendapat kode baru.

- **Sudah disandingkan dengan alamat ini?** Jalankan `sail host status`. Jika sudah terhubung, lanjutkan ke langkah 5. Untuk memulihkan layanan di alamat yang sama, jalankan `sail login`. Layanan akan dimulai ulang dengan kredensial yang ada.
- **Alamat salah (`origin_mismatch`)?** Untuk pindah alamat, jalankan `sail uninstall`, lalu salin dan jalankan perintah pemasangan dari halaman Mesin di aplikasi yang dituju. Pencopotan menghapus data lokal SailorBridge, termasuk salinan kerjanya.

## 4. Setujui mesin

Masukkan kode penyandingan di halaman penyandingan pada browser, lalu pilih **Pasangkan**. Cocokkan nama mesin dan **Kode kunci** dengan yang tertera di terminal. Saat pertama kali menyandingkan mesin, baca dan setujui pemberitahuan tentang izin pengguna yang menjalankan `sail`, lalu pilih **Setujui mesin**.

**Periksa** — Tunggu hingga status **Daring** muncul di **Mesin**. Terminal juga mengonfirmasi bahwa mesin sudah disandingkan dan daring.

## 5. Buat tim

Pilih **Buat Tim**. Beri nama tim, pilih mesin yang daring, dan masukkan jalur absolut pada mesin itu di kolom **Direktori proyek**. Jika direktori belum ada, SailorBridge membuatnya saat pertama kali digunakan. Di bagian **Tujuan**, biarkan **Gabung otomatis** terpilih untuk menggabungkan perubahan ke cabang utama di repositori jarak jauh. Pilih **Cabang** jika setiap tugas perlu dikirim ke cabang tersendiri untuk ditinjau. Lalu buat tim.

**Periksa** — Mesin yang dipilih muncul di tim baru dengan status **Daring**.

## 6. Kirim pesan pertama

Buka **Obrolan** tim dan tanyakan “Direktori proyek mana yang kita gunakan?”

**Periksa** — **Pemimpin** menjawab dalam obrolan yang sama.

## 7. Selesaikan tugas pertama

Kirim `/agent Hitung berkas yang berada langsung di direktori proyek dan laporkan jumlahnya.` di obrolan tim. Buka **⋯ → Daftar tugas** untuk mengikuti perkembangannya.

**Periksa** — Tugas berstatus **Selesai**. Buka laporan serah terima dan baca jumlah berkasnya.
