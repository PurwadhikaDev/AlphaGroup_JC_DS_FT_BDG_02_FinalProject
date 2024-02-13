# **Business Analytics: Predicting Used Car Price in UK**
Created By : Rafidghadah Damarta dan Zahir Ilham

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

### **Tableau**

[Link Dashboard](https://public.tableau.com/views/FinalProjectAlphaTeam/Dashboard?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link)
