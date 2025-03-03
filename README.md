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

- Pernyataan Masalah 1:
  Dalam industri musik digital, pengguna sering mengalami kesulitan dalam menemukan lagu-lagu baru yang sesuai dengan preferensi mereka. Ketidakmampuan sistem untuk menyajikan rekomendasi yang relevan dapat mengurangi kepuasan pengguna dan menghambat eksplorasi musik baru.

- Pernyataan Masalah 2:
  Kurangnya rekomendasi yang dipersonalisasi dapat menyebabkan keterlibatan pengguna terhadap platform musik menurun. Tanpa sistem rekomendasi yang efektif, pengguna mungkin kesulitan menemukan lagu-lagu yang sesuai dengan selera mereka, yang berpotensi mengurangi durasi penggunaan aplikasi.

- Pernyataan Masalah 3:
  Sebagian besar platform musik mengandalkan data eksplisit seperti rating atau likes untuk menghasilkan rekomendasi. Namun, tidak semua pengguna secara aktif memberikan rating atau menandai lagu favorit mereka, sehingga diperlukan metode alternatif untuk menyusun rekomendasi yang akurat tanpa bergantung pada data eksplisit tersebut.

# Goals

- Jawaban Pernyataan Masalah 1:
  Mengembangkan sistem rekomendasi lagu yang dapat secara otomatis menyesuaikan dengan preferensi pengguna, baik berdasarkan artis favorit maupun genre musik yang sering didengarkan.

- Jawaban Pernyataan Masalah 2:
  Meningkatkan engagement pengguna dengan platform musik melalui pengalaman yang lebih personal dan interaktif dalam menemukan lagu-lagu baru yang relevan.

- Jawaban Pernyataan Masalah 3:
  Menerapkan pendekatan berbasis embedding untuk menghasilkan rekomendasi lagu yang relevan meskipun tidak tersedia data rating eksplisit dari pengguna.

# Solution Approach

  Untuk mencapai tujuan tersebut, sistem rekomendasi lagu akan dikembangkan dengan beberapa pendekatan berikut:

1. Rekomendasi Berdasarkan Artis:
- Mengidentifikasi lagu-lagu dari artis yang sama dengan lagu yang sedang didengarkan oleh pengguna.
- Menggunakan informasi artis dari dataset untuk memberikan rekomendasi yang lebih relevan.

2. Rekomendasi Berdasarkan Kesamaan Judul Lagu:
- Menerapkan teknik TF-IDF (Term Frequency-Inverse Document Frequency) untuk mengukur kesamaan antarjudul lagu.
- Menghitung cosine similarity antara judul lagu untuk memberikan rekomendasi yang lebih kontekstual.
  
3. Rekomendasi Berdasarkan Model Embedding:
- Menggunakan model RecommenderNet untuk menghasilkan embedding lagu dan mengidentifikasi keterkaitan antar lagu.
- Menghasilkan daftar 10 lagu teratas yang paling relevan untuk direkomendasikan kepada pengguna berdasarkan pola keterkaitan dalam dataset lagu.

# Evaluation Metrics

  Untuk mengukur kinerja sistem rekomendasi, beberapa metrik evaluasi akan digunakan:

1. Root Mean Squared Error (RMSE):
- Digunakan untuk mengukur sejauh mana prediksi model mendekati rating aktual yang diberikan oleh pengguna.
- Nilai RMSE yang lebih rendah menunjukkan akurasi prediksi yang lebih baik.

# Data Understanding

Dataset yang digunakan dalam analisis ini merupakan meta-data dari lagu dan artis pada platform Spotify. Dataset ini diperoleh dari Kaggle melalui tautan berikut: 

https://www.kaggle.com/datasets/vatsalmavani/spotify-dataset

Dataset ini berisi informasi tentang lagu, artis, genre, dan berbagai fitur musik yang dapat digunakan untuk berbagai keperluan analisis, termasuk rekomendasi musik dan analisis tren industri musik. Dataset ini berasal dari tahun 2022 dan tidak memiliki lisensi yang diketahui.

# Struktur Dataset

Dataset terdiri dari beberapa file, masing-masing berisi jenis informasi yang berbeda:

1. data.csv
- Berisi informasi tingkat lagu, termasuk metadata dan atribut musik seperti tempo, energy, danceability, dan acousticness.
- Berguna untuk rekomendasi lagu berdasarkan kesamaan fitur musik.

2. data_by_artist.csv
- Data yang diagregasi berdasarkan artis.
- Cocok untuk merekomendasikan artis serupa berdasarkan karakteristik musik mereka.

3. data_by_genres.csv
- Berisi data lagu yang dikelompokkan berdasarkan genre.
- Berguna untuk analisis spesifik genre tetapi tidak langsung untuk rekomendasi lagu atau artis.

4. data_by_year.csv
- Menyediakan informasi tentang tren musik berdasarkan tahun.
- Berguna untuk menganalisis perubahan preferensi atau karakteristik musik dari waktu ke waktu.

5. data_w_genres.csv
- Menghubungkan lagu dengan genre spesifik.
- Memungkinkan eksplorasi distribusi genre dalam koleksi lagu.

# Variabel Utama dalam Dataset

Dataset mencakup variabel-variabel utama berikut:

- track_name: Nama lagu.
- artist_name: Nama artis yang membawakan lagu.
- genre: Genre lagu.
- year: Tahun rilis lagu.
- tempo: Kecepatan lagu dalam ketukan per menit (BPM).
- energy: Tingkat energi lagu, berkisar antara 0 hingga 1.
- danceability: Indikator seberapa cocok lagu untuk menari, berkisar antara 0 hingga 1.
- acousticness: Indikator seberapa akustik lagu tersebut, berkisar antara 0 hingga 1.
- popularity: Skor popularitas lagu di Spotify.

# Analisis Dataset

1. data.csv
- Bentuk: 170.653 baris dan 19 kolom.
- Missing Values: Tidak ada missing value yang terdeteksi.
- Duplikat: Tidak ada duplikat yang terdeteksi.
- Outlier: Tidak diperiksa secara eksplisit, tetapi analisis lebih lanjut mungkin diperlukan.
- Insight Utama:
  1. Lagu unik: 170.653.
  2. Lagu paling populer: "Dakiti" dengan skor popularitas 100.
  3. Contoh lagu: "Piano Concerto No. 3 in D Minor, Op. 30: III. Finale. Alla breve".

2. data_by_artist.csv
- Bentuk: 28.680 baris dan 14 kolom.
- Missing Values: Tidak ada missing value yang terdeteksi.
- Duplikat: Tidak ada duplikat yang terdeteksi.
- Insight Utama:
  1. Artis unik: 28.680.

3. data_by_genres.csv
- Bentuk: 2.973 baris dan 14 kolom.
- Missing Values: Tidak ada missing value yang terdeteksi.
- Duplikat: Tidak ada duplikat yang terdeteksi.
- Insight Utama:
  1. Genre unik: 2.973.
  2. Contoh genre: "21st century classical", "432hz", "8-bit".

4. data_by_year.csv
- Bentuk: 100 baris dan 14 kolom.
- Missing Values: Tidak ada missing value yang terdeteksi.
- Duplikat: Tidak ada duplikat yang terdeteksi.
- Insight Utama:
  1. Mencakup 100 tahun tren musik.

5. data_w_genres.csv
- Bentuk: 28.680 baris dan 14 kolom.
- Missing Values: Tidak ada missing value yang terdeteksi.
- Duplikat: Tidak ada duplikat yang terdeteksi.
- Insight Utama:
  1. Artis unik dengan genre: 28.680.
  2. Genre unik: 10.743.

# Analisis Gabungan Dataset

- Total Lagu Unik: 213.048 (berdasarkan ID unik).
- Total Artis/Genre Unik: 65.741.
- Dataset yang Digabungkan: Menggabungkan semua dataset tidak menghasilkan missing value, menunjukkan data yang bersih dan konsisten.

# Deskripsi Fitur

Dataset mencakup fitur-fitur berikut:

1. Fitur Numerik:
- valence, acousticness, danceability, energy, instrumentalness, liveness, loudness, speechiness, tempo, popularity.

2. Fitur Kategorikal:
- track_name, artist_name, genre, id, release_date.

3. Fitur Temporal:
- year.


# Data Preparation

Data preparation merupakan proses krusial dalam analisis data untuk memastikan kualitas data yang digunakan dalam model atau visualisasi. Berikut adalah tahapan lengkap yang dilakukan dalam proses ini:

1. Membaca Data
- Dataset utama dibaca dari file CSV menggunakan pd.read_csv(), yaitu:
- data.csv sebagai dataset utama yang berisi informasi lagu.
- data_by_genres.csv sebagai dataset yang mengelompokkan lagu berdasarkan genre.

2. Pemeriksaan Missing Values
- Pemeriksaan nilai yang hilang dilakukan dengan data.isnull().sum(). Langkah ini penting untuk mengetahui apakah terdapat data yang tidak lengkap, yang dapat memengaruhi analisis.

3. Menghapus Missing Values
- Data yang memiliki nilai kosong dihapus menggunakan data.dropna(). Penghapusan dilakukan untuk memastikan bahwa hanya data yang lengkap yang digunakan dalam analisis.

4. Mengurutkan Data
- Data yang telah dibersihkan kemudian diurutkan berdasarkan kolom id dalam urutan menaik menggunakan sort_values('id', ascending=True). Langkah ini bertujuan untuk memastikan bahwa data memiliki urutan yang terstruktur.

5. Memeriksa Jumlah Lagu Unik
- Jumlah lagu unik dihitung dengan len(fix_songs['id'].unique()). Hal ini dilakukan untuk mengetahui jumlah lagu yang benar-benar berbeda dalam dataset.

6. Menampilkan Daftar Genre Unik
- Seluruh genre unik dalam dataset ditampilkan menggunakan data_by_genres['genres'].unique(). Langkah ini penting untuk memahami variasi genre dalam dataset.

7. Memfilter Lagu Berdasarkan Genre
- Lagu dengan genre tertentu, misalnya pop, difilter menggunakan data_by_genres[data_by_genres['genres'] == 'pop']. Langkah ini memungkinkan analisis lebih lanjut terhadap lagu dalam genre tertentu.

8. Memfilter Lagu Berdasarkan Artis
- Lagu-lagu yang dinyanyikan oleh artis tertentu, seperti Ed Sheeran, diidentifikasi menggunakan fix_songs[fix_songs['artists'].str.contains('Ed Sheeran', na=False)]. Langkah ini bermanfaat untuk melihat distribusi lagu berdasarkan artis tertentu.

9. Mengganti Nama Genre yang Tidak Konsisten
- Beberapa genre yang kurang spesifik atau kurang relevan diperbaiki dengan mengganti genre game menjadi electronic menggunakan data_by_genres.replace('game', 'electronic'). Hal ini dilakukan untuk memastikan konsistensi dalam penamaan genre.

10. Menghapus Duplikasi Data
- Lagu dengan id yang sama dihapus menggunakan fix_songs.drop_duplicates('id'). Tujuannya adalah untuk memastikan bahwa setiap lagu hanya muncul sekali dalam dataset agar tidak terjadi duplikasi dalam analisis.

11. Membuat DataFrame Baru
- Data yang telah dibersihkan disusun ulang menjadi DataFrame baru yang hanya berisi kolom yang relevan:
- id (ID lagu)
- song_name (Nama lagu)
- artists (Nama artis)
- DataFrame baru dibuat menggunakan pd.DataFrame() dan memastikan hanya lagu unik yang dimasukkan ke dalam dataset yang telah dibersihkan.

12. Menampilkan Data Awal
- Lima baris pertama dari dataset hasil akhir ditampilkan dengan songs_new.head(). Hal ini dilakukan untuk memastikan bahwa proses pembersihan dan pemrosesan data telah berjalan dengan benar sebelum data digunakan lebih lanjut.

13. Merge Data
- Dataset data dan data_by_genres digabungkan berdasarkan kolom id menggunakan pd.merge(). Langkah ini dilakukan untuk menggabungkan informasi lagu dengan informasi genre.

14. Ekstraksi Fitur dengan TF-IDF
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

  Model rekomendasi lagu ini dievaluasi menggunakan dua metrik utama, yaitu Binary Crossentropy Loss dan Root Mean Squared Error (RMSE). Kedua metrik ini digunakan untuk mengukur performa model dalam memprediksi relevansi antara pengguna dan lagu yang direkomendasikan.

1. Binary Crossentropy Loss
- Binary Crossentropy (BCE) digunakan sebagai fungsi loss karena sistem rekomendasi ini diformulasikan sebagai masalah klasifikasi biner, di mana model memprediksi probabilitas bahwa pengguna akan menyukai lagu tertentu.
- Semakin rendah nilai loss, semakin baik model dalam memprediksi relevansi lagu.

2. Root Mean Squared Error (RMSE)
- RMSE digunakan untuk mengukur tingkat kesalahan model dalam melakukan prediksi skor rekomendasi.
- Semakin rendah nilai loss, semakin baik model dalam memprediksi relevansi lagu.
- RMSE memberikan gambaran seberapa jauh prediksi model dari nilai sebenarnya. Nilai yang lebih rendah menunjukkan performa model yang lebih baik.

# Hasil Evaluasi
- Model dilatih selama 100 epoch menggunakan Adam Optimizer dengan learning rate sebesar 0.001. Performa model selama pelatihan dianalisis melalui kurva metrik RMSE pada data pelatihan dan validasi.
- Binary Crossentropy Loss selama pelatihan menunjukkan tren penurunan, yang mengindikasikan bahwa model mampu mempelajari pola preferensi pengguna terhadap lagu dengan baik.
- RMSE juga menunjukkan tren penurunan, yang berarti prediksi model semakin akurat seiring bertambahnya epoch.
- Pada akhir pelatihan, RMSE pada data validasi relatif stabil dan tidak mengalami peningkatan signifikan, menandakan bahwa model tidak mengalami overfitting.
- Visualisasi hasil pelatihan ditampilkan melalui grafik RMSE terhadap epoch, yang menunjukkan perbedaan performa model pada data pelatihan dan validasi. Kurva yang stabil dan menurun menandakan bahwa model telah mencapai konvergensi.



![Screenshot 2025-03-03 170745](https://github.com/user-attachments/assets/e38b06b8-a27b-4f72-a0ed-c8086e3bcb95)





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
