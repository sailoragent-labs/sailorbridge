[← SailorBridge](README.md)

# Mesin

Mesin adalah komputer yang Anda hubungkan ke akun untuk menjalankan pemimpin tim atau mengambil tugas. Pasang `sail` di setiap mesin dan setujui di browser. Layanan latar belakang menjaga mesin tetap terhubung setelah terminal ditutup.

## Pasang klien dan pasangkan mesin

1. Gunakan mesin yang Anda kendalikan dengan Linux x64 atau macOS arm64 atau x64. Pasang Git. Untuk chat dan tugas, pasang Claude Code atau Codex dan masuk di mesin itu dengan akun mesin AI Anda sendiri. Penyandingan bisa selesai sebelum Anda masuk ke mesin AI.
2. Di aplikasi, buka **Mesin**, lalu **Pasangkan mesin baru**. Salin perintah pemasangan yang ditampilkan ke terminal mesin yang ingin Anda hubungkan. Perintah dapat dijalankan dari direktori mana saja. Perintah memasang `sail`, memulai penyandingan, dan menampilkan kode delapan karakter yang berlaku 10 menit.
3. Masukkan kode itu di **Kode penyandingan** pada browser dan pilih **Pasangkan**. Cocokkan nama mesin dan **Kode kunci** dengan yang ada di terminal. Pada penyandingan pertama, baca pemberitahuan sebelum menerimanya. Agent dapat membaca, mengubah, dan menghapus berkas, memakai kredensial, dan mengakses jaringan dengan izin pengguna sistem operasi yang menjalankan `sail`. Gunakan mesin atau kontainer khusus jika memerlukan isolasi.
4. Pilih **Setujui mesin**. Jaga mesin tetap terhubung saat mengambil kredensial dan memulai layanan. Saat **Mesin** menunjukkan **Daring** dan terminal mengonfirmasi koneksi, Anda dapat memilih **Siapkan Akun** atau **Buat Tim**. [Buat tim](teams.md)

## Periksa koneksi atau pasangkan mesin lain

Buka mesin di **Mesin** untuk melihat nama, platform, **Terakhir Online**, **Dipasangkan pada**, dan **Versi Klien**. Anda dapat mengubah nama di sini agar mesin lebih mudah dibedakan. Di mesin itu sendiri, jalankan `sail host status` untuk memeriksa penyandingan, koneksi, dan status layanan serta menemukan log lokal.

Untuk memakai komputer lain, buka lagi **Pasangkan mesin baru** dan jalankan perintah yang ditampilkan di komputer tersebut. Setelah daring, tambahkan mesin ke tim dan atur folder proyeknya di sana. Satu mesin dapat melayani beberapa tim. Setiap tugas berjalan pada satu mesin yang memenuhi syarat dalam timnya. [Kelola mesin tim](teams.md)

## Perbarui atau perbaiki pemasangan

Pembaruan otomatis aktif secara bawaan. Setelah memverifikasi pembaruan, layanan memulai ulang dan melanjutkan pekerjaan lokal. Langkah yang selesai disimpan. Langkah lokal yang terputus dapat dijalankan lagi. Untuk memperbarui secara manual, jalankan `sail upgrade` pada mesin. Hasilnya menunjukkan apakah pembaruan dipasang, versi sudah terbaru, atau terjadi kesalahan. Jalankan `sail --version` untuk memeriksa versi terpasang.

Jika layanan perlu dipulihkan, jalankan `sail login`. Di alamat yang sama, perintah ini memasang ulang dan memulai ulang layanan dengan kredensial yang ada. Jika kredensial ditolak dan mesin masih terdaftar, perintah memulai penyandingan untuk perbaikan. Browser menampilkan **Pasangkan ulang mesin yang ada** dan menunjukkan mesin yang akan diganti. Periksa detail dan setujui kode baru. Mesin tetap menjadi anggota timnya. Tanggal penyandingan untuk pemulihan kata sandi dihitung ulang dari saat mesin menerima kredensial baru.

## Keluarkan mesin atau hapus pemasangan

Untuk berhenti menggunakan mesin di seluruh akun, buka menu pada baris mesin di **Mesin**, pilih **Hapus**, dan konfirmasikan. Kredensial mesin dicabut. Mesin keluar dari timnya dan berhenti bekerja saat menerima pemberitahuan, langsung jika terhubung atau pada koneksi berikutnya. Salinan kerja lokalnya tetap disimpan. Untuk memakainya lagi, jalankan `sail login` di mesin itu, setujui penyandingan baru, dan tambahkan ke tim yang membutuhkannya.

Untuk menghapus pemasangan dari komputer, simpan dahulu pekerjaan yang Anda butuhkan dari salinan kerja SailorBridge. Jalankan `sail uninstall` pada mesin itu. Perintah menghentikan layanan dan menghapus `sail`, definisi layanan, entri jalur shell yang dibuat penginstal, serta seluruh direktori `~/.sailorbridge/`. Ini mencakup kredensial, pendaftaran akun, log, catatan obrolan lokal, salinan kerja, dan salinan cadangan `sail`. Direktori proyek dan direktori login mesin AI milik Anda tetap disimpan. Untuk memasang lagi, gunakan perintah di **Pasangkan mesin baru**.

## Jika ada masalah

- Jika penyandingan melaporkan bahwa Git tidak ada, pasang Git dan jalankan `sail login` untuk melanjutkan. Jika belum masuk ke mesin AI, tangani secara terpisah dengan `claude login` atau `codex login` sebelum memulai obrolan atau tugas.
- Jika kode kedaluwarsa, jalankan `sail login` untuk mendapat kode baru. Jika nama mesin atau **Kode kunci** berbeda, pilih **Batalkan pemasangan** dan periksa terminal di mesin yang dimaksud. Jika persetujuan berhasil tetapi mesin belum tersambung dalam 10 menit, jalankan `sail host status`, lalu `sail login` untuk menyambungkannya kembali.
- Jika mesin tiba-tiba luring, periksa jaringan dan layanannya dengan `sail host status`. Batas waktu bawaan sebelum mesin dianggap luring adalah 90 detik. Pemberitahuan luring baru muncul setelah mesin luring selama 10 menit dan hilang saat mesin kembali.
- Jika pembaruan gagal, buka mesin untuk membaca alasannya dan jalankan perintah perbaikan yang ditampilkan sebagai pengguna yang memasang `sail`. Jika cadangan lokal tidak dapat digunakan, jalankan perintah pemasangan dari halaman penyandingan.
- Jika mesin melaporkan perubahan identitas server, mesin menolak koneksi. Gunakan `sail host status --trust` untuk melihat sidik jari yang tersimpan di mesin. Jika perubahan memang diharapkan, jalankan `sail login`, periksa sidik jari baru di terminal, dan setujui penyandingan baru.
- Jika `sail login` melaporkan `origin_mismatch`, ikuti prosedur penghapusan pemasangan di atas sebelum mengganti alamat. Lalu salin perintah pemasangan dari halaman **Mesin** di aplikasi yang dituju. Kredensial penyandingan lokal yang tidak terbaca juga mengharuskan Anda menghapus pemasangan dan menyandingkan ulang.
- Jika `sail uninstall` melaporkan bahwa layanan tidak dapat mengonfirmasi pengeluaran mesin, berkas lokal sudah dihapus. Buka **Mesin** dan keluarkan mesin dari daftar di sana.
