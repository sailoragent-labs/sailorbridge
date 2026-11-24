[← SailorBridge](README.md)

# Pemecahan masalah

Mulai dari tempat pekerjaan terhenti. Untuk masalah login atau pembayaran, baca pesan di halaman tersebut. Untuk masalah mesin, periksa terminal di mesin itu. Untuk tugas, buka **Daftar tugas**, pilih tugas, lalu baca **Kenapa belum berjalan**. Bagian itu menjelaskan apakah tugas membutuhkan tindakan Anda atau akan dilanjutkan sendiri.

## Dapatkan kembali akses ke akun

| Yang terlihat | Yang perlu dilakukan |
| --- | --- |
| ID Kapten sudah diambil atau pendaftaran hari ini penuh | Coba ID lain yang tersedia. Jika batas harian pendaftaran gratis tercapai, kembali besok. Untuk ID berbayar, gunakan **Tautan penukaran** awal untuk menyelesaikan pendaftaran. |
| **Konfirmasi bahwa ini Anda** setelah memasukkan kata sandi | Gunakan autentikator, jalankan `sail confirm` di mesin yang telah disandingkan lalu masukkan kodenya, atau cocokkan angka yang ditampilkan di browser yang dikenal jika pilihan itu tersedia. Gunakan permintaan masuk terbaru. Jika kedaluwarsa, masuk lagi. |
| Terlalu banyak kegagalan masuk atau kode autentikator dipakai ulang | Setelah 5 kegagalan dalam 15 menit, penguncian bawaan berlangsung 15 menit. Tunggu selama waktu yang ditampilkan. Jika kode autentikator sudah dipakai, tunggu kode berikutnya. |
| Lupa kata sandi atau kode pemulihan kedaluwarsa | Jalankan `sail recover` di terminal mesin yang telah disandingkan. Pilih **Lupa kata sandi?** lalu masukkan ID Kapten dan kode 8 karakter yang ditampilkan. Kode berlaku 10 menit dan dapat dipakai sekali. Kode baru dari mesin itu menggantikan yang lama. Jika kredensial mesin ditolak, coba mesin lain yang telah disandingkan. Tanpa mesin tersanding yang dapat digunakan, Anda perlu mendaftarkan ID baru. |
| **Pemulihan akun menunggu berlaku** | Mesin yang disandingkan kurang dari 72 jam lalu mengharuskan masa tunggu 72 jam, termasuk setelah perbaikan yang mengganti kredensialnya. Untuk penyandingan yang lebih lama, verifikasi dua langkah yang aktif setidaknya 72 jam memerlukan kode autentikator untuk pemulihan langsung. Tanpa kode itu, ajukan permintaan 72 jam. Tunggu sampai waktu yang ditampilkan. Jika Anda tidak meminta pemulihan, pilih **Batalkan pemulihan ini** di perangkat yang masih masuk. |

## Buat mesin atau tim kembali berfungsi

- Jika pemasangan berhenti karena Git belum ada, pasang Git lalu jalankan ulang perintah dari **Pasangkan mesin baru**. Jika belum masuk ke Claude Code atau Codex, penyandingan tetap bisa selesai. Jalankan `claude login` atau `codex login` di mesin sebelum meminta tim bekerja.
- Jika kode penyandingan kedaluwarsa, jalankan `sail login` untuk membuat kode baru. Masukkan di **Pasangkan mesin baru**, pilih **Pasangkan**, dan cocokkan nama mesin serta **Kode kunci** dengan terminal sebelum memilih **Setujui mesin**. Jika kode berbeda, batalkan penyandingan dan mulai lagi. Setelah menyetujui, tunggu hingga mesin tersambung.
- Jika mesin belum terhubung dalam 10 menit, jalankan `sail host status`. Perintah ini menampilkan status layanan dan jalur log. Di alamat yang sama, jalankan `sail login` untuk memulihkan layanan. Untuk `origin_mismatch`, jika ingin berganti alamat, `sail uninstall` menghapus data lokal SailorBridge, termasuk salinan kerja tugas. Lalu jalankan perintah pemasangan dari halaman **Mesin** aplikasi yang dituju dan pasangkan lagi.
- Jika pembaruan gagal, buka mesin di **Mesin** dan ikuti keterangan penyebab serta perintah perbaikan yang ditampilkan. Jika unduhan gagal, coba lagi nanti dengan `sail upgrade`. Jika penulisan gagal, periksa ruang disk dan gunakan akun yang memasang `sail`.
- Jika pembuatan tim meminta mesin, pasangkan satu dan tunggu hingga **Daring**. Jika mesin terakhir tim tidak bisa dikeluarkan, gunakan **Tambah mesin** terlebih dahulu. Jika direktori tim tidak dapat dibuat, pilih **Ubah direktori di pengaturan tim**. Gunakan jalur direktori absolut di mesin tempat kesalahan terjadi. Berkas di jalur itu, izin tulis yang tidak tersedia, atau disk hanya-baca bisa mencegah pembuatan. [Mesin](machines.md) · [Tim](teams.md)

## Dapatkan jawaban di obrolan

- Jika mesin **Pemimpin** luring, obrolan tim menyimpan pesan Anda dan mengirimkannya saat mesin terhubung kembali. Jika tim tidak memiliki mesin yang dapat dipakai, tambahkan mesin dan kirim ulang pesan.
- Jika mesin AI memerlukan login, masuk di mesin yang disebutkan. Jika semua akun yang dapat dipakai **Pemimpin** kehabisan kuota, kirim ulang pesan setelah waktu pengaturan ulang. Jika model ditolak, ikuti petunjuk pembaruan mesin AI dan coba lagi, atau pilih akun serta model yang tersedia. [Akun mesin AI dan laju kerja](engine-accounts-and-pacing.md)
- Jika pesan masuk sebagai jawaban atas pertanyaan dan tidak sampai ke **Pemimpin**, jawab pertanyaan terbuka atau pilih **Hentikan** pada kartunya. Lalu kirim pesan. Jika kartu konfirmasi telah diganti atau dijawab, periksa kartu terbaru atau tugas sebelum bertindak.
- Jika berkas ditolak, gunakan obrolan tim dan kirim paling banyak 4 lampiran per pesan, masing-masing hingga 5 MiB. Jenis yang didukung adalah PNG, JPEG, WebP, PDF, teks biasa, dan Markdown. Pilih ulang lampiran yang tidak tersedia. Unggahan yang belum dikirim kedaluwarsa setelah 24 jam. Saat akun menyentuh batas 1 GiB, tunggu ruang kosong ketika berkas terkirim kedaluwarsa setelah 30 hari. Untuk pesan yang terlalu besar, bagi teks menjadi beberapa pesan berukuran paling banyak 64 KiB.
- Dalam sesi agent, jika akun membutuhkan login atau kuota, tangani dahulu lalu pilih **Lanjutkan**. Jika sesi antartim mencapai batas putaran, penerima dapat memperpanjangnya 10 atau 20 putaran atau memilih **Putaran tanpa batas**. Pemrakarsa menunggu penerima. [Chat](chat.md)

## Cari tahu mengapa tugas menunggu

Buka tugas di **Daftar tugas**. Baca **Kenapa belum berjalan** sebelum memutuskan apakah perlu memulai ulang sesuatu.

| Yang menahan tugas | Yang perlu dilakukan |
| --- | --- |
| Pengiriman tugas dijeda atau tugas ini dijeda | Gunakan **Lanjutkan pembagian** untuk tim atau **Lanjutkan** untuk tugas itu saja. |
| Mesin sibuk, tim mencapai batas tugas, atau paket mencapai batas agent | Pekerjaan dimulai saat slot tersedia. Periksa **Pekerjaan bersamaan** untuk tim atau **Batas paralel** di **Langganan** untuk akun Anda. |
| Tugas memerlukan penulis dan peninjau | Pilih **Ke akun**. Pastikan satu mesin tim memiliki akun yang diperlukan dan aktif untuk kedua langkah. Penulis dan peninjau di mesin yang berbeda tidak dapat menjalankan tugas yang sama bersama-sama. |
| Mesin mencapai batas laju atau kehabisan kuota | Tunggu perkiraan waktu yang ditampilkan. Jika menunggu karena laju, **Beralih ke Tanpa Batas** mengubah pengaturan laju semua tim setelah konfirmasi. Jika kuota habis, tugas memeriksa lagi dan dilanjutkan di mesin yang sama saat kuota kembali. |
| Tugas membutuhkan jawaban atau prasyarat | Pilih **Jawab** jika pertanyaan ditujukan kepada Anda. Setelah 5 menit menunggu jawaban, tugas melepaskan slot. Setelah dijawab, tugas berlanjut saat mesin asalnya kosong. Jika ada prasyarat, buka nomor tugas yang ditampilkan dan periksa hasilnya. |
| Mesin menolak tugas atau berhenti melapor | Baca alasan di bawah tugas. Mesin lain yang memenuhi syarat bisa mengambil tugas yang ditolak. Jika semua kandidat menolak, buka **Catatan mesin** untuk melihat alasannya. Jika mesin yang sedang bekerja kehilangan koneksi, mesin itu dapat melanjutkan jika kembali lebih dahulu. Setelah 30 menit tanpa pembaruan klaim, mesin lain dapat memulai dari awal. |
| **Belum Selesai** atau **Gagal** | Buka **Laporan serah terima** untuk melihat langkah terakhir, alasan, dan pekerjaan yang disimpan. Perbaiki masalah yang dilaporkan. Gunakan **Lanjutkan** jika tersedia untuk meneruskan tugas yang sama dari pekerjaan yang disimpan, atau **Ulangi** untuk memulai lagi. Jika push gagal, laporan mencantumkan cabang, commit, dan perintah push untuk pekerjaan yang tersimpan secara lokal. |

## Perbaiki perintah, jadwal, atau entri memori

- Jika terminal menampilkan “Jalankan perintah ini di dalam pekerjaan atau sesi pemimpin tim.” (`local_team_context_missing`), perintah memerlukan sesi aktif meskipun Anda berada di direktori tim. Tanyakan kepada **Pemimpin** di obrolan tim, atau buka **Daftar tugas**, **Acara terjadwal**, atau **Memori tim** untuk menangani item yang sudah ada. [Perintah untuk item tim bernomor](commands.md#gunakan-item-tim-bernomor)
- Jika perintah garis miring tidak dikenal, ketik `/` untuk melihat alur aktif. Jika referensi bernomor tidak ditemukan, periksa tim serta jenis item dan ketik `#` sebelum nomornya di obrolan. Jika `sail exec` melaporkan tujuan luring, perintah belum berjalan. Jika hasilnya hilang *setelah* perintah mulai berjalan, periksa mesin tujuan sebelum mencoba lagi. [Perintah](commands.md)
- Jika acara terjadwal ditolak, pilih waktu mendatang untuk acara sekali jalan, atau interval 5–720 menit untuk acara berulang. Satu tim bisa memiliki hingga 20 acara. Hapus acara yang tidak dibutuhkan untuk menyediakan ruang. Acara sekali jalan yang sudah selesai harus dibuat lagi agar berjalan lagi. Jika acara merujuk ke alur nonaktif atau nomor yang tidak ada, perbaiki pesan untuk pelaksanaan berikutnya. [Alur dan acara terjadwal](flows-and-scheduled-events.md)
- Jika perubahan memori ditolak, buka **Memori tim**. Di sana Anda dapat mengubah entri terkunci. Jika orang lain mengubahnya lebih dulu, baca isi terbaru sebelum menyimpan. Jika ruang untuk sematan penuh, lepaskan sematan atau pendekkan entri sebelum menyematkan entri lain. [Memori tim](team-memory.md)

## Periksa pembayaran yang belum berhasil

Jika pembayaran tertunda, kembali ke pembelian awal dan periksa statusnya sebelum membayar lagi. Jika langganan menampilkan **Pembayaran gagal**, **Perbarui Metode Pembayaran dan Bayar Tunggakan** membuka halaman pembayaran untuk melunasi saldo terutang. [Paket dan penagihan](plans-and-billing.md)

## Jika ada masalah

Jika masalah berlanjut, catat langkah, pesan persisnya, hal yang Anda harapkan, dan tempat masalah terjadi. Sertakan versi, OS mesin, dan mesin AI jika diketahui. Untuk masalah akun atau pembayaran, gunakan kontak privat yang tercantum di README. Untuk masalah keamanan, gunakan tautan keamanan privatnya. Jangan sertakan kredensial, kode penyandingan, detail pembayaran, atau kode sumber privat dalam laporan publik. [Melaporkan masalah](README.md#melaporkan-masalah)
