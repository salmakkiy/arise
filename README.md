# ARISE — Daily Quest System

Aplikasi quest harian berbahasa Indonesia dalam satu berkas HTML. Progres, statistik, dan daftar quest disimpan di browser.

## Menjalankan secara lokal

Unduh repositori ini, lalu jalankan dari folder yang berisi `index.html`:

```sh
python3 -m http.server 8000
```

Buka `http://localhost:8000/` di browser. Hentikan server dengan Ctrl+C. Tidak ada langkah build atau instalasi paket aplikasi; Python 3 hanya dipakai untuk server pratinjau.

Gunakan alamat dan port yang sama saat kembali ke aplikasi. Penyimpanan browser terpisah untuk setiap origin, sehingga membuka port lain tidak otomatis menampilkan progres yang tersimpan sebelumnya.

## Penyimpanan dan cadangan

- Progres memakai `localStorage` dengan kunci `arise_save_v1`; tidak ada sinkronisasi progres lintas perangkat yang diimplementasikan di berkas ini.
- Menghapus data situs/browser dapat menghilangkan progres. Jika penyimpanan tidak tersedia, aplikasi menampilkan peringatan bahwa progres tidak akan tersimpan.
- Di Pengaturan, gunakan **Ekspor JSON** untuk mengunduh `arise_save.json` atau menyalin JSON cadangan.
- Untuk memulihkan cadangan, buka **Impor JSON** dan tempel isi JSON hasil ekspor. Impor mengganti data saat ini, jadi ekspor cadangan terlebih dahulu jika progres lama masih diperlukan.
- Perlakukan berkas cadangan sebagai data pribadi: isinya mencakup profil, progres, dan catatan yang disimpan dalam aplikasi.

## Ketergantungan saat membuka halaman

`index.html` memuat Google Fonts dan Chart.js 4.4.3 dari CDN. Video latihan dimuat saat dibuka. Karena ada sumber eksternal tersebut, repositori ini tidak menjanjikan pengalaman yang sepenuhnya offline.

Pergantian tanggal aplikasi memakai zona waktu `Asia/Jakarta`.
