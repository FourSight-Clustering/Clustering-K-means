# FourSight

# Stage 1

## Lists
1. Data Quality Assesment 
2. Data Cleaning
3. Analytical Question
4. Business Success Metrics


## Insight  
### 1. Dataset Exploration<br>
1. Cek adanya missing values di setiap kolom dataset.  
2. Identifikasi inconsistent entries seperti format yang berbeda dalam sat kolom (contoh: kolom tanggal dengan format yang tidak seragam).  
3. Cari outliers dengan menggunakan metode statistik (misalnya interquartile range atau z-score) untuk mendeteksi nilai-nilai yang menyimpang  

### 2. Data Cleaning<br>
1. Handling missing values: Anda bisa memilih untuk menghapus data yang hilang atau mengisinya dengan nilai rata-rata (mean), median, atau nilai lain yang relevan.  
2. Correcting inconsistent entries: Sesuaikan format yang tidak konsisten, misalnya mengubah semu entri tanggal ke format yang seragam.  
3. Removing duplicates: Hapus baris-baris data yang berulang menggunakan fungsi filtering.  

### 3. Data Integration<br>

Variabel key dari calender adalah listing_id, Variabel key dari Listing adalah id dan penggabungan menggunakan “inner”  

### 4. Feature Engineering <br>
Variabel baru yang ditambahkan :  
1. Month: Mengambil bulan dari kolom date.  
2. Holiday Indicator: Fitur biner untuk menandakan apakah tanggal tersebut adalah hari libur nasional. Libur nasional untuk Amerika Serikat tahun 2016 sudah diberikan sebelumnya.  
3. Tanggal Features (Day of Week, Month, Quarter, Season): Untuk fitur tambahan seperti hari dalam seminggu, bulan, kuartal, dan musim  
4. Distance to Points of Interest: Menghitung jarak ke pusat kota atau objek wisata utama menggunakan koordinat geospasial (Haversine formula). Menggunakan Haversine formula untuk menghitung jarak antara dua titik berdasarkan latitudo dan longitudonya.  
Encoding :  
1. One Hot Encoding : room_type, season, bed_type  
2. Label Encoding : host_respon_time, host_is_superhost, available  
3. Custom Encoding (Menggunakan mean,std, dan median price_y): Property_type

**VISUALISASI DAN INSIGHT**

1. Ketersediaan Kamar Saat Ini: 934.542  
- Angka ini menunjukkan jumlah total unit yang tersedia di Seattle.
2. Dominasi Entire Home/Apt dalam Proporsi Jenis Kamar
- 63,5% dari listing adalah Entire Home/Apt, menunjukkan bahwa mayorita pemilik properti lebih memilih menyewakan seluruh unit daripada hanya satu kamar.  
- 32,8% adalah Private Room, yang juga cukup signifikan tetapi jauh lebih keci dibandingkan Entire Home/Apt.  
- Shared Room hampir tidak terlihat dalam proporsi, yang bisa menunjukka bahwa model berbagi kamar kurang diminati di pasar ini.  

**Insight dari Tabel Deskripsi:**<br>
● Dominasi Seattle: Semua data yang ditampilkan berasal dari Seattle, menunjukkan bahwa kota ini memiliki jumlah
listing terbanyak.  
● Tipe Akomodasi Populer: "Entire Home/Apt" dengan harga rata-rata $287,5 memiliki jumlah listing tertingg (13.207), menunjukkan bahwa properti sewa satu unit penuh lebih diminati dibandingkan tipe lain.  
● Private Room sebagai Alternatif**: Private Room dengan harga antara $60-$75 juga memiliki jumlah listing yang
cukup tinggi, menandakan adanya pasar bagi penyewa yang mencari opsi lebih terjangkau.  
● Ketersediaan Tinggi: Semua properti memiliki ketersediaan 365 hari, yang berarti banyak host menawarkan properti mereka sepanjang tahun tanpa batasan waktu tertentu.  