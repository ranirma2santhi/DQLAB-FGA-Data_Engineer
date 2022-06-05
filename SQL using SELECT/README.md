# Catatatan Modul Fundamental SQL Using SELECT Statement


**1. Pengambilan Satu Kolom**

         SELECT nama_produk FROM ms_produk
    
 **2. Mengambil Lebih dari Satu Kolom dari Tabel**
 
         SELECT nama_produk, harga FROM ms_produk    // Untuk beberapa kolom
         SELECT * FROM ms_produk // Untuk Semua
    
 **3. Membatasi Pengambilan Jumlah Row Data - [ LIMIT ]**
 
          SELECT nama_produk, harga FROM ms_produk LIMIT 5;
       
 **4. Menghilangkan Duplikasi - [ SELECT DISTINCT ]**
          
          SELECT DISTINCT nama_customer, alamat FROM ms_pelanggan;
          
  **5. Prefix untuk spesifik tabel  - [ ms_produk.kode_produk]**
  
      *) biasanya digunakan untuk jika ada lebih dari satu tabel/di INERJOIN
      
          SELECT ms_produk.kode_produk FROM ms_produk;
          
      
          
  **6. Menggunakan Alias - [ AS ]**
  
          SELECT no_urut AS nomor, nama_produk AS nama from ms_produk; // dengan 'AS'
          SELECT no_urut nomor, nama_produk nama FROM ms_produk; // tanpa 'AS'
          
  **7. Gabungan Prefix dan AS**
  
          SELECT t2.nama_produk , t2.harga  FROM ms_produk AS t2; // dengan 'AS'
          SELECT t2.nama_produk , t2.harga  FROM ms_produk t2; // tanpa 'AS'
          
          SELECT ms_produk.harga AS harga_jual FROM ms_produk;
          
  **8. Penggunaan 'WHERE' untuk data kondisi tertentu**
  
          SELECT * FROM ms_produk WHERE nama_produk = 'Tas Travel Organizer DQLab';
          SELECT * FROM ms_produk WHERE harga > 50000;
          
          // Dengan Opreand
          SELECT * FROM ms_produk WHERE nama_produk = 'Gantungan Kunci DQLab' OR nama_produk = 'Tas Travel Organizer DQLab' OR nama_produk = 'Flashdisk DQLab 64 GB';
          SELECT * FROM ms_produk WHERE nama_produk = 'Gantungan Kunci DQLab' AND harga<50000;
          
          
