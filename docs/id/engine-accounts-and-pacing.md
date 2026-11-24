[← SailorBridge](README.md)

# Akun mesin AI dan laju kerja

Agent Anda memakai akun mesin AI yang sudah masuk di mesin Anda. Anda bisa melihat akun yang dapat dipakai tim, sisa kuota, dan kapan pekerjaan akan dilanjutkan. Paket SailorBridge menentukan jumlah agent yang dapat berjalan bersamaan. Akses model dan kuota berasal dari penyedia mesin AI.

## Temukan atau tambahkan akun

1. Masuk ke Claude Code atau Codex di mesin tempat Anda ingin menjalankannya. Jalankan `sail account list`. Login bawaan terdeteksi otomatis. Namanya biasanya adalah nama mesin AI diikuti `@` dan nama mesin.
2. Untuk menambah login lain, masuk ke mesin AI menggunakan direktori akun terpisah. Jalankan `sail account add <name> <directory>` dengan direktori itu dan nama sepanjang 1–64 karakter yang unik di mesin, tanpa spasi atau garis miring. Sebagai contoh, jika login kedua berada di sana, jalankan `sail account add work "$HOME/codex-work"`. Pemeriksaan kuota berikutnya akan mendeteksinya tanpa perlu memulai ulang.
3. Buka **Sumber daya**, lalu **Akun**. Pilih akun untuk melihat mesin, kuota, dan model yang tersedia. Akun yang dilaporkan dengan nama yang sama oleh mesin AI yang sama di mesin berbeda muncul dalam satu baris. Direktori login, email, dan kredensial tetap berada di mesin.

Codex menerima login langganan. Claude Code menerima login langganan atau kunci API. Gemini CLI, Copilot CLI, OpenCode, Qwen Code, dan Pi hanya mendukung pendaftaran akun dan pemeriksaan lokal. Dari kelimanya, hanya Gemini CLI dan OpenCode yang mengenali direktori terpisah dengan nama masing-masing.

## Gunakan endpoint yang kompatibel dengan Claude

Untuk penyedia seperti DeepSeek atau GLM, siapkan direktori akun Claude Code terpisah di mesin Anda. Di `settings.json` dalam direktori itu, tetapkan URL dasar penyedia di `env.ANTHROPIC_BASE_URL` dan kredensialnya di `env.ANTHROPIC_API_KEY` atau `env.ANTHROPIC_AUTH_TOKEN`. Tetapkan `ANTHROPIC_MODEL` dalam objek `env` yang sama ke nama model dari penyedia. Anda dapat memetakan keluarga Opus, Sonnet, dan Haiku secara terpisah dengan `ANTHROPIC_DEFAULT_OPUS_MODEL`, `ANTHROPIC_DEFAULT_SONNET_MODEL`, dan `ANTHROPIC_DEFAULT_HAIKU_MODEL`.

Jalankan `sail account add <name> <directory>` di sana dengan nama dan jalur yang Anda pilih. Akun berjalan melalui Claude Code. Buka **Model yang tersedia** untuk melihat nama model yang dibaca dari direktori. Model endpoint memakai pemetaan tersebut dan tidak punya pengaturan tingkat upaya. Detail tugas menampilkan model yang benar-benar dijalankan.

## Siapkan akun GLM, DeepSeek, atau Kimi dari templat

`sail account create` menulis berkas pengaturan Claude Code lokal dengan endpoint penyedia, usulan model untuk tingkat atas, menengah, dan bawah, serta teks pengganti kunci. Perintah ini tidak meminta, membaca, atau mengirim kunci Anda dan tidak mendaftarkan akun.

Untuk menyiapkan GLM, jalankan perintah ini di mesin tempat akun akan dipakai.

```sh
sail account create glm
```

Perintah menampilkan tiga baris. Di sini `~` berarti direktori home Anda.

```text
Usulan model (Opus/Fable, Sonnet, Haiku/subagen): glm-5.3, glm-5.2, glm-5.3-flash.
Ada tiga ID model berbeda. Model untuk Sonnet diusulkan sebagai tingkat menengah.
Edit ~/.sailorbridge/account-templates/glm/settings.json, ganti penanda dengan kunci API Anda, lalu jalankan sail account add <name> ~/.sailorbridge/account-templates/glm.
```

Berkas `settings.json` yang dihasilkan berisi templat ini.

```json
{
  "env": {
    "ANTHROPIC_AUTH_TOKEN": "REPLACE_WITH_YOUR_API_KEY",
    "ANTHROPIC_BASE_URL": "https://api.z.ai/api/anthropic",
    "ANTHROPIC_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "glm-5.2",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "glm-5.3-flash",
    "ANTHROPIC_DEFAULT_FABLE_MODEL": "glm-5.3",
    "CLAUDE_CODE_SUBAGENT_MODEL": "glm-5.3-flash"
  }
}
```

Buka berkas di penyunting teks seperti `nano`.

```sh
nano ~/.sailorbridge/account-templates/glm/settings.json
```

Ganti `REPLACE_WITH_YOUR_API_KEY` dengan kunci GLM Anda sendiri, pertahankan tanda kutip, lalu simpan berkas. Daftarkan direktori dengan nama pilihan Anda. Contoh ini menggunakan `glm`. Nama harus unik di mesin ini, sepanjang 1–64 karakter, tanpa spasi atau `/`.

```sh
sail account add glm ~/.sailorbridge/account-templates/glm
sail account list
```

Cari `glm` di daftar terminal. Setelah mesin melaporkan akun, buka **Sumber daya** lalu **Akun** di aplikasi. Pilih `glm` untuk melihat **Model yang tersedia** untuk akun itu.

Untuk DeepSeek atau Kimi, mulai dengan perintah penyedia Anda. Buka `settings.json` di jalur yang ditampilkan dan ganti teks pengganti dengan kunci penyedia. Gunakan perintah `sail account add` yang ditampilkan dengan nama pilihan Anda, lalu periksa `sail account list`.

| Perintah templat | Endpoint di berkas | Usulan model yang ditampilkan |
| --- | --- | --- |
| `sail account create deepseek` | `https://api.deepseek.com/anthropic` | Tingkat atas memakai `deepseek-v4-pro`. Tingkat menengah dan bawah sama-sama memakai `deepseek-flash`. |
| `sail account create kimi` | `https://api.kimi.com/coding/` | Gunakan kunci Kimi Coding Plan. Ketiga tingkat memakai `k3.1-pro[1m]`. |

MiniMax memerlukan `--region international` atau `--region china`. GLM, DeepSeek, dan Kimi menolak `--region`.

## Baca kuota dan sisihkan sebagian untuk Anda

Buka akun di **Akun**. Periksa **Kuota**, **Reset**, dan **Dibaca** bersama-sama. Pembacaan langganan dapat menampilkan periode lima jam, periode mingguan, atau jatah mingguan untuk model tertentu. Codex melaporkan jatah mingguan standarnya. Pemeriksaan kuota tidak memakai token model. Jika pembacaan baru gagal, hasil pembacaan yang berhasil hingga satu jam sebelumnya masih bisa tampil, dengan penanda bahwa datanya lama. Jika hasil pembacaan tidak tersedia, alasannya ditampilkan dan akun masih mungkin memenuhi syarat untuk bekerja.

- **Bisa digunakan** mengendalikan penugasan baru ke akun ini di semua tim Anda. Menonaktifkannya tetap memungkinkan pekerjaan yang sedang berjalan selesai.
- **Batas cadangan** menyisihkan persentase untuk pemakaian Anda sendiri. Atur dari 0% hingga 100% dengan kenaikan 5. Jika sisa kuota untuk periode yang lebih panjang dari satu hari sama dengan atau di bawah persentase ini, pekerja dan **Pemimpin** berhenti memakai akun. Periode pendek memakai seluruh jatahnya.
- Untuk akun yang diukur berdasarkan pengeluaran, atur **Batas bulanan** ke jumlah maksimum yang boleh dipakai mesin selama satu bulan kalender. Ini berlaku untuk DeepSeek, misalnya. GLM menyediakan pembacaan kuotanya sendiri. Setelah batas tercapai, pekerjaan baru menunggu hingga tengah malam UTC pada tanggal pertama bulan berikutnya, kecuali Anda menaikkan batas. Langkah yang sedang berjalan dapat selesai meski melewati batas. Jika akun yang sama didaftarkan di beberapa mesin, masing-masing mengukur pengeluarannya sendiri. Jika muncul **Biaya Tidak Tersedia**, Anda melihat jumlah token dan batas tidak dapat diterapkan.
- **Kredit Reset** muncul saat Claude atau Codex melaporkannya. Buka kredit, periksa apa yang diatur ulang dan kapan kedaluwarsa, lalu pilih **Tukar** dan konfirmasikan. **Tukar Reset** di daftar akun menggunakan kredit yang memenuhi syarat dan paling cepat kedaluwarsa. Mesin yang menyimpan akun melakukan pengaturan ulang. Periksa hasilnya sebelum memakai kredit lain.

## Pilih akun dan model untuk satu tim

Buka **Daftar akun** dari menu obrolan tim. Akun di mesin tim disertakan secara bawaan. Atur **Peran** ke **Keduanya**, **Hanya Tulis**, atau **Hanya Tinjau** untuk mengendalikan langkah pekerja yang dapat memakai akun. Gunakan **Hanya Ketua** untuk mencadangkannya bagi obrolan di tim ini. **Keluarkan dari Tim** dan **Tambah Akun ke Tim** mengubah ketersediaannya untuk tim ini.

Di **Detail tim**, buka pengaturan pengiriman tugas. Di **Model Ketua**, pilih akun aktif di mesin tim, lalu pilih salah satu model yang terdeteksi dan tingkat upaya jika tersedia. Memilih akun di mesin lain memindahkan **Pemimpin** ke sana untuk pesan berikutnya. Jika akun pilihan tidak dapat dijalankan, balasan menyebut mesin AI dan model pengganti.

Untuk pekerja, tetapkan model dan tingkat upaya pilihan untuk setiap tingkat kesulitan dan mesin AI di pengaturan model tim. Opsi penulis dan peninjau dalam alur menentukan mesin AI. Dalam peninjauan otomatis, peninjau sebisa mungkin menghindari keluarga model yang benar-benar dipakai penulis. Jika alur meminta mesin AI yang akunnya tidak dimiliki tim untuk peran itu, tugas dapat memakai pemilihan otomatis pada proses tersebut. Detail tugas menjelaskan perubahan ini.

Satu tugas membutuhkan satu mesin yang bisa menjalankan semua langkahnya. Di mesin itu, setiap langkah memakai akun aktif yang diizinkan untuk mesin AI dan perannya. Di antara akun yang memenuhi syarat, login yang menunggu pembaruan mendapat giliran pertama. Berikutnya, akun yang kuotanya diatur ulang dalam satu hari, dimulai dari waktu pengaturan ulang terdekat. Untuk pengaturan ulang yang lebih lama, pemilihan mempertimbangkan kuota yang dapat digunakan, kapasitas paket, dan waktu hingga pengaturan ulang. Akun tanpa hasil pembacaan mendapat giliran terakhir. Peninjauan inkremental atau peninjauan pertama dengan paling banyak 120 baris yang berubah mengutamakan paket lebih kecil yang masih memiliki kapasitas.

## Atur laju pekerjaan baru

Buka **Sumber daya**, lalu **Mode Laju**. Pengaturan bawaan, **Sesuai Kuota**, menyebarkan pekerjaan sepanjang periode kuota. Penggunaan akun mendahului laju ketika persentase kuota terpakai melebihi persentase waktu yang sudah berlalu lebih dari 100/7 poin persentase (sekitar 14.3), dan periode masih tersisa lebih dari sepertujuh. Jika semua akun yang memenuhi syarat mendahului laju, mesin menunggu sebelum mengambil tugas baru. Tugas yang sudah berjalan dapat dilanjutkan. Obrolan dengan **Pemimpin** juga dapat berlanjut.

Pilih **Tanpa Batas** agar semua tim dapat mengambil tugas baru tanpa menunggu batas laju itu. Cadangan akun dan batas kuota yang habis tetap berlaku. Jika akun dipilih untuk **Pemimpin** di salah satu tim dan kuota tersisa kurang dari 10% pada periode yang berlaku untuk seluruh akun, pekerja menyisakan akun itu untuk obrolan. Anda dapat kembali ke **Sesuai Kuota** di halaman yang sama.

## Jika ada masalah

- Jika berkas templat sudah ada, perintah menolak menimpanya dan menampilkan jalurnya. Sunting berkas tersebut dan daftarkan direktorinya.
- Jika perintah menolak direktori, periksa jalur yang ditampilkan. Direktori harus dimiliki pengguna Anda dan memiliki mode `0700` agar hanya Anda yang dapat mengaksesnya. Setelah pemilik dan izin benar, jalankan perintah templat lagi.
- `sail uninstall` menghapus `~/.sailorbridge/`, termasuk berkas pengaturan ini, jadi simpan salinan kunci Anda di tempat lain juga.
- Jika pendaftaran gagal, ikuti perintah login dari terminal untuk direktori yang Anda berikan. Direktori itu harus mengidentifikasi satu mesin AI. Gunakan `sail account list` untuk memeriksa nama. Untuk menghapus pendaftaran atau mengabaikan login bawaan, jalankan `sail account remove <name>`. Kredensial lokal tetap disimpan. Untuk mengenali kembali login bawaan, jalankan `sail account restore claude` atau `sail account restore codex`, atau buka **Login yang diabaikan** pada mesin dan pilih **Pulihkan**.
- Untuk **Login Kedaluwarsa**, masuk lagi pada mesin yang disebutkan. Untuk **Login Perlu Diperbarui**, mesin mencoba memperbarui login. Untuk **Jaringan Tidak Tersedia**, periksa koneksi mesin itu. Penyedia yang terkena pembatasan laju atau tidak tersedia dicoba lagi setelah jeda. Jika akun menampilkan **Model Belum Terbaca** di pemilih model, tunggu pembacaan atau pilih akun dengan model yang terdeteksi.
- Jika tim menolak penghapusan akun **Pemimpin**, pilih dulu akun lain di **Model Ketua**. Jika tugas kekurangan penulis atau peninjau, pilih **Ke akun** dari detailnya dan aktifkan peran yang kurang di mesin yang dapat menjalankan seluruh tugas.
- Buka **Daftar tugas** dan baca **Kenapa belum berjalan**. Jika menunggu karena pengaturan laju, perkiraan waktu ditampilkan. Anda dapat menunggu atau mengonfirmasi **Beralih ke Tanpa Batas** untuk semua tim. Tugas yang sudah kehabisan akun yang bisa digunakan menunggu di mesin yang sama dan memeriksa lagi pada waktu yang ditampilkan. Masuk atau mendapat kuota kembali memungkinkan tugas dilanjutkan otomatis.
