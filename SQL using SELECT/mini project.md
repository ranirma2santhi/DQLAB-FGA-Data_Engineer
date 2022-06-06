**Tugas :**

   Menyiapkan data transaksi penjualan dengan total revenue >= IDR 100.000  dari tabel tr_penjualan



**Output yang diinginkan :**

   kode_pelanggan, nama_produk, qty, harga, dan total, serta diurutkan mulai dari total revenue terbesar


**Clue :** 

   Perkalian antara kolom qty dan harga untuk memperoleh total revenue setiap kode pelanggan yang dinyatakan ke dalam kolom total, dan
   menggunakan “ORDER BY total DESC” pada akhir query untuk mengurutkan data.


**Hasil QUERY:**

        SELECT kode_pelanggan, nama_produk, qty, harga, qty * harga as total 
        FROM tr_penjualan WHERE  qty * harga >= 100000 ORDER BY total DESC;
