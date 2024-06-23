## Insight

### Insight Data Deskriptif : 

1. Jumlah pengunjung web tertinggi pada bulan Mei
![Pic1](https://github.com/rialdiharry/finprorakamin/assets/172503212/2ad11137-38df-45a7-ab76-ea02bc834f42)

2. Pelanggan mayoritas adalah Returning_Visitor sebanyak 85.5%
![Pic2](https://github.com/rialdiharry/finprorakamin/assets/172503212/8715df5a-732a-4e6c-9493-654daa371fb3)

3. Kunjungan pelanggan mayoritas diluar weekend 
![Pic3](https://github.com/rialdiharry/finprorakamin/assets/172503212/6af68202-3818-4d1e-ab98-000d95c12be8)

4. Dari 12946 data, sebanyak 10938 atau 85.5% tidak melakukan pembelian sisanya 2008 atau 15.5% yang melakukan pembelian  
![Pic4](https://github.com/rialdiharry/finprorakamin/assets/172503212/df997858-005e-4f07-b0f4-66aaa0294ae0)

5. Sistem operasi yang banyak digunakan oleh pengunjung yaitu sistem operasi 2
![Pic5](https://github.com/rialdiharry/finprorakamin/assets/172503212/0a0f9b14-bd37-44e7-8d1d-2716f4f9de61)

6. Browser yang banyak digunakan oleh pengunjung yaitu browser 2
![Pic6](https://github.com/rialdiharry/finprorakamin/assets/172503212/19d8eb66-3a47-46f8-b1f0-b363dcf8897d)

7. Region pengunjung terbanyak berasal dari region 1
![Pic7](https://github.com/rialdiharry/finprorakamin/assets/172503212/f5c62589-8a6a-4ee5-b9a5-c90081b66219)

8. Traffic type pengunjung terbanyak yaitu traffic type 2
![Pic8](https://github.com/rialdiharry/finprorakamin/assets/172503212/2a532da8-2991-4cb0-a4e7-2319af2bb8c6)

### Kesimpulan Data Deskriptif :

1. Terdapat beberapa kolom dengan nilai null yang lebih dari 1-2% (Administrative_Duration, ProductRelated_Duration, OperatingSystems) handling missing value, dan yang <2% akan dilakukan drop data (Administrative, Administrative)
Semua kolom numerik skew (dilihat dari perbedaan antara mean > median)
2. Tidak ada kolom kategori yang perlu didrop karena hanya punya 1 nilai unik atau punya nilai unik sebanyak jumlah baris
3. Terdapat data duplicate sebanyak 711 baris

### Insight Univariate :

1. Distribusi data dari feature-feature numerikal cenderung memiliki oulier (long-tailed) <br>
Outlier yang memiliki nilai yang sangat jauh yaitu : Administrative_Duration, Informational_Duration, ProductRelated, ProductRelated_Duration, PageValues
2. Distrubusi data dari feature numerikal cenderung positif-skewed, dan distribusi data mendekati nolai 0
3. Distribusi data cenderung menumpuk ekstrim di nilai 0, yaitu : administrative, administrative_Duration, Informational, Informational_Duration, productrelated, productrelated_duration, pagevalues
4. Pengunjung web tertinggi pada bulan Mei dan November
5. Operating System yang banyak digunakan oleh pengunjung yaitu OS 2
6. Browser yang banyak digunakan yaitu browser 2
7. Visitor yang berkunjung berasal dari region 1
8. Pengunjung paling banyak datang melalui traffic type 2
9. Mayoritas pengunjung dari kategori returning_visitor
10. Lebih banyak kunjungan di weekdays
11. Pengunjung sebanyak 10398 tidak melakukan pembelian
12. Jumlah kunjungan paling banyak di luar Special Day

### Insight MultiVariate :
- Antar kolom numerikal
1. Terdapat nilai multikolinieritas yang tinggi (> 0.7) antara fitur ExitRates-BounceRates, sehingga dapat di drop salah satunya
2. Terdapat fitur-fitur yang kemungkinan bernilai redundan karena nilai korelasi cukup tinggi seperti administrative - administrative_duration, info-info_duration, productrelate-product_duration, bouncerate-exitrate, sehingga dapat di drop salah satunya
3. Page Values memiliki nilai korelasi tinggi yaitu 0.50 dengan fitur revenue sebagai target

- Antar kolom kategorikal
1. visitor type - operatingsystem, visitor type- browser, visitor type - traffic type memiliki korelasi yang cukup tinggi
2. operatingsystem - browser memiliki korelasi yang tinggi
3. fitur-fitur yang lain memiliki korelasi yang cukup rendah

### Insight Bi-Variate :
- Terdapat tiga jenis visitor :
1. Jumlah "Returning visitor" paling banyak namun persentase pengunjung yang menghasilkan revenue paling sedikit dibanding dari kedua jenis lainnya.
2. Pengunjung "New Visitor" memiliki persentase pendapatan yang lebih tinggi dibandingkan dengan pengunjung kembali, dengan 24.65% dari mereka yang menghasilkan pendapatan.
3. Pengunjung "Other" memiliki persentase pendapatan sebesar 17.98%, lebih rendah dari pengunjung baru tetapi lebih tinggi dari pengunjung kembali.
<br>
- Total Visitor per Month Vs Revenue :
1. Bulan November juga memiliki jumlah pendapatan tertinggi (803) di antara semua bulan.
2. Bulan-bulan dengan jumlah pendapatan yang signifikan lainnya adalah Mei (379) dan Maret (201).
3. Februari memiliki jumlah pendapatan yang paling rendah (3), menunjukkan bahwa ini adalah bulan dengan performa paling rendah dalam hal pendapatan.
<br>
- Visitor per Region Vs Revenue :
1. Wilayah 2 memiliki persentase pendapatan tertinggi (16.64%), diikuti oleh Wilayah 9 (16.54%), dan Wilayah 5 (16.32%)
<br>
- Weekend Vs Revenue
1. Persentase transaksi yang menghasilkan pendapatan lebih tinggi pada akhir pekan (17.50%) dibandingkan dengan hari biasa (14.91%).
2. Ini menunjukkan bahwa meskipun jumlah pengunjung lebih rendah pada akhir pekan, persentase transaksi yang menghasilkan pendapatan lebih tinggi.
<br>
- Special Day Vs Revenue :
1. Mayoritas transaksi (16.54%) terjadi pada hari yang tidak dianggap sebagai Hari Khusus (SpecialDay = 0.0).
<br>
- Traffic Type Vs Revenue 
1. persentage dengan pendapatan yang tertinggi yaitu traffic type 16 (33.3%) dan count Traffic Type terbanyak yaitu Traffic Type 2 (889)
<br>
- Operating Systems Vs Revenue :
1. Mayoritas pengunjung menggunakan operating system 2 dan percentase konversi tertinggi yaitu operating systems 8
<br>
- Browser Vs Revenue : 
1. Pengunjung mayoritas menggunakan browser 2 
<br>
- Special Day per Month :
1. Special Day banyak di bulan February dan May
<br>
- ProductRelated, Administrative, informational Vs Revenue :
1. Interaksi dengan halaman terkait produk (Product Related) merupakan faktor penting dalam mendorong pembelian.

## Bisnis Rekomendasi : 
1. Fokus pada Pengunjung Baru (New Visitor): Meskipun jumlah pengunjung yang kembali (Returning Visitor) mungkin lebih banyak,<br> 
namun persentase pendapatan yang dihasilkan oleh pengunjung baru (New Visitor) lebih tinggi. <br>
Oleh karena itu, proporsi strategi pemasaran dapat dilakukan untuk new visitor lebih besar dibandingkan dengan returning visitor dan tetap memperhatikan pengalaman pengunjung baru untuk meningkatkan konversi.

2. Berdasarkan data pendapatan bulanan, rekomendasi bisnis yang dapat diberikan adalah meningkatkan strategi pemasaran dan promosi selama bulan-bulan dengan performa tinggi seperti November, Mei, dan Maret. Fokus pada memanfaatkan momentum penjualan yang kuat pada bulan-bulan ini dapat membantu meningkatkan pendapatan secara keseluruhan. Sebaliknya, bulan Februari memerlukan evaluasi lebih lanjut untuk memahami faktor-faktor yang mengakibatkan performa pendapatan yang rendah, mungkin dengan memperkuat strategi promosi untuk menggerakkan penjualan di periode ini. 

3. Perhatikan Hari Khusus (Special Day): Meskipun mayoritas transaksi terjadi pada hari biasa, penting untuk tetap memperhatikan hari khusus (Special Day), terutama pada bulan Februari dan Mei, di mana ada banyak hari khusus. Ini bisa menjadi peluang untuk menawarkan penawaran khusus atau promosi untuk menarik lebih banyak konversi.

4. Fokus pada Optimalisasi Halaman Terkait Produk: Karena rata-rata kunjungan halaman terkait produk lebih tinggi untuk pembeli, bisnis harus memastikan halaman ini dioptimalkan dengan baik. Hal ini termasuk memastikan kecepatan halaman yang cepat, desain yang menarik, dan informasi yang relevan serta jelas.

5. Eksplorasi Potensi Akhir Pekan (Weekend): Meskipun jumlah pengunjung mungkin lebih rendah pada akhir pekan, persentase transaksi yang menghasilkan pendapatan lebih tinggi. Ini menunjukkan bahwa ada potensi yang belum dimanfaatkan pada akhir pekan, dan bisnis dapat mempertimbangkan untuk mengembangkan strategi pemasaran atau promosi khusus untuk menarik lebih banyak konversi selama periode ini.

6. Region 1, 3, dan 2 memiliki jumlah total dan jumlah pendapatan tertinggi. Alokasikan lebih banyak sumber daya seperti kampanye pemasaran, promosi yang dipersonalisasi, dan dukungan pelanggan ke region tersebut untuk memanfaatkan potensi pendapatan yang lebih tinggi.

7. Traffic type 2 memiliki jumlah pengunjung terbanyak tetapi konversinya rendah sehingga perlu mengalokasikan sumberdaya untuk meningkatkan konversi salah satu contohnya seperti promosi/diskon.
