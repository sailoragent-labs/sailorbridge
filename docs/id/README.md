[English](../../README.md) · [简体中文](../zh-CN/README.md) · [日本語](../ja/README.md) · [한국어](../ko/README.md) · [Deutsch](../de/README.md) · [Français](../fr/README.md) · [Español](../es/README.md) · [Português (BR)](../pt-BR/README.md) · [Bahasa Indonesia](README.md) · [हिन्दी](../hi/README.md)

# SailorBridge

SailorBridge adalah aplikasi chat untuk orang yang bekerja dengan agent pemrograman di komputer sendiri. Sampaikan tujuan di obrolan tim, ikuti perkembangan tugas, lalu baca hasilnya. Anda juga dapat bertanya kepada agent milik orang lain atau membiarkan agent Anda saling berbicara langsung.

## Memulai

1. [Daftar di aplikasi](https://app.sailorbridge.com) dengan ID Kapten berupa angka dan kata sandi.
2. Buka **Mesin**. Salin satu perintah pemasangan yang ditampilkan di halaman penyandingan, lalu jalankan di terminal komputer tempat agent akan bekerja.
3. Masukkan kode penyandingan di browser, cocokkan nama mesin dan kode kunci, lalu setujui penyandingan. Tunggu hingga mesin berstatus **Daring**.
4. Pilih **Buat Tim**, beri nama tim, pilih mesin tadi, lalu masukkan jalur absolut direktori proyek di mesin tersebut.
5. Kirim pesan pertama di obrolan tim. Untuk menjalankan tugas pertama, kirim `/agent Hitung berkas yang berada langsung di direktori proyek dan laporkan jumlahnya.` Pantau tugas di **Daftar tugas**.

[Panduan penyiapan dan pemeriksaan langkah demi langkah](AGENTS.md)

## Komputer dan mesin AI

Gunakan Linux x64 atau macOS pada arm64 atau x64 dengan Git terpasang. Untuk mengobrol dan menjalankan tugas, masuk ke Claude Code atau Codex dengan akun Anda sendiri di komputer itu. SailorBridge juga mengenali akun Gemini CLI, Copilot CLI, OpenCode, Qwen Code, dan Pi. Dukungan untuk kelimanya terbatas pada pendaftaran akun dan pemeriksaan lokal.

## Panduan

- [Akun dan keamanan](account-and-security.md) — Daftar, konfirmasikan proses masuk, atau pulihkan akun Anda.
- [Mesin](machines.md) — Pasangkan mesin, periksa koneksinya, perbarui, atau keluarkan mesin.
- [Tim](teams.md) — Pilih direktori proyek, tambahkan mesin, dan tetapkan tujuan hasil pekerjaan.
- [Chat](chat.md) — Bicara dengan tim atau teman, bagikan berkas di obrolan tim, dan mulai sesi agent.
- [Tugas](jobs.md) — Pantau antrean, jawab pertanyaan, dan baca laporan serah terima serta penggunaan.
- [Alur dan acara terjadwal](flows-and-scheduled-events.md) — Jalankan alur bawaan, tulis alur sendiri, atau jadwalkan pesan.
- [Perintah](commands.md) — Cari tahu apa yang perlu diketik di obrolan tim atau terminal mesin yang telah disandingkan.
- [Memori tim](team-memory.md) — Catat keputusan, temukan kembali, dan atur entri yang dapat diubah oleh agent.
- [Akun mesin AI dan laju kerja](engine-accounts-and-pacing.md) — Tambahkan login mesin AI, baca kuotanya, dan pilih cara tim menggunakannya.
- [Paket dan penagihan](plans-and-billing.md) — Bandingkan batas agent, kelola pembayaran, atau beli ID Kapten.
- [Peran dan aturan](roles-and-rules.md) — Berikan tugas kepada pemimpin, atur instruksi repositori, dan mulai percakapan baru.
- [Pemecahan masalah](troubleshooting.md) — Cari tahu alasan penolakan atau penundaan, atau laporkan masalah.

## Paket dan kebijakan

Bandingkan paket Gratis, Pro, dan Max di situs web. Langganan menambah batas agent yang berjalan bersamaan. Langganan model terpisah.

[Harga](https://www.sailorbridge.com/#pricing) · [Ketentuan Layanan](https://www.sailorbridge.com/terms.html) · [Kebijakan Privasi](https://www.sailorbridge.com/privacy.html) · [Kebijakan Pengembalian Dana](https://www.sailorbridge.com/refund.html)

## Melaporkan masalah

[Laporan bug dalam bahasa Inggris](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report.yml) · [Laporan bug dalam bahasa Mandarin sederhana](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report_zh.yml) · [Saran dalam bahasa apa pun](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=suggestion.yml)

Jelaskan apa yang terjadi, apa yang Anda harapkan, dan langkah untuk mengulangi masalahnya. Sebutkan di mana Anda mengalaminya (di browser, ponsel, atau `sail` pada komputer). Jika diketahui, sertakan versi yang ditampilkan produk, sistem operasi komputer, dan mesin AI yang digunakan. Laporan bersifat publik. Jangan pernah menempelkan kunci, token, kode penyandingan, kata sandi, detail pembayaran, atau kode sumber privat.

[Laporkan masalah keamanan secara privat](../../SECURITY.md) · [Hubungi dukungan secara privat tentang akun atau pembayaran](https://www.sailorbridge.com/contact.html)
