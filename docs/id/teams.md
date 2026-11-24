[← SailorBridge](README.md)

# Tim

Satu tim menyediakan untuk satu proyek obrolan dengan **Pemimpin**, antrean tugas, memori tim, serta satu atau lebih mesin. Anda dapat memiliki beberapa tim dan memakai mesin yang sama di lebih dari satu tim. Hanya Anda yang bisa melihat dan mengubah pengaturan tim.

## Buat tim untuk proyek Anda

1. Pasangkan mesin yang akan menjalankan pemimpin. Saat statusnya **Daring**, pilih **Buat Tim** di halaman penyandingan. Anda juga dapat memulai dari **Tim** dengan memilih **Buat tim**. [Pasangkan mesin](machines.md)
2. Masukkan **Nama tim** dan pilih mesin tadi. Anda dapat memilih **Avatar** serta akun pemimpin, model, dan tingkat upaya dari opsi yang ada di mesin itu, atau memakai pengaturan bawaan.
3. Di **Direktori proyek**, masukkan jalur absolut pada mesin yang dipilih, dimulai dengan `/`. Jika sudah bekerja di repositori, gunakan direktori lokalnya. Jika ingin memakai repositori jarak jauh yang sudah ada, klon dahulu pada mesin itu dan siapkan kredensial Git di sana. SailorBridge mendeteksi cabang utama repositori.
4. Pilih **Tujuan** dan pilih **Buat tim**. Tim kini mencantumkan mesin tersebut. Buka **Obrolan** untuk berbicara dengan pemimpin. [Gunakan obrolan tim](chat.md)

Saat pertama kali tim menggunakan jalur itu, tim membuka folder yang sudah ada atau membuatnya. Untuk folder biasa yang berisi berkas, tim menginisialisasi Git dan mengambil snapshot awal. Jika folder berisi beberapa repositori Git tepat di bawahnya, beri tahu pemimpin repositori mana yang dimaksud. Setiap tugas bekerja dalam satu repositori. Pekerjaan lintas repositori dibagi menjadi tugas terpisah.

## Pilih tujuan perubahan

Buka tim Anda di **Tim** untuk membuka **Detail tim**. Ubah **Direktori proyek** atau **Tujuan** di sana. Perubahan berlaku mulai tugas berikutnya yang diambil mesin.

| Tujuan | Tempat menemukan commit tugas |
| --- | --- |
| **Gabung otomatis** (bawaan) | Mesin mencoba mendorong ke cabang utama jarak jauh, lalu memperbarui cabang utama lokalnya dengan fast-forward. Periksa laporan serah terima jika cabang utama sudah berubah atau repositori jarak jauh mewajibkan peninjauan. Jika laporan mencantumkan cabang tugas, gabungkan cabang tersebut di repositori jarak jauh. |
| **Cabang** | Setiap tugas mendorong cabangnya sendiri, `sb/<job>`, agar Anda dapat meninjau dan menggabungkannya. Tugas lain dimulai dari cabang utama proyek. |

Setiap mesin menggunakan remote Git dan kredensial repositori itu sendiri. Mesin mengambil perubahan dari cabang utama jarak jauh sebelum memulai tugas dan memperbarui salinan lokalnya dengan fast-forward jika memungkinkan. Jika push gagal, buka **Laporan serah terima** tugas untuk mengetahui alasan, cabang lokal, commit, dan perintah push. [Temukan laporan serah terima tugas](jobs.md)

## Tambahkan, pindahkan, atau keluarkan mesin

Di **Detail tim**, buka **Daftar Mesin** dan pilih tombol tambah untuk **Tambah mesin**. Pilih mesin yang telah disandingkan dan pilih **Sama dengan folder tim** atau masukkan jalur absolut khusus untuk mesin itu di **Folder proyek**. Jalurnya dapat disunting nanti. Mesin yang memenuhi syarat dan memiliki kapasitas kini dapat mengambil tugas dari antrean yang sama.

Untuk mengeluarkan mesin dari tim ini, pilih mesin dan konfirmasikan **Keluarkan dari tim**. Mesin berhenti mengambil tugas baru dari antrean ini. Jika Anda mengeluarkan atau mencabut akses mesin bertanda **Pemimpin berjalan di sini**, mesin tersisa yang paling awal bergabung mengambil alih sebagai pemimpin. Mesin terakhir dalam tim tidak bisa dikeluarkan. Tambahkan penggantinya terlebih dahulu.

## Atur cara tim mengambil tugas

Kembali ke **Detail tim** untuk mengubah cara tim menjalankan pekerjaan.

- Di **Pengaturan Tugas**, **Pembagian** mengendalikan pekerjaan baru. Pilih **Dijeda** untuk menahan tugas dalam antrean sementara tugas yang sudah berjalan tetap dilanjutkan. Pilih **Normal** agar mesin kembali mengambil tugas dari antrean.
- **Pekerjaan bersamaan** menggunakan **Tanpa batas** secara bawaan, sehingga batas jumlah agent yang bisa berjalan bersamaan pada akun Anda berlaku. Pilih **Atur jumlah** untuk membatasi jumlah tugas tim yang berjalan. Penurunan angka berlaku saat tugas yang berjalan selesai.
- Di **Model Ketua**, pilih akun, lalu model dan tingkat upaya jika tersedia. Akun dicantumkan bersama mesinnya. Memilih akun pada mesin tim lain memindahkan pemimpin ke sana untuk pesan berikutnya. Pemimpin menggunakan ringkasan percakapan dan memori tim yang sama. Tugas yang sedang berjalan tetap di mesinnya.
- Untuk pekerja, pilih model pilihan dan, jika tersedia, tingkat upaya untuk setiap tingkat kesulitan dan penyedia. **Kembalikan default** mengembalikan pilihan ke pengaturan bawaan tim. Di **Daftar akun**, Anda dapat membatasi akun hanya untuk penulisan, peninjauan, atau pemimpin. [Akun mesin AI dan laju kerja](engine-accounts-and-pacing.md)

## Bubarkan tim

Buka **Detail tim**, pilih **Bubarkan tim**, periksa jumlah sesi agent yang akan berakhir, lalu ketik nama tim untuk mengonfirmasi. Pembubaran bersifat permanen. Tindakan ini membatalkan tugas terbuka, menghapus acara terjadwal, dan menghapus tim dari daftar serta akses masuk ke obrolan. Permintaan sesi agent yang tertunda dan sesi aktif tim berakhir. Setiap peserta menyimpan riwayat sesinya. Mesin tetap disandingkan dengan akun Anda.

## Jika ada masalah

- Jika tidak ada mesin yang bisa dipilih, pilih **Pasangkan mesin** saat membuat tim atau **Pasangkan mesin baru** saat menambahkan mesin. Jika akses mesin sudah dicabut, pasangkan lagi sebelum menambahkannya.
- Jika tugas atau chat melaporkan bahwa direktori tidak bisa dibuat, periksa jalur di mesin yang mencoba menggunakannya. Berkas di jalur tersebut, tidak adanya izin tulis, atau disk hanya-baca bisa mencegah pembuatan. Pilih **Ubah direktori di pengaturan tim** dan masukkan direktori yang dapat ditulisi untuk mesin itu.
- Jika akun atau model pemimpin tidak lagi tersedia saat membuat tim, pilih lagi dari daftar yang diperbarui. Jika pekerjaan masih mengantre setelah pembuatan, baca **Kenapa belum berjalan** pada detail tugas untuk melihat apakah pengiriman tugas, batas, atau akun menahannya.
