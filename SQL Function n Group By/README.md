# Catatan Modul Fundamental SQL Using FUNCTION and GROUP BY
**KONSEP FUNCTION**

> Fungsi Scalar :  langsung memberikan nilai balikan (return nilai) dari input. 

> fungsi aggregate : fungsi yang melalukan operasi/ perhitungan lalu memberikan nilai return. 

> Rumus Umum : Nama_fungsi(Nilai input)
 
 

**1. Contoh Fungsi Skalar**

link referensi lainnya: https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html


        // FUNGSI SKALAR NUMBERIK
        SELECT StudentID, FullName, Smt1, Smt2, ABS(selisih) AS selisih FROM students; // Absolut
        SELECT StudentID, FullName, CEILING(Smt1) AS Smt1, CEILING(Smt2) AS Smtr2, selisih FROM students; // Pembulatan ke atas
        SELECT StudentID, FullName, FLOOR(Smt1) AS Smt1, FLOOR(Smt2) AS Smt2, selisih FROM students; // Pembulatan Kebawah
        SELECT StudentID, FullName, ROUND(Smt1,1) AS Smt1, ROUND(Smt2,0) AS Smt2, selisih From students; // jumlah angka belakang koma
        SELECT MOD(StudentID,3), FullName From students; // Modulo
        
        
        // FUNGSI SKALAR STRING
        SELECT Id_Karyawan, CONCAT(FirstName, LastName)AS Name, MarkGrowth FROM tb_Karyawan; // Menggabungkan
        SELECT Id_Karyawan, SUBSTRING_INDEX(Email,'@',1) AS Name FROM tb_Karyawan; // split(memisah) --> index mulai 1
        SELECT Id_Karyawan, SUBSTR(FirstName, 2, 3) AS Initial FROM tb_Karyawan; // Mengambil beberapa huruf
        SELECT Id_Karyawan, FirstName, LENGTH(FirstName)as Total_Char FROM tb_Karyawan; // hitung jumlah karater
        SELECT Id_Karyawan, Email, REPLACE(Email,'yahoo','gmail') AS New_Email FROM tb_Karyawan; // replace
        

**2. Contoh Fungsi Agregat**

        SELECT SUM(Bulan1) AS Total_1, SUM(Bulan2) AS Total_2 FROM tb_product; // Menjumlahkan(total)
        SELECT COUNT(ProductName) as TotalProduct FROM tb_product; // Menghitung banyak
        SELECT AVG(Bulan1) AS AVG_1, AVG(Bulan2) AS AVG_2 FROM tb_product; // Rata-Rata
        
 
 **KONSEP GROUP BY**
 
 >Pengelompokan Data dengan Nilai Sama

>Posisi : 
>
>1. Setelah 'FROM' 
>2. Setelah 'WHERE' : Kalau Pakai
>3. Sebelum 'GROUP BY' : Kalau Pakai
 
        // GROUP BY Satu Kolom
        SELECT kota,
        COUNT(DISTINCT order_id) AS total_order,
        SUM(harga_item) AS total_belanja
        FROM tb_penjualan
        GROUP BY kota;

        // GROUP BY Dua Kolom
        SELECT kota, brand, 
        COUNT(DISTINCT order_id) as total_order, 
        SUM(harga_item) AS total_belanja FROM tb_penjualan GROUP BY kota, brand;

        // CASE (Pengkondisian)
        SELECT MONTH(order_date) AS order_month, SUM(harga_item) AS total_belanja, 
        CASE  
            WHEN SUM(harga_item) >= 30000000000 THEN 'Target Achieved'
            WHEN SUM(harga_item)<= 25000000000 THEN 'Less Performed'
            ELSE 'Follow Up'
        END as remark
        FROM tb_penjualan
        GROUP BY order_month;
 
