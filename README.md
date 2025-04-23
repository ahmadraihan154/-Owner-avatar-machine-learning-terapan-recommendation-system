<p align="right" style="font-size: 12px;">
<i>Disclaimer: Referensi yang digunakan dapat dilihat pada bagian paling bawah tulisan. Setiap tulisan berwarna <span style="color:blue;">biru</span> merupakan tautan yang dapat diklik menuju sumber aslinya.</i>
</p>

# Nama : Ahmad Raihan
# Project : Recommendation System - Sistem Rekomendasi Film

# 1. Project Overview
## Latar Belakang
![10-Rekomendasi-Film-Teknologi-dan-Artificial-Intelligence-yang-Seru-dan-Keren](https://github.com/user-attachments/assets/e1350004-1a98-4b60-9569-c04d77a2c99b)

Perkembangan industri perfilman di dunia sangat pesat, ditandai dengan meningkatnya jumlah film yang dirilis setiap tahunnya. Platform seperti IMDb telah lama digunakan untuk menyajikan informasi serta menjadi tempat berbagi opini antar penikmat film di seluruh dunia. Tanggapan dan ulasan dari pengguna di IMDb seringkali dijadikan tolak ukur kesuksesan sebuah film [[1](https://doi.org/10.52362/jmijayakarta.v2i3.868)].

Namun, seiring dengan banyaknya judul film yang tersedia, penonton kerap kali mengalami kesulitan dalam memilih film yang ingin mereka tonton. Meskipun IMDb telah menyediakan klasifikasi berdasarkan genre, klasifikasi ini masih terlalu umum dan belum mampu mencerminkan preferensi personal pengguna secara spesifik. Misalnya, penonton yang menyukai film bergenre komedi dengan sedikit sentuhan romansa tentu akan memiliki preferensi yang berbeda dengan penonton yang menyukai komedi dengan unsur aksi. Hal ini menunjukkan perlunya sebuah sistem yang mampu memberikan rekomendasi film secara lebih personal dan relevan. Sistem rekomendasi film merupakan salah satu penerapan *machine learning* yang bertujuan membantu platform layanan streaming digital dalam memberikan informasi kepada pengguna terkait film-film dengan rating terbaik, serta menyarankan film favorit berdasarkan preferensi dan perilaku pengguna [[2](https://doi.org/10.54082/jiki.104)].

Berdasarkan latar belakang tersebut, penulis memilih topik ini sebagai studi kasus dalam proyek *machine learning* yang sedang dikembangkan. Diharapkan model ini nantinya dapat berguna dalam memberikan rekomendasi film kepada pengguna secara lebih akurat dan sesuai dengan kebutuhan masing-masing.

# 2. Business Understanding
![1_nYVObp29l1_9hPNJKhQvGA-1](https://github.com/user-attachments/assets/bc3fc484-02be-40d6-8f9a-570f3d4d9fac)

Sistem rekomendasi film memiliki peran penting dalam meningkatkan kenyamanan pengguna saat mencari film yang sesuai dengan selera mereka. Dari sisi bisnis, memahami kebutuhan pengguna secara mendalam serta bagaimana sistem dapat memberikan solusi yang tepat menjadi faktor krusial. Seiring dengan meningkatnya jumlah konten film yang tersedia di berbagai platform streaming, banyak pengguna merasa kewalahan saat harus menentukan film mana yang ingin mereka tonton. Kondisi ini mempertegas pentingnya kehadiran sistem rekomendasi yang andal untuk menyaring dan menyarankan film berdasarkan preferensi personal pengguna.
## 2.1 Problem Statement
Berdasarkan latar belakang di atas, proyek ini bertujuan untuk menjawab beberapa permasalahan utama terkait sistem rekomendasi film:
1. **Bagaimana cara melakukan proses pengolahan data yang optimal agar dapat digunakan dalam pembangunan sistem rekomendasi film yang efektif?**
2. **Bagaimana cara membangun sistem rekomendasi dengan melihat kemiripan dari film-film yang telah disukai oleh pengguna sebelumnya?**  
3. **Bagaimana cara membangun sistem rekomendasi dengan melihat preferensi antar pengguna?**  
  
## 2.2 Goal
Tujuan dari proyek ini adalah:
1. **Mengolah dan menyiapkan data secara efisien agar dapat dimanfaatkan dalam pembangunan sistem rekomendasi film.**
2. **Mengembangkan sistem rekomendasi yang mampu menyarankan film dengan karakteristik serupa dari film-film yang telah disukai pengguna.**
3. **Membangun sistem rekomendasi yang mampu mengenali preferensi pengguna lain yang memiliki kesamaan minat, untuk memberikan saran film yang relevan.**

## 2.3 Solution Statement
Dalam proyek ini, untuk menjawab permasalahan yang telah diidentifikasi sebelumnya, digunakan pendekatan analisis data dan metode sistem rekomendasi sebagai berikut:

1. Menerapkan teknik *Exploratory Data Analysis (EDA)* dan *Data Preparation* untuk memahami struktur data dan melakukan pembersihan, transformasi, serta seleksi data yang relevan.
   
2. Menggunakan pendekatan *Content-Based Filtering* untuk merekomendasikan film berdasarkan kemiripan karakteristik film dengan film-film yang sebelumnya disukai oleh pengguna. 

3. Menerapkan pendekatan *Model-Based Collaborative Filtering* berbasis deep learning untuk memberikan rekomendasi film berdasarkan pola kesamaan antar pengguna.

Ketiga pendekatan ini diintegrasikan untuk membangun sistem rekomendasi film yang tidak hanya responsif terhadap kebutuhan pengguna, tetapi juga mampu beradaptasi terhadap perubahan perilaku dan selera pengguna dari waktu ke waktu.

# 3. Data Understanding
## 3.1 Informasi Dataset

Dataset yang digunakan dalam proyek ini adalah **The Movies Dataset**. Informasi detail mengenai dataset dapat dilihat pada tabel berikut:

| Jenis                  | Keterangan                             |
|------------------------|-----------------------------------------|
| **Sumber**             | Dataset: Kaggle                         |
| **Dataset Owner**      | Rounak Banik                            |
| **Lisensi**            | CC0: Public Domain                      |
| **Kategori**           | Movies & TV Shows                       |
| **Usability**          | 8.24                                    |
| **Jenis dan Ukuran Berkas** | ZIP Version 7 (943.76 MB)         |
| **Jumlah File Dataset**| 7 File (CSV)                            |

Berikut ini adalah daftar file CSV yang terdapat dalam *The Movies Dataset* beserta penjelasannya:

| Nama File              | Deskripsi                                                                 |
|------------------------|---------------------------------------------------------------------------|
| **ratings.csv**        | Berisi data penilaian (rating) pengguna terhadap berbagai film.           |
| **ratings_small.csv**  | Versi kecil dari `ratings.csv`, cocok untuk eksplorasi awal dan uji coba. |
| **movies_metadata.csv**| Informasi metadata dari film, seperti judul, tanggal rilis, genre, dll.   |
| **credits.csv**        | Informasi mengenai pemain dan kru produksi film.                          |
| **keywords.csv**       | Berisi daftar kata kunci terkait dengan film (tags, topik).               |
| **links.csv**          | Menghubungkan ID film pada dataset ini dengan ID dari platform lain seperti IMDb dan TMDb. |
| **links_small.csv**    | Versi kecil dari `links.csv` untuk keperluan testing.                     |

Selanjutnya pada tahap ini dataset diatas akan disimpan pada variabel menggunakan fungsi pandas.read_csv. Hasilnya dapat ditampilkan pada gambar berikut:

![image](https://github.com/user-attachments/assets/1ae17a58-8133-423c-8cb2-ff54aa10fa79)

Berdasarka gambar diatas, terdapat 45.436 data film dari `movies_metadata.csv`, dengan total 26.024.289 data rating dari 270.896 pengguna, dan sebanyak 45.115 film memiliki rating dari `ratings.csv`. Untuk keperluan eksplorasi awal, tersedia juga `ratings_small.csv` yang berisi 100.004 rating dari 671 pengguna terhadap 9.066 film. File `links.csv` dan `links_small.csv` menghubungkan ID film ke basis data eksternal seperti IMDb dan TMDb, masing-masing berisi 45.843 dan 9.125 data. Sementara itu, `credits.csv` memuat 45.476 informasi terkait pemain dan kru film, dan `keywords.csv` berisi 46.419 data kata kunci yang menggambarkan tema atau topik film.

Pada pengerjaan proyek ini, hanya menggunakan 2 file csv yaitu **ratings_small.csv (variabel ratings) dan movies_metadata.csv (variabel movies).**

## 3.2 EDA - Deskripsi Variabel

Gambaran dari data movies dapat dilihat pada tabel dibawah :

| adult | belongs_to_collection                                | budget    | genres                                                   | homepage                               | id   | imdb_id   | original_language | original_title             | overview                                                                 | release_date | revenue      | runtime | spoken_languages                                | status    | tagline                                          | title                      | video | vote_average | vote_count |
|-------|------------------------------------------------------|-----------|-----------------------------------------------------------|----------------------------------------|------|-----------|-------------------|-----------------------------|---------------------------------------------------------------------------|--------------|--------------|---------|--------------------------------------------------|-----------|--------------------------------------------------|-----------------------------|--------|---------------|-------------|
| False | {'id': 10194, 'name': 'Toy Story Collection'}        | 30000000  | [{'id': 16, 'name': 'Animation'}, {'id': 35, 'name': ... | http://toystory.disney.com/toy-story  | 862  | tt0114709 | en                | Toy Story                  | Led by Woody, Andy's toys live happily in his room until...             | 1995-10-30   | 373554033.0  | 81.0    | [{'iso_639_1': 'en', 'name': 'English'}]         | Released  | NaN                                              | Toy Story                  | False  | 7.7           | 5415.0      |
| False | NaN                                                  | 65000000  | [{'id': 12, 'name': 'Adventure'}, {'id': 14, 'name': ... | NaN                                    | 8844 | tt0113497 | en                | Jumanji                    | When siblings Judy and Peter discover an enchanted board game...        | 1995-12-15   | 262797249.0  | 104.0   | [{'iso_639_1': 'en', 'name': 'English'}, ...     | Released  | Roll the dice and unleash the excitement!         | Jumanji                    | False  | 6.9           | 2413.0      |

| No. | Kolom                  | Non-Null Count | Tipe Data |
|-----|------------------------|----------------|-----------|
| 0   | adult                  | 45466          | object    |
| 1   | belongs_to_collection  | 4494           | object    |
| 2   | budget                 | 45466          | object    |
| 3   | genres                 | 45466          | object    |
| 4   | homepage               | 7782           | object    |
| 5   | id                     | 45466          | object    |
| 6   | imdb_id                | 45449          | object    |
| 7   | original_language      | 45455          | object    |
| 8   | original_title         | 45466          | object    |
| 9   | overview               | 44512          | object    |
| 10  | popularity             | 45461          | object    |
| 11  | poster_path            | 45080          | object    |
| 12  | production_companies   | 45463          | object    |
| 13  | production_countries   | 45463          | object    |
| 14  | release_date           | 45379          | object    |
| 15  | revenue                | 45460          | float64   |
| 16  | runtime                | 45203          | float64   |
| 17  | spoken_languages       | 45460          | object    |
| 18  | status                 | 45379          | object    |
| 19  | tagline                | 20412          | object    |
| 20  | title                  | 45460          | object    |
| 21  | video                  | 45460          | object    |
| 22  | vote_average           | 45460          | float64   |
| 23  | vote_count             | 45460          | float64   |

Dari tabel di atas terlihat bahwa ada **24 kolom/variabel yang digunakan dalam dataset `movies_metadata.csv`**, yaitu:

  - **adult** : Menunjukkan apakah film ditujukan untuk penonton dewasa (True/False).
  - **belongs_to_collection** : Informasi apakah film termasuk dalam sebuah seri/koleksi film tertentu .
  - **budget** : Anggaran produksi film dalam satuan dolar.
  - **genres** : Daftar genre yang dikategorikan dalam film (misalnya: Comedy, Action).
  - **homepage** : Alamat situs resmi film (jika tersedia).
  - **id** : Identifier unik dari film dalam dataset ini.
  - **imdb_id** : Identifier unik film dari situs IMDb.
  - **original_language** : Bahasa asli saat film diproduksi (misalnya: en untuk English).
  - **original_title** : Judul asli film saat pertama kali dirilis.
  - **overview** : Ringkasan atau sinopsis singkat mengenai cerita film.
  - **popularity** : Skor popularitas film berdasarkan berbagai metrik (seperti views, ratings).
  - **poster_path** : Path atau nama file gambar poster film.
  - **production_companies** : Daftar perusahaan produksi yang terlibat dalam pembuatan film.
  - **production_countries** : Negara tempat film diproduksi.
  - **release_date** : Tanggal rilis resmi film.
  - **revenue** : Pendapatan atau pemasukan dari film dalam satuan dolar.
  - **runtime** : Durasi film dalam satuan menit.
  - **spoken_languages** : Bahasa yang digunakan di dalam film.
  - **status** : Status film (misalnya: Released, Post Production).
  - **tagline** : Slogan atau kutipan promosi film.
  - **title** : Judul film.
  - **video** : Menunjukkan apakah film memiliki video tambahan terkait. Nilainya berupa True atau False.
  - **vote_average** : Rata-rata skor atau penilaian yang diberikan oleh pengguna (misalnya IMDb atau TMDb) terhadap film, biasanya dalam skala 1–10.
  - **vote_count** : Jumlah total suara atau penilaian yang diterima oleh film.


Dataset ini terdiri dari **45.466 entri data**, dengan tipe data yang digunakan yaitu sebagai berikut:
  - Terdapat **4 kolom bertipe numerik** dengan tipe data `float64`, yaitu: `revenue`, `runtime`, `vote_average`, dan `vote_count`.
  - Sisanya, yaitu **20 kolom**, bertipe `object`, termasuk kolom teks, boolean (disimpan dalam bentuk string), serta kolom dengan format JSON (seperti `genres`, `production_companies`, dll).

Gambaran dari data ratings dapat dilihat pada tabel dibawah:

| userId | movieId | rating | timestamp  |
|--------|---------|--------|------------|
| 1      | 31      | 2.5    | 1260759144 |
| 1      | 1029    | 3.0    | 1260759179 |

| #  | Column     | Non-Null Count | Dtype   |
|----|------------|----------------|---------|
| 0  | userId     | 100004         | int64   |
| 1  | movieId    | 100004         | int64   |
| 2  | rating     | 100004         | float64 |
| 3  | timestamp  | 100004         | int64   |

Dari tabel di atas terlihat bahwa ada **4 kolom/variabel yang digunakan dalam dataset `ratings_small.csv`**, yaitu:
- **userId** : Identifier unik dari pengguna yang memberikan rating.
- **movieId** : Identifier unik dari film yang diberi rating oleh pengguna.
- **rating** : Nilai rating yang diberikan pengguna terhadap film, dalam skala 0.5 hingga 5.0.
- **timestamp** : Waktu saat rating diberikan, dalam bentuk UNIX timestamp.

Dataset ini terdiri dari **100.004 entri data**, dengan tipe data yang digunakan yaitu sebagai berikut:
- `int64` untuk kolom `userId`, `movieId`, dan `timestamp`
- `float64` untuk kolom `rating`

Dari hasil pengecekan variabel pada kedua dataset di atas, ditemukan ketidaksesuaian tipe data pada kolom `id` di dataframe `movies`, yang bertipe `object`, sedangkan kolom `movieId` di `ratings_small` bertipe `int64`.

Penyesuaian tipe data ini penting dilakukan agar proses *join* antar dataframe dapat berjalan dengan benar, terutama karena kedua dataframe akan digabung untuk membangun sistem rekomendasi film berdasarkan data rating pengguna. Tahap Penyesuaian akan dilakukan pada **Data Preparation** untuk memastikan kedua dataset memiliki tipe data yang konsisten.

## 3.3 EDA - Univariate Analysis

### a. Menghitung total data unik dari dataset movies dan ratings

![image](https://github.com/user-attachments/assets/9d1079d0-3824-432f-8e8f-ff8c6b101f02)

Dari hasil di atas, terdapat 45.436 film pada dataset `movies`, dengan 9.066 film yang memiliki rating dan 671 pengguna yang memberikan rating pada dataset `ratings_small`.

### b. Melihat Informasi statistik dari dataset movies dan ratings

Informasi statistik dari dataset movies dan ratings disajikan pada tabel dibawah:

##### Statistik Dataset Movies

| **Column**       | **Count** | **Mean**         | **Std**         | **Min** | **25%** | **50%** | **75%** | **Max**         |
|------------------|-----------|------------------|-----------------|---------|---------|---------|---------|-----------------|
| revenue          | 45,460    | 11,209,350.0     | 64,332,250.0    | 0.0     | 0.0     | 0.0     | 0.0     | 2,787,965,000   |
| runtime          | 45,203    | 94.12            | 38.41           | 0.0     | 85.0    | 95.0    | 107.0   | 1,256.0         |
| vote_average     | 45,460    | 5.62             | 1.92            | 0.0     | 5.0     | 6.0     | 6.8     | 10.0            |
| vote_count       | 45,460    | 109.90           | 491.31          | 0.0     | 3.0     | 10.0    | 34.0    | 14,075.0        |

Insight dari movies:
  - Revenue memiliki nilai yang sangat besar namun terdapat film dengan revenue 0, yang menunjukkan adanya film dengan pendapatan yang tidak tercatat atau film dengan anggaran kecil.
  - Runtime film bervariasi dari sangat pendek (0 menit, mungkin film yang belum selesai atau data yang tidak tercatat) hingga lebih dari 1.200 menit, yang menunjukkan beberapa film dengan durasi sangat panjang.
  - Vote Average menunjukkan rata-rata rating film, yang dimulai dari 0 dengan  berkisar antara 5 hingga 7, lalu nilai tertinggi 10.
  - Vote Count menunjukkan banyaknya ulasan yang diterima film. Banyak film yang memiliki jumlah suara rendah (bahkan ada film yang memiliki jumlah suara 0), namun ada beberapa film yang mendapatkan ribuan ulasan.

##### Statistik Dataset Ratings

| **Column**   | **Count** | **Mean**    | **Std**    | **Min** | **25%**  | **50%**  | **75%**  | **Max**   |
|--------------|-----------|-------------|------------|---------|----------|----------|----------|-----------|
| userId       | 100,004   | 347.01      | 195.16     | 1.0     | 182.0    | 367.0    | 520.0    | 671.0     |
| movieId      | 100,004   | 12,548.66   | 26,369.20  | 1.0     | 1,028.0  | 2,406.5  | 5,418.0  | 163,949.0 |
| rating       | 100,004   | 3.54        | 1.06       | 0.5     | 3.0      | 4.0      | 4.0      | 5.0       |
| timestamp    | 100,004   | 1,129,639,000 | 191,685,800 | 789,652,009 | 965,847,824 | 1,110,422,000 | 1,296,192,000 | 1,476,641,000 |

Insight dari Ratings :
  - UserId menunjukkan distribusi pengguna yang memberikan rating.
  - MovieId menunjukkan bahwa film yang dinilai/memiliki rating.
  - Rating menunjukkan bahwa sebagian besar rating yang diberikan adalah 3 hingga 5.
  - Timestamp menunjukkan waktu ketika rating diberikan. Nilai timestamp yang tinggi menunjukkan data yang lebih baru, sementara nilai timestamp yang lebih rendah menunjukkan data yang lebih lama. Timestamp dicatat dalam bentuk waktu UNIX.

### c. Visualisasi Distribusi Rating Film

![Untitled](https://github.com/user-attachments/assets/70859746-06a5-40ea-b400-f5f810327d09)

Insight yang didapatkan dari barchart diatas adalah :
- **Rating 4** adalah rating yang paling banyak diberikan oleh pengguna, dengan persentase tertinggi sebesar **28.75%**. Hal ini menunjukkan bahwa sebagian besar pengguna cenderung memberikan penilaian positif terhadap film yang mereka tonton.
- **Rating 3** menyusul dengan persentase **20.06%**, diikuti oleh **rating 5** yang mencapai **15.09%**. Ini menunjukkan bahwa mayoritas film dinilai berada dalam kategori biasa hingga sangat baik.
- **Rating 0.5** hanya diberikan oleh **1.10%** pengguna, menandakan bahwa hanya sedikit film yang dianggap sangat buruk oleh penonton.

### d. Visualisasi Distribusi Genre dalam Film

![Untitled](https://github.com/user-attachments/assets/96213cfc-9cf4-4c89-8417-e379edfc0f3f)

Insight yang didapatkan dari barchart diatas adalah:
  - Genre Drama menjadi genre yang paling sering muncul dengan lebih dari 20.000 kemunculan pada film, diikuti oleh Comedy sekitar 13.000. Ini menunjukkan bahwa banyak film mengandung unsur cerita emosional dan humor, dua genre yang populer di kalangan penonton.
  
  - Perlu dicatat bahwa satu film bisa memiliki lebih dari satu genre. Oleh karena itu, angka ini tidak menunjukkan jumlah film unik, melainkan jumlah total kemunculan genre dalam seluruh dataset film.

  - Beberapa "genre" seperti Carousel Productions, Aniplex, dan lainnya sebenarnya bukan genre, melainkan nama perusahaan produksi. Ini kemungkinan besar disebabkan oleh data yang belum dibersihkan atau salah kategorisasi. Ini menjadi sinyal bahwa perlu dilakukan data cleaning untuk memisahkan genre dari entitas lainnya seperti studio atau produser.

### e. Analisis Rating dan Vote dari Masing-Masing Film
| Title                          | User Rating Mean | TMDb/IMDb Mean Rating | Total Vote |
|-------------------------------|------------------|------------------------|------------|
| Terminator 3: Rise of the Machines | 4.26             | 5.90                   | 324        |
| The Million Dollar Hotel       | 4.49             | 5.90                   | 311        |
| Solaris                        | 4.13             | 7.69                   | 305        |
| The 39 Steps                   | 4.22             | 7.40                   | 291        |
| Monsoon Wedding                | 3.71             | 6.80                   | 274        |
| Once Were Warriors             | 4.30             | 7.60                   | 244        |
| Three Colors: Red              | 3.95             | 7.80                   | 228        |
| Men in Black II               | 4.26             | 6.10                   | 224        |
| The Passion of Joan of Arc     | 3.48             | 8.20                   | 218        |
| Silent Hill                    | 3.67             | 6.30                   | 215        |

Insight yang dapat diberikan:
- Berdasarkan 10 film dengan total vote terbanyak:
  - *Terminator 3: Rise of the Machines* menjadi film dengan jumlah vote terbanyak (324 vote), dengan rata-rata rating dari pengguna sebesar 4.26 dan rating 5.9 dari TMDb/IMDb.
  
  - Terdapat selisih penilaian antara komunitas pengguna dan TMDb/IMDb pada beberapa film, misalnya:
    - *The Million Dollar Hotel*: user rating 4.49 vs TMDb/IMDb rating 5.9.
    - *The Passion of Joan of Arc*: user rating 3.48 vs TMDb/IMDb rating 8.2.
  
  - Hal ini menunjukkan bahwa preferensi pengguna yang memberikan rating bisa berbeda signifikan dibandingkan agregat rating dari platform lain seperti TMDb atau IMDb, baik karena demografi, ekspektasi, maupun persepsi terhadap film tertentu.

![Untitled](https://github.com/user-attachments/assets/45ce12fc-8603-42e6-b406-1277204c807c)

Insight yang didapatkan dari kedua scatterplot diatas adalah

  - Dari kedua grafik, terlihat bahwa film dengan rating menengah hingga tinggi (sekitar 6–8 di TMDB/IMDB dan 3–4 di user rating) cenderung mendapatkan jumlah vote yang lebih banyak.

  - Sedangkan film dengan rating sangat rendah atau sangat tinggi cenderung memiliki jumlah vote yang lebih sedikit dimana ini bisa terjadi karena film tersebut kurang populer atau hanya menarik bagi segmen tertentu.

  - Meskipun rentang rating TMDb/IMDb lebih luas (0–10) dan user rating lebih sempit (0-5), keduanya memperlihatkan tren serupa: film dengan rating ekstrem (terlalu rendah atau terlalu tinggi) justru cenderung mendapatkan vote lebih sedikit dibandingkan film dengan rating moderat.

# 4. Data Preparation
Sebelum membangun sistem rekomendasi, tahap data preparation sangat penting dilakukan untuk memastikan bahwa data yang digunakan telah bersih, konsisten, dan siap untuk dianalisis lebih lanjut. Dalam proyek ini, proses data preparation dibagi ke dalam tiga tahapan utama, yaitu:

## 4.1 Data Preparation Umum
Pada tahap ini, dilakukan penyesuaian data secara menyeluruh yang berlaku untuk kedua pendekatan sistem rekomendasi, baik content-based filtering maupun collaborative filtering. Adapun tahapannya adalah sebagai berikut:

### 4.1.1 Pemilihan Fitur yang Relevan
Pada tahap ini, dilakukan seleksi fitur dari kedua dataset untuk memastikan hanya data yang relevan yang digunakan dalam proses selanjutnya:
    - Dari dataframe movies, fitur yang dipilih adalah id, genres, dan title, karena ketiganya memiliki peran penting dalam proses pencocokan konten dan identifikasi film.
    - Dari dataframe ratings_small, seluruh fitur akan digunakan kecuali timestamp, yang dihapus karena tidak berkontribusi langsung terhadap pembuatan sistem rekomendasi.

| id    | genres                                                                 | title                           |
|-------|------------------------------------------------------------------------|---------------------------------|
| 862   | [{'id': 16, 'name': 'Animation'}, {'id': 35, 'name': 'Comedy'}]         | Toy Story                       |
| 8844  | [{'id': 12, 'name': 'Adventure'}, {'id': 14, 'name': 'Fantasy'}]        | Jumanji                         |
| 15602 | [{'id': 10749, 'name': 'Romance'}, {'id': 35, 'name': 'Comedy'}]        | Grumpier Old Men                |
| 31357 | [{'id': 35, 'name': 'Comedy'}, {'id': 18, 'name': 'Drama'}]             | Waiting to Exhale               |
| 11862 | [{'id': 35, 'name': 'Comedy'}]                                          | Father of the Bride Part II     |

| userId | movieId | rating |
|--------|---------|--------|
| 1      | 31      | 2.5    |
| 1      | 1029    | 3.0    |
| 1      | 1061    | 3.0    |
| 1      | 1129    | 2.0    |
| 1      | 1172    | 4.0    |

### 4.1.2 Penyesuaian Nama dan Tipe Data
Berdasarkan hasil pengecekan EDA, perlu dilakukan **penyesuaian tipe data pada kolom `id` di dataframe `movies` agar konsisten dengan tipe data `int64` pada kolom `movieId` di dataframe `ratings_small`**.

Setelah penyesuaian tipe data, nama kolom `id` pada dataframe `movies` perlu diubah menjadi `movieId` agar proses penggabungan (join) antar dataframe dapat dilakukan dengan benar.

### 4.1.3. Mengonversi Fitur Genre menjadi Format yang Terstruktur

Pada tahap ini, kolom `genres` yang awalnya berisi data dalam bentuk list of dictionaries diubah menjadi format yang lebih terstruktur, yaitu **list of genre names**. Hal ini dilakukan agar data lebih mudah dianalisis dan diproses untuk keperluan rekomendasi.

Selanjutnya, **list kosong pada kolom `genres` diubah menjadi NaN** untuk memudahkan identifikasi dan penanganan baris yang tidak memiliki genre. Langkah ini penting untuk memastikan bahwa data yang tidak relevan dapat dihapus atau ditangani dengan tepat selama analisis lebih lanjut.

Proses ini bertujuan untuk mempermudah pemanfaatan data genre dalam pembuatan model rekomendasi yang lebih efisien dan akurat.

| movieId | genres                        | title                         |
|---------|-------------------------------|-------------------------------|
| 862     | [Animation, Comedy, Family]    | Toy Story                     |
| 8844    | [Adventure, Fantasy, Family]   | Jumanji                       |
| 15602   | [Romance, Comedy]              | Grumpier Old Men              |
| 31357   | [Comedy, Drama, Romance]       | Waiting to Exhale             |
| 11862   | [Comedy]                       | Father of the Bride Part II   |

### 4.1.4. Menggabungkan DataFrame Movies dan Ratings_small
- Pada tahap ini, setelah dilakukan penyesuaian pada DataFrame movies dan ratings_small, dilakukan penggabungan (join) antara DataFrame movies dan ratings_small.

- Tujuan dari penggabungan ini adalah untuk mengaitkan setiap film dengan rating yang diberikan oleh pengguna, sehingga informasi mengenai rating film dapat disertakan dalam analisis lebih lanjut.

| movieId | genres                               | title | userId | rating |
|---------|--------------------------------------|-------|--------|--------|
| 949     | [Action, Crime, Drama, Thriller]     | Heat  | 23     | 3.5    |
| 949     | [Action, Crime, Drama, Thriller]     | Heat  | 102    | 4.0    |
| 949     | [Action, Crime, Drama, Thriller]     | Heat  | 232    | 2.0    |
| 949     | [Action, Crime, Drama, Thriller]     | Heat  | 242    | 5.0    |
| 949     | [Action, Crime, Drama, Thriller]     | Heat  | 263    | 3.0    |

### 4.1.5 




## 4.2 Data Preparation Khusus untuk Content-Based Filtering
Setelah melalui proses data preparation umum, tahap selanjutnya difokuskan pada pengolahan data yang relevan dengan pendekatan content-based filtering. Fokus utama pada bagian ini adalah mengekstraksi dan mempersiapkan informasi konten dari film yang akan digunakan untuk menghitung kesamaan antar item. Adapun tahapannya adalah sebagai berikut:

### 4.2.1 

## 4.3 Data Preparation Khusus untuk Collaborative Filtering
Setelah proses data preparation umum dilakukan, tahap selanjutnya mengarah pada persiapan data yang akan digunakan dalam pendekatan collaborative filtering. Di sini, fokusnya adalah pada interaksi pengguna dan item yang akan dianalisis untuk membangun sistem rekomendasi berbasis perilaku pengguna. Adapun tahapannya adalah sebagai berikut:


















