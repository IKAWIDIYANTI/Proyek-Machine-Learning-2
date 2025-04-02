# Laporan Proyek Machine Learning - Ika Widiyanti

# Project Overview

Spotify merupakan salah satu platform streaming musik terbesar di dunia, dengan jutaan lagu dan pengguna aktif setiap bulannya. Namun, dengan banyaknya pilihan lagu yang tersedia, pengguna sering mengalami kesulitan dalam menemukan lagu baru yang sesuai dengan preferensi mereka. Tantangan ini dapat mengurangi kepuasan pengguna serta menurunkan tingkat keterlibatan mereka dengan platform. Oleh karena itu, diperlukan sebuah sistem rekomendasi musik yang efektif untuk membantu pengguna menemukan lagu-lagu baru yang sesuai dengan selera mereka.

Sistem rekomendasi memiliki peran penting dalam meningkatkan pengalaman pengguna dengan memberikan rekomendasi yang lebih personal. Salah satu pendekatan yang banyak digunakan dalam sistem rekomendasi adalah Content-Based Filtering, yang bekerja dengan menganalisis karakteristik atau atribut suatu item untuk menemukan kesamaan dengan item lain. Dalam konteks musik, fitur-fitur seperti genre, tempo, instrumen, dan lirik dapat digunakan untuk mengukur kemiripan antara lagu-lagu yang ada. Dengan metode ini, pengguna akan mendapatkan rekomendasi lagu berdasarkan preferensi sebelumnya, sehingga meningkatkan relevansi dan kepuasan terhadap rekomendasi yang diberikan.

Teknologi streaming musik telah mengalami perkembangan signifikan dalam beberapa tahun terakhir, mengubah cara individu menikmati dan menemukan musik. Menurut penelitian yang dilakukan oleh Celma (2010), sistem rekomendasi memainkan peran kunci dalam meningkatkan keterlibatan pengguna dengan platform streaming musik, karena memungkinkan penemuan lagu-lagu baru yang relevan dengan preferensi pengguna. Selain itu, metode Content-Based Filtering telah digunakan secara luas dalam berbagai penelitian untuk meningkatkan akurasi rekomendasi (Ricci et al., 2015). Salah satu teknik yang digunakan dalam pendekatan ini adalah TF-IDF (Term Frequency-Inverse Document Frequency), yang berguna dalam mengevaluasi pentingnya suatu kata dalam kumpulan dokumen. Dalam pemrosesan data teks untuk sistem rekomendasi musik, metode ini dapat digunakan untuk menganalisis lirik lagu sehingga sistem dapat memberikan rekomendasi yang lebih akurat.

Keberadaan sistem rekomendasi yang efektif tidak hanya meningkatkan pengalaman pengguna, tetapi juga memberikan manfaat bagi platform streaming musik itu sendiri. Dengan meningkatkan keterlibatan pengguna, sistem ini berkontribusi pada peningkatan waktu yang dihabiskan pengguna di dalam platform serta meningkatkan retensi dan loyalitas pengguna. Oleh karena itu, penelitian dan pengembangan sistem rekomendasi berbasis Content-Based Filtering menjadi hal yang penting untuk memastikan bahwa pengalaman mendengarkan musik menjadi lebih personal dan memuaskan.

Referensi :

https://e-journal.hamzanwadi.ac.id/index.php/edumatic/article/view/2162

https://journal.eng.unila.ac.id/index.php/jitet/article/view/5949/2373

https://santika.upnjatim.ac.id/submissions/index.php/santika/article/view/201/96


# Business Understanding

# Problem Statement

- Pernyataan Masalah 1: Pengguna kesulitan menemukan lagu baru yang memiliki karakteristik musik mirip dengan lagu yang telah mereka dengarkan.
- Pernyataan Masalah 2: Pengguna ingin mendapatkan rekomendasi lagu berdasarkan genre favorit mereka, tetapi rekomendasi yang ada kurang sesuai.
- Pernyataan Masalah 3: Pengguna ingin mendengarkan lagu dari artis yang serupa atau memiliki gaya musik yang mirip dengan artis favorit mereka.
- Pernyataan Masalah 4: Pengguna kesulitan menemukan lagu yang sesuai dengan mood atau emosi yang sedang mereka rasakan.
- Pernyataan Masalah 5: Rekomendasi lagu yang ada kurang akurat karena tidak menggabungkan berbagai fitur musik (seperti tempo, energi, instrumentalness, dll.) secara optimal.
- Pernyataan Masalah 6: Pengguna baru (new users) kesulitan mendapatkan rekomendasi yang relevan karena belum memiliki riwayat mendengarkan lagu (cold start problem).
- Pernyataan Masalah 7: Pengguna ingin mendapatkan rekomendasi lagu yang menggabungkan preferensi artis dan genre secara bersamaan.
- 
# Goals

- Jawaban Pernyataan Masalah 1: Memberikan rekomendasi lagu berdasarkan kesamaan fitur musik (seperti tempo, nada, energi, dll.) dengan lagu yang telah didengarkan pengguna.
- Jawaban Pernyataan Masalah 2: Memberikan rekomendasi lagu berdasarkan genre yang sering didengarkan oleh pengguna.
- Jawaban Pernyataan Masalah 3: Menyajikan lagu dari artis yang serupa atau memiliki gaya musik mirip dengan artis favorit pengguna.
- Jawaban Pernyataan Masalah 4: Mengelompokkan lagu berdasarkan mood atau emosi (seperti senang, sedih, santai) dan memberikan rekomendasi sesuai suasana hati pengguna.
- Jawaban Pernyataan Masalah 5: Menggabungkan berbagai fitur musik (seperti tempo, energi, instrumentalness, dll.) untuk menghasilkan rekomendasi yang lebih akurat dan personal.
- Jawaban Pernyataan Masalah 6: Memberikan rekomendasi awal yang relevan untuk pengguna baru (cold start problem) berdasarkan lagu-lagu populer atau tren terkini.
- Jawaban Pernyataan Masalah 7: Memberikan rekomendasi lagu yang menggabungkan preferensi artis dan genre secara bersamaan untuk memenuhi selera pengguna.
  
# Solution Approach

  Untuk mencapai tujuan tersebut, sistem rekomendasi lagu akan dikembangkan dengan beberapa pendekatan berikut:

1. Content-Based Filtering (Kesamaan Fitur Musik):

- Pendekatan: Menggunakan fitur-fitur musik seperti tempo, nada, energi, dan instrumentalness untuk menemukan lagu-lagu yang mirip dengan lagu favorit pengguna.
- Implementasi: Membangun model yang menganalisis fitur-fitur musik dari lagu yang telah didengarkan pengguna dan mencari lagu-lagu lain dengan fitur yang serupa.
- Keuntungan: Rekomendasi yang dihasilkan sangat personal dan sesuai dengan preferensi musik pengguna.

2. Genre-Based Recommendation:

- Pendekatan: Memberikan rekomendasi berdasarkan genre yang sering didengarkan oleh pengguna.
- Implementasi: Menganalisis riwayat genre yang sering diputar oleh pengguna dan merekomendasikan lagu-lagu dari genre yang sama.
- Keuntungan: Memudahkan pengguna menemukan lagu baru dalam genre favorit mereka.

3. Artist-Based Recommendation:

- Pendekatan: Menyajikan lagu dari artis yang serupa atau memiliki gaya musik mirip dengan artis favorit pengguna.
- Implementasi: Menggunakan data tentang artis favorit pengguna dan mencari artis lain dengan karakteristik musik yang mirip.
- Keuntungan: Memperkenalkan pengguna pada artis baru yang sesuai dengan selera mereka.

4. Mood-Based Recommendation:

- Pendekatan: Mengelompokkan lagu berdasarkan suasana hati dan emosi (seperti senang, sedih, santai) dan memberikan rekomendasi sesuai mood pengguna.
- Implementasi: Menggunakan analisis audio (seperti tempo, energi) dan lirik lagu untuk mengidentifikasi mood, lalu merekomendasikan lagu dengan mood yang sesuai.
- Keuntungan: Meningkatkan engagement pengguna dengan rekomendasi yang sesuai dengan emosi mereka.

5. Hybrid Recommendation (Kombinasi Fitur Musik):

- Pendekatan: Menggabungkan berbagai fitur musik (seperti tempo, energi, instrumentalness, dll.) untuk menghasilkan rekomendasi yang lebih akurat.
- Implementasi: Membangun model yang mempertimbangkan kombinasi fitur musik untuk memberikan rekomendasi yang lebih personal.
- Keuntungan: Rekomendasi yang dihasilkan lebih akurat dan sesuai dengan preferensi pengguna.

6. Cold Start Problem Solution:

- Pendekatan: Memberikan rekomendasi awal untuk pengguna baru berdasarkan lagu-lagu populer atau tren terkini.
- Implementasi: Menggunakan data popularitas lagu dan tren musik untuk memberikan rekomendasi awal yang relevan.
- Keuntungan: Mengatasi masalah cold start dengan memberikan rekomendasi yang masih relevan meskipun pengguna belum memiliki riwayat mendengarkan lagu.

7. Artist and Genre Combination Recommendation:

- Pendekatan: Menggunakan kombinasi artis dan genre untuk menemukan lagu yang sesuai dengan selera pengguna.
- Implementasi: Menganalisis artis dan genre favorit pengguna, lalu mencari lagu-lagu yang menggabungkan kedua elemen tersebut.
- Keuntungan: Memberikan rekomendasi yang lebih spesifik dan sesuai dengan preferensi pengguna.


# Evaluation Metrics

Untuk mengukur kualitas sistem rekomendasi berbasis content-based filtering, digunakan beberapa metrik evaluasi berbasis relevansi, yaitu:

1. Precision@K
  - Precision@K mengukur persentase item rekomendasi yang relevan dari total rekomendasi yang diberikan.
  - Semakin tinggi Precision@K, semakin baik sistem dalam memberikan rekomendasi yang relevan.

2. Recall@K
  - Recall@K mengukur seberapa banyak item relevan yang berhasil direkomendasikan dibandingkan dengan semua item relevan yang tersedia.
  - Jika Recall@K tinggi, artinya model dapat menangkap sebagian besar item yang seharusnya direkomendasikan.

3. Coverage
  - Coverage mengukur seberapa banyak lagu dalam dataset yang mendapatkan rekomendasi.
  - Coverage dihitung sebagai rasio antara jumlah lagu yang berhasil diberikan.
  - Jika coverage tinggi, berarti model dapat memberikan rekomendasi yang lebih luas dan tidak hanya berfokus pada lagu tertentu

# Data Understanding

Dataset yang digunakan dalam analisis ini merupakan meta-data dari lagu dan artis pada platform Spotify. Dataset ini diperoleh dari Kaggle melalui tautan berikut: 

https://www.kaggle.com/datasets/vatsalmavani/spotify-dataset

Dataset ini berisi informasi tentang lagu, artis, genre, dan berbagai fitur musik yang dapat digunakan untuk berbagai keperluan analisis, termasuk rekomendasi musik dan analisis tren industri musik. Dataset ini berasal dari tahun 2022 dan tidak memiliki lisensi yang diketahui.

Terdapat 5 file dataset yang saling terkait:
1. data.csv (Data lagu utama)
2. data_by_artist.csv (Agregasi data per artis)
3. data_by_genres.csv (Agregasi data per genre)
4. data_by_year.csv (Tren musik per tahun)
5. data_w_genres.csv (Mapping artis-genre)

# Dataset Utama: data.csv
   
1. Jumlah Baris & Kolom
  - 170.653 baris (lagu) × 19 kolom
2. Kondisi Data
  - Tidak ada missing values pada kolom asli.
  - release_date: Setelah konversi ke datetime, ditemukan 119.798 entri kosong (70%).

3. Outlier: 







![Screenshot 2025-03-16 233832](https://github.com/user-attachments/assets/462d4d9f-7cab-451b-9773-826ea19296a7)








- Sebaran Data Tidak Normal
  - Box plot menunjukkan distribusi yang sangat tidak simetris, dengan banyak outliers ke arah kanan (nilai duration_ms yang sangat tinggi).
- Outliers yang Signifikan
  - Outliers terlihat sangat banyak dan tersebar jauh dari batas atas, yang menunjukkan adanya nilai ekstrim di dataset.
- Kemungkinan Data Skewed ke Kanan
  - Sebagian besar data tampaknya berada di kisaran nilai kecil, sementara ada beberapa data dengan nilai duration_ms yang jauh lebih besar. Ini mengindikasikan distribusi skewed positif (right-skewed).

4. Pembersihan outlier:







![Screenshot 2025-03-16 233913](https://github.com/user-attachments/assets/9b677b1b-8d4a-475b-91b2-631de24ea44d)








- Distribusi Data Lebih Normal
  - Setelah pembersihan, box plot menunjukkan distribusi yang lebih simetris dibandingkan sebelumnya. Tidak ada outliers ekstrem yang mengganggu.
- Rentang Data Lebih Terkontrol
  - Whisker pada box plot sekarang lebih pendek, yang menunjukkan bahwa semua nilai berada dalam rentang yang wajar tanpa adanya nilai ekstrem.
- Interquartile Range (IQR) Lebih Representatif
  - Kotak (box) dalam box plot kini lebih proporsional dan mencerminkan persebaran mayoritas data dengan lebih baik.
5. Uraian Fitur












![Screenshot 2025-04-02 120016](https://github.com/user-attachments/assets/80673c4b-a02f-4085-82cb-b5c2eebdb0cb)













![Screenshot 2025-04-02 120032](https://github.com/user-attachments/assets/ad2eb635-3adf-483b-900a-acc34eeac6c4)















# Agregasi per Artis: data_by_artist.csv
1. Jumlah Baris & Kolom
  - 28.680 baris (artis) × 15 kolom
2. Kondisi Data
  - Tidak ada missing values.
3. Outlier:








![Screenshot 2025-03-16 234227](https://github.com/user-attachments/assets/7f3fffdf-dc20-45e5-932e-19e46d72e9b0)









- Banyak Outliers di Sisi Kiri (Nilai Negatif Ekstrem)
  - Box plot menunjukkan banyak titik outlier (lingkaran kecil) di sisi kiri, yang berarti ada banyak lagu dengan nilai "loudness" yang sangat rendah.
- Distribusi Cenderung Condong ke Kiri
  - Sebagian besar data berada di rentang antara -30 hingga -25 dB, tetapi masih ada nilai jauh lebih kecil (di bawah -55 dB), yang dianggap sebagai outliers.

4. Pembersihan outlier:








![Screenshot 2025-03-16 234415](https://github.com/user-attachments/assets/ab8a8146-a238-4df3-b2d4-80554aa625ab)









- Outliers Berhasil Dihilangkan
  - Dibandingkan dengan box plot sebelumnya, sekarang tidak ada lagi titik outliers (lingkaran kecil) yang muncul di luar whiskers. Distribusi Loudness Lebih Stabil
  - Data sekarang lebih terkonsentrasi di sekitar rentang -25 dB hingga 0 dB. Median terlihat lebih jelas berada di sekitar -10 dB.
- Rentang Data Lebih Rapi dan Representatif
  - Sebelum pembersihan, ada banyak nilai yang terlalu ekstrem di sisi negatif (di bawah -40 dB).
  - Setelah pembersihan, rentang lebih terkonsentrasi sehingga analisis bisa lebih akurat tanpa dipengaruhi nilai ekstrem.
5. Uraian Fitur
















![Screenshot 2025-04-02 120331](https://github.com/user-attachments/assets/2fa8d74e-b975-4c6f-ae50-00d5564cc22f)


















# Agregasi per Genre: data_by_genres.csv
1. Jumlah Baris & Kolom
  - 2.973 baris (genre) × 14 kolom
2. Kondisi Data
  - Tidak ada missing values.
3. Pembersihan:
  - Genre kosong ([] atau "") diubah menjadi "Unknown".
  - duration_ms dikonversi ke integer.
4. Uraian Fitur
  - Mirip dengan data_by_artist, tetapi diagregasi per genre (bukan per artis).
5. Outlier: Tidak ada outlier yang terdeteksi.









![Screenshot 2025-03-16 234601](https://github.com/user-attachments/assets/c1936d93-fadd-4107-8aec-cc051809b393)











![Screenshot 2025-03-16 234612](https://github.com/user-attachments/assets/cb697832-0769-471e-8521-c5c5f093ac41)












# Tren Tahunan: data_by_year.csv
1. Jumlah Baris & Kolom
  - 100 baris (1921–2020) × 14 kolom
2. Kondisi Data
  - Tidak ada missing values atau outlier.
3. Pembersihan:
  - popularity dikonversi dari float ke integer.
4. Uraian Fitur

    Menunjukkan perubahan karakteristik musik dari tahun ke tahun, seperti:
  - Rata-rata danceability, energy, tempo, dll.
  - Tren popularitas musik per tahun.

Outlier: Tidak ada outlier yang terdeteksi.











![Screenshot 2025-03-16 234747](https://github.com/user-attachments/assets/d3819041-ceb8-44b8-b9ce-59d2e1615e7a)












# Mapping Artis-Genre: data_w_genres.csv
1. Jumlah Baris & Kolom
  - 28.680 baris × 16 kolom
2. Kondisi Data
  - Tidak ada missing values.
3. Pembersihan:
  - genres diubah dari string ke list.
  - duration_ms diubah ke detik (duration_s).
  - popularity dipotong ke 0–100.
4. Outlier: Tidak ada outlier yang terdeteksi.










![Screenshot 2025-03-16 234907](https://github.com/user-attachments/assets/0b2ef1a8-0727-44f7-9354-a1c0e024ef58)











5. Uraian Fitur















![Screenshot 2025-04-02 120820](https://github.com/user-attachments/assets/6f171be0-33e5-404b-84fa-fd3826541a9d)














# Kesimpulan
1. Dataset ini lengkap untuk analisis musik berbasis audio features.
2. Pembersihan dilakukan untuk:
  - Menangani missing values (release_date).
  - Menghilangkan outlier (duration_ms, loudness).
  - Standarisasi format (genres, popularity).
3. Analisis potensial:
  - Tren musik dari waktu ke waktu.
  - Hubungan antara fitur audio dan popularitas.
  - Klasifikasi genre berdasarkan karakteristik lagu.

# Data Preparation

# Teknik Data Preparation yang Dilakukan

1. Penggabungan Data (Merging)

- Proses: Melakukan penggabungan beberapa dataset menggunakan kunci tertentu seperti id dan artists. Dataset yang digabungkan meliputi features_music, cold_start, mood, genres, artists, dan artists_genres.
- Alasan: Penggabungan data diperlukan untuk menyatukan informasi yang tersebar di berbagai dataset sehingga dapat digunakan untuk analisis dan rekomendasi yang lebih komprehensif. Misalnya, menggabungkan fitur musik dengan informasi genre dan artis memungkinkan sistem rekomendasi untuk mempertimbangkan lebih banyak faktor.

2. Pemeriksaan Missing Values

- Proses: Mengecek adanya missing values pada setiap kolom di dataset menggunakan fungsi isnull().sum().
- Alasan: Missing values dapat mengganggu analisis dan menghasilkan rekomendasi yang tidak akurat. Pemeriksaan ini membantu mengidentifikasi kolom yang memerlukan penanganan lebih lanjut, seperti imputasi atau penghapusan.

3. Sorting Data

- Proses: Mengurutkan data berdasarkan kolom tertentu seperti id atau artists menggunakan fungsi sort_values().
- Alasan: Sorting memudahkan dalam melakukan pemeriksaan data, identifikasi duplikat, dan memastikan konsistensi data.

4. Pemeriksaan Duplikat

- Proses: Mengecek adanya data duplikat menggunakan fungsi duplicated().sum().
- Alasan: Data duplikat dapat menyebabkan bias dalam analisis dan rekomendasi. Menghapus atau menggabungkan duplikat diperlukan untuk memastikan kualitas data.

5. Transformasi Data

- Proses: Mengubah format data pada kolom genres dari list menjadi string menggunakan fungsi apply() dan lambda.
- Alasan: Transformasi ini memudahkan dalam pemrosesan dan analisis data, terutama ketika genre perlu dijadikan sebagai fitur dalam model rekomendasi.

6. Pemeriksaan Unique Values

- Proses: Menghitung jumlah nilai unik pada kolom tertentu seperti id menggunakan fungsi len() dan unique().
- Alasan: Memastikan bahwa setiap entri memiliki identifikasi yang unik dan tidak ada duplikasi yang tersembunyi.

7. Pembersihan Data

- Proses: Menghapus atau menangani data yang tidak relevan, seperti genre yang mengandung nilai "unknown".
- Alasan: Data yang tidak relevan dapat mengurangi akurasi model rekomendasi. Pembersihan data memastikan bahwa hanya data yang valid dan relevan yang digunakan.

# Alasan Tahapan Data Preparation
- Konsistensi Data: Memastikan data yang digunakan konsisten dan siap untuk diproses lebih lanjut.
- Kualitas Data: Menghilangkan noise, missing values, dan duplikat yang dapat memengaruhi hasil analisis.
- Integrasi Data: Menggabungkan informasi dari berbagai sumber untuk mendapatkan gambaran yang lebih lengkap.
- Efisiensi Pemrosesan: Transformasi dan pembersihan data memudahkan dalam pembuatan model dan analisis.
- Akurasi Rekomendasi: Data yang bersih dan terstruktur dengan baik akan menghasilkan rekomendasi yang lebih akurat dan relevan.


# Modeling

Pada tahap ini, sistem rekomendasi dibangun dengan menggunakan beberapa pendekatan berbasis algoritma machine learning. Berikut adalah penjelasan mengenai model yang dikembangkan beserta output rekomendasi yang dihasilkan.

1. Rekomendasi Berdasarkan Kesamaan Fitur Musik
   
Pendekatan ini menggunakan algoritma Nearest Neighbors dengan metrik cosine similarity untuk merekomendasikan lagu berdasarkan kemiripan fitur musik seperti acousticness, danceability, energy, dan lainnya.

- Proses:
  - Fitur musik distandardisasi menggunakan StandardScaler untuk memastikan semua fitur memiliki skala yang sama.
  - Model NearestNeighbors dilatih pada data yang telah di-scale untuk mencari lagu-lagu dengan fitur yang paling mirip.
  - Rekomendasi dihasilkan dengan mencari lagu-lagu terdekat berdasarkan kemiripan fitur.

- Output:








![Screenshot 2025-03-17 001118](https://github.com/user-attachments/assets/76daea11-f850-4b89-bf2b-b77d14259489)









- Hasil:










![Screenshot 2025-03-17 001125](https://github.com/user-attachments/assets/03101330-ef32-4aeb-80cf-b1d079094e42)










- Kelebihan:
  - Rekomendasi sangat personal karena didasarkan pada fitur musik yang spesifik.
  - Cocok untuk pengguna yang memiliki preferensi kuat terhadap karakteristik musik tertentu.

- Kekurangan:

  - Membutuhkan data fitur musik yang lengkap dan akurat.
  - Kurang efektif jika fitur musik tidak mencerminkan preferensi pengguna secara holistik.

2. Rekomendasi Berdasarkan Genre
   
Pendekatan ini menggunakan TF-IDF Vectorizer untuk mengubah data genre menjadi representasi numerik, kemudian menghitung kemiripan antar artis menggunakan cosine similarity.

- Proses:
  - Data genre diubah menjadi vektor TF-IDF untuk menangkap pentingnya setiap genre dalam representasi artis.
  - Model NearestNeighbors digunakan untuk mencari artis dengan genre yang paling mirip.
  - Rekomendasi dihasilkan berdasarkan artis-artis dengan genre yang serupa.

Output:









![Screenshot 2025-03-17 001404](https://github.com/user-attachments/assets/13dc95b5-9ccb-4820-a86c-68504f0c7df3)









- Hasil:










![Screenshot 2025-03-17 001410](https://github.com/user-attachments/assets/d2dcb86b-fd26-4873-88cf-c75792e0cb4f)










- Kelebihan:

  - Rekomendasi berdasarkan genre cocok untuk pengguna yang menyukai artis dengan genre tertentu.
  - Mudah diimplementasikan dan tidak memerlukan fitur musik yang kompleks.

- Kekurangan:

  - Kurang personal karena hanya mempertimbangkan genre, bukan karakteristik musik secara keseluruhan.
  - Tidak efektif jika genre yang dimiliki artis terlalu umum atau kurang spesifik.

3. Rekomendasi Berdasarkan Mood atau Emosi
   
Pendekatan ini menggunakan fitur valence dan energy untuk merekomendasikan lagu dengan mood yang serupa.

- Proses:

  - Fitur mood distandardisasi menggunakan StandardScaler.
  - Model NearestNeighbors digunakan untuk mencari lagu dengan mood yang paling mirip berdasarkan valence dan energy.
  - Rekomendasi dihasilkan dengan mencari lagu-lagu terdekat dalam ruang fitur mood.

- Output:









![Screenshot 2025-03-17 001638](https://github.com/user-attachments/assets/6ee51f41-dd0b-4523-87d7-043dcc550128)










- Hasil:











![Screenshot 2025-03-17 001647](https://github.com/user-attachments/assets/71cec673-8d8a-4428-84f4-810d15e71c44)











- Kelebihan:

  - Cocok untuk pengguna yang mencari lagu berdasarkan suasana hati atau emosi.
  - Mudah diinterpretasikan karena hanya menggunakan dua fitur utama (valence dan energy).

- Kekurangan:

  - Terbatas pada dua fitur, sehingga kurang mencerminkan kompleksitas preferensi musik pengguna.
  - Kurang efektif jika preferensi pengguna tidak sepenuhnya bergantung pada mood.

4. Rekomendasi untuk Pengguna Baru (Cold Start Problem)

Pendekatan ini dirancang untuk memberikan rekomendasi awal kepada pengguna baru yang belum memiliki riwayat preferensi.

- Proses:

  - Rekomendasi diberikan berdasarkan popularitas lagu.
  - Lagu-lagu dengan skor popularitas tertinggi direkomendasikan kepada pengguna baru.

- Output:











![Screenshot 2025-03-17 001925](https://github.com/user-attachments/assets/d2958af3-256d-4fdb-915a-1b4616d5e22f)











- Hasil:












![Screenshot 2025-03-17 002007](https://github.com/user-attachments/assets/6fcec955-11fd-4b6c-8853-0aa0619f213a)














- Kelebihan:

  - Solusi sederhana dan efektif untuk masalah cold start.
  - Tidak memerlukan data historis pengguna.

- Kekurangan:

  - Rekomendasi kurang personal karena hanya berdasarkan popularitas.
  - Tidak mempertimbangkan preferensi spesifik pengguna.

5. Rekomendasi Berdasarkan Artis
   
Pendekatan ini menggunakan algoritma Nearest Neighbors dengan metrik cosine similarity untuk merekomendasikan artis-artis yang mirip berdasarkan fitur musik seperti acousticness, danceability, energy, dan valence.

- Proses:

  - Fitur musik distandardisasi menggunakan StandardScaler.
  - Model NearestNeighbors dilatih pada data yang telah di-scale untuk mencari artis-artis dengan fitur musik yang paling mirip.
  - Rekomendasi dihasilkan dengan mencari artis-artis terdekat berdasarkan kemiripan fitur.

- Output:












![Screenshot 2025-03-17 002349](https://github.com/user-attachments/assets/00822ae4-ff94-49f6-9b04-d5e2e30da1ca)














- Hasil:













![Screenshot 2025-03-17 002355](https://github.com/user-attachments/assets/6a824385-fd7f-47a6-9104-7bc0cc1c4870)












- Kelebihan:

  - Rekomendasi sangat personal karena didasarkan pada fitur musik yang spesifik.
  - Cocok untuk pengguna yang memiliki preferensi kuat terhadap karakteristik musik tertentu.

- Kekurangan:

  - Membutuhkan data fitur musik yang lengkap dan akurat.
  - Kurang efektif jika fitur musik tidak mencerminkan preferensi pengguna secara holistik.

6. Rekomendasi Berdasarkan Kombinasi Fitur Musik

Pendekatan ini menggabungkan beberapa fitur musik seperti acousticness, danceability, energy, instrumentalness, liveness, loudness, speechiness, tempo, dan valence untuk merekomendasikan lagu-lagu yang mirip.

- Proses:

  - Fitur musik distandardisasi menggunakan StandardScaler.
  - Model NearestNeighbors dilatih pada data yang telah di-scale untuk mencari lagu-lagu dengan fitur yang paling mirip.
  - Rekomendasi dihasilkan dengan mencari lagu-lagu terdekat berdasarkan kemiripan fitur.

- Output:












![Screenshot 2025-03-17 002557](https://github.com/user-attachments/assets/7310cc2e-e33f-48d3-bd82-b727fb45f400)












- Hasil:











![Screenshot 2025-03-17 002603](https://github.com/user-attachments/assets/7b22a652-dd42-46bc-894c-7a4f648eef9a)














- Kelebihan:

  - Rekomendasi sangat personal karena didasarkan pada kombinasi fitur musik yang kompleks.
  - Cocok untuk pengguna yang memiliki preferensi kuat terhadap karakteristik musik tertentu.

- Kekurangan:

  - Membutuhkan data fitur musik yang lengkap dan akurat.
  - Kurang efektif jika fitur musik tidak mencerminkan preferensi pengguna secara holistik.

7. Rekomendasi Berdasarkan Kombinasi Artis dan Genre

Pendekatan ini menggunakan TF-IDF Vectorizer untuk mengubah data genre menjadi representasi numerik, kemudian menghitung kemiripan antar artis menggunakan cosine similarity.

- Proses:

  - Data genre diubah menjadi vektor TF-IDF untuk menangkap pentingnya setiap genre dalam representasi artis.
  - Model NearestNeighbors digunakan untuk mencari artis dengan genre yang paling mirip.
  - Rekomendasi dihasilkan berdasarkan artis-artis dengan genre yang serupa.

- Output:












![Screenshot 2025-03-17 002754](https://github.com/user-attachments/assets/6ac5193b-5e09-4209-98d8-9678f86632d5)












![Screenshot 2025-03-17 002800](https://github.com/user-attachments/assets/e22057e1-4888-40a8-be1d-6f650cefe407)













- Kelebihan:

  - Rekomendasi berdasarkan genre cocok untuk pengguna yang menyukai artis dengan genre tertentu.
  - Mudah diimplementasikan dan tidak memerlukan fitur musik yang kompleks.

- Kekurangan:

  - Kurang personal karena hanya mempertimbangkan genre, bukan karakteristik musik secara keseluruhan.
  - Tidak efektif jika genre yang dimiliki artis terlalu umum atau kurang spesifik.


# Evaluation

Dalam proyek ini, menggunakan metrik evaluasi presisi (precision) untuk mengukur kualitas rekomendasi yang dihasilkan oleh berbagai sistem yang telah diimplementasikan. Presisi dipilih karena ingin memastikan bahwa rekomendasi yang diberikan benar-benar relevan dengan preferensi pengguna.

# Metrik Evaluasi: Presisi (Precision)
1. Relevansi ditentukan berdasarkan kriteria tertentu, seperti:
  - Kesamaan fitur musik (untuk rekomendasi lagu) → Jika nilai cosine similarity > 0.7, dianggap relevan.
  - Kesamaan genre (untuk rekomendasi artis) → Jika minimal 1 genre sama (untuk evaluasi dasar) atau 2 genre sama (untuk evaluasi berbasis TF-IDF).
  - Kesamaan mood (untuk rekomendasi berdasarkan valence dan energy) → Jika nilai cosine similarity > 0.8.
2. Cold Start menggunakan popularitas lagu sebagai asumsi bahwa lagu populer cenderung relevan bagi pengguna baru.

# Hasil Evaluasi Sistem Rekomendasi

Berikut ringkasan hasil evaluasi dari 7 sistem rekomendasi yang diuji:














![Screenshot 2025-04-02 122050](https://github.com/user-attachments/assets/b49b4fab-8ee8-43f0-bb4e-164f7c62c2e8)
















# Rata-rata Presisi: 0.71
# Analisis Hasil
1. Sistem dengan Presisi Sempurna (1.00):
  - Sistem yang berbasis fitur musik (lagu/artis) dan mood memberikan hasil sangat baik karena menggunakan cosine similarity untuk membandingkan vektor fitur.
  - Cold Start juga dianggap sempurna karena menggunakan data popularitas yang umumnya diterima secara luas.
2. Sistem dengan Presisi Rendah (0.00):
  - Rekomendasi berbasis genre (baik dengan HashingVectorizer maupun TF-IDF) gagal memberikan rekomendasi yang relevan. Hal ini mungkin disebabkan oleh:
    - Representasi genre yang terlalu sparse (banyak artis dengan genre unik).
    - Kriteria relevansi (minimal 1 atau 2 genre sama) mungkin terlalu ketat untuk dataset ini.
3. Rata-rata Presisi (0.71):
  - Secara keseluruhan, sistem bekerja baik untuk rekomendasi berbasis fitur musik, tetapi perlu perbaikan untuk rekomendasi berbasis genre.

# Rekomendasi Perbaikan
1. Untuk Rekomendasi Genre:
  - Gunakan weighted genre similarity (misalnya, genre utama diberi bobot lebih tinggi).
  - Terapkan clustering genre sebelum rekomendasi untuk mengelompokkan artis dengan karakteristik serupa.
2. Untuk Cold Start:
  - Tambahkan filter berdasarkan region atau trending untuk personalisasi awal.
3. Optimasi Threshold:
  - Eksperimen dengan nilai threshold relevansi yang berbeda (misalnya, turunkan untuk genre).

    
# Dampak Model Terhadap Business Understanding

Model rekomendasi lagu yang dikembangkan bertujuan untuk meningkatkan pengalaman pengguna dengan memberikan rekomendasi lagu yang relevan berdasarkan berbagai preferensi dan kebutuhan pengguna. Berikut adalah evaluasi terhadap dampak model dalam menjawab problem statement dan mencapai goals yang telah ditetapkan:

1. Apakah model telah menjawab setiap problem statement?
   
Model yang dikembangkan telah dirancang untuk menjawab setiap permasalahan yang diidentifikasi dalam problem statement. Berikut adalah penjelasannya:

- Pernyataan Masalah 1: Pengguna kesulitan menemukan lagu baru yang memiliki karakteristik musik mirip dengan lagu yang telah mereka dengarkan.
- Jawaban Model: Model menggunakan content-based filtering berdasarkan fitur musik seperti acousticness, danceability, energy, dan lainnya untuk merekomendasikan lagu dengan karakteristik yang mirip. Contohnya, fungsi song_recommendations menggunakan Nearest Neighbors dengan metrik cosine similarity untuk menemukan lagu-lagu serupa.
  
- Pernyataan Masalah 2: Pengguna ingin mendapatkan rekomendasi lagu berdasarkan genre favorit mereka.
- Jawaban Model: Model menggunakan TF-IDF Vectorizer untuk menganalisis genre dan memberikan rekomendasi berdasarkan kemiripan genre. Contohnya, fungsi artist_recommendations merekomendasikan artis dengan genre yang mirip.

- Pernyataan Masalah 3: Pengguna ingin mendengarkan lagu dari artis yang serupa atau memiliki gaya musik yang mirip dengan artis favorit mereka.
- Jawaban Model: Model menggunakan artist-based recommendation dengan menganalisis kemiripan artis berdasarkan fitur musik atau genre. Contohnya, fungsi artist_recommendations memberikan rekomendasi artis dengan gaya musik yang mirip.

- Pernyataan Masalah 4: Pengguna kesulitan menemukan lagu yang sesuai dengan mood atau emosi yang sedang mereka rasakan.
- Jawaban Model: Model menggunakan mood-based recommendation dengan memanfaatkan fitur seperti valence dan energy untuk merekomendasikan lagu yang sesuai dengan suasana hati pengguna. Contohnya, fungsi song_recommendations berdasarkan mood menggunakan fitur valence dan energy.

- Pernyataan Masalah 5: Rekomendasi lagu yang ada kurang akurat karena tidak menggabungkan berbagai fitur musik secara optimal.
- Jawaban Model: Model menggabungkan berbagai fitur musik seperti tempo, loudness, instrumentalness, dan lainnya untuk menghasilkan rekomendasi yang lebih akurat. Contohnya, fungsi song_recommendations menggunakan kombinasi fitur musik untuk meningkatkan kualitas rekomendasi.

- Pernyataan Masalah 6: Pengguna baru (new users) kesulitan mendapatkan rekomendasi yang relevan karena belum memiliki riwayat mendengarkan lagu (cold start problem).
- Jawaban Model: Model mengatasi masalah cold start dengan memberikan rekomendasi berdasarkan lagu-lagu populer atau tren terkini. Contohnya, fungsi recommend_songs_for_new_user memberikan rekomendasi awal berdasarkan popularitas lagu.

- Pernyataan Masalah 7: Pengguna ingin mendapatkan rekomendasi lagu yang menggabungkan preferensi artis dan genre secara bersamaan.
- Jawaban Model: Model menggabungkan preferensi artis dan genre menggunakan hybrid recommendation. Contohnya, fungsi artist_recommendations dan song_recommendations dapat dikombinasikan untuk memberikan rekomendasi yang lebih spesifik.

2. Apakah model berhasil mencapai setiap goals yang diharapkan?
   
Model telah mencapai tujuan utama dengan memberikan rekomendasi yang relevan dan personal. Berikut adalah evaluasi terhadap setiap goal:

- Goal 1: Memberikan rekomendasi lagu berdasarkan kesamaan fitur musik.
- Hasil: Model berhasil merekomendasikan lagu dengan fitur musik yang mirip, seperti yang terlihat pada fungsi song_recommendations yang menggunakan fitur acousticness, danceability, dan lainnya.

- Goal 2: Memberikan rekomendasi lagu berdasarkan genre favorit pengguna.
- Hasil: Model berhasil merekomendasikan lagu berdasarkan genre menggunakan TF-IDF Vectorizer dan cosine similarity, seperti yang terlihat pada fungsi artist_recommendations.

- Goal 3: Menyajikan lagu dari artis yang serupa atau memiliki gaya musik mirip dengan artis favorit pengguna.
- Hasil: Model berhasil merekomendasikan artis dengan gaya musik yang mirip, seperti yang terlihat pada fungsi artist_recommendations.

- Goal 4: Mengelompokkan lagu berdasarkan mood atau emosi dan memberikan rekomendasi sesuai suasana hati pengguna.
- Hasil: Model berhasil merekomendasikan lagu berdasarkan mood menggunakan fitur valence dan energy, seperti yang terlihat pada fungsi song_recommendations untuk mood-based recommendation.

- Goal 5: Menggabungkan berbagai fitur musik untuk menghasilkan rekomendasi yang lebih akurat.
- Hasil: Model berhasil menggabungkan fitur musik seperti tempo, loudness, dan instrumentalness untuk meningkatkan akurasi rekomendasi, seperti yang terlihat pada fungsi song_recommendations.

- Goal 6: Memberikan rekomendasi awal yang relevan untuk pengguna baru (cold start problem).
- Hasil: Model berhasil memberikan rekomendasi awal berdasarkan popularitas lagu, seperti yang terlihat pada fungsi recommend_songs_for_new_user.

- Goal 7: Memberikan rekomendasi lagu yang menggabungkan preferensi artis dan genre secara bersamaan.
- Hasil: Model berhasil menggabungkan preferensi artis dan genre untuk memberikan rekomendasi yang lebih spesifik, seperti yang terlihat pada fungsi artist_recommendations dan song_recommendations.

3. pakah setiap solusi statement yang direncanakan berdampak?
   
Model yang dikembangkan telah memberikan dampak positif dalam meningkatkan pengalaman pengguna. Berikut adalah analisis dampaknya:

- Dampak Positif:

1. Meningkatkan Keterlibatan Pengguna: Rekomendasi yang personal dan relevan membuat pengguna lebih tertarik untuk mengeksplorasi lagu baru.
2. Mempercepat Pencarian Lagu: Pengguna dapat menemukan lagu yang sesuai dengan preferensi mereka lebih cepat.
3. Meningkatkan Eksplorasi Musik: Rekomendasi yang bervariasi memungkinkan pengguna menemukan genre dan artis baru yang sesuai dengan selera mereka.
4. Mengatasi Cold Start Problem: Pengguna baru dapat langsung mendapatkan rekomendasi yang relevan meskipun belum memiliki riwayat mendengarkan lagu.

- Area Perbaikan:

1. Akurasi Rekomendasi: Meskipun model sudah memberikan rekomendasi yang relevan, akurasi dapat ditingkatkan dengan menambahkan lebih banyak fitur atau menggunakan algoritma yang lebih canggih.
2. Penanganan Data: Pre-processing data perlu disempurnakan untuk menangani variasi penulisan nama artis atau genre.
3. Skalabilitas: Model perlu diuji dengan dataset yang lebih besar untuk memastikan kinerja yang optimal dalam skala yang lebih luas.
