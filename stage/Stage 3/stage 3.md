# FourSight

# Stage 3

## Lists
1. Penentuan Model
2. Model Evaluation
3. Error Analysis
4. Hyperparameter
5. Kolaborasi Tim dengan Alat Digital
6. Kesimpulan


## Insight  
### MODEL FINAL TESTING<br>
- KMeans terbukti sebagai algoritma klasterisasi paling efektif berdasarkan evaluasi, dengan skor tinggi pada Calinski-Harabasz Index dan Silhouette Score.
- Agglomerative Clustering juga memberikan hasil yang cukup baik, meskipun sedikit di bawah KMeans.
- DBSCAN menunjukkan pemisahan klaster yang baik dalam Davies-Bouldin Index, tetapi kurang optimal pada Silhouette Score dan Calinski-Harabasz Index.
- SOM memberikan hasil terlemah dibandingkan algoritma lainnya.



### Error Analysis <br>
- **Tidak ada Error Analysis dalam Clustering**  
Berbeda dengan supervised learning, clustering tidak memiliki error analysis karena tidak ada data training dan testing untuk dibandingkan.  

- **Evaluasi yang Digunakan**  
Sebagai gantinya, evaluasi dalam clustering dilakukan melalui profilisasi cluster dan rekomendasi bisnis, bukan melalui error analysis seperti pada supervised learning.  

Analisis selanjutnya akan berfokus pada identifikasi karakteristik masing-masing klaster serta penyusunan rekomendasi bisnis yang relevan berdasarkan hasil klasterisasi.  

### Hyperparameter Tuning<br>

KMeans menghasilkan klaster yang lebih jelas dan padat dibandingkan DBSCAN, seperti ditunjukkan oleh nilai Davies-Bouldin Index, Silhouette Score, dan Calinski-Harabasz Index yang lebih unggul.

Metode terbaik yang dipilih: KMeans dengan 5 klaster.


### Cluster PCA <br>
Gambar 3D ini menunjukkan hasil klasterisasi KMeans dengan 5 klaster dalam ruang PCA 3D. Setiap warna mewakili klaster, dengan pemisahan yang cukup jelas, terutama pada Cluster 1 dan 2.  
Namun, terdapat sedikit tumpang tindih antara Cluster 4 dan Cluster 5, yang menunjukkan kemiripan fitur antar data di klaster tersebut. Secara keseluruhan, KMeans berhasil mengelompokkan data dengan baik berdasarkan pola PCA  

- **Cluster 1** (Budget Single): Akomodasi hemat untuk 1-2 orang ($113/malam) dengan privasi penuh dalam Entire Home/Apt.

- **Cluster 2** (Spacious Family Home):
Properti luas untuk keluarga besar (6 orang, $200/malam), memiliki 3 kamar tidur dan cocok untuk grup.

- **Cluster 3** (Luxury Group Stay): 
Mirip Cluster 2, tetapi lebih mahal ($202/malam) dan mencakup lebih banyak tamu dalam harga sewa.

- **Cluster 4** (Economy Shared Room): 
Pilihan termurah ($70/malam) dengan kamar Shared Room, cocok untuk penghematan biaya tetapi dengan privasi terbatas.

- **Cluster 5** (Mid-Range Private Room):
 Opsi harga menengah ($134/malam) untuk 4 orang dengan Private Room, memberikan keseimbangan antara harga dan kenyamanan.

### Kesimpulan<br>
Klasterisasi berhasil mengelompokkan properti berdasarkan harga, kapasitas, dan tipe akomodasi. K-Means dengan 5 klaster menunjukkan pola yang jelas: dari opsi hemat (Cluster 1 & 4), menengah (Cluster 5), hingga keluarga & grup besar (Cluster 2 & 3).  
Hasil ini dapat membantu dalam strategi harga dan pemasaran sesuai dengan preferensi pelanggan.