 # MINI PROJECT INNER JOIN
 
 
 **TUGAS:**
 
 Suatu hari, departemen marketing & promotion meminta bantuan untuk meng-query data-data pelanggan yang membeli produk Kotak Pensil DQLab, Flashdisk DQLab 32 GB, dan Sticky Notes DQLab 500 sheets.

Buatlah query menggunakan tabel ms_pelanggan dan tr_penjualan untuk mendapatkan data - data yang diminta oleh marketing yaitu kode_pelanggan, nama_customer, alamat.

**TABEL :**
 
 
 Tabel ms_pelanggan
 
        +---------+----------------+---------------------+------------------------------------------+
        | no_urut | kode_pelanggan | nama_customer       | alamat                                   |
        +---------+----------------+---------------------+------------------------------------------+
        |       1 | dqlabcust01    | Eva Novianti, S.H.  | Vila Sempilan, No. 67 - Kota B           |
        |       2 | dqlabcust02    | Heidi Goh           | Vila Sempilan, No. 11 - Kota B           |
        |       3 | dqlabcust03    | Unang Handoko       | Vila Sempilan, No. 1 - Kota B            |
        |       4 | dqlabcust04    | Jokolono Sukarman   | Vila Permata Intan Berkilau, Blok C5-7   |
        |       5 | dqlabcust05    | Tommy Sinaga        | Vila Permata Intan Berkilau, Blok A1/2   |
        |       6 | dqlabcust06    | Irwan Setianto      | Vila Gunung Seribu, Blok O1 - No. 1      |
        |       7 | dqlabcust07    | Agus Cahyono        | Vila Gunung Seribu, Blok F4 - No. 8      |
        |       8 | dqlabcust08    | Maria Sirait        | Vila Bukit Sagitarius, Gang. Sawit No. 3 |
        |       9 | dqlabcust09    | Ir. Ita Nugraha     | Vila Bukit Sagitarius, Gang Kelapa No. 6 |
        |      10 | dqlabcust10    | Djoko Wardoyo, Drs. | Vila Bukit Sagitarius, Blok A1 No. 1     |
        |      11 | dqlabcust11    | Unang Handoko       | Vila Sempilan, No. 1 - Kota B            |
        |      12 | dqlabcust12    | Tommy Sinaga        | Vila Permata Intan Berkilau, Blok A1/2   |
        +---------+----------------+---------------------+------------------------------------------+
        
        
        
Tabel tr_penjualan
        
        
        +----------------+----------------+---------+-------------+-------------------------------+------+--------+
        | kode_transaksi | kode_pelanggan | no_urut | kode_produk | nama_produk                   | qty  | harga  |
        +----------------+----------------+---------+-------------+-------------------------------+------+--------+
        | tr-001         | dqlabcust07    |       1 | prod-01     | Kotak Pensil DQLab            |    5 |  62500 |
        | tr-001         | dqlabcust07    |       2 | prod-03     | Flash disk DQLab 32 GB        |    1 | 100000 |
        | tr-001         | dqlabcust07    |       3 | prod-09     | Buku Planner Agenda DQLab     |    3 |  92000 |
        | tr-001         | dqlabcust07    |       4 | prod-04     | Flashdisk DQLab 32 GB         |    3 |  40000 |
        | tr-002         | dqlabcust01    |       1 | prod-03     | Gift Voucher DQLab 100rb      |    2 | 100000 |
        | tr-002         | dqlabcust01    |       2 | prod-10     | Sticky Notes DQLab 500 sheets |    4 |  55000 |
        | tr-002         | dqlabcust01    |       3 | prod-07     | Tas Travel Organizer DQLab    |    1 |  48000 |
        | tr-003         | dqlabcust03    |       1 | prod-02     | Flashdisk DQLab 64 GB         |    2 |  55000 |
        | tr-004         | dqlabcust03    |       1 | prod-10     | Sticky Notes DQLab 500 sheets |    5 |  55000 |
        | tr-004         | dqlabcust03    |       2 | prod-04     | Flashdisk DQLab 32 GB         |    4 |  40000 |
        | tr-005         | dqlabcust05    |       1 | prod-09     | Buku Planner Agenda DQLab     |    3 |  92000 |
        | tr-005         | dqlabcust05    |       2 | prod-01     | Kotak Pensil DQLab            |    1 |  62500 |
        | tr-005         | dqlabcust05    |       3 | prod-04     | Flashdisk DQLab 32 GB         |    2 |  40000 |
        | tr-006         | dqlabcust02    |       1 | prod-05     | Gift Voucher DQLab 250rb      |    4 | 250000 |
        | tr-006         | dqlabcust02    |       2 | prod-08     | Gantungan Kunci DQLab         |    2 |  15800 |
        +----------------+----------------+---------+-------------+-------------------------------+------+--------+
        
        
 **HASIL QUERY**
        
        SELECT DISTINCT ms_pelanggan.kode_pelanggan, ms_pelanggan.nama_customer, ms_pelanggan.alamat 
        FROM ms_pelanggan 
        INNER JOIN tr_penjualan
        ON ms_pelanggan.kode_pelanggan = tr_penjualan.kode_pelanggan 
        WHERE tr_penjualan.nama_produk = 'Kotak Pensil DQLab' 
        OR tr_penjualan.nama_produk = 'Flashdisk DQLab 32 GB' 
        OR tr_penjualan.nama_produk = 'Sticky Notes DQLab 500 sheets';
