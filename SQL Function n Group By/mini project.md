# MINI PROJECT

**Laporan yang diminta :**

1. Total jumlah seluruh penjualan (total/revenue).
2. Total quantity seluruh produk yang terjual.
3. Total quantity dan total revenue untuk setiap kode produk.
4. Rata - Rata total belanja per kode pelanggan.
5. Menambahkan kolom baru dengan nama ‘kategori’ yang mengkategorikan total/revenue ke dalam 3 kategori: High: > 300K; Medium: 100K - 300K; Low: <100K.
 
 
 **tabel 'tr_penjualan':**
 
 
![image](https://user-images.githubusercontent.com/65942352/172422701-7b3f1d2a-5af0-46cc-a379-2179aeeba6dc.png)


**HASIL QUERY :**


        // 1. Total jumlah seluruh penjualan (total/revenue).
        
        SELECT SUM(total) as total 
        FROM tr_penjualan;
        
        
        // 2. Total quantity seluruh produk yang terjual.
        
        SELECT SUM(qty) as qty 
        FROM tr_penjualan;
        
        
        // 3. Total quantity dan total revenue untuk setiap kode produk.
        
        SELECT kode_produk, SUM(qty) as qty, SUM(total) as total 
        FROM tr_penjualan
        GROUP BY kode_produk;
        
        
        // 4. Rata - Rata total belanja per kode pelanggan.
        
        SELECT kode_pelanggan, AVG(total) as avg_total 
        FROM tr_penjualan
         GROUP BY kode_pelanggan;
         
         
        //5. Menambahkan kolom baru dengan nama ‘kategori’
        
        SELECT kode_transaksi,kode_pelanggan,no_urut,kode_produk, nama_produk, qty, total,
        CASE  
          WHEN total > 300000 THEN 'High'
          WHEN total < 100000 THEN 'Low'   
          ELSE 'Medium'  
        END as kategori 
        FROM tr_penjualan;
