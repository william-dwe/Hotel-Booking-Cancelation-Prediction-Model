# Hotel-Booking-Cancelation-Prediction-Model

## Latar Belakang Permasalahan
<div align="justify">
Sektor pariwisata kian mengalami perkembangan yang pesat seiring dengan majunya globalisasi dan terbangunnya jaringan infrastruktur seperti internet yang menjangkau seluruh kalangan masyarakat di seluruh belahan dunia. Penyebaran informasi melalui internet yang menjadi ciri khas dari era globalisasi juga turut mendukung segala usaha sosialisasi dan word-of-mouth-marketing mengenai tempat-tempat wisata serta pengalaman-pengalaman turis yang menarik, sedemikian rupa sehingga membawa masyarakat global untuk semakin tertarik untuk melakukan travelling.<br/><br/>
Akan tetapi, dibalik semua peluang menjanjikan yang ada, terdapat masalah yang cukup signifikan dalam industri perhotelan, yaitu "pembatalan mendadak". Bahkan, data historis menunjukkan bahwa terdapat sekitar 16,4 cancellations per hari per satu hotel pada rentang waktu Januari hingga Juli tahun 2016 (Freed, 2016). Permasalahan tersebut sangatlah signifikan dan penting mengingat bahwa angka ini diekspektasi untuk terus bertambah dengan semakin maraknya budaya cancel and re-book reservasi hotel. Singkatnya, konsumen tidak ingin menghabiskan lebih banyak uang apabila mereka memiliki kesempatan untuk mengurangi pengeluaran mereka.<br/><br/>

<div align="center">
<img src="https://dynamic-media-cdn.tripadvisor.com/media/photo-o/13/7a/9a/81/kolam-renang.jpg?w=900&h=-1&s=1"
     alt="Visualisasi Hotel, Sumber: tripadvisor.com"/> <br/>
Visualisasi Hotel - Gets Hotel Semarang, Sumber: tripadvisor.com
</div>
<br/>

Dengan mengidentifikasi lebih dini konsumen mana yang berpeluang besar untuk melakukan pembatalan pesanan dan konsumen mana yang berpeluang kecil untuk melakukan pembatalan, dapat dilakukan pengambilan tindakan secara lebih lanjut. Pengambilan tindakan bisa dilakukan berupa pemberian insentif untuk konsumen yang memiliki peluang besar untuk melakukan pembatalan pesanan, khususnya untuk pesanan yang berada di luar busy day. Dengan demikian, alokasi insentif menjadi lebih terfokus dan terpersonalisasi untuk setiap konsumen dan memiliki dampak yang lebih baik secara keuangan bagi perusahaan penyedia hospitality services terkait.<br/><br/>
Keadaan pandemi seperti yang sedang terjadi ketika percobaan ini dibuat (awal tahun 2021), menjadi salah satu faktor yang semakin memperlihatkan pentingnya untuk memperhatikan lebih lanjut mengenai tingkat pembatalan pesanan hotel. Hal tersebut sehubungan dengan hotel dan penyedia hospitality services sejenis harus semakin waspada menghadapi growth rebound yang akan terjadi mulai pada tahun 2022 hingga 2023 (Krishnan, Mann, Seitzman, & Wittkamp, 2020). Apabila perusahaan tidak dapat memprediksikan kemungkinan pembatalan hotel dengan baik, maka besar kemungkinan terjadi penyempitan revenue dan pembengkakan opportunity cost.</div>

## Metodologi Penyelesaian Permasalahan
<div align="justify">
Penelitian pembangunan model prediksi pembatalan pesanan kamar hotel, dilakukan dalam beberapa tahapan. Secara umum, proses penelitian dimulai dari identifikasi data-data apa yang diperlukan beserta asal muasal dari data terkait. Setelahnya dilakukan proses akuisisi data sehingga data bisa digunakan dalam proses pemodelan. Setelah melakukan proses akuisisi, proses dilanjutkan dengan tahapan identifikasi karakteristik data atau biasa disebut juga dengan data exploration.<br/><br/>
Setelah memahami karakteristik dari data, maka penelitian dapat dilanjutkan ke tahapan pre-processing. Pada tahapan data pre-processing, terdapat 5 (lima) sub tahapan yaitu: penanganan missing value, penanganan outlier, pengubahan datatype, penanganan imbalance data dan feature engineering. Setelah menyelesaikan tahapan pre-processing, proses pembangunan model dapat dilanjutkan ke tahapan pemodelan data. Terdapat 5 (lima) sub tahapan pada tahap pemodelan data yang terdiri atas: splitting dataset, testing model, feature selection, hyperparameter tuning dan model stacking. Setelah berhasil melakukan proses pemodelan data, maka dapat ditarik kesimpulan berupa rumusan rekomendasi bagi stakeholder yang sekaligus menutup alur proses penelitian ini.</div>

<div align="center">
<img src="https://github.com/lgamal/Hotel-Booking-Cancelation-Prediction-Model/blob/main/visualisasi%20metode%20penelitian.png"
     alt="Visualisasi Metodologi Penelitian"/> <br/>
Diagram urutan proses pelaksanaan penelitian pembangunan model prediksi pembatalan pesanan hotel
</div>

## Hasil Penelitian
Berikut merupakan hasil-hasil yang diperoleh dari pelaksanaan penelitian pembangunan model prediksi klasifikasi pembatalan pesanan kamar hotel:
#### Kesimpulan
1. Telah berhasil dibangun suatu model prediksi untuk mengklasifikasikan pesanan yang berpeluang untuk dibatalkan dan pesanan yang kurang berpeluang untuk dibatalkan, dengan akurasi 83,56%. Model yang dibangun berbasis pada model random forest dengan pengaturan hyperparameter ‘max_features’ sebesar 10 dan ‘n_estimators’ sebesar 200. Proses pemodelan menggunakan berbagai macam fitur pilihan yang diambil secara langsung maupun fitur yang direkayasa melalui feature engineering. 
2. Telah berhasil diperoleh 4 (empat) faktor-faktor penting yang berperan aktif dalam menentukan keberhasilan suatu pesanan. Keempat faktor tersebut diperoleh berdasarkan feature importance atau rata-rata gini score terbesar yang diperoleh pada proses pemodelan. Keempat fitur tersebut diantaranya: lead time, ADR, arrival date week number, dan deposit type.
#### Saran
1.	Sehubungan dengan lead time, terdapat 3 (tiga) usulan yaitu:<br/>
a.	Memberlakukan sistem maksimal lead time pemesanan<br/>
b.	Memberikan insentif langsung (insentif yang diberikan di awal pemesanan, misal potongan harga) untuk pesanan dengan waktu lead time yang rendah untuk menggeser pola pemesanan dari pemesanan jangka panjang (lead time tinggi) yang besar peluang untuk dibatalkan, menjadi pemesanan jangka pendek (lead time rendah) yang lebih kecil peluang untuk dibatalkannya.<br/>
c.	Memberikan insentif tidak langsung (insentif yang diberikan di akhir proses pemesanan, misal cashback ataupun kupon diskon untuk pemesanan berikutnya) untuk pesanan dengan waktu lead time jangka panjang. <br/>
2.	Sehubungan dengan ADR atau average daily rate, terdapat usulan berupa memberikan insentif untuk pemesanan kamar hotel yang menghasilkan revenue lebih tinggi pada kondisi ADR rendah untuk meningkatkan ADR, serta mengalokasikan biaya insentif untuk meningkatkan aspek pelayanan lain apabila ADR sudah cukup tinggi. Kondisi ADR rendah adalah ketika nilai ADR berada di bawah 50 (lima puluh), sementara kondisi ADR tinggi adalah ketika nilai ADR berada di atas 150 (seratus lima puluh).
3.	Sehubungan dengan arrival date week number, terdapat usulan berupa:
a.	Memperketat proses pemesanan untuk waktu kedatangan yang jatuh di kisaran pertengahan tahun yang berpeluang lebih besar untuk dibatalkan dibandingkan dengan pemesanan untuk awal dan akhir tahun.<br/>
b.	Melonggarkan pemesanan dan mengalokasikan dana insentif pada masa-masa awal dan akhir tahun untuk menarik minat konsumen & meningkatkan revenue.<br/>
4.	Sehubungan dengan deposit type, terdapat usulan berupa:
a.	Memberlakukan sistem non refund untuk pesanan-pesanan yang berkemungkinan besar akan dibatalkan. <br/>
b.	Lebih memfokuskan sistem non refund pada minggu-minggu sibuk dan rawan seperti yang berada pada pertengahan tahun. <br/>
c.	Memberlakukan sistem pembayaran non refund pada beberapa hari sebelum waktu kedatangan untuk mengakomodasi kerugian akibat pembatalan pesanan secara mendadak.<br/>
