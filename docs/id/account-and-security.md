[← SailorBridge](README.md)

# Akun dan keamanan

**ID Kapten** berupa angka adalah nama yang Anda gunakan untuk masuk. ID itu tetap terhubung dengan akun saat Anda mengganti nama panggilan, kata sandi, atau browser. Pasangkan mesin yang Anda kendalikan selagi Anda masih bisa masuk. Anda akan membutuhkan mesin yang telah disandingkan jika lupa kata sandi.

## Buat akun

1. Buka [aplikasi](https://app.sailorbridge.com) dan pilih **Daftar**. Masukkan nomor yang Anda inginkan, dari 3 hingga 11 digit. Jika muncul **Sudah diklaim**, ubah nomornya dan periksa nomor lain.
2. Periksa keterangan yang ditampilkan untuk nomor itu. ID biasa dengan 6–8 digit dan semua ID dengan 9–11 digit gratis. ID yang lebih pendek dan pola khusus hingga 8 digit dikenai biaya sekali bayar. Untuk nomor berbayar, simpan **Tautan penukaran** di halaman pembayaran agar Anda bisa menyelesaikan pendaftaran di perangkat lain. [Harga](https://www.sailorbridge.com/#pricing)
3. Buat dan konfirmasi kata sandi. Anda bisa memilih avatar yang tersedia atau tetap memakai inisial Anda. Konfirmasikan usia dan terima **Ketentuan Layanan**, lalu pilih **Daftar**. Aplikasi akan memasukkan Anda ke akun. [Pasangkan mesin pertama](machines.md)

## Masuk dan konfirmasikan browser baru

Pilih **Masuk** dan masukkan **ID Kapten** serta **Kata Sandi**. Browser baru meminta konfirmasi jika Anda sudah menyandingkan mesin atau menggunakan verifikasi dua langkah. Jika verifikasi dua langkah aktif, Anda harus mengonfirmasi setiap kali masuk, termasuk di browser yang sudah dikenal.

Di **Konfirmasi bahwa ini Anda**, gunakan salah satu metode yang tersedia.

- Untuk **Kode autentikator**, masukkan kode terkini dari aplikasi autentikator.
- Untuk **Kode dari mesin**, jalankan `sail confirm` di terminal mesin yang telah disandingkan. Masukkan kode delapan karakter di halaman masuk.
- Jika halaman menampilkan nomor dua digit, buka browser lain tempat Anda sudah masuk. Pastikan **Kode kunci** sama pada kedua layar, lalu ketuk nomor dua digit dari halaman masuk. Jika orang lain yang memulai permintaan, pilih **Bukan saya**.

## Atur profil dan lindungi proses masuk

Buka **Saya**. Anda dapat mengatur **Nama Panggilan** dan memilih **Avatar** dari galeri. **Bahasa** mengatur bahasa tampilan dan bahasa balasan, mulai dari giliran chat atau tugas berikutnya. Di **Gaya jawaban**, pilih **Pemula** untuk penjelasan lebih lengkap atau **Ahli** untuk balasan lebih singkat.

Buka **Keamanan**, lalu **Verifikasi dua langkah**. Pilih **Aktifkan**, verifikasi kata sandi, dan pindai kode QR dengan aplikasi autentikator. Masukkan kode terkininya dan pilih **Konfirmasi dan aktifkan**. Untuk menonaktifkannya, pilih **Nonaktifkan verifikasi dua langkah** dan berikan kata sandi beserta kode baru.

Untuk mengubah kata sandi, isi **Kata Sandi Saat Ini**, **Kata Sandi Baru**, dan **Konfirmasi kata sandi baru** di bagian **Keamanan**. Masukkan kode autentikator jika verifikasi dua langkah aktif. Setelah perubahan, Anda tetap masuk di browser ini dan sesi lain berakhir.

## Periksa aktivitas dan kunci perangkat

Buka **Saya**, lalu **Keamanan** dan **Catatan keamanan terbaru**. Daftar mencakup 90 hari terakhir. Jika ada login yang berhasil di browser baru, aplikasi akan bertanya apakah itu Anda. Pilih **Ini saya** atau **Bukan saya**. Setiap browser mencatat konfirmasinya sendiri. Percobaan masuk yang gagal muncul di daftar tanpa permintaan persetujuan.

Jika melihat login yang tidak Anda lakukan, ubah kata sandi. **Keluar dari Sesi Lain** mengakhiri sesi di browser lain. Jika hanya perlu memutus satu mesin, keluarkan mesin itu dari **Mesin**. **Cabut semua mesin** memutus semua mesin yang telah disandingkan. Anda harus memasangkan masing-masing lagi agar bisa bekerja atau memberikan kode pemulihan. Anda juga bisa menghapus satu catatan keamanan setelah mengonfirmasi. Browser lain tetap menerima pemberitahuannya sendiri sampai mengonfirmasi kejadian tersebut.

Di **Keamanan**, buka **Kunci** untuk melihat browser dan mesin yang menandatangani pekerjaan atas nama Anda. Untuk menambahkan browser baru, buka **Menunggu bergabung** di browser yang sudah ada dalam daftar. Bandingkan kode pendek 12 karakter di kedua browser dan pilih **Tambahkan** hanya jika kodenya cocok. Gunakan **Keluarkan** untuk kunci yang sudah tidak dipakai atau **Tandai dicuri** untuk perangkat yang hilang. Mengeluarkan kunci mesin juga mengeluarkan mesin itu dari akun. Jika Anda memulai pengaturan ulang daftar kunci di sebuah mesin, konfirmasikan di browser setelah memeriksa nama mesinnya.

## Pulihkan kata sandi yang terlupa

1. Di terminal mesin yang telah disandingkan, jalankan `sail recover`. Perintah ini menampilkan ID Kapten dan kode pemulihan sekali pakai dengan delapan karakter yang berlaku 10 menit. Kode baru dari mesin yang sama menggantikan kode pertama.
2. Di halaman masuk, pilih **Lupa kata sandi?**. Masukkan ID dan **Kode pemulihan** dari terminal. Periksa nama mesin dan tanggal penyandingan pada halaman sebelum memasukkan kata sandi baru.
3. Ikuti jalur pemulihan yang ditampilkan. Usia penyandingan dihitung sejak penyandingan atau perbaikan kredensial terakhir.

| Mesin yang dipakai untuk pemulihan | Verifikasi dua langkah | Yang terjadi |
| --- | --- | --- |
| Disandingkan kurang dari 72 jam yang lalu | Pengaturan apa pun | Ajukan permintaan pemulihan 72 jam, meskipun Anda punya kode autentikator. |
| Disandingkan setidaknya 72 jam yang lalu | Nonaktif, atau diaktifkan kurang dari 72 jam yang lalu | Atur ulang langsung dengan kode pemulihan. Pemulihan menonaktifkan verifikasi dua langkah yang baru diaktifkan. |
| Disandingkan setidaknya 72 jam yang lalu | Sudah aktif setidaknya 72 jam | Masukkan kode autentikator untuk langsung mengatur ulang kata sandi dan tetap memakai verifikasi dua langkah. Tanpa kode itu, ajukan permintaan pemulihan 72 jam. |

Jika perlu menunggu, pilih **Ajukan pemulihan dengan masa tunggu 72 jam** dan ikuti waktu yang ditampilkan di halaman pemulihan. Perangkat yang masih masuk mendapat pemberitahuan. Anda dapat memilih **Batalkan pemulihan ini** di salah satunya. Login yang berhasil juga membatalkan permintaan. Saat pengaturan ulang berlaku, masuk dengan kata sandi baru. Pemulihan dengan masa tunggu mengatur ulang verifikasi dua langkah.

Setelah pemulihan, periksa **Dipasangkan pada** di **Mesin** dan keluarkan mesin yang tidak Anda kenal. Anda bisa mengaktifkan kembali verifikasi dua langkah di **Keamanan**.

## Keluar atau hapus akun

Gunakan **Keluar** di **Saya** untuk mengakhiri sesi browser ini. Untuk menutup akun, pilih **Hapus akun**, periksa tim dan mesin yang terdampak, lalu konfirmasikan dengan kata sandi dan kode autentikator jika diaktifkan. Penghapusan mengakhiri sesi di perangkat Anda, mencabut akses mesin, dan membatalkan langganan. Masuk dalam tujuh hari untuk membatalkan permintaan. Selama periode itu, pemulihan kata sandi tidak tersedia karena akses mesin telah dicabut. Setelah tenggat, akun dihapus dan nomornya tidak dapat digunakan lagi.

## Jika ada masalah

- Setelah lima kegagalan masuk dalam 15 menit, penguncian bawaan berlangsung 15 menit. Tunggu selama waktu yang ditampilkan. Kode autentikator hanya bisa dipakai sekali. Jika baru saja memakainya, tunggu kode berikutnya.
- Jika konfirmasi browser kedaluwarsa atau Anda mengetuk nomor yang salah, mulai lagi proses masuk. Anda juga bisa memakai salah satu metode kode yang tersedia. Jalankan `sail confirm` untuk kode masuk baru dan `sail recover` untuk kode pemulihan kata sandi baru.
- Jika mesin tidak bisa menerbitkan kode pemulihan, coba mesin lain yang telah disandingkan dengan akun Anda. Jika tidak ada yang memiliki kredensial valid, akun tidak bisa dipulihkan. Daftarkan ID baru.
