# FourSight

# Stage 0

## Lists
1. Dataset Exploration
2. Business Understanding
3. Analytical Question
4. Business Success Metrics


## Insight
### 1. Dataset Exploration<br>
**Kesimpulan dari HeatMap “Review”**  
- id kemungkinan besar adalah identifier unik untuk ulasan atau transaksi yang menghubungkan listing_id dan reviewer_id.  
- listing_id dan id memiliki hubungan yang cukup kuat, menunjukkan bahwa setiap listing mungkin memiliki banyak entri terkait (id).  
- Hubungan antara reviewer_id dan listing_id lebih lemah, yang mungkin menunjukkan bahwa seorang reviewer bisa
meninjau beberapa listing yang berbeda.

**Kesimpulan dari HeatMap DF2 “Listing”**  
● Properti yang lebih besar cenderung bisa menampung lebih banyak tamu dengan lebih banyak kamar dan tempat tidur.  
● Listing yang lebih sering tersedia cenderung memiliki pola ketersediaan yang mirip dalam berbagai rentang waktu.  
● Listing dengan lebih banyak ulasan total cenderung menerima ulasan lebih sering.  
● Review scores biasanya bergerak bersama: jika sebuah listing mendapatkan skor tinggi dalam satu aspek, aspek lainnya juga kemungkinan besar tinggi.


### 2. Business Understanding<br>
**Masalah Spesifik yang Relevan:**<br>
● Optimasi Penetapan Harga (Pricing Strategy): Menentukan harga optimal  
untuk setiap properti berdasarkan faktor seperti lokasi, fasilitas, rating,
dan permintaan musiman.  
● Prediksi Permintaan: Memperkirakan tingkat hunian berdasarkan waktu tertentu, seperti musim liburan atau acara besar di Seattle.  
● Segmentasi Pasar: Mengidentifikasi jenis pelanggan (wisatawan bisnis,keluarga, pasangan) untuk mempersonalisasi layanan dan penawaran.  
● Analisis Kompetitif: Membandingkan properti dengan kompetitor dalam
wilayah yang sama untuk memahami tren pasar.

### 3. Analytical Question<br>

1. Bagaimana trend harga sewa property tertentu baik harga sewa satuan unit maupun harga harian secara agregat pada lini masa tertentu? Adakah waktu-waktu khusus dimana trend harga property mengalami peningkatan atau penurunan? 

Jika mengambil pertanyaan pertama, maka task yang bisa diajukan adalah analisis prediksi harga unit atau tingkat
keterisian unit pada waktu tertentu. Dalam hal ini, teknik regresi atau forecasting (time series analysis) dapat digunakan.
Beberapa contoh algoritma yang bisa digunakan dalam penelirian lanjutan adalah: decision tree regressor, ARIMA, KNN-Regressor
dan Linear Regression. Yang akan menjadi variabel bebas (X) adalah waktu dan variabel terikatnya (y) adalah harga property atau
rata-rata tingkat keterisian.

2. Adakah hubungan dari review yang diberikan oleh user baik secara kuantitas review maupun secara kualitas review
terhadap jumlah sewa (rata-rata keterisian) property? Misal apakah property yang jumlah reviewnya banyak, harganya
cenderung mahal atau cenderung terisi penuh? Atau apakah property yang kualits reviewnya bagus harganya cenderung mahal atau cenderung terisi penuh?

Jika mengambil pertanyaan kedua, maka dapat dianalisis menggunakan chi-square apakah terdapat hubungan asosiatif yang signifikan antara jumlah review dengan rata-rata harga unit. Atau jumlah review dengan rata-rata tingkat keterisian unit. Teknik analisis sentimen juga dapat digunakan untuk mengetahui kualitas dari review (positif, negatif, netral). Lebih lanjut dapat dianalisis apakah kualitas review mempengaruhi harga dan tingkat keterisian. Jika mengambil kasus kuantitatif, variabel bebasnya adalah jumlah review, semantara variabel terikatnya adalah harga atau tingkat keterisian yang diasumsikan tidak memiliki hubungan asosiatif terhadap waktu. Jika mengambil kasus kualitatif, variabel bebasnya adalah kualitas review (positif, negatif, netral) dan variabel terikatnya adalah harga atau tingkat keterisian unit. Metode yang digunakan bisa berupa Chiq Square Contigency atau membangun model ML untuk analisis sentiment.


3. Adakah hubungan antara waktu sebuah review diberikan dengan harga atau tingkat keterisian property. Hal ini
memungkinkan dimana ketika suatu property akan banyak diminati setelah banyak direview pada bulan sebelumnya. Namun jika bulan sebelumnya ternyata reviewnya sedikit, maka bisa jadi bulan depan peminatnya sedikit juga.

Jika mengambil pertanyaan ketiga, dapat menggunakan kombinasi antara kedua pertanyaan diatas, yaitu time series analysis dan review analysis. Task yang dapat dikerjakan adalah menganalisis apakah ada hubungan asosiatif yang signifikan jumlahreview pada bulan sebelumnya dengan harga atau tingkat keterisian property pada bulan setelahnya. Dalam kasus ini, variabel bebasnya adalah jumlah review pada bulan sebelumnya dan variabel terikatnya adalah harga atau keterisian unit pada bulan berikutnya. Tentunya kedua variabel harus memiliki rentang series yang sama. Misal sama-sama bulanan atau mingguan.Metode yang digunakan bisa gabungan antara time series analysis dengan Chiq Square Contigency atau membangun model ML
untuk analisis sentiment.

### 4. Business Success Metrics <br>
1. Time Series Analysis + Spatial Analysis<br>

**A. Time Series Analysis (Analisis Deret Waktu)**  
● **Tujuan**: Mengetahui tren harga di berbagai waktu, seperti mengenali musim sibuk dan sepi berdasarkan data ketersediaan.  
● **Metode**: Prediksi harga berdasarkan data kalender dan harga di setiap periode waktu.  
● **Metrik** :  
○ Mean Absolute Error (MAE) : Rata-rata absolut perbedaan antara nilai prediksi dan nilai aktual. MAE mengukur seberapa besar  
kesalahan prediksi model dalam satuan yang sama dengan data, dan memberikan gambaran yang jelas tentang seberapa besar perbedaan antara prediksi dan nilai yang sebenarnya  
○ Root Mean Squared Error (RMSE) : Akar dari rata-rata kuadrat perbedaan antara prediksi dan nilai aktual. RMSE memberikan penalt lebih besar pada kesalahan yang besar. digunakan dalam analisis time series untuk mengukur akurasi prediksi, dan lebih sensitif terhadap outlier dibandingkan MAE  
○ Mean Absolute Percentage Error (MAPE) : Persentase rata-rata perbedaan antara prediksi dan nilai aktual, yang diukur dalam bentuk persentase. MAPE memberikan gambaran yang jelas tentang akurasi prediksi dalam bentuk persentase, memudahkan interpretas dalam konteks bisnis  
○ R-squared (R2) : Persentase variabilitas dalam data yang dapat dijelaskan oleh model. R2 mengukur seberapa baik model mengaproksimasi data yang sebenarnya. digunakan untuk mengukur kekuatan model dalam menjelaskan variabilitas data. Semakin tinggi R2, semakin baik model dalam memprediksi data.  

**B. Spatial Analysis (Analisis Spasial)**  
● **Tujuan**: Menganalisis pola pemesanan berdasarkan lokasi dan menyusun strategi harga per area.  
● **Data yang Digunakan**:  
○ Koordinat geospasial (latitude, longitude), dan data lokasi properti.  
○ Faktor spasial seperti kedekatan dengan tempat wisata atau pusat bisnis.  
● **Metode**:  
○ Clustering (misalnya, K-Means atau DBSCAN) untuk menemukan hotspot pemesanan di area tertentu.
○ Geospatial Analysis untuk memahami bagaimana lokasi properti memengaruhi permintaan.  
● **Metrik** :  
○ Spatial Clustering (K-means atau DBSCAN) : Mengelompokkan lokasi berdasarkan kemiripan spasial, untuk
menemukan hotspot atau area dengan permintaan tinggi  
○ Spatial Autocorrelation (Moran's I) : Mengukur tingkat keterkaitan spasial antar objek atau lokasi dalam area yan lebih besar. Ini mengukur seberapa besar nilai suatu objek (misalnya, harga) dipengaruhi oleh nilai objek terdekat.  
○ Cross-Validation : digunakan untuk mengukur keandalan model dengan membagi data menjadi training set dan
test set secara berulang