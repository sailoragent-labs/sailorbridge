[← SailorBridge](README.md)

# Perintah

Gunakan obrolan tim untuk memberi permintaan kepada **Pemimpin** atau memulai alur. Gunakan `sail` di terminal untuk mengelola mesin tempatnya terpasang, memeriksa pekerjaan tim, atau menjalankan perintah di mesin lain dalam tim yang sama.

## Pilih perintah di obrolan tim

Buka **Obrolan** untuk tim Anda dan ketik `/`. Menu mencantumkan empat pintasan, alur tim yang aktif, dan terakhir `/clear`. Pilih item, tambahkan permintaan dalam bahasa Anda, lalu kirim. Nama perintah tetap dalam bahasa Inggris. Pilihan `/clear` langsung berlaku.

| Yang diketik | Yang terjadi |
| --- | --- |
| `/job #12 What is this waiting for?` | **Pemimpin** menerima tugas 12 dan pertanyaan Anda. |
| `/event #6 Move this to weekdays.` | **Pemimpin** menerima acara terjadwal 6 dan perubahan yang Anda minta. |
| `/memory #3 When does this apply?` | **Pemimpin** menerima entri memori 3 dan pertanyaan Anda. |
| `/do Check the current branch.` | **Pemimpin** mengerjakan permintaan dalam giliran chat ini dan melaporkan hasilnya, termasuk hal yang tidak dapat diselesaikan. |
| `/clear` | Menyembunyikan pesan sebelumnya di obrolan tim ini dan memulai percakapan baru. |

Gunakan nomor dari daftar yang sesuai untuk tim itu. Tugas, acara, dan entri memori masing-masing memiliki penomoran sendiri. **Buka Chat** di halaman detail mengisi pintasan dan nomor yang sesuai. Untuk menyebut mesin, ketik `@` dan pilih dari daftar tim.

## Jalankan alur berdasarkan nama

| Perintah | Yang Anda dapatkan |
| --- | --- |
| `/ask` | Satu pertanyaan setiap kali, lalu ringkasan kebutuhan di obrolan. |
| `/plan` | Tugas perencanaan. Baca rencana dan putuskan apakah tugas yang diusulkan perlu dimasukkan ke antrean. |
| `/agent` | Satu pekerja menjalankan tugas dan melaporkan hasilnya. |
| `/write-review` | Penulis mengerjakan tugas, menjalankan pemeriksaan, dan memperbaikinya sesuai pengaturan peninjauan alur. |
| `/memory-tidy` | Tugas yang memeriksa, menggabungkan, atau menghapus entri memori tim. |
| `/docs-tidy` | Tugas yang memeriksa dokumen proyek dan melaporkan masalah yang membutuhkan pertimbangan Anda. |
| `/code-sweep` | Pemeriksaan hanya-baca dengan tugas perapian bernomor yang bisa Anda pilih untuk dijalankan. |
| `/write-flow` | Uraikan tugas yang berulang. Jika tugas berhasil, alur baru disimpan di tim ini. |
| `/edit-flow` | Berikan nama alur dan perubahannya. Penyuntingan yang berhasil menggantikan alur khusus. Menyunting alur bawaan membuat alur khusus dengan nama baru. |

Contohnya, kirim `/agent Count the top-level files in this project.` Mengirim sendiri alur latar belakang berarti mengizinkan tugas dijalankan. **Pemimpin** menulis tugas berdasarkan percakapan, atau teks Anda langsung masuk antrean jika **Langsung mulai** aktif. Buka **Lihat detail** di baris tugas dalam obrolan untuk memantaunya. Saat **Pemimpin** mengusulkan alur latar belakang sebagai balasan atas chat biasa, baca kartunya dan pilih **Ya, Kerjakan** untuk memulai. [Alur dan acara terjadwal](flows-and-scheduled-events.md)

## Pasangkan, periksa, atau keluarkan mesin

| Perintah terminal | Kapan digunakan |
| --- | --- |
| `sail login` | Perintah pemasangan menjalankannya untuk Anda. Jalankan lagi untuk membuat kode penyandingan baru atau memulihkan layanan di alamat yang sama dengan kredensial yang ada. |
| `sail host status` | Periksa penyandingan, koneksi, layanan, versi, dan lokasi log. Tambahkan `--trust` untuk melihat sidik jari kunci server yang tersimpan. |
| `sail --version` | Tampilkan versi yang terpasang. |
| `sail upgrade` | Periksa pembaruan sekarang. Hasilnya menunjukkan apakah versi baru terpasang, versi sudah terbaru, atau pembaruan gagal. |
| `sail host service status` | Periksa layanan latar belakang. Gunakan `sail host service install`, `sail host service restart`, atau `sail host service stop` untuk memasang, memulai ulang, atau menghentikannya. |
| `sail host run` | Jalankan layanan mesin di latar depan saat tidak ada instans lain yang berjalan. |
| `sail confirm` | Di **Konfirmasi bahwa ini Anda**, dapatkan kode masuk sekali pakai dari terminal mesin yang telah disandingkan. |
| `sail recover` | Di **Lupa kata sandi?**, dapatkan ID Kapten dan kode pemulihan kata sandi sekali pakai dari terminal mesin yang telah disandingkan. |
| `sail uninstall` | Hapus SailorBridge dan data lokalnya, termasuk salinan kerja dan log. Direktori proyek serta login mesin AI milik Anda tetap disimpan. |

Untuk login mesin AI, `sail account list` menunjukkan apa yang dikenali mesin ini. Gunakan `sail account add <name> <directory>` untuk mendaftarkan direktori login, `sail account remove <name>` untuk menghapus pendaftaran atau mengabaikan login bawaan, dan `sail account restore <provider>` agar login bawaan yang diabaikan dikenali lagi. Untuk endpoint yang kompatibel, `sail account create <provider>` menulis templat pengaturan di `~/.sailorbridge/`, yang dihapus oleh `sail uninstall`. [Siapkan akun GLM, DeepSeek, atau Kimi dari templat](engine-accounts-and-pacing.md#siapkan-akun-glm-deepseek-atau-kimi-dari-templat)

## Gunakan item tim bernomor

Di terminal, jalankan perintah berikut dalam direktori proyek yang dikonfigurasi untuk tim pada mesin yang telah disandingkan. Gunakan nomor item tim Anda. Misalnya, tugas yang ditampilkan sebagai `#12` di obrolan menjadi `12` dalam perintah terminal.

| Tindakan | Perintah yang dapat dijalankan di terminal |
| --- | --- |
| Temukan tugas | `sail job list` menampilkan daftar tugas terbuka. Tambahkan `--all` untuk menyertakan tugas yang sudah berakhir. `sail job get 12` menampilkan tugas 12. Tambahkan `--json` untuk melihat detail lengkap. |
| Hentikan atau hapus tugas | `sail job stop 12` menghentikan tugas. `sail job delete 12` menghapus catatan tugas yang telah berakhir. |
| Temukan acara | `sail event list` mencantumkan acara aktif yang masih akan dijalankan. Tambahkan `--all` untuk menyertakan acara nonaktif atau selesai. `sail event get 6` menampilkan pesan dan jadwal. |
| Hapus acara | `sail event delete 6` menghapus acara terjadwal. |
| Hapus entri memori | `sail memory delete 3` menghapus entri secara permanen. Untuk menghapus entri terkunci, gunakan **Memori tim** di aplikasi. |

Perintah berikut memerlukan sesi **Pemimpin** aktif atau tugas yang sedang berjalan. Menjalankannya dari terminal mengembalikan `local_team_context_missing` meskipun Anda berada di direktori tim. Sampaikan kebutuhan Anda kepada **Pemimpin** di obrolan tim. Untuk menangani sendiri item yang sudah ada, buka **Daftar tugas**, **Acara terjadwal**, atau **Memori tim** di aplikasi. Pelaksana hanya memiliki akses baca ke tugas dan acara.

| Siapa yang menjalankan | Tindakan dan perintah |
| --- | --- |
| **Pemimpin** | `sail job create <flow> "<task>"` mengantrekan alur latar belakang. `sail job edit 12 "<revised task>"` mengubah tugas terbuka. `sail job retry 12` melanjutkan pekerjaan yang memenuhi syarat dengan nomor yang sama. |
| **Pemimpin** | `sail event create "Check the queue" --weekdays 09:00` menjadwalkan pesan obrolan tim dalam zona waktu mesin. Jadwal lain menggunakan `--once`, `--daily`, atau `--every`. Gunakan `--tz` untuk menentukan zona waktu. `sail event edit 6 --disable` menjeda acara. |
| **Pemimpin** atau pekerja | `sail memory list` mencantumkan entri. `sail memory titles` mencantumkan judul. `sail memory search "release checklist"` mengembalikan hingga 10 hasil. `sail memory get 3` membaca entri. |
| **Pemimpin** atau pekerja | `sail memory create "<title>" "<body>"` mencatat fakta atau mengajukan koreksi dengan judul yang sama. `sail memory edit 3 "<body>"` mengubah entri. `sail memory conflicts` mencantumkan konflik yang belum selesai. |
| **Pemimpin** | `sail memory resolve <id> --value "<correct text>"` menyelesaikan konflik. Perintah ini menerima ID konflik. Entri yang terkunci membutuhkan keputusan Anda di **Memori tim**. |
| **Pemimpin** atau pekerja | `sail memory list --tidy` mencantumkan kandidat dan versinya. `sail memory review 3 --rev <version>` menandai entri yang layak dipertahankan. `sail memory merge` menerima argumen `--entry <id>:<version>` berulang, ditambah `--title` dan `--body`. Di antara tugas pekerja, hanya `/memory-tidy` yang dapat menghapus entri. |

Jika perintah melaporkan keputusan yang tertunda, periksa nilai saat ini dalam balasan sebelum menganggap perubahan sudah berlaku.

## Jalankan perintah secara lokal atau di mesin tim lain

Untuk perintah lokal, `sail run git status` mengirim keluarannya ke terminal. Untuk perintah panjang yang noninteraktif, tambahkan `--fold` sebelum perintah. Anda mendapat hasil, baris terakhir keluaran, dan jalur ke log lengkap. Untuk jendela tmux lokal, `sail tmux read <window>` menampilkan teksnya. `sail tmux send <window> "<text>"` mengisi kolom masukan. Kirim `sail tmux send <window> --key Enter` ketika ingin mengirimkan masukan tersebut.

Untuk menjalankan perintah di mesin lain milik Anda dalam tim yang sama, mulai dari direktori tim dan ganti `build-machine` dengan nama mesin tujuan. Misalnya, `sail exec build-machine git status --short` berjalan di direktori tim pada mesin tujuan. Kode keluar dan 40 baris terakhir keluaran gabungan, hingga 16 KiB, kembali ke terminal Anda. Gunakan `--json` sebelum nama mesin untuk satu hasil JSON.

Batas waktu bawaan adalah 5 menit. Untuk mengubahnya, tempatkan `--timeout` dan jumlah detik positif sebelum nama mesin. Satu mesin pengirim dapat memiliki hingga 8 perintah yang menunggu hasil. Menekan Ctrl-C menghentikan terminal Anda menunggu. Perintah di mesin tujuan mungkin masih berjalan.

## Jika ada masalah

- Jika perintah chat tidak dikenal, ketik `/` dan pilih alur aktif. Jika kartu konfirmasi lama menunjuk ke alur nonaktif, aktifkan alur di **Alur tim** atau pilih alur yang tersedia dan kirim permintaan baru.
- Jika pintasan bernomor tidak ditemukan, buka **Daftar tugas**, **Acara terjadwal**, atau **Memori tim** untuk tim ini. Periksa nomor dan sertakan `#` di obrolan.
- Jika `sail exec` tidak dapat mengidentifikasi tim, pindah ke salah satu direktori tim yang tercantum. Jika mesin tujuan luring atau berhenti menerima pekerjaan, coba lagi setelah mesin daring dan menerima pekerjaan. Mesin tujuan yang daring punya waktu hingga 10 menit untuk mengambil perintah dari antrean. Jika mesin luring sebelum mengambil perintah, perintah menunggu 60 detik hingga mesin tersambung kembali. Jika mesin tujuan terputus setelah perintah dimulai, periksa hasilnya sebelum menjalankannya lagi.
