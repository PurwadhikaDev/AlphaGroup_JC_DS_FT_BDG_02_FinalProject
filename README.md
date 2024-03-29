# **Business Analytics: Predicting Used Car Price in UK**
Created By : Rafidghadah Damarta dan Zahir Ilham

## **Business Problem Understanding**
### **Context**

Pandemi covid 19 memberikan efek ke berbagai macam bisnis termasuk bisnis jual-beli mobil bekas. Berdasarkan data [Society of Motor Manufacturers and Traders](https://www.smmt.co.uk/category/vehicle-data/used-car-sales-data/), sepanjang tahun 2022 transaksi mobil bekas di Inggris Raya mengalami penurunan. Namun pada tahun 2023 transaksi mobil bekas di Inggris Raya mengalami pemulihan. Hal ini dibuktikan dengan [pertumbuhan transaksi mobil bekas sebesar 4.1% di Q1 tahun 2023](https://www.smmt.co.uk/2023/05/used-car-sales-q1-2023/) dan menjadi awal terbaik semenjak tahun 2020. Pertumbuhan moderate ini terus terjadi hingga Q3 tahun 2023. Walaupun pada Q4 mengalami penurunan sebesar -4.3%, hal ini masih menunjukan bahwa bisnis jual-beli mobil bekas di Inggris Raya sedang mengalami pertumbuhan kembali. 

Webuy Used Cars merupakan perusahaan jual-beli mobil bekas berfokus dalam menjual kendaraan pribadi dengan tipe dan harga yang bermacam-macam. Perusahaan beroperasi dengan cara menyediakan website jual-beli. Penjual dapat membuat iklan untuk mobil yang ingin dijual dan menentukan harganya sesuai keinginan atau mengambil harga rekomendasi yang diberikan Webuy Used Cars. Dari harga jual tersebut, perusahaan akan mengambil komisi sebesar [12% dari harga jual](https://www.hiltoncarsupermarket.co.uk/blog/how-uk-car-dealers-earn-from-selling-new-and-used-cars). Setelah beroperasi di beberapa negara, perusahaan memutuskan untuk melakukan ekspansi ke Inggris Raya.  

Sebagai fasilitator jual-beli mobil bekas, perusahaan ingin menawarkan jasa pembuatan iklan di website yang mereka miliki ke penjual yang kesulitan mendapatkan pembeli namun, menawarkan kepada seluruh penjual mobil bekas dapat menjadi strategi yang tidak efektif karena, hal tersebut dapat memakan banyak waktu dan menurunkan kredibilitas Webuy Used Cars itu sendiri jika mobi tidak kian laku. Oleh karena itu, sebagai pendatang baru di pasar Inggris Raya, mengetahui karakteristik mobil bekas yang ada di pasar Inggris Raya menjadi hal yang penting.

Selain karakteristik mobil, penentuan harga juga menjadi penting. Jika penjual memberikan harga yang lebih mahal dari harga pasar, maka akan menyebabkan mobil sulit terjual. Hal ini juga akan menyebabkan kerugian bagi perushaan, karena pembeli mobil akan beralih ke pesaing lainya. Sementara jika penjual memberikan harga yang lebih murah dari harga pasar, maka akan menyebabkan penjual dan perusahaan tidak mendapatkan keuntungan yang optimal. Oleh karena itu, rekomendasi harga yang sesuai dengan harga pasar menjadi penting.  

### **Problem Statement**

- Siapa stakeholder yang memiliki masalah?
    - Tim riset dan pengembangan Webuy Used Cars
- Masalah yang dihadapi oleh stakeholder tersebut?
    - Kesulitan menentukan karakteristik mobil bekas yang ada di Inggris Raya, membuat tim riset dan pengembangan Webuy Used Cars kesulitan untuk menawarkan penjual membuat iklan di website.
    - Kesulitan menentukan harga mobil bekas yang sesuai dengan harga pasar secara akurat, membuat stakeholder sulit untuk mendapatkan keuntungan yang optimal, dengan harga yang kompetitif.
- Mengapa masalah perlu dipecahkan?
    - Melakukan penawaran jasa pembuatan iklan kepada seluruh penjual mobil bekas dapat memakan banyak waktu dan menurunkan kredibilitas Webuy Used Cars jika mobil tidak kian laku. 
    - Kesalahan dalam penetapan harga dapat menyebabkan mobil bekas yang terlalu mahal yang tidak terjual untuk periode yang lama, menyebabkan tekanan finansial pada pemilik mobil bekas dan perusahaan. Di sisi lain, mobil bekas yang dihargai rendah dapat menyebabkan kehilangan peluang pendapatan, mengakibatkan kerugian finansial bagi perusahaan.

 ### **Goals**

- Apa tujuan dan target dari penyelesaian masalah?
     - Mengembangkan model prediktif dengan metric evaluation MAPE kurang dari 12% untuk memastikan akurasi tinggi dalam memprediksi harga mobil bekas. Hal ini berdasarkan [percobaan lain yang memprediksi harga mobil bekas di India yang berhasil menghasilkan MAPE <12%](https://www.atlantis-press.com/article/125971556.pdf).
    - Identifikasi dan analisis faktor-faktor signifikan yang memengaruhi keputusan pembelian mobil bekas, dengan fokus pada segment harga mobil, sehingga memberikan wawasan yang actionable bagi para stakeholder.
 
  ### **Analytic Approach**

- Apa rancangan solusi yang anda tawarkan untuk menyelesaikan masalah dari stakeholder?
    - Pendekatan analitis dimulai dengan Exploratory Data Analysis (EDA) menyeluruh untuk mendapatkan pemahaman mendalam tentang dataset. Selain itu, penjelasan rinci tentang teknik regresi itu sendiri. Pemodelan juga akan melibatkan validasi silang dan penyesuaian hiperparameter untuk memastikan kekokohan dan generalisasi model.

- Kapan dan bagaimana stakeholder akan memanfaatkan atau menggunakan solusi tersebut?
  - Wawasan yang diperoleh dari analisis ini dapat membantu tim riset dan pengembangan Webuy Used Cars dalam membuat keputusan berbasis data, memfasilitasi transaksi yang lebih terinformasi dan menguntungkan di pasar mobil bekas Inggris Raya.
 
  ### **Metric Evaluation**

Untuk megetahui performa suatu model memprediksi targetnya maka kita membutuhkan metric evaluation dengan mengukur nilai errornya. Pada percobaan ini kita menggunakan beberapa metric evaluation diantaranya:

| Metrics | Explaination |
|--------|-------------------|
| MAPE (Mean Absolute Percentage Error) | - MAPE mengevaluasi kesalahan prediksi sebagai persentase dari nilai sebenarnya. <br> - Kemudahan interpretasi kesalahan sebagai persentase membuatnya lebih intuitif dalam konteks bisnis. <br> - Memfasilitasi perbandingan akurasi antar model atau prediksi pada skala yang berbeda. |

Semakin kecil nilai metric evaluation, maka semakin kecil errornya menunjukkan semakin baik suatu model memprediksi nilai targetnya.

## **Data Understanding**
Dataset source: https://www.kaggle.com/datasets/adityadesai13/used-car-dataset-ford-and-mercedes/data

Terdapat 10 kolom di dalam dataset. Berikut adalah infromasi tiap kolom pada dataset:
| Attribute | Data Type | Description |
| --- | --- | --- |
| Brand | Object | Merek mobil |
| Model | Object | Nama model mobil |
| Year | Integer | Tahun produksi mobil |
| Price | Integer | Harga mobil |
| Transmission | Object | Transmisi mobil |
| Mileage | Integer | Jarak tempuh yang sudah tercapai oleh mobil tersebut |
| Fuel Type | Object | Jenis bahan bakar mobil |
| Tax | Integer | Harga pajak mobil |
| Mpg | Float | Rata-rata jarak yang ditempuh per unit energi yang dikonsumsi mobil tersebut |
| Engine Size | Float | Ukuran mesin dari mobil tersebut |

## **Data Analysis**

Untuk mengetahui karakteristik mobil yang ada di Inggris Raya berdasarkan kategori harga, kami akan mencoba menjawab pertanyaan berikut:

- Kapan tahun produksi mobil yang memiliki jumlah terbanyak pada daftar berdasarkan kategori harga?
- Apa merek mobil yang paling sering muncul pada daftar berdasarkan kategori harga?
- Apa model mobil yang umumnya muncul dalam daftar berdasarkan kategori harga?
- Jenis transmisi mobil mana yang sering muncul dalam daftar berdasarkan kategori harga?
- Jenis bahan bakar mana yang sering muncul dalam daftar berdasarkan kategori harga?
- Berapa tenaga mesin yang sering digunakan mobil dalam daftar berdasarkan kategori harga?
- Berapa rentan nilai efisiensi bahan bakar per mil (Mpg) yang sering muncul dalam daftar berdasarkan kategori harga?

Analisis lengkap terlampir pada notebook

## **Data Preparation**
Tahapan preprocessing yang dilakukan sebelum modeling

    Drop Duplicate
    Remove Whitespace
    Check Outliers
    Check Multicolinearity
    Encoding
    Scaling

## **Conclussion and Recommendation**

### **Conclusion**

**Karakteristik Mobil Berdasarkan Segment Harga:**

1. **Tahun Pembuatan:**
    - Budget: Mobil pada kategori harga ini didominasi oleh mobil produksi tahun 2016 hingga 2017.
    - Standard: Mobil pada kategori harga ini didominasi oleh mobil produksi tahun 2017 hingga 2019.
    - Premium: Mobil pada kategori harga ini didominasi oleh mobil produksi tahun 2019.

2. **Merek Kendaraan:**
    - Budget: Mobil pada kategori harga ini didominasi oleh merek Vauxhall dan Ford, menawarkan mobil yang ekonomis.
    - Standard: Mobil pada kategori harga ini didominasi oleh merek Ford, Volkswagen, dan Vauxhall.
    - Premium: Mobil pada kategori harga ini didominasi oleh merek Mercedes Benz, BMW, dan Audi, menawarkan teknologi canggih, desain mewah, dan performa mesin tinggi.

3. **Model Kendaraan:**
    - Budget: Cocok untuk konsumen yang menginginkan kendaraan dengan tipe bentuk mini hingga small dengan gaya hatchback yang cocok digunakan di perkotaan.
    - Standard: Memiliki variasi yang lebih beragam, cocok untuk kebutuhan konsumen yang lebih bervariasi.
    - Premium: Cocok untuk konsumen yang menginginkan kendaraan dengan teknologi canggih, desain mewah, dan performa mesin tinggi, menawarkan tipe bentuk large hingga executive.

4. **Transmisi:**
    - Budget: Lebih cocok untuk konsumen yang terbiasa dengan transmisi manual, menawarkan harga terjangkau dan kontrol penuh terhadap kinerja mesin.
    - Standard: Menawarkan lebih banyak variasi, mencakup baik transmisi manual maupun otomatis, untuk memenuhi preferensi konsumen yang beragam.
    - Premium: Lebih cocok untuk konsumen yang tidak terbiasa dengan transmisi manual, namun ingin memiliki kontrol ekstra terhadap mesin dengan kenyamanan dari transmisi otomatis atau semi-auto.

5. **Bahan Bakar:**
    - Budget: Mayoritas menggunakan bahan bakar petrol, menawarkan harga terjangkau dan biaya perawatan yang ekonomis.
    - Standard: Lebih banyak variasi termasuk petrol dan diesel, memenuhi kebutuhan konsumen yang beragam.
    - Premium: Mayoritas menggunakan bahan bakar diesel, cocok untuk konsumen yang menginginkan performa tinggi dari mesin.

6. **Tenaga Mesin:**
    - Budget: Cocok untuk konsumen yang menginginkan mobil dengan mesin bertenaga kecil hingga menengah, menawarkan efisiensi bahan bakar yang lebih baik.
    - Standard: Memiliki variasi mesin yang lebih luas, dari kecil hingga besar, untuk memenuhi kebutuhan konsumen yang beragam.
    - Premium: Cocok untuk konsumen yang mengutamakan performa mesin tinggi, dengan mesin menengah hingga besar.

7. **Efisiensi Bahan Bakar:**
    - Budget: Mayoritas kendaraan menawarkan efisiensi bahan bakar baik, cocok untuk konsumen yang mencari kendaraan dengan efisiensi tinggi.
    - Standard: Memberikan efisiensi bahan bakar baik hingga cukup baik, menawarkan berbagai pilihan untuk konsumen.
    - Premium: Menawarkan efisiensi bahan bakar yang lebih rendah, fokus pada performa dan kemewahan.


<br>

**Karakteristik Model Machine Learning yang Diperoleh:**

1. **Metric yang Digunakan**: 
   Penggunaan Mean Absolute Percentage Error (MAPE) memungkinkan interpretasi kesalahan prediksi secara intuitif sebagai persentase, yang lebih mudah dimengerti dalam konteks bisnis.

2. **Model Terbaik dari Cross-Validation**: 
   Model terbaik sebelum penyetelan (tuning) adalah model Random Forest dengan MAPE sebesar **0.074**.

3. **Model Terbaik setelah Penyetelan (Tuning)**: 
   Setelah penyetelan, MAPE berhasil diturunkan menjadi **0.0695**, menunjukkan peningkatan performa sebesar 0.0045 atau 4.5%.

4. **Kualitas Model (R-Squared)** :
   Model mampu menjelaskan sekitar 96.52% variabilitas dalam harga mobil, menunjukkan kecocokan yang baik dalam menjelaskan hubungan antara fitur-fitur input dan harga mobil.

5. **Parameter Terbaik untuk Model Random Forest**:
   - Jumlah Pohon (n_estimators): 76
   - Minimal Sampel untuk Split (min_samples_split): 8
   - Minimal Sampel di Setiap Leaf (min_samples_leaf): 1
   - Jumlah Fitur Maksimum untuk Setiap Split (max_features): 7
   - Kedalaman Maksimum Pohon (max_depth): 20
   - Penggunaan Bootstrap (bootstrap): False

6. **Fitur yang Paling Berpengaruh** dalam Model Random Forest untuk Memprediksi Harga:
   - Engine Size
   - Year
   - Mpg (Miles Per Gallon)
   - Transmission
   - Mileage

7. **Error Residual**: 
    Berikut adalah ringkasan insight mengenai distribusi residual pada harga prediksi:

    a. **Overestimate pada Rentang -40000 hingga -20000:**
    - Terdapat dua data *Overestimate*.
    - Model cenderung overestimate harga mobil Mercedes Benz S Class dengan tahun pembuatan di bawah 2010 karena kurangnya data pada rentang tersebut.
    - Harga actual pada data test underpriced jika dibandingkan harga pasaran pada data train sehingga menyebabkan prediksi *overestimate*.

    b. **Underestimate pada Rentang 20000 hingga 90000:**
    - Terdapat tujuh data dengan persentase ekstrim antara 33.28% hingga 90.33%.
    - Prediksi underestimate pada rentang ini disebabkan oleh kurangnya data mobil pada rentang tersebut dalam data train. Akibatnya, ketika model digunakan untuk memprediksi karakteristik mobil yang sedikit berbeda pada data test, prediksi menjadi tidak akurat. Selain itu, harga aktual pada data test juga cenderung overpriced jika dibandingkan dengan harga pasaran yang ada dalam data train.
    - Harga actual pada data test *Overpriced* dibandingkan dengan harga pasaran pada data train, menyebabkan prediksi underestimate.

8. **Performa Model Berdasarkan Rentang Harga**:
    - Rentang harga kendaraan mempengaruhi tingkat kesalahan prediksi (MAPE), dengan rentang harga di bawah 10.000 menunjukkan MAPE di atas rerata keseluruhan 6.95%, menandakan peningkatan error.
    - Rentang harga 80.000-90.000 menunjukkan MAPE sangat rendah, kurang dari 2%, menunjukkan prediksi yang sangat akurat.
    - Rentang harga 90.000-100.000 menunjukkan peningkatan error yang signifikan dengan MAPE di atas 11%, mengindikasikan prediksi yang kurang akurat.
    - Rentang harga 130.000-140.000 juga menunjukkan MAPE sangat rendah, di bawah 2%, menandakan prediksi yang sangat akurat.

9. **Analisis Performa Model Berdasarkan Rentang Harga**:
    - Error terbesar disebabkan oleh Mercedes Benz S Class Engine Size 4.0 dan Year 2019 dengan error sebesar 26.18%. Model mempelajari cukup baik untuk karakteristik mobil serupa, namun harga yang diberikan pada data test jauh di atas rerata harga mobil serupa sehingga menyebabkan prediksi menjadi *underestimate*.
    - Prediksi untuk rentang harga 0-10.000 cenderung melebihi nilai aktual, karena kurangnya data kendaraan dengan tahun produksi sebelum 2011, yang membuat model sulit untuk menyesuaikan prediksi secara akurat.
    - Rentang harga 80.000-90.000 dan 130.000-140.000 menunjukkan performa prediksi yang sangat baik dengan error yang sangat kecil. Hal ini disebabkan persebaran data harga prediksi pada rentang tersebut sangat sedikit namun memiliki karakteristik yang serupa berdasarkan feature importance seperti `Engine Size`, `Year`, `Mpg`, dan `Transmission`.

10. **Cost Benefit**:
    - Hasil analisis ini dapat dimanfaatkan oleh perusahaan untuk mengurangi biaya dan meminimalkan upaya tenaga kerja yang diperlukan sebagai estimator harga mobil. Sebagai contoh, upah minimum pekerja di Inggris Raya adalah [£2013.44](https://id.tradingeconomics.com/united-kingdom/minimum-wages) per bulan, dengan asumsi bahwa mereka bekerja selama 8 jam setiap hari kerja. Dengan menggunakan model kami untuk memprediksi harga, kita tidak perlu menambah pekerjaan untuk melakukan estimasi harga dan dapat mengurangi biaya sebanyak £2013.44 per bulan.
    - Untuk meningkatkan potensi margin keuntungan hingga 12%, perusahaan dapat menggunakan model prediksi harga mobil yang telah dikembangkan. Sebagai contoh, kami melakukan simulasi prediksi harga mobil dengan spesifikasi sebagai berikut:

        - Merek: Audi
        - Model: A1
        - Tahun: 2019
        - Transmisi: Semi-Auto
        - Jarak Tempuh: 2500 mil
        - Jenis Bahan Bakar: Petrol
        - Pajak: £145
        - Konsumsi BBM: 44.5 mpg
        - Ukuran Mesin: 1.5

      Prediksi harga pasaran untuk mobil ini adalah `£22,510.469`, yang masuk dalam rentang harga `£20,000 - £30,000` dengan error sebesar `6.33%`. Artinya, harga mobil sebenarnya diperkirakan berada di kisaran `£21,079.94 - £23,941.00.`Untuk memperoleh margin
      keuntungan hingga `12%,` perusahaan harus mencari mobil dengan harga awal antara `£18,566.35 - £21,067.28`. Dengan menerapkan model ini, diharapkan perusahaan dapat meningkatkan margin keuntungan hingga yang optimal.

### **Recommendation**

Dataset yang kami miliki merupakan data mobil yang terpampang di iklan. Karena data tidak sepenuhnya mencerminkan preferensi atau minat sebenarnya dari pelanggan. Dalam hal ini, ada beberapa rekomendasi yang dapat kami berikan kepada webuyused car antara lain:

1. **Sumber Data Untuk Analysys:** Selain data iklan, perusahaan sebaiknya juga mengumpulkan dan menganalisis data historis penjualan mobil bekas, survei pelanggan, dan sumber data lainnya. Dengan demikian, akan terbentuk pemahaman yang lebih holistik tentang preferensi dan perilaku pembeli.

2. **Penelitian Pasar yang Komprehensif:** Perlu dilakukan penelitian pasar yang menyeluruh untuk memahami tren dan preferensi konsumen dalam kategori mobil bekas. Ini termasuk analisis kompetitor, survei pelanggan potensial, serta pemahaman mendalam tentang kondisi dan tren pasar yang sedang berlangsung.

3. **Segmentasi Pelanggan yang Lebih Terperinci:** Identifikasi segmen pelanggan yang lebih terperinci berdasarkan preferensi, anggaran, dan kebutuhan mereka. Dengan memahami secara mendalam kebutuhan dan keinginan setiap segmen, perusahaan dapat menyesuaikan strategi pemasaran dan penawaran produk untuk melayani pelanggan dengan lebih baik.

4. **Kemitraan Strategis dengan Dealer:** Pertimbangkan untuk menjalin kemitraan strategis dengan dealer mobil bekas lokal atau platform jual beli mobil terkemuka seperti facebook marketplace. Melalui kemitraan ini, perusahaan dapat memperoleh wawasan langsung dari profesional di lapangan, serta akses ke data penjualan yang lebih akurat dan terkini.

5. **Integrasi Karakteristik Mobil dalam Strategi Penetapan Harga:** Gabungkan analisis data yang mendalam dan segmentasi pelanggan dengan karakteristik mobil yang ditemukan, seperti tahun pembuatan, merek, model, transmisi, bahan bakar, tenaga mesin, dan efisiensi bahan bakar. Dengan demikian, perusahaan dapat menyesuaikan harga mobil secara lebih tepat sesuai dengan nilai tambah yang ditawarkan oleh setiap kendaraan, meningkatkan daya saing dan potensi penjualan mobil bekas.


-----

Berikut adalah rekomendasi untuk meningkatkan kehandalan pemodelan yang telah kami bangun:

1. **Pertimbangkan Fitur Tambahan**: Pertimbangkan untuk menambahkan fitur tambahan yang dapat meningkatkan kinerja model. Seperti kondisi body kendaraan, interior dan mesin.

2. **Eksplorasi Model Alternatif**: Selain Random Forest, kita mengetahui pada tahapan cross validasi diperoleh model lain yang juga stabil yaitu, Catboost. Dengan melakukan tuning model alternatif lainnya diharapkan akan diperoleh model yang lebih handal.

3. **Penanganan Overestimate dan Underestimate**: Perlu dilakukan penyesuaian harga pasaran yang lebih akurat pada data test untuk memastikan bahwa harga aktual mencerminkan nilai pasaran yang sebenarnya. Hal ini akan membantu model dalam membuat prediksi yang lebih akurat dengan meminimalkan perbedaan antara harga aktual dan harga pasaran yang dipelajari oleh model.

4. **Penambahan Data**: Penambahan dataset mobil terutama pada fitur-fitur yang memiliki banyak outliers dapat meningkatkan kinerja model terutama pada features yang paling penting untuk model Random Forest yang telah dibangun. Penambahan data tersebut diharapkan agar model dapat lebih belajar dari data yang sudah ada sebelumnya namun jumlahnya masih sedikit. 

## **Tableau**
[Link Dashboard](https://public.tableau.com/views/FinalProjectAlphaTeam/Dashboard?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link)

## **Best Model**
[Link Model](https://drive.google.com/file/d/1rjNbQ8gpbyaUUaCryF1zU-R7na3C6rnK/view?usp=sharing)
