[← SailorBridge](README.md)

# Memori tim

Memori tim menyimpan keputusan, konvensi, dan perbaikan yang dapat digunakan oleh **Pemimpin** dan pekerja untuk tugas berikutnya. Setiap entri memiliki judul, isi, sumber, dan nomor seperti `#6`. Satu entri dimiliki oleh satu tim. Tim lain dan teman tidak dapat menjelajahinya.

## Catat hal yang perlu diingat

Di obrolan tim, sebutkan apa yang perlu diingat dan kapan berlaku. Misalnya, “Ingat bahwa contoh pemasangan harus ada di panduan penyiapan. Gunakan aturan ini saat mengubah perintah pemasangan.” **Pemimpin** memberi tahu Anda apa yang dicatat. Buka menu **Tindakan lainnya** di obrolan tim dan pilih **Memori tim** untuk melihat entri. Buka judul entri untuk membaca teks lengkap dan melihat siapa yang terakhir mengubahnya.

## Temukan entri dan gunakan di obrolan

Buka **Cari** di **Memori tim**. Masukkan kata dari judul atau isi. Semua kata harus cocok untuk menghasilkan kecocokan teks, dan halaman pertama juga dapat menampilkan hingga tiga entri dengan makna serupa. Entri yang disematkan muncul pertama di daftar biasa.

Jika tahu nomornya, cari `#6` untuk mendapatkan entri 6 saja. Mencari `6` juga menemukan kecocokan teks. Buka entri dan pilih **Buka Chat**. Kolom masukan sekarang berisi `/memory #6`. Tambahkan pertanyaan atau koreksi dan kirim.

## Sunting, sematkan, kunci, atau hapus entri

- Buka entri, ubah **Isi**, dan pilih **Simpan**. **History** menunjukkan 10 versi terakhir. Periksa **Observed** dan **Expires** untuk fakta yang bisa berubah. Entri dengan status **Expired** tetap bisa dibaca, jadi periksa apakah sarannya masih berlaku.
- Aktifkan **Disematkan** untuk memasukkan instruksi ke materi yang diberikan kepada **Pemimpin** dan pekerja. Entri menampilkan penggunaan ruang sematan tim. Semua judul dan isi yang disematkan dapat memakai ruang hingga 8 KiB secara keseluruhan.
- Aktifkan **Terkunci** jika hanya Anda yang boleh mengubah atau menghapusnya. Menyematkan saja masih memungkinkan agent menyunting entri. Anda dapat menyunting entri terkunci di web.
- Pilih **Hapus** dan konfirmasikan untuk menghapus entri secara permanen. Nomornya tidak akan dipakai lagi.

## Rapikan entri tim

Kirim `/memory-tidy` di obrolan tim. Tugas memeriksa entri, menandai yang layak disimpan, menggabungkan entri terkait, dan menghapus entri yang tidak berguna lagi. Buka **Laporan serah terima** untuk melihat apa yang dikerjakan dan apa yang masih memerlukan keputusan Anda. Entri terkunci tetap dipertahankan jika tugas mengusulkan penghapusan atau penggabungan.

Perapian otomatis berjalan paling banyak sekali per tim dalam rentang 24 jam berjalan ketika ada entri yang perlu diperiksa. Agar hanya berjalan atas permintaan atau jadwal Anda, buka **Alur tim**, pilih `memory-tidy`, lalu matikan **Rapikan otomatis**.

## Jika ada masalah

- Penyematan yang akan melampaui 8 KiB ditolak. Lepaskan sematan dari entri lain atau pendekkan teks yang disematkan, lalu coba lagi.
- Jika seseorang menyunting entri ketika Anda bekerja, isi terbaru ditampilkan. Baca sebelum menerapkan ulang koreksi.
- Jika dua pembaruan memakai judul yang sama, koreksi oleh penulis yang sama dapat langsung berlaku. Jika berbeda, tingkat konfirmasi yang lebih tinggi atau pengamatan lebih baru pada tingkat yang sama dapat menyelesaikannya. Jika pembaruan perlu keputusan, entri menampilkan **Konflik belum diselesaikan** dan mempertahankan teks saat ini. Buka entri, periksa fakta, dan simpan teks yang benar. Entri terkunci memerlukan keputusan Anda.
- Jika **Pemimpin** melaporkan bahwa suatu memori tidak tersimpan, ulangi apa yang ingin Anda minta untuk diingat. Jika agent ditolak karena entri terkunci, buat sendiri perubahannya di **Memori tim**.
