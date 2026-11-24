[← SailorBridge](README.md)

# Alur dan acara terjadwal

Alur memberi tim Anda cara yang dapat diulang untuk melakukan tugas. Alur memiliki nama yang bisa Anda ketik di obrolan, serta langkah dan opsi yang disimpan untuk tim itu. Acara terjadwal mengirim pesan ke obrolan tim pada waktu pilihan Anda. Pesan itu dapat bertanya kepada pemimpin atau memulai alur.

## Temukan dan jalankan alur

Di obrolan tim, ketik `/` untuk melihat alur aktif dan keterangannya. Pilih alur, tambahkan apa yang Anda inginkan, lalu kirim. Contohnya, `/ask What should the export include?` memulai percakapan tentang kebutuhan ekspor. Alur interaktif bertanya di obrolan. Alur latar belakang masuk ke **Daftar tugas**.

Saat Anda mengirim perintah alur latar belakang, **Pemimpin** biasanya menggunakan percakapan untuk menyusun uraian tugas dan memasukkannya ke antrean. Jika **Langsung mulai** aktif untuk alur itu, kata-kata Anda menjadi uraian dan tugas langsung mengantre. Opsi ini nonaktif secara bawaan untuk alur latar belakang bawaan. Saat pemimpin mengusulkan tugas atas inisiatifnya sendiri, pilih **Ya, Kerjakan** untuk memulainya.

| Alur bawaan | Kapan digunakan dan apa hasilnya |
| --- | --- |
| `/ask` | Perjelas keputusan. Jawab pertanyaan satu per satu untuk mendapat ringkasan kebutuhan. |
| `/plan` | Rencanakan pekerjaan yang membutuhkan beberapa tugas. Baca rencana dan kelompok tugas yang diusulkan, lalu pilih **Antrekan Semua Tugas**, **Ubah Rencana**, atau **Nanti Saja**. Perencanaan itu sendiri merupakan tugas yang bisa dipantau. |
| `/agent` | Berikan tugas mekanis atau yang menyita waktu kepada pekerja. Satu pekerja mengerjakannya dan melaporkan hasil tanpa putaran peninjauan. |
| `/write-review` | Berikan tugas implementasi kepada tim dan jelaskan cara memeriksanya. Penulis mengerjakan tugas, pemeriksaan dijalankan, lalu penulis dan peninjau memeriksa hasilnya. |
| `/memory-tidy` | Tinjau memori tim, hapus entri yang tidak berguna lagi, dan gabungkan duplikat. Laporan serah terima mencantumkan tindakan dan saran yang memerlukan keputusan Anda. Tim juga bisa menjalankannya otomatis saat ada entri yang perlu diperiksa, paling banyak sekali dalam 24 jam. |
| `/docs-tidy` | Periksa kembali dokumentasi yang terdampak perubahan dan periksa sampel sisanya secara bergiliran. Laporan serah terima membedakan perbaikan mekanis dari pertanyaan untuk Anda. |
| `/code-sweep` | Periksa kode untuk mencari peluang perapian. Baca usulan bernomor di laporan serah terima dan beri tahu pemimpin mana yang harus dikerjakan. Pemeriksaan ini bersifat hanya-baca. |
| `/write-flow` dan `/edit-flow` | Uraikan tugas berulang untuk membuat alur, atau jelaskan bagaimana alur yang ada harus diubah. Hasilnya disimpan untuk tim Anda. |

## Pilih siapa yang menulis dan meninjau

Buka ⋯ di obrolan tim, pilih **Alur tim**, lalu buka `/write-review`. Halaman menampilkan langkah dan opsi yang dipakai untuk tugas mendatang di tim ini.

| Opsi | Cara menggunakannya |
| --- | --- |
| **Siapa yang menulis** | Pertahankan **Otomatis** untuk memilih penyedia sesuai kesulitan tugas atau pilih mesin AI untuk langkah penulisan. |
| **Siapa yang meninjau** | Pertahankan **Otomatis** untuk mencari peninjau independen dari keluarga model berbeda atau pilih mesin AI untuk peninjauan. Penulis melakukan peninjauan mandirinya sendiri. Pengaturan model tim menentukan model yang digunakan. |
| **Putaran tinjauan mandiri** | Pilih 0–10, dengan nilai bawaan 3. Setiap putaran, penulis memeriksa pekerjaannya, memperbaiki temuan, dan memeriksa kembali hingga tidak ada temuan atau batas tercapai. Atur ke 0 untuk melewati peninjauan mandiri. |
| **Maksimal berapa putaran** | Pilih 0–10, dengan nilai bawaan 6. Atur ke 0 untuk Solo, yang melewati peninjauan independen dan mempertahankan pengaturan peninjauan mandiri. |

Temuan P1 membuat seluruh perubahan perlu ditinjau ulang. Temuan yang lebih ringan membuat perbaikannya perlu ditinjau. Mulai putaran ketiga, jika tidak ada P1, penulis dapat menyelesaikan sisa perbaikan dan menyerahkan hasil tanpa peninjauan lagi. Jika temuan P1 masih ada saat batas putaran tercapai, buka **Laporan serah terima** untuk melihat temuan yang menghentikan tugas.

Agar kode dapat digabungkan, seluruh pemeriksaan yang berlaku harus lulus pada commit akhir. Jika perubahan dokumentasi saja tidak memiliki pemeriksaan yang berlaku, peninjau independen harus menyetujui alasannya. Di Solo, perubahan tanpa pemeriksaan tetap berstatus **Belum Selesai**. [Baca pemeriksaan dan laporan serah terima tugas](jobs.md)

## Tulis atau sunting alur tim

1. Di obrolan tim, kirim `/write-flow` diikuti langkah, kriteria selesai, tindakan jika suatu langkah gagal, dan hasil yang harus diserahkan. Contohnya, `/write-flow List Markdown files changed since the last commit. Report their paths. If none changed, say so.`
2. Jika penulis membutuhkan keputusan, jawab pertanyaan di obrolan. Setelah alur ditulis dan diperiksa, obrolan menampilkan nama yang dipakai untuk menyimpannya. Pilih **Lihat alur** untuk membaca deskripsi, langkah, dan opsinya. Nama itu kini tersedia di menu `/`.
3. Untuk mengubah alur, pilih **Edit di Chat** atau kirim `/edit-flow <name> <change>`. Jelaskan apa yang harus diubah dan dipertahankan. Menyunting alur khusus menggantikan versi tim itu. Menyunting alur bawaan menghasilkan alur khusus dengan nama berbeda. Baca laporan serah terima untuk melihat nilai opsi yang berlaku dan aturan langkah yang terhapus karena penyuntingan.

Anda juga bisa mengubah opsi alur di halaman detailnya. Jika alur mengikuti instruksi tersimpan, Anda bisa menyuntingnya di sana untuk pelaksanaan berikutnya. Matikan **Aktif** untuk mengeluarkan alur dari menu tim untuk pelaksanaan baru. Tugas yang mengantre dan yang sedang berjalan dapat diselesaikan. Kedua perintah penulisan alur tetap tersedia.

## Jadwalkan pesan

1. Di menu ⋯ tim, buka **Acara terjadwal** dan gunakan tombol tambah untuk **Tambah acara**. Di **Pesan yang ingin disampaikan**, masukkan pesan yang ingin dikirim, hingga 16 KiB. Contohnya, `/docs-tidy Check the project documentation.`
2. Pilih **Frekuensi**. Pilih **Sekali** untuk tanggal dan waktu lokal yang akan datang, **Setiap hari** untuk waktu setiap hari, atau **Hari kerja** untuk Senin sampai Jumat. Dengan **Setiap beberapa menit**, atur **Interval (menit)** dari 5 hingga 720. Gunakan **Dari** dan **Sampai** untuk membatasi jam pelaksanaan dalam sehari.
3. Periksa **Zona waktu**, yang awalnya mengikuti zona browser Anda, lalu simpan. Daftar menampilkan baris pertama pesan dan waktu pelaksanaan berikutnya. Membuat acara mengizinkan pengiriman pesan. Pada waktu yang ditentukan, pesan muncul atas nama Anda di obrolan dengan penanda **Terjadwal**. Setiap pemicu memakai satu giliran penuh pemimpin.

Waktu mengikuti zona pilihan. Jika perubahan waktu musim panas melewati waktu terjadwal, acara menggunakan waktu valid berikutnya. Jika jam mengulang waktu itu, acara memakai kejadian pertama. Acara berkala dengan jendela waktu melewati kejadian di luar jendela itu.

Buka acara untuk menyunting pesan atau waktunya. Menyimpan akan menghitung ulang waktu berikutnya. Nonaktifkan acara untuk menghentikan pesan mendatang, lalu aktifkan saat ingin melanjutkan. Pengaktifan kembali dimulai dari saat itu. Setelah gangguan layanan penjadwalan, hanya kejadian terbaru yang terlewat yang dikirim. Cari acara berdasarkan teks atau nomor persisnya, seperti `#6`. Gunakan **Selesai** untuk mencari acara sekali jalan yang sudah selesai.

## Jika ada masalah

- Jika obrolan tidak mengenali alur, ketik `/` untuk melihat nama-nama yang aktif bagi tim ini. Aktifkan lagi alur di **Alur tim** jika perlu. Jika rencana tidak dapat mengantrekan kelompok tugas karena `/write-review` nonaktif, aktifkan sebelum mengirimkan ulang pekerjaan.
- Satu tim bisa memiliki 30 alur khusus. Saat mencapai batas, hapus alur khusus yang tidak diperlukan sebelum membuat alur lain. Jika nama sudah dipakai, sunting alur itu atau pilih nama lain. Jika penyuntingan melaporkan bahwa aturan langkah yang dihapus terlalu panjang untuk dimuat dalam laporan serah terima, pendekkan atau pindahkan aturan di halaman alur dan coba menyunting lagi.
- Satu tim bisa memiliki hingga 20 acara terjadwal. Saat mencapai batas, hapus satu acara sebelum menambah yang baru. Jika acara sekali jalan sudah berjalan, buat yang baru untuk mengulanginya. Gunakan waktu mendatang dan interval dalam rentang di atas.
- Jika pesan terjadwal menyebut alur yang hilang atau nonaktif atau item bernomor yang tidak ada, kejadian itu sudah terpakai. Perbaiki pesan atau aktifkan alur sebelum kejadian berikutnya. Jika alur interaktif terjadwal melaporkan alur lain masih sibuk, alur menunggu pemicu berikutnya.
