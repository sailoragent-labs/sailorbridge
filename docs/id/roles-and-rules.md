[← SailorBridge](README.md)

# Peran dan aturan

Setiap tim memiliki **Pemimpin**. Anda berbicara dengannya di obrolan tim. Pemimpin menjawab pertanyaan, menjalankan perintah singkat, dan menyerahkan pekerjaan yang lebih panjang ke sebuah alur. Pelaksana menjalankan salah satu langkah alur itu di mesin tim. Anda memberi instruksi tetap kepada mesin AI di repositori proyek. Penyunting peran dan pustaka aturan tidak tersedia.

## Berikan pekerjaan yang sesuai kepada tim

Buka **Obrolan** untuk tim Anda. Tanyakan “Kita sedang berada di cabang mana?” **Pemimpin** dapat memeriksa direktori tim dan menjawab di percakapan. Untuk pemeriksaan singkat di mesin lain dalam tim, ketik `@`, pilih mesin, dan sebutkan apa yang harus diperiksa. Anda mendapat ringkasan hasilnya.

Untuk pekerjaan yang ingin Anda terima setelah ditinjau, kirim permintaan seperti “Perbarui petunjuk penyiapan dan minta agar petunjuk itu ditinjau.” Saat **Pemimpin** mengusulkan alur latar belakang, baca tugas di kartu. Pilih **Ya, Kerjakan** untuk memasukkannya ke antrean atau **Bukan Begitu** untuk menjelaskan apa yang perlu diubah. Buka **Daftar tugas** untuk mengikuti langkah pekerja. Jika pekerja memerlukan keputusan, **Pemimpin** memeriksa apa yang sudah diketahui tim dan bertanya kepada Anda di obrolan jika memerlukan jawaban.

## Berikan instruksi tetap kepada mesin AI

Letakkan instruksi untuk seluruh proyek di `AGENTS.md` dalam repositori untuk Codex atau `CLAUDE.md` untuk Claude Code. Misalnya, catat perintah yang harus dijalankan sebelum menyerahkan perubahan. Mesin AI membaca berkas instruksinya saat bekerja di repositori itu. Untuk fakta yang perlu diingat tim di berbagai tugas, Anda juga bisa meminta tim mengingatnya di obrolan. [Memori tim](team-memory.md)

## Lanjutkan percakapan setelah jeda

Kirim pesan berikutnya dalam obrolan tim yang sama. **Pemimpin** dapat memulai sesi mesin AI baru setelah jeda panjang, pergantian mesin AI, atau perpindahan ke mesin lain. Pemimpin mengambil ringkasan tim yang tersimpan, pesan terbaru, memori tim, dan tugas yang belum selesai. Jika muncul **Merapikan percakapan…**, Anda tetap bisa mengirim pesan. **Pemimpin** menjawab setelah selesai meringkas.

## Jika ada masalah

- Jika detail lama hilang, sertakan nomor tugas, keputusan, atau berkas yang relevan di pesan berikutnya. Sesi baru menerima 20 pesan terbaru dan ringkasan jika tersedia.
- Jika instruksi yang keliru dari percakapan sebelumnya terus terbawa, pilih **Kosongkan obrolan**, periksa nama tim, dan konfirmasikan. Pesan sebelumnya hilang dari tampilan obrolan dan sesi berikutnya dimulai tanpa ringkasan lama. Jika instruksi berasal dari berkas repositori atau memori tim, perbaiki di sana.
- Jika **Pemimpin** kehabisan waktu, ajukan lagi langkah yang lebih kecil atau kirim pekerjaan yang lebih panjang sebagai tugas. [Perintah](commands.md)
