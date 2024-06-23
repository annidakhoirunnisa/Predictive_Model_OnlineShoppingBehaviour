# 🛒 **Unlocking Online Shopper Behavior** 🛒
---
## 📂 **Stage 0 : Problem Statement**
### Problem Statement
- E-commerce didefinisikan sebagai tempat terjadinya transaksi atau pertukaran informasi antara penjual dan pembeli di dunia maya, tanpa harus berada dalam satu tempat atau ruang tertentu. E-commerce juga memberikan manfaat yang dapat dirasakan oleh konsumen secara langsung, yaitu menghemat waktu serta tidak ada batasan jarak. Adapun Indikator dari E-Commerce yaitu tingkat kepercayaan, harga, dan informasi.

- Dalam praktiknya, persaingan industri e-commerce sangat ketat sehingga perusahaan e-commerce bersaing dalam menawarkan beberapa jenis promosi yang mampu menarik perhatian konsumen, seperti gratis ongkir seluruh wilayah, voucher cashback, paket diskon, dan flash sale. Selain itu perusahaan e-commerce bersaing dalam pengembangan website untuk kenyamanan pengguna Hal-hal tersebut sangat mempengaruhi perilaku konsumen dalam mengambil keputusan pembelian. Menurut peneliti, Konsumen merupakan tonggak dari keberhasilan penjual atau pelaku bisnis ecommerce yang menginginkan keuntungan dalam jalannya usaha.

- Sebagai konsultan perusahaan e-commerce yang telah memiliki data pembelian online, kami akan menggunakan data tersebut untuk meningkatkan performa perusahaan dengan cara membangun sebuah model yang dapat memprediksi pengunjung untuk melakukan transaksi pada situs website suatu e-commerce. Hasil prediksi yang tepat dapat digunakan dalam strategi pemasaran suatu produk tertentu sehingga dapat meningkatkan revenue perusahaan.

- Berdasarkan data, dari 12.946 pengguna e-commerce hanya 15.5% yang menghasilkan revenue. Bagaimana cara meningkatkan revenue perusahaan ?


### Goals
- Meningkatkan revenue dari e-commerce tersebut.


### Objectives
- Membuat model prediktif untuk memprediksi pengunjung melakukan transaksi di e-commerce.
- Menganalisis faktor-faktor yang mempengaruhipengunjungmelakukan transaksi

### Business Matrics
-  Revenue Conversion Rate
<br>

---

## 📂 **Stage 1 : Exploratory Data Analysis**
### Dataset
<p align="center">
  Tabel 1 – Informasi Data <br>
</p>

<p align="center">
  <img src="https://github.com/Juliana9417/Final_Project/assets/172182011/ac551e0f-ec91-4a4a-b7f9-7ae2e1e75501" alt="InformasiData">
</p>

### Descriptive Statistics

<p align="center">
  Tabel 2  – Data Deskriptif Numerikal
</p>

<p align="center">
  <img src="https://github.com/Juliana9417/Final_Project/assets/172182011/8ad6a165-887d-40c2-acbe-42c5c2f50042" alt="DataDeskritiveNumerik">
</p>

<br>

<p align="center">
   Tabel 3  – Data Deskriptive Kategori
</p> 

<p align="center">
  <img src="https://github.com/Juliana9417/Final_Project/assets/172182011/be4758d7-f873-4a03-a39d-08743f801e8f" alt="DataDeskritiveKategori">
</p>

<br>

### Insight Data Deskriptif : 

1. Jumlah pengunjung web tertinggi pada bulan Mei
2. Pelanggan mayoritas adalah Returning_Visitor sebanyak 85.5%
3. kunjungan pelanggan mayoritas diluar weekend 
4. Dari 12946 data, sebanyak 10938 atau 85.5% tidak melakukan pembelian sisanya 2008 atau 15.5% yang melakukan pembelian  
5. Sistem operaasi yang banyak digunakan oleh pengunjung yaitu sistem operasi 2
6. Browser yang banyak digunakan oleh pengunjung yaitu browser 2
7. Region pengunjung banyak berasal dari region 1
8. Traffic type pengunjung terbanyak yaitu traffic type 2 <br>
<br>

### Kesimpulan Data Deskriptif :

1. Terdapat beberapa kolom dengan nilai null yang lebih dari 1-2% (Administrative_Duration, ProductRelated_Duration, OperatingSystems) handling missing value, dan yang <2% akan dilakukan drop data (Administrative, Administrative)
Semua kolom numerik skew (dilihat dari perbedaan antara mean > median)
2. Tidak ada kolom kategori yang perlu didrop karena hanya punya 1 nilai unik atau punya nilai unik sebanyak jumlah baris
<br>

### Univariate Analisis : 
<p align="center">
  
![DisplotNumerikal](https://github.com/Juliana9417/Final_Project/assets/172182011/406d8ad1-c3f7-4946-9328-dd0ea767e99e)

  Gambar 1 – Displot Numerikal 
</p>
<br>
### Insight : 
- Semua kolom cenderung berbentuk positive skewed, dan distribusi data mendekati nilai 0.
- Kolom ‘Informational’ dan ExitRates’ berbentuk Multimodal.
- Kolom ‘BounceRates’ berbentuk Bimodal.
<br>

<p align="center">

![ViolinMunerikal](https://github.com/Juliana9417/Final_Project/assets/172182011/0c32e267-eb43-465d-8300-b6f0dd293f81)

  Gambar 2 – Violin Numerikal 
</p>
<br>
### Insight : 
- Distribusi data cenderung menumpuk ekstrim mendekati nilai 0.00 pada kolom : 
- Administrative, Administrative_Duration, Informational, Informational_Duration, ProductRelated, ProductRelated_Duration, BounceRates, dan PageValues.
- Sementara, pada kolom ‘ExitRates’ distribusi data menumpuk di antara 0.00 - 0.05.
<br>


### Multivariate Analisis : 
<p align="center">
  
![MultivariateNumerikal](https://github.com/Juliana9417/Final_Project/assets/172182011/eaf5da5b-d8f9-446f-834e-5431af3d9bec)
 
  Gambar 3 – Multivariate Numerikal 
</p>
<br>
### Insight : 
-Deteksi kemungkinan moderate redundant features (nilai korelasi tinggi >= 0.6).
1. ‘Administrative’ dan ‘Administrative_Duration’
2. ‘Informational’ dan ‘Informational_Duration’

-Deteksi kemungkinan highly redundant features (nilai korelasi tinggi > 0.7).
1. ‘ProductRelated’ dan ‘ProductRelated_Duration’
2. ‘BounceRates’ dan ‘ExitRates’

- Kolom yang berpotensi redundant, kemungkinan akan di hapus salah satu pada tahap Data Processing.
- Korelasi target ‘Revanue' memiliki korelasi positif kuat dengan fitur ‘PageValues’ (0.50).
<br>
<br>
<p align="center">

  ![MultivariateKategorikal](https://github.com/Juliana9417/Final_Project/assets/172182011/3300d7f4-e99b-41e6-a9ab-ee9ef80114c5)

  Gambar 4 – Multivariate Kategorikal
</p>
<br>
### Insight : <br>
- Korelasi yang cukup kuat antar kolom: <br>
1. ‘VisitorType’ dan ‘OperatingSystems’ 
2. ‘VisitorType’ dan ‘Browser’
3. ‘VisitorType’ dan ‘TrafficType’

- Deteksi kemungkinan moderate redundant features (nilai korelasi tinggi >= 0.6) pada ‘OperatingSystems’ dan ‘Browser’
- Fitur-fitur yang lainnya memiliki korelasi yang cukup rendah.
- Korelasi target ‘Revenue’ dangan semua fitur kategorikal memiliki korelasi positive (walaupun sangat lemah), dengan nilai korelasi fitur ‘Month’ paling tinggi (0,18).
<br>

### Bi-Variate Analisis : 

<p align="center">

 ![Visitortype](https://github.com/Juliana9417/Final_Project/assets/172182011/df78f66a-42c2-4141-bb9f-a64523f1fdf5)

  Gambar 5 – Visitor Type Vs Revenue
</p>
<br>
### Insight <br>
- Terdapat tiga jenis visitor : <br>
1. Jumlah "Returning visitor" paling banyak, namun persentase pengunjung yang menghasilkan revenue paling sedikit dibanding dua jenis lainnya.
2. Pengunjung "New Visitor" lebih sedikit daripada "Returning visitor", namun memiliki persentase pendapatan tertinggi dibanding dua jenis lainnya, yaitu 24.65%.
3. Pengunjung "Other" memiliki persentase pendapatan sebesar 17.98%, lebih rendah dari "New Visitor" tetapi lebih tinggi dari "Returning visitor".
<br>
<br>
<p align="center">

  ![Month](https://github.com/Juliana9417/Final_Project/assets/172182011/ee64fe96-e4fd-4879-8238-756c539a5604)

  Gambar 6 – Month Vs Revenue
</p>
<br>
### Insight <br>
1. Bulan November memiliki jumlah revenue tertinggi (803) di antara semua bulan.
2. Bulan-bulan dengan jumlah revenue yang signifikan tinggi lainnya adalah Mei (379) dan Maret (201).
3. Februari memiliki jumlah revenue yang paling rendah (3), menunjukkan bahwa ini adalah bulan dengan performa paling rendah dalam hal pendapatan.
<br>
<br>
<p align="center">

  ![Region](https://github.com/Juliana9417/Final_Project/assets/172182011/74032eb8-7e71-42d1-862e-11f0b3751e2f)

  Gambar 7 – Visitor per Region Vs Revenue
</p>
<br>
### Insight <br>
1. Wilayah 2 memiliki persentase pendapatan tertinggi (16.64%), diikuti oleh Wilayah 9 (16.54%), dan Wilayah 5 (16.32%).
<br>
<br>
<p align="center">

  ![Weekend](https://github.com/Juliana9417/Final_Project/assets/172182011/cdc11647-39c0-4789-8450-7131ec004786)

  Gambar 8 – Weekend Vs Revenue
</p>
<br>
### Insight <br>
1. Persentase pengunjung yang menghasilkan pendapatan lebih tinggi pada akhir pekan (17.50%) dibandingkan dengan hari biasa (14.91%).
2. Grafik menunjukkan meskipun jumlah pengunjung lebih rendah pada akhir pekan, potensi pengunjung melakukan transaksi lebih besar dibandingkan hari biasa.
<br>
<br>
<p align="center">

![ProductRelated](https://github.com/Juliana9417/Final_Project/assets/172182011/c074167e-426a-49b8-b420-bc10f423fb2e)

  Gambar 9 – Product Related, Administrative, Informational Vs Revenue
</p>
<br>
### Insight <br>
1. Interaksi pengunjung dengan halaman terkait produk (Product Related) merupakan faktor paling penting dalam mendorong pembelian.
<br>


---

### Business Recomendation <br>
1. Fokus pada Pengunjung Baru (New Visitor).Meskipun jumlah pengunjung yang kembali (Returning Visitor) mungkin lebih banyak, namun persentase pendapatan yang dihasilkan oleh pengunjung baru (New Visitor) lebih tinggi. Oleh karena itu, proporsi strategi pemasaran dapat dilakukan untuk new visitor lebih besar dibandingkan dengan returning visitor dan tetap memperhatikan pengalaman pengunjung baru untuk meningkatkan konversi.

2. Meningkatkan strategi pemasaran dan promosi selama bulan-bulan dengan performa tinggi seperti November, Mei, dan Maret. Fokus pada memanfaatkan momentum penjualan yang kuat pada bulan-bulan ini dapat membantu meningkatkan pendapatan secara keseluruhan. Sebaliknya, bulan Februari memerlukan evaluasi lebih lanjut untuk memahami faktor-faktor yang mengakibatkan performa pendapatan yang rendah, mungkin dengan memperkuat strategi promosi untuk menggerakkan penjualan di periode ini.

3. Perhatikan Hari Khusus (Special Day). Mkipun mayoritas transaksi terjadi pada hari biasa, penting untuk tetap memperhatikan hari khusus (Special Day), terutama pada bulan Februari dan Mei, di mana ada banyak hari khusus. Ini bisa menjadi peluang untuk menawarkan penawaran khusus atau promosi untuk menarik lebih banyak konversi.

4. Fokus pada Optimalisasi Halaman Terkait Produk. Karena ata-rata pembeli melakukan kunjungan ke halaman terkait produk lebih banyak dibandingkan halaman lainnya, bisnis harus memastikan halaman ini dioptimalkan dengan baik. Hal ini termasuk memastikan kecepatan halaman yang cepat, desain yang menarik, dan informasi yang relevan serta jelas.

5. Eksplorasi Potensi Akhir Pekan (Weekend).Meskipun jumlah pengunjung mungkin lebih rendah pada akhir pekan, namun persentase transaksi ini menghasilkan pendapatan lebih tinggi. Ini menunjukkan bahwa ada potensi yang belum dimanfaatkan pada akhir pekan, dan bisnis dapat mempertimbangkan untuk mengembangkan strategi pemasaran atau promosi khusus untuk menarik lebih banyak konversi selama periode ini.

6. Region 1, 3, dan 2 memiliki jumlah total dan jumlah pendapatan tertinggi. Alokasikan lebih banyak sumber daya seperti kampanye pemasaran, promosi yang dipersonalisasi, dan dukungan pelanggan ke region tersebut untuk memanfaatkan potensi pendapatan yang lebih tinggi.

7. Traffic type 2 memiliki jumlah pengunjung terbanyak tetapi konversinya rendah. erlu mengalokasikan sumberdaya untuk meningkatkan konversi salah satu contohnya seperti promosi/diskon.
