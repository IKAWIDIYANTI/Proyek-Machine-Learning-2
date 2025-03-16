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

  Untuk mengukur kinerja sistem rekomendasi, digunakan beberapa metrik evaluasi berikut:

- Accuracy: Mengukur seberapa akurat model dalam memprediksi lagu yang sesuai dengan preferensi pengguna.
- Precision: Mengukur seberapa banyak lagu yang direkomendasikan benar-benar relevan dengan preferensi pengguna.
- Recall: Mengukur seberapa banyak lagu yang relevan berhasil ditemukan oleh model dari seluruh lagu yang seharusnya direkomendasikan.
- Loss Function (Binary Crossentropy): Mengukur seberapa baik model dalam memprediksi probabilitas kelas yang benar, terutama dalam mengkategorikan lagu sebagai populer atau tidak populer.

# Data Understanding

Dataset yang digunakan dalam analisis ini merupakan meta-data dari lagu dan artis pada platform Spotify. Dataset ini diperoleh dari Kaggle melalui tautan berikut: 

https://www.kaggle.com/datasets/vatsalmavani/spotify-dataset

Dataset ini berisi informasi tentang lagu, artis, genre, dan berbagai fitur musik yang dapat digunakan untuk berbagai keperluan analisis, termasuk rekomendasi musik dan analisis tren industri musik. Dataset ini berasal dari tahun 2022 dan tidak memiliki lisensi yang diketahui.

# Variabel atau Fitur pada Dataset

Berikut adalah penjelasan mengenai variabel atau fitur yang terdapat dalam dataset:

- valence: Mengukur seberapa positif atau negatif suasana lagu. Nilai mendekati 1 menunjukkan suasana yang positif, sedangkan nilai mendekati 0 menunjukkan suasana yang negatif.
- year: Tahun rilis lagu.
- acousticness: Mengukur seberapa akustik sebuah lagu. Nilai mendekati 1 menunjukkan lagu yang sangat akustik.
- artists: Daftar artis yang terlibat dalam lagu.
- danceability: Mengukur seberapa mudah sebuah lagu dapat digunakan untuk menari. Nilai mendekati 1 menunjukkan lagu yang sangat mudah untuk menari.
- duration_ms: Durasi lagu dalam milidetik.
- energy: Mengukur intensitas dan aktivitas lagu. Nilai mendekati 1 menunjukkan lagu yang sangat energetik.
- explicit: Menunjukkan apakah lagu mengandung lirik eksplisit (1) atau tidak (0).
- id: ID unik untuk setiap lagu.
- instrumentalness: Mengukur seberapa instrumental sebuah lagu. Nilai mendekati 1 menunjukkan lagu yang sangat instrumental.
- key: Key atau nada dasar lagu dalam notasi musik.
- liveness: Mengukur keberadaan penonton dalam rekaman. Nilai mendekati 1 menunjukkan lagu yang direkam langsung.
- loudness: Mengukur kenyaringan lagu dalam desibel (dB).
- mode: Menunjukkan mode lagu, yaitu mayor (1) atau minor (0).
- name: Nama lagu.
- popularity: Popularitas lagu berdasarkan skala 0 hingga 100.
- release_date: Tanggal rilis lagu.
- speechiness: Mengukur keberadaan kata-kata yang diucapkan dalam lagu. Nilai mendekati 1 menunjukkan lagu yang lebih banyak berbicara.
- tempo: Tempo lagu dalam beats per minute (BPM).

# Proses Data Understanding

- Statistik Deskriptif: Dilakukan analisis statistik deskriptif untuk memahami distribusi data, seperti mean, median, standar deviasi, dan range untuk setiap fitur.
- Visualisasi Data: Menggunakan box plot untuk mengidentifikasi outlier dalam fitur seperti duration_ms dan loudness. Box plot membantu dalam memahami sebaran data dan mendeteksi nilai-nilai ekstrem yang mungkin mempengaruhi analisis.
- Pembersihan Outlier: Outlier diidentifikasi menggunakan metode Interquartile Range (IQR) dan dihapus untuk memastikan data lebih representatif. Misalnya, outlier pada fitur duration_ms dihapus untuk memastikan durasi lagu berada dalam rentang yang wajar.

# Penanganan Data Hilang:

Kolom release_date diubah menjadi format datetime, dan nilai yang tidak valid diubah menjadi NaT (Not a Time). Hal ini memastikan konsistensi dalam analisis temporal.

# Transformasi Data:

- Beberapa kolom seperti duration_ms diubah menjadi duration_s (durasi dalam detik) untuk memudahkan interpretasi.
- Nilai popularity dipastikan berada dalam rentang 0 hingga 100 dengan menggunakan metode clipping.

# Analisis Variabel Kategorikal:

Kolom genres yang awalnya berisi list diubah menjadi format yang lebih mudah diolah. Jika list kosong, diisi dengan nilai ['unknown'].

# Insight dari Proses Data Understanding

- Distribusi Data: Sebagian besar fitur seperti acousticness, danceability, dan energy memiliki distribusi yang bervariasi, dengan beberapa fitur seperti loudness menunjukkan adanya outlier yang signifikan.
- Outlier: Outlier pada fitur seperti duration_ms dan loudness menunjukkan adanya lagu dengan durasi sangat panjang atau kenyaringan yang sangat rendah. Pembersihan outlier membantu dalam membuat analisis lebih akurat.
- Popularitas: Popularitas lagu bervariasi dari 0 hingga 100, dengan beberapa lagu memiliki popularitas yang sangat rendah atau sangat tinggi.


# Data Preparation

Data preparation merupakan proses krusial dalam analisis data untuk memastikan kualitas data yang digunakan dalam model atau visualisasi. Berikut adalah tahapan lengkap yang dilakukan dalam proses ini:

1. Membaca Data
- Dataset utama dibaca dari file CSV menggunakan pd.read_csv(), yang meliputi:
- data.csv sebagai dataset utama yang berisi informasi lagu.
- data_by_genres.csv sebagai dataset yang mengelompokkan lagu berdasarkan genre.

2. Menangani Missing Values
- Data yang memiliki nilai kosong dihapus menggunakan data.dropna().
- Penghapusan dilakukan untuk memastikan hanya data yang lengkap yang digunakan dalam analisis.

3. Mengurutkan Data
- Data diurutkan berdasarkan kolom id dalam urutan menaik menggunakan sort_values('id', ascending=True).
- Hal ini dilakukan untuk menjaga struktur data yang lebih terorganisir.

4. Menghapus Duplikasi Data
- Lagu dengan id yang sama dihapus menggunakan fix_songs.drop_duplicates('id').
- Tujuan dari langkah ini adalah memastikan bahwa setiap lagu hanya muncul sekali dalam dataset.

5. Mengganti Nama Genre yang Tidak Konsisten
- Genre yang kurang spesifik atau tidak relevan disesuaikan menggunakan data_by_genres.replace('game', 'electronic').
- Hal ini dilakukan agar penamaan genre dalam dataset lebih konsisten.

6. Membuat DataFrame Baru
- Data yang telah dibersihkan disusun ulang menjadi DataFrame baru yang hanya berisi kolom yang relevan:
    1. id (ID lagu)
    2. song_name (Nama lagu)
    3. artists (Nama artis)
- DataFrame ini dibuat menggunakan pd.DataFrame() dengan memastikan hanya lagu unik yang digunakan.

7. Menggabungkan Data
- Dataset data dan data_by_genres digabungkan berdasarkan kolom id menggunakan pd.merge().
- Penggabungan ini dilakukan untuk mengaitkan informasi lagu dengan informasi genre.

8. Ekstraksi Fitur dengan TF-IDF
- Ekstraksi fitur dengan TF-IDF (Term Frequency-Inverse Document Frequency) dilakukan untuk mengukur pentingnya sebuah kata (dalam hal ini, nama artis) dalam konteks dataset lagu. Proses ini dimulai dengan inisialisasi TfidfVectorizer dan fitting terhadap kolom artists.
- Matriks TF-IDF kemudian dihasilkan dengan mentransformasikan data menggunakan tf.fit_transform(data['artists']).
- Hasil matriks TF-IDF ditampilkan dalam bentuk DataFrame untuk memudahkan interpretasi.


# Modeling

Sistem rekomendasi yang dikembangkan bertujuan untuk memberikan rekomendasi lagu berdasarkan kemiripan artis dan kesamaan fitur teks menggunakan metode berbasis konten (Content-Based Filtering). Dua pendekatan utama yang digunakan adalah rekomendasi berbasis artis dan rekomendasi berbasis kemiripan judul lagu menggunakan TF-IDF dan cosine similarity.

1. Rekomendasi Berdasarkan Artis

Pendekatan ini mengasumsikan bahwa pengguna yang menyukai lagu dari seorang artis tertentu kemungkinan besar juga akan menyukai lagu-lagu lain dari artis yang sama. Model ini bekerja dengan cara:

- Mengidentifikasi artis dari lagu yang diberikan sebagai input.
- Mencari lagu-lagu lain yang dinyanyikan oleh artis yang sama.
- Menyaring lagu agar tidak merekomendasikan lagu yang sama dengan input.
- Menghasilkan Top-N rekomendasi berdasarkan hasil pencarian.
- Berikut adalah hasil rekomendasi untuk lagu Rockin' Chair - Live:



![Screenshot 2025-03-04 020607](https://github.com/user-attachments/assets/4a0a47f8-386d-45c9-ba5b-c47f644f90b6)






- Kelebihan:
1. Mudah diimplementasikan.
2. Memberikan rekomendasi yang cukup relevan jika pengguna ingin menemukan lebih banyak lagu dari artis yang disukai.

- Kekurangan:
1. Tidak dapat merekomendasikan lagu dari artis lain yang memiliki gaya musik serupa.
2. Keterbatasan dalam menangani variasi preferensi pengguna.

2. Rekomendasi Berdasarkan Kemiripan Judul Lagu

Metode ini menggunakan TF-IDF (Term Frequency-Inverse Document Frequency) untuk mengubah teks dari judul lagu dan nama artis menjadi representasi numerik, kemudian menghitung kemiripan antara lagu menggunakan cosine similarity. Cara kerja metode ini:

- Menggabungkan nama lagu dan artis sebagai representasi teks.
- Menggunakan TF-IDF untuk mengubah teks menjadi vektor fitur.
- Menghitung kemiripan kosinus antara lagu yang dicari dengan seluruh lagu dalam dataset.
- Mengurutkan dan memilih Top-N lagu dengan skor kemiripan tertinggi.
- Hasil rekomendasi untuk lagu Song for Zula:




![Screenshot 2025-03-04 020619](https://github.com/user-attachments/assets/21890856-76f9-49e1-bb15-a314dbea219a)





- Kelebihan:
1. Dapat merekomendasikan lagu dari artis yang berbeda tetapi memiliki kesamaan dalam judul lagu.
2. Lebih fleksibel dibandingkan metode berbasis artis karena mempertimbangkan kesamaan teks.

- Kekurangan:
1. Bisa menghasilkan rekomendasi yang tidak sepenuhnya relevan jika hanya berdasarkan kemiripan teks.
2. Tidak memperhitungkan faktor lain seperti genre atau popularitas lagu.

# Evaluation

# Metrik Evaluasi

  Untuk mengukur kinerja sistem rekomendasi, digunakan beberapa metrik evaluasi berikut:

1. Accuracy
- Model dievaluasi berdasarkan akurasi prediksi terhadap data uji. Akurasi mengukur seberapa banyak prediksi yang benar dibandingkan dengan total prediksi yang dibuat.

2. Precision
- Precision digunakan untuk mengukur seberapa banyak item yang direkomendasikan benar-benar relevan. Precision dihitung sebagai rasio antara jumlah prediksi positif yang benar dengan total prediksi positif yang dibuat oleh model.

3. Recall
- Recall mengukur seberapa banyak item yang relevan berhasil ditemukan oleh model dari seluruh item yang seharusnya direkomendasikan.

4. Loss Function (Binary Crossentropy)
- Model menggunakan binary crossentropy sebagai fungsi loss karena sistem rekomendasi ini mengubah nilai popularity menjadi kategori biner (populer atau tidak populer). Loss function ini mengukur seberapa baik model dalam memprediksi probabilitas kelas yang benar.

# Hasil Evaluasi

1. Akurasi Model
- Dari hasil training, akurasi model pada data pelatihan mencapai 80.48%, sedangkan akurasi pada data validasi (test set) adalah 79.67%. Ini menunjukkan bahwa model mampu mengklasifikasikan popularitas lagu dengan cukup baik, meskipun masih ada ruang untuk peningkatan.

2. Precision (Presisi)
- Precision model adalah 0.6076, yang berarti dari semua lagu yang diprediksi populer, sekitar 60.76% benar-benar populer. Nilai ini menunjukkan bahwa model memiliki tingkat kesalahan tertentu dalam mengidentifikasi lagu populer, sehingga masih ada prediksi positif yang salah (false positives).

3. Recall (Daya Ingat/Sensitivitas)
- Recall model adalah 0.6517, yang berarti dari semua lagu yang sebenarnya populer, model berhasil mengidentifikasi 65.17% dengan benar. Ini menunjukkan bahwa model cukup baik dalam menangkap lagu-lagu yang memang populer, meskipun masih ada beberapa lagu populer yang tidak terdeteksi dengan benar (false negatives).

4. Visualisasi Loss
- Training Loss menurun seiring bertambahnya epoch, yang menunjukkan bahwa model semakin baik dalam mempelajari pola dari data pelatihan.
- Validation Loss juga menurun hingga titik tertentu, tetapi kemudian mulai sedikit berfluktuasi, yang bisa menjadi indikasi bahwa model mulai mengalami overfitting setelah beberapa epoch.
- Dari grafik, terlihat bahwa loss cenderung stabil setelah epoch ke-17, menunjukkan bahwa model mencapai titik keseimbangan dalam belajar dari data.





![Screenshot 2025-03-09 013529](https://github.com/user-attachments/assets/35134494-db30-4d4a-b760-00762acd1d25)






![Screenshot 2025-03-09 013536](https://github.com/user-attachments/assets/59f59e6d-478f-4d0f-9890-5f15d83dded0)






![Screenshot 2025-03-09 011856](https://github.com/user-attachments/assets/40cb2f65-cf8a-4a98-bfc1-d14a16d99f6f)







# Dampak Model Terhadap Business Understanding

Model rekomendasi lagu yang dikembangkan bertujuan untuk meningkatkan pengalaman pengguna dengan memberikan rekomendasi lagu yang relevan. Evaluasi dilakukan untuk mengukur sejauh mana model ini menjawab permasalahan bisnis dan mencapai tujuan yang telah ditetapkan.

1. Apakah model telah menjawab setiap problem statement?
- Model yang dikembangkan telah dirancang untuk memberikan rekomendasi lagu berdasarkan beberapa pendekatan, seperti:
- Rekomendasi berdasarkan kesamaan artis
- Rekomendasi berdasarkan kemiripan judul lagu
- Rekomendasi berdasarkan kombinasi judul lagu dan artis
- Dengan pendekatan ini, model telah mampu memberikan rekomendasi yang sesuai dengan preferensi pengguna, menjawab problem statement terkait pencarian lagu yang relevan dan meningkatkan pengalaman mendengarkan musik.

2. Apakah model berhasil mencapai setiap goals yang diharapkan?
- Model telah mencapai tujuan utama, yaitu meningkatkan keterlibatan pengguna dengan menyediakan rekomendasi yang lebih personal dan relevan. Berdasarkan hasil prediksi, model mampu:
- Memberikan rekomendasi yang bervariasi, mencakup berbagai genre dan artis.
- Menghasilkan daftar lagu yang relevan dengan minat pengguna.
- Menunjukkan fleksibilitas dalam metode rekomendasi, baik melalui model embedding maupun pendekatan berbasis TF-IDF dan cosine similarity.
- Namun, terdapat beberapa area yang dapat ditingkatkan, seperti:
    1. Penyesuaian bobot dalam model embedding untuk meningkatkan akurasi prediksi.
    2. Penyempurnaan pre-processing data agar model dapat menangani berbagai format penulisan nama artis dengan lebih baik.

3. Apakah setiap solusi statement yang direncanakan berdampak?
- Model yang dikembangkan telah memberikan dampak positif dalam meningkatkan pengalaman pengguna dengan cara:
- Mempercepat pencarian lagu yang sesuai dengan preferensi pengguna.
- Meningkatkan eksplorasi musik dengan memberikan rekomendasi yang lebih luas dan beragam.
- Mempermudah pengguna dalam menemukan lagu berdasarkan artis yang disukai.
- Namun, terdapat beberapa kendala yang perlu diperhatikan:
  1. Keakuratan rekomendasi masih dapat ditingkatkan dengan mempertimbangkan lebih banyak fitur dalam model.
  2. Model perlu diuji lebih lanjut dengan dataset yang lebih besar untuk memastikan kinerja yang optimal dalam skala yang lebih luas.
