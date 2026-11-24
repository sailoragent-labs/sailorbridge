[← SailorBridge](README.md)

# Tugas

Satu tugas adalah satu pelaksanaan alur. Setiap tim memiliki satu antrean bersama untuk semua mesinnya. Anda dapat memberikan tugas kepada tim melalui obrolan, memeriksa kemajuannya dengan nomor, dan membuka laporan serah terima untuk melihat hasilnya dan hal yang masih membutuhkan perhatian Anda.

## Masukkan pekerjaan ke antrean

Di obrolan tim, kirim nama alur dan tugas, misalnya `/agent Count the files at the top level of this project and report the count.` Tugas masuk ke antrean dan diambil oleh mesin yang memenuhi syarat ketika memiliki kapasitas. Mesin itu menjalankan tugas di salinan kerjanya sendiri.

Jika **Pemimpin** mengusulkan pekerjaan dalam percakapan, baca usulan dan pilih **Ya, Kerjakan** untuk memasukkannya ke antrean. Untuk rencana dengan beberapa tugas, baca daftar sebelum memilih **Antrekan Semua Tugas**. **Ubah Rencana** memungkinkan Anda menjelaskan perubahan. **Nanti Saja** membuat kelompok tugas tetap di luar antrean. Setelah diterima, setiap tugas mendapat nomor sendiri. [Pilih alur](flows-and-scheduled-events.md)

## Temukan tugas dan baca statusnya

Buka menu ⋯ di obrolan tim dan pilih **Daftar tugas**, atau pilih **Lihat detail** pada tugas di obrolan. Daftar mula-mula menampilkan **Jalan**, lalu mengingat filter terakhir Anda di browser ini. Pilih **Semua** untuk menyertakan tugas yang sudah berakhir. Cari berdasarkan teks tugas atau nama alur, atau masukkan nomor lengkap dengan tanda pagar, seperti `#6`, untuk menemukannya di semua filter.

| Yang terlihat | Artinya |
| --- | --- |
| **Antre** | Tugas menunggu diambil. Baris di bawahnya menunjukkan alasannya. Nomor tugas yang disebutkan mengidentifikasi prasyarat yang sedang ditunggu. |
| **Jalan** | Mesin telah mengambil tugas. Buka untuk melihat tahap dan mesin saat ini. |
| **Menunggu pemimpin** atau **Menunggu Anda** | Pemimpin menangani pertanyaan yang dapat dijawabnya. Jika keputusan Anda diperlukan, pilih **Jawab** dan balas di obrolan. Filter **Anda** menampilkan tugas yang menunggu Anda. |
| **Selesai** | Alur telah menyerahkan hasilnya. **Selesai, pemeriksaan gagal** berarti ada hasil dengan pemeriksaan gagal. Baca pemeriksaan sebelum memakai hasilnya. |
| **Belum Selesai** | Alur berhenti sebelum menyerahkan semua yang diminta. Baca di mana alur berhenti dan apa yang kurang. Pekerjaan yang telah dihasilkan tetap disimpan. |
| **Gagal** | Kesalahan mengakhiri proses. Buka laporan dan **Catatan mesin** untuk melihat alasannya. |
| **Batal** | Tugas dihentikan. Entri tetap tersedia dalam daftar. |

**Dijeda** dan **Kuota** juga dapat menjelaskan mengapa tugas sedang tidak berjalan. Buka **Kenapa belum berjalan** untuk melihat apa yang ditunggu dan tindakan yang tersedia, jika ada.

## Baca tugas, laporan serah terima, dan penggunaan

Pilih baris bernomor. **Detail tugas** menampilkan status, **Waktu berjalan**, dan **Putaran**. **Informasi Tugas** mencakup mesin, siapa yang memulai tugas, dan **Waktu antre**. Perluas **Langkah** untuk melihat tahap mana yang berjalan, durasinya, serta mesin AI dan model yang digunakan. Jika ada, **Masalah kualitas** menampilkan temuan peninjauan mandiri, peninjauan oleh rekan, dan putaran terakhir peninjauan oleh rekan.

Saat tugas berakhir, buka **Laporan serah terima**. Baca **Perubahan**, **Pemeriksaan**, **Hasil tinjauan**, **Belum dicek**, dan **Perlu keputusan Anda**. Jika tugas yang selesai memiliki pemeriksaan gagal, pemeriksaan itu ditampilkan paling awal. Untuk tugas yang menghasilkan commit, baca di mana commit disimpan. Jika mesin gagal mendorong commit, laporan memuat cabang lokal, commit, alasan, dan perintah yang dapat Anda jalankan. Tugas yang hanya membuat laporan dapat memberikan jawaban tanpa commit.

Buka **Penggunaan** dan perluas **Per Putaran** untuk melihat jumlah token dan model yang sebenarnya digunakan. Penggunaan dicatat berdasarkan penyedia, akun, dan model. Total dalam laporan mencakup pelaksanaan terakhir kali mesin mengambil tugas. Waktu dalam antrean dicatat terpisah dari waktu proses.

## Jeda, ubah, hentikan, atau lanjutkan tugas

- Pada tugas yang mengantre, pilih **Jeda** agar mesin tidak mengambilnya, lalu pilih **Lanjutkan** jika tugas sudah bisa berjalan lagi. Pilih **Mulai sekarang** untuk memindahkan tugas ke awal antrean. Jika slot sudah terisi, Anda bisa terus menunggu atau secara eksplisit menghentikan tugas yang berjalan untuk membebaskannya.
- Untuk mengubah tugas terbuka, pilih **Buka Chat** dari tugas itu. Nomor tugas akan terisi. Tambahkan persyaratan baru dan kirim pesan. Jika pemimpin mengusulkan perubahan, pilih **Ya, Ubah**. Uraian tugas yang mengantre langsung diperbarui. Pelaksanaan yang sedang berjalan berhenti dan tugas kembali mengantre dengan nomor yang sama.
- Untuk mengakhiri tugas, pilih **Hentikan** dan konfirmasikan. Tugas yang Anda hentikan secara eksplisit memerlukan instruksi Anda untuk melanjutkan. Untuk tugas yang telah berakhir dengan titik lanjut yang tersimpan dan pekerjaan yang masih dapat digunakan, buka ⋯ dan pilih **Lanjutkan**. Tugas memakai nomor yang sama dan salinan kerja yang disimpan atau cabang yang sudah didorong. Jika persyaratan berubah sebelum tugas dilanjutkan, tugas dimulai dari awal.
- Pilih **Ulangi** untuk mengantrekan tugas baru dengan alur, uraian, repositori, dan opsi semula. Tugas mendapat nomor baru dan Anda masih bisa membaca tugas sebelumnya. Gunakan opsi ini jika **Lanjutkan** tidak tersedia. **Hapus** menghapus catatan tugas yang telah berakhir secara permanen setelah konfirmasi.

## Jika ada masalah

- Jika pengiriman tugas dijeda untuk seluruh tim, pilih **Lanjutkan pembagian** saat ingin mesin kembali mengambil tugas baru. Jika tim atau akun Anda mencapai batas jumlah tugas atau agent yang bisa berjalan bersamaan, tugas dimulai saat slot tersedia. [Pengaturan pengiriman tugas tim](teams.md)
- Jika tugas menunggu jawaban Anda, Anda bisa membalas setelah lima menit pertama. Setelah lima menit, mesin melepaskan slot. Setelah Anda menjawab, mesin yang sama melanjutkan segera setelah kosong.
- Jika tugas membutuhkan penulis atau peninjau, pilih **Ke akun**. Satu mesin harus memiliki akun yang dibutuhkan untuk seluruh tugas. Jika semua mesin kandidat menolak, tugas gagal dan catatannya menunjukkan alasan setiap mesin. Jika tugas menunggu kuota atau laju, periksa perkiraan waktunya. Pekerjaan dilanjutkan saat kuota atau kapasitas tersedia. [Akun mesin AI dan laju kerja](engine-accounts-and-pacing.md)
- Jika mesin kehilangan kontak, mesin dapat melanjutkan setelah tersambung kembali. Setelah 30 menit tanpa memperpanjang klaim, mesin tim lain dapat mengambil tugas dan memulai dari awal. Tiga kali kehilangan kontak pada tugas yang sama mengakhirinya dengan status **Gagal**. Periksa mesin sebelum melanjutkan atau mengulang tugas. [Periksa mesin](machines.md)
- Kegagalan sistem yang dapat dipulihkan bisa dilanjutkan otomatis hingga 10 kali selama masa tugas. Jika tugas tetap berakhir, baca laporan terakhir, tangani penyebabnya, dan gunakan **Lanjutkan** jika tersedia.
