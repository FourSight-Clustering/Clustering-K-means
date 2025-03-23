# FourSight

# Stage 2

## Lists
1. Model Selection 
2. Model training  
3. Profilisasi Cluster  
4. Streamlit User Interface  


## Insight  
### 1. Model Selection<br>
Clustering memungkinkan pengelompokan data berdasarkan karakteristik tertentu, yang bermanfaat bagi Airbnb dalam:  
- Mengidentifikasi segmen pelanggan berdasarkan preferensi dan perilaku.  
- Menganalisis pola harga dan lokasi untuk strategi penetapan harga yang lebih optimal.  
- Mengelompokkan properti berdasarkan fitur untuk pengalaman pengguna yang lebih baik.  



### 2. Model training <br>
Pelatihan model adalah proses melatih algoritma ML dengan data pelatihan yang memadai untuk menunjukkan korelasi antara hasil dan variabel yang memengaruhi.  
Dalam hal ini diperlukan data cleaning dan feature engineering. Model yang dipilih menggunakan K-Means karena dianggap mampu digunakan untuk data dengan skala besar.


1. **MinMaxScaler** adalah fungsi unutk melakukan normalisasi data. Artinya skala data akan diubah sehingga hanya bernilai antara 0 dan 1. Nilai 0 untuk data terendah, dan nilai 1 untuk data tertinggi.  
2. **Imputer dari Scikit-Learn** yang digunakan untuk mengganti data yang hilang dengan nilai tertentu. Ini dapat mempercepat proses data preprocessing.  
3. **One hot encoder** digunakan untuk melakukan label encoding khusus pada label-label yang memiliki lebih dari dua kategori. Hal ini memungkinkan setiap kategori untuk dibuatkan satu kolom khusus, sehingga menjadi binary.  
Teknik ini digunakan untuk menghindari bias yang bersifat ordinal pada LabelEncoding.  


### 3. Profilisasi Cluster<br>

**Cluster 1 :** <br>
Harga (price): Rp137 ribuan (sedang, kuning)<br>
Review score rating: 97,46 (tertinggi, merah) → Sangat baik<br>
Superhost: (tertinggi, merah) → Semua host di cluster adalah Superhost<br>
Jarak ke pusat kota:  (terdekat kedua)<br>
Respon time host: 1,38 jam (tercepat, hijau)<br>
→ Kategori: Properti berkualitas tinggi, harga sedang, superhost, dan dekat kota.<br>

**Cluster 2** (Harga termurah, sedikit fasilitas, jarak terjauh)<br>
Harga: Rp72 ribuan (termurah, hijau)<br>
Review score rating: 95,45 (terendah, hijau)<br>
Superhost: 19,8% (tertinggi kedua, oranye)<br>
Kapasitas: 2 orang, 1 kamar tidur → Paling minimalis<br>
Jarak ke pusat kota:  (terjauh, merah)<br>
→ Kategori: Budget-friendly, fasilitas minimal, jarak agak jauh dari pusat kota.<br>


**Cluster 3** (Fasilitas paling sedikit, superhost sedikit)<br>
Harga: Rp122 ribuan (sedang, kuning)<br>
Superhost: 0% (terendah, hijau) → Tidak ada Superhost<br>
Kapasitas: 3 orang, 1 kamar tidur → Mirip Cluster 2<br>
Jarak ke pusat kota:  (terdekat, hijau)<br>
Respon time host: 1,63 jam (ke-2 tertinggi, oranye)<br>
→ Kategori: Properti dekat kota, tapi hostnya bukan Superhost.<br>


**Cluster 4** (Harga tertinggi, kapasitas besar, review bagus)<br>
Harga: Rp230 ribuan (tertinggi, merah)<br>
Kapasitas: 5-6 orang, 2,5 kamar tidur (tertinggi, merah)<br>
Jarak ke pusat kota: (ke-3 tertinggi, oranye)<br>
Respon time host: 1,71 jam (tertinggi, merah)<br>
→ Kategori: Properti mewah, harga mahal, cocok untuk keluarga/banyak orang.<br>

***Berdasarkan Tipe Kamar:*<br>**
**Cluster 1**: Mayoritas terdiri dari Entire Home/Apt dengan harga menengah (137,52) dan jumlah ulasan tertinggi. Mayoritas menggunakan Real Bed, menunjukkan kenyamanan standar dengan akses penuh ke akomodasi.  

**Cluster 2**: Didominasi oleh Private Room dengan harga paling rendah (72,65). Berbagai jenis tempat tidur digunakan, termasuk Futon yang cukup tinggi, menandakan opsi ekonomis dengan fasilitas terbatas.


**Cluster 3**: Seluruh room type nya adalah Entire/Apartemen dengan harga menengah (122,37), tanpa Shared Room, dan didominasi Real Bed, mencerminkan kenyamanan lebih baik dibandingkan Cluster 2. 


**Cluster 4**: Hampir semua Entire Home/Apt dengan harga tertinggi (230,11), sangat didominasi Real Bed, mencerminkan akomodasi premium dengan kenyamanan terbaik.

### 4. Streamlit User Interface  <br>
