WARUNGKU PRO — PETUNJUK MEMULAI

ISI TAHAP PERTAMA
- Kerangka aplikasi web yang bisa dipasang sebagai PWA.
- Tambah dan lihat daftar barang.
- Menyimpan data barang di browser/perangkat (localStorage).
- Ekspor cadangan data JSON.
- Service worker untuk membuka aplikasi kembali saat offline setelah pertama kali dibuka online.
- Cetak halaman atau simpan ke PDF melalui menu cetak browser.

PENTING
Ini baru prototipe awal, bukan aplikasi kasir lengkap untuk operasional nyata.
Belum ada transaksi kasir, utang/piutang, laporan laba, login, sinkronisasi antar-cabang,
atau integrasi printer Bluetooth/USB.
Data lokal tidak otomatis berpindah antar-HP/laptop. Jangan masukkan data bisnis penting
sebelum tersedia database tersinkron, pencadangan teruji, dan pengujian.

CARA MENJALANKAN DI LAPTOP
1. Ekstrak file ZIP ke folder.
2. Pastikan Python 3 terpasang (banyak laptop sudah bisa memasangnya gratis).
3. Buka Terminal/Command Prompt di folder ini.
4. Jalankan: python -m http.server 8000
   Jika perintah itu tidak berjalan di Windows, coba: py -m http.server 8000
5. Buka browser ke: http://localhost:8000
6. Tambahkan barang contoh, lalu refresh halaman untuk memastikan data masih ada.
7. Untuk uji offline: buka aplikasi saat online dulu, lalu matikan internet dan refresh.
   PWA/service worker memerlukan localhost atau HTTPS; jangan membuka file HTML langsung.

CARA MENCOBA DI HP
- Cara paling mudah untuk tahap awal adalah menguji dari laptop terlebih dahulu.
- Agar HP dapat memasang aplikasi dan memakai cache offline, aplikasi harus disajikan lewat HTTPS
  atau jaringan lokal dengan pengaturan yang sesuai. Untuk akses dari luar rumah dan sinkronisasi
  antar-cabang, kita perlu hosting dan backend/database online.

URUTAN PEMBANGUNAN SELANJUTNYA
1. Database lokal yang lebih kuat (IndexedDB) dan identitas cabang/perangkat.
2. Modul kasir: keranjang, pembayaran tunai/non-tunai, kembalian, transaksi.
3. Pengurangan stok otomatis dan riwayat stok.
4. Utang pelanggan, pembayaran cicilan, dan utang pemasok.
5. Laporan omzet, harga pokok barang terjual, laba kotor, biaya, laba bersih.
6. Sinkronisasi multi-cabang dengan ID transaksi unik, aturan konflik, dan audit log.
7. Cetak struk: browser print dahulu; Bluetooth/USB tergantung printer, browser, dan perangkat.
8. Login, hak akses, backup otomatis, dan uji pemulihan data.

CATATAN KEUNTUNGAN
Laba bersih bukan sekadar omzet dikurangi harga modal satu barang.
Perhitungan perlu memperhitungkan jumlah barang terjual, diskon, retur, biaya operasional,
dan penyesuaian stok.
