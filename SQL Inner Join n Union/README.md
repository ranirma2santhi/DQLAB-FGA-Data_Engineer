# Fundamental SQL Using INNER JOIN and UNION

>INNER JOIN : Penggabungan tabel secara horizontal (menambah kolom), berdasarkan key.
>
> UNION : Penggabungan tabel secara vertikal (menambah baris),  kolom harus sama.

 
   
   
**1. INNER JOIN**

        // Menampilkan seluruh tabel
        SELECT * 
        FROM tr_penjualan 
        INNER JOIN ms_produk 
        ON tr_penjualan.kode_produk = ms_produk.kode_produk; 
        
        
        // Menampilkan tabel tertentu
        SELECT tr_penjualan.kode_transaksi, tr_penjualan.kode_pelanggan, tr_penjualan.kode_produk, 
        ms_produk.nama_produk, ms_produk.harga, tr_penjualan.qty,
        ms_produk.harga * tr_penjualan.qty as total
        FROM tr_penjualan
        INNER JOIN ms_produk
        ON tr_penjualan.kode_produk = ms_produk.kode_produk;
        
        
        
 **2. UNION**
 
        // Tabel kolom yang sudah sama 
        SELECT * FROM tabel_A
        UNION
        SELECT * FROM tabel_B;
        
        
        // Dengan kondisi
        SELECT * FROM tabel_A 
        WHERE kode_pelanggan = 'dqlabcust03'
        UNION 
        SELECT * FROM tabel_B
        WHERE kode_pelanggan = 'dqlabcust03';


        // Yang berbeda nama atau urutan kolom (dengan menyelaraskan)
        SELECT CustomerName, ContactName, City, PostalCode 
        FROM Customers
        UNION
        SELECT SupplierName, ContactName, City, PostalCode 
        FROM Suppliers;











