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

2. Precision@K:
- Mengukur proporsi rekomendasi yang diberikan dalam top-K yang relevan dengan preferensi pengguna.
  
3. Recall@K:
- Mengukur sejauh mana sistem mampu merekomendasikan lagu-lagu yang relevan dibandingkan dengan seluruh lagu yang seharusnya direkomendasikan.

4. F1-Score:
- Merupakan harmonic mean dari precision dan recall untuk mengevaluasi keseimbangan antara kedua metrik tersebut.

5. User Satisfaction:
- Mengukur tingkat kepuasan pengguna secara subjektif melalui survei atau feedback langsung.
- Digunakan untuk memahami seberapa baik sistem rekomendasi memenuhi ekspektasi pengguna dalam menemukan lagu-lagu baru yang sesuai dengan preferensi mereka.

# Data Understanding

Dataset yang digunakan dalam analisis ini merupakan meta-data dari lagu dan artis pada platform Spotify. Dataset ini diperoleh dari Kaggle melalui tautan berikut: 

https://www.kaggle.com/datasets/vatsalmavani/spotify-dataset

Dataset ini berisi informasi tentang lagu, artis, genre, dan berbagai fitur musik yang dapat digunakan untuk berbagai keperluan analisis, termasuk rekomendasi musik dan analisis tren industri musik. Dataset ini berasal dari tahun 2022 dan tidak memiliki lisensi yang diketahui.

# Struktur Dataset

  Dataset ini terdiri dari beberapa file dengan cakupan informasi yang berbeda, yaitu:

1. data.csvFile ini berisi informasi tentang lagu, artis, serta berbagai fitur musik yang dapat digunakan untuk rekomendasi berdasarkan kesamaan fitur musik. Informasi yang tersedia dalam file ini mencakup metadata lagu dan atribut musik seperti tempo, energy, danceability, serta acousticness.

2. data_by_artist.csvBerisi data yang telah diagregasi berdasarkan artis. File ini dapat digunakan untuk rekomendasi artis serupa berdasarkan karakteristik musik yang mereka hasilkan.

3. data_by_genres.csvBerisi informasi tentang lagu yang dikelompokkan berdasarkan genre. File ini dapat digunakan untuk analisis tambahan yang berkaitan dengan genre musik, namun tidak digunakan langsung untuk rekomendasi lagu atau artis.

4. data_by_year.csvMenyediakan informasi mengenai tren musik berdasarkan tahun. File ini berguna untuk analisis tren musik dari waktu ke waktu, misalnya untuk melihat perubahan preferensi genre atau evolusi karakteristik musik berdasarkan periode tertentu.

5. data_w_genres.csvFile ini menghubungkan lagu dengan genre spesifik yang dimilikinya. Informasi dalam file ini dapat digunakan untuk eksplorasi lebih lanjut mengenai distribusi genre dalam koleksi lagu.

# Variabel dalam Dataset

  Beberapa variabel utama yang terdapat dalam dataset ini meliputi:

- track_name : Nama lagu.
- artist_name : Nama artis yang membawakan lagu.
- genre : Genre dari lagu.
- year : Tahun rilis lagu.
- tempo : Kecepatan lagu dalam beats per minute (BPM).
- energy : Tingkat energi lagu, dengan nilai antara 0 hingga 1.
- danceability : Indikator seberapa cocok lagu untuk menari, dengan nilai antara 0 hingga 1.
- acousticness : Indikator seberapa akustik lagu tersebut, dengan nilai antara 0 hingga 1.
- popularity : Skor popularitas lagu di Spotify.

# Exploratory Data Analysis

  Untuk memahami lebih lanjut mengenai dataset, beberapa tahapan eksplorasi data dilakukan:

- Struktur Data: Melihat informasi dasar dataset menggunakan data.info() untuk mengetahui jumlah entri, tipe data, dan apakah terdapat nilai yang hilang.
- Jumlah Lagu Unik: Menghitung jumlah lagu unik dalam dataset dengan len(data["id"].unique()).
- Nama Lagu Pertama: Mengambil nama lagu pertama dalam dataset menggunakan data["name"].iloc[0].
- Popularitas Lagu: Mengurutkan lagu berdasarkan tingkat popularitas dan menampilkan lima lagu teratas dengan data[["name", "popularity"]].sort_values(by="popularity", ascending=False).head().
- Informasi Genre: Mengeksplorasi data berdasarkan genre dengan data_by_genres.info(), serta menghitung jumlah genre unik menggunakan len(data_by_genres["genres"].unique()).
- Daftar Genre: Menampilkan sepuluh genre pertama dalam dataset dengan data_by_genres["genres"].unique()[:10].
- Jumlah Artis Unik: Menghitung jumlah artis unik dalam dataset data_by_artist menggunakan len(data_by_artist["artists"].unique()).
- Dimensi Data Artis: Mengecek bentuk dataset artis dengan data_by_artist.shape dan menampilkan lima entri pertama menggunakan data_by_artist.head().
- Deskripsi Data Berdasarkan Tahun: Menggunakan data_by_year.describe() untuk melihat statistik dasar data yang dikelompokkan berdasarkan tahun.
- Jumlah Artis dengan Genre: Menghitung jumlah artis yang memiliki informasi genre dalam dataset data_w_genres menggunakan len(data_w_genres.artists.unique()).
- Jumlah Genre Unik: Menghitung jumlah genre unik dalam dataset data_w_genres dengan len(data_w_genres.genres.unique()).
- Tampilan Data Awal: Menampilkan lima baris pertama dari dataset data_w_genres menggunakan data_w_genres.head().
- Tahapan eksplorasi ini bertujuan untuk memahami karakteristik dataset, menemukan pola awal, serta menentukan langkah selanjutnya dalam analisis yang akan dilakukan.

# Data Preparation

  Data preparation merupakan proses penting dalam analisis data untuk memastikan data yang digunakan dalam model atau visualisasi memiliki kualitas yang baik. Tahapan yang dilakukan dalam proses ini meliputi:

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
  1. id (ID lagu)
  2. song_name (Nama lagu)
  3. artists (Nama artis)
- DataFrame baru dibuat menggunakan pd.DataFrame() dan memastikan hanya lagu unik yang dimasukkan ke dalam dataset yang telah dibersihkan.

12. Menampilkan Data Awal
- Lima baris pertama dari dataset hasil akhir ditampilkan dengan songs_new.head(). Hal ini dilakukan untuk memastikan bahwa proses pembersihan dan pemrosesan data telah berjalan dengan benar sebelum data digunakan lebih lanjut.

# Modeling

  Tahapan ini membahas sistem rekomendasi yang dikembangkan untuk memberikan rekomendasi lagu berdasarkan kesamaan artis dan kesamaan judul lagu menggunakan pendekatan berbasis TF-IDF (Term Frequency-Inverse Document Frequency) serta cosine similarity.

# Rekomendasi Lagu Berdasarkan Kesamaan Artis

Pendekatan pertama yang digunakan adalah merekomendasikan lagu berdasarkan kesamaan artis. Model ini bekerja dengan mencari lagu-lagu yang dinyanyikan oleh artis yang sama dengan lagu target.

- Langkah-langkah Implementasi:
1. Preprocessing Data: Data lagu yang tersedia terdiri dari kolom song_name dan artists, di mana artists berupa daftar nama artis.
2. TF-IDF Vectorization: Menggunakan TfidfVectorizer untuk mengekstrak fitur dari nama artis.
3. Filtering Lagu dengan Artis yang Sama: Jika sebuah lagu dipilih, maka sistem akan mencari lagu lain yang dinyanyikan oleh artis yang sama.
4. Menyaring Lagu yang Sama: Lagu yang sama dengan lagu input akan dihapus dari hasil rekomendasi.
5. Menampilkan Hasil: Sistem menampilkan sejumlah lagu yang dinyanyikan oleh artis yang sama.

- Kelebihan:
1. Sangat efektif untuk memberikan rekomendasi lagu dari artis yang disukai oleh pengguna.
2. Mudah diimplementasikan tanpa memerlukan perhitungan kompleks.

- Kekurangan:
1. Tidak mempertimbangkan kesamaan antar lagu berdasarkan karakteristik lain seperti genre atau lirik.
2. Jika seorang artis hanya memiliki sedikit lagu dalam dataset, rekomendasi yang diberikan akan terbatas.

# Rekomendasi Lagu Berdasarkan Kesamaan Judul

Pendekatan kedua adalah merekomendasikan lagu berdasarkan kesamaan judul lagu menggunakan TF-IDF dan cosine similarity.

- Langkah-langkah Implementasi:
1. Preprocessing Data: Dataset diproses dengan menggabungkan informasi song_name dan artists menjadi satu teks untuk mendapatkan representasi yang lebih baik.
2. TF-IDF Vectorization: TfidfVectorizer digunakan untuk mengonversi teks ke dalam bentuk vektor numerik dengan menghilangkan kata-kata umum (stop words).
3. Menghitung Cosine Similarity: Cosine similarity digunakan untuk mengukur tingkat kemiripan antara lagu yang dipilih dengan lagu-lagu lain berdasarkan representasi TF-IDF.
4. Sorting dan Seleksi Hasil: Lagu-lagu dengan skor kemiripan tertinggi dipilih sebagai rekomendasi.

- Kelebihan:
1. Mampu memberikan rekomendasi berdasarkan kemiripan judul lagu, yang dapat mencerminkan gaya musik atau tema tertentu.
2. Dapat digunakan untuk menemukan lagu dengan nama yang mirip namun dari artis berbeda.

- Kekurangan:
1. Jika nama lagu terlalu umum, hasil rekomendasi mungkin kurang relevan.
2. Tidak mempertimbangkan faktor lain seperti popularitas lagu atau genre.

# Rekomendasi Lagu Berdasarkan Kombinasi Judul dan Artis

Pendekatan terakhir mengombinasikan informasi judul lagu dan nama artis dalam satu representasi teks untuk meningkatkan akurasi rekomendasi.

- Langkah-langkah Implementasi:
1. Menggabungkan Judul dan Artis: Kolom song_name dan artists digabungkan menjadi satu string.
2. TF-IDF Vectorization: TfidfVectorizer diterapkan pada kolom gabungan untuk membangun representasi vektor yang lebih kaya.
3. Cosine Similarity: Digunakan untuk mengukur tingkat kemiripan antara lagu berdasarkan kombinasi judul dan artis.
4. Sorting dan Seleksi Hasil: Lagu dengan skor kemiripan tertinggi ditampilkan sebagai rekomendasi.

- Kelebihan:
- Menghasilkan rekomendasi yang lebih kontekstual dengan mempertimbangkan baik judul maupun artis.
- Lebih fleksibel dibandingkan dengan hanya menggunakan judul atau artis saja.

- Kekurangan:
1. Masih bergantung pada pemrosesan teks, sehingga tidak mempertimbangkan elemen lain seperti tempo atau genre secara langsung.

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


