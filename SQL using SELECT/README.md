# Catatatan Modul Fundamental SQL Using SELECT Statement


**1. Pengambilan Satu Kolom**

         SELECT nama_produk FROM tb_produk
    
 **2. Mengambil Lebih dari Satu Kolom dari Tabel**
 
         SELECT nama_produk, harga FROM tb_produk    // Untuk beberapa kolom
         SELECT * FROM tb_produk // Untuk Semua
    
 **3. Membatasi Pengambilan Jumlah Row Data - [ LIMIT ]**
 
          SELECT nama_produk, harga FROM tb_produk LIMIT 7;
       
 **4. Menghilangkan Duplikasi - [ SELECT DISTINCT ]**
          
          SELECT DISTINCT nama_customer, alamat FROM tb_pelanggan;
          
  **5. Prefix untuk spesifik tabel  - [ ms_produk.kode_produk]**
  
      *) biasanya digunakan untuk jika ada lebih dari satu tabel/di INERJOIN
      
          SELECT ms_produk.kode_produk FROM tb_produk;
          
      
          
  **6. Menggunakan Alias - [ AS ]**
  
          SELECT no_urut AS nomor, nama_produk AS nama from tb_produk; // dengan 'AS'
          SELECT no_urut nomor, nama_produk nama FROM tb_produk; // tanpa 'AS'
          
  **7. Gabungan Prefix dan AS**
  
          SELECT t2.nama_produk , t2.harga  FROM tb_produk AS t2; // dengan 'AS'
          SELECT t2.nama_produk , t2.harga  FROM tb_produk t2; // tanpa 'AS'
          
          SELECT ms_produk.harga AS harga_jual FROM tb_produk;
          
  **8. Penggunaan 'WHERE' untuk data kondisi tertentu**
  
          SELECT * FROM tb_produk WHERE nama_produk = 'Tas Travel Organizer DQLab';
          SELECT * FROM tb_produk WHERE harga > 50000;
          
          // Dengan Opreand
          SELECT * FROM tb_produk WHERE nama_produk = 'Mawar' OR nama_produk = 'Melati' OR nama_produk = 'Magnolia';
          SELECT * FROM tb_produk WHERE nama_produk = 'Mawar' AND harga<5000;
          
          
