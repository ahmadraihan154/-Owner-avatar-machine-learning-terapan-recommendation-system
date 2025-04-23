<p align="right" style="font-size: 12px;">
<i>Disclaimer: Referensi yang digunakan dapat dilihat pada bagian paling bawah tulisan. Setiap tulisan berwarna <span style="color:blue;">biru</span> merupakan tautan yang dapat diklik menuju sumber aslinya.</i>
</p>

# Nama : Ahmad Raihan
# Project : Recommendation System - Sistem Rekomendasi Film

# 1. Project Overview
## Latar Belakang
![10-Rekomendasi-Film-Teknologi-dan-Artificial-Intelligence-yang-Seru-dan-Keren](https://github.com/user-attachments/assets/e1350004-1a98-4b60-9569-c04d77a2c99b)

Dalam beberapa tahun terakhir, industri hiburan, khususnya perfilman, mengalami pertumbuhan pesat yang didorong oleh kemajuan teknologi dan kemudahan akses digital. Di Indonesia, peningkatan ini terlihat jelas dari melonjaknya jumlah penonton film lokal yang mencapai lebih dari 78 juta pada tahun 2024 [[1](https://sisiplus.katadata.co.id/berita/LAINNYA/2259/jumlah-penonton-film-indonesia-tembus-78-juta-terbanyak-sepanjang-sejarah)]. Perkembangan ini menunjukkan bahwa film telah menjadi bagian penting dari gaya hidup masyarakat modern.

Namun, pertumbuhan tersebut juga membawa tantangan baru, terutama dalam hal penyajian konten yang sesuai dengan preferensi masing-masing pengguna. Banyaknya pilihan film yang tersedia, baik di bioskop maupun platform digital, justru sering kali membuat pengguna kebingungan dalam menentukan tontonan yang paling sesuai dengan selera mereka. Pengguna kerap dihadapkan pada daftar panjang film tanpa informasi yang cukup, yang mengakibatkan waktu pencarian menjadi tidak efisien dan pengalaman menonton kurang memuaskan [[2](	https://doi.org/10.36040/jati.v9i2.13251)].

Permasalahan ini semakin penting seiring meningkatnya kebutuhan pengguna akan layanan yang cepat, akurat, dan personal. Di tengah maraknya konten digital, pengguna tidak hanya menginginkan banyak pilihan, tetapi juga mengharapkan kemudahan dalam menemukan konten yang relevan dengan minat dan kebutuhan mereka. Tanpa bantuan yang tepat, proses pencarian film menjadi kurang efektif dan cenderung membuat pengguna melewatkan konten yang sebenarnya sesuai dengan preferensi mereka [[3](https://doi.org/10.25126/jtiik.20231036616)].

Berdasarkan permasalahan yang ditemui, maka diperlukan sebuah sistem yang mampu membantu pengguna dalam menemukan film yang sesuai dengan preferensi mereka secara efisien dan personal. Solusi ini diharapkan dapat mempermudah proses pencarian, menghemat waktu pengguna, serta meningkatkan kepuasan dalam menikmati konten hiburan yang tersedia secara digital.

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

### 3.3.1. Menghitung total data unik dari dataset movies dan ratings

![image](https://github.com/user-attachments/assets/9d1079d0-3824-432f-8e8f-ff8c6b101f02)

Dari hasil di atas, terdapat 45.436 film pada dataset `movies`, dengan 9.066 film yang memiliki rating dan 671 pengguna yang memberikan rating pada dataset `ratings_small`.

### 3.3.2. Melihat Informasi statistik dari dataset movies dan ratings

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

### 3.3.3. Visualisasi Distribusi Rating Film

![Untitled](https://github.com/user-attachments/assets/70859746-06a5-40ea-b400-f5f810327d09)

Insight yang didapatkan dari barchart diatas adalah :
- **Rating 4** adalah rating yang paling banyak diberikan oleh pengguna, dengan persentase tertinggi sebesar **28.75%**. Hal ini menunjukkan bahwa sebagian besar pengguna cenderung memberikan penilaian positif terhadap film yang mereka tonton.
- **Rating 3** menyusul dengan persentase **20.06%**, diikuti oleh **rating 5** yang mencapai **15.09%**. Ini menunjukkan bahwa mayoritas film dinilai berada dalam kategori biasa hingga sangat baik.
- **Rating 0.5** hanya diberikan oleh **1.10%** pengguna, menandakan bahwa hanya sedikit film yang dianggap sangat buruk oleh penonton.

### 3.3.4. Visualisasi Distribusi Genre dalam Film

![Untitled](https://github.com/user-attachments/assets/96213cfc-9cf4-4c89-8417-e379edfc0f3f)

Insight yang didapatkan dari barchart diatas adalah:
  - Genre Drama menjadi genre yang paling sering muncul dengan lebih dari 20.000 kemunculan pada film, diikuti oleh Comedy sekitar 13.000. Ini menunjukkan bahwa banyak film mengandung unsur cerita emosional dan humor, dua genre yang populer di kalangan penonton.
  
  - Perlu dicatat bahwa satu film bisa memiliki lebih dari satu genre. Oleh karena itu, angka ini tidak menunjukkan jumlah film unik, melainkan jumlah total kemunculan genre dalam seluruh dataset film.

  - Beberapa "genre" seperti Carousel Productions, Aniplex, dan lainnya sebenarnya bukan genre, melainkan nama perusahaan produksi. Ini kemungkinan besar disebabkan oleh data yang belum dibersihkan atau salah kategorisasi. Ini menjadi sinyal bahwa perlu dilakukan data cleaning untuk memisahkan genre dari entitas lainnya seperti studio atau produser.

### 3.3.5. Analisis Rating dan Vote dari Masing-Masing Film
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

### 4.1.5. Mengatasi Nilai yang Missing
Pada tahap sebelumnya, setelah fitur `genres` diubah menjadi list of genre names, ditemukan adanya beberapa nilai yang hilang (missing) pada kolom tersebut. Hal ini bisa terjadi karena beberapa film tidak memiliki genre yang tercantum atau karena ketidaksempurnaan dalam data.

Untuk menjaga kualitas data yang akan digunakan dalam pembangunan model sistem rekomendasi, nilai-nilai yang missing tersebut diatasi dengan cara menghapus baris-baris yang bersangkutan. Langkah ini penting agar model tidak terdampak oleh data yang tidak lengkap atau tidak relevan.

## 4.2 Data Preparation Khusus untuk Content-Based Filtering
Setelah melalui proses data preparation umum, tahap selanjutnya difokuskan pada pengolahan data yang relevan dengan pendekatan content-based filtering. Fokus utama pada bagian ini adalah mengekstraksi dan mempersiapkan informasi konten dari film yang akan digunakan untuk menghitung kesamaan antar item. Adapun tahapannya adalah sebagai berikut:

### 4.2.1 Mengatasi Data yang Duplikat
Setelah proses penggabungan DataFrame di tahapan data preparation umum, ditemukan adanya data duplikat. Hal ini wajar terjadi karena satu film dapat diberi rating oleh banyak pengguna, sehingga terdapat beberapa baris dengan `movieId` yang sama namun `userId` dan `rating` yang berbeda.

Namun, untuk keperluan **content-based filtering**, fokus utama adalah pada informasi unik dari setiap film. Oleh karena itu, duplikasi tersebut perlu dihapus agar tidak mempengaruhi representasi fitur film.

Penghapusan dilakukan menggunakan fungsi `drop_duplicates()`, yang menghasilkan pengurangan jumlah baris dari **44.792 baris menjadi 2.800 baris**, sementara jumlah kolom tetap **5 kolom**.

### 4.2.2 Pemilihan Fitur yang Relevan

**Content-Based Filtering berfokus pada karakteristik item**, dalam hal ini adalah film. Oleh karena itu, hanya fitur-fitur yang merepresentasikan konten film yang akan digunakan. Fitur yang dipilih antara lain: **`movieId`**, **`title`**, dan **`genres`**, karena ketiganya dapat menggambarkan isi atau kategori dari masing-masing film.

Sementara itu, fitur seperti **`userId`** dan **`rating`** tidak digunakan pada tahap ini, karena pendekatan content-based tidak mempertimbangkan preferensi pengguna secara langsung, melainkan lebih fokus pada kesamaan antar item (film).

| movieId | genres                                | title                  |
|---------|----------------------------------------|------------------------|
| 949     | [Action, Crime, Drama, Thriller]       | Heat                   |
| 710     | [Adventure, Action, Thriller]          | GoldenEye              |
| 1408    | [Action, Adventure]                    | Cutthroat Island       |
| 524     | [Drama, Crime]                         | Casino                 |
| 4584    | [Drama, Romance]                       | Sense and Sensibility  |

### 4.2.3 Ekstraksi Fitur Teks dari Kolom Genre
Tahap ini menggunakan teknik **TF-IDF (Term Frequency Inverse Document Frequency)** untuk mengubah isi kolom `genres` menjadi representasi numerik berbasis teks. Representasi ini membantu sistem mengenali kemiripan antar film berdasarkan kesamaan genre yang dimiliki.

Sebelum menerapkan `TfidfVectorizer`, data pada kolom `genres` perlu dikonversi dari format list menjadi string. Hal ini dilakukan karena `TfidfVectorizer` hanya dapat memproses input dalam bentuk teks (string), bukan dalam bentuk list atau array.

Adapun hasil akhir dari ektraksi fitur dengan TF-IDF dapat dilihat pada tabel dibawah:

| Title                  | Action  | Adventure | Animation | Comedy | Crime   | Documentary | Drama   | Family | Fantasy | Fiction | ... | Horror | Movie | Music | Mystery | Romance | Science | Thriller | TV  | War | Western |
|------------------------|---------|-----------|-----------|--------|---------|-------------|---------|--------|---------|---------|-----|--------|-------|--------|----------|---------|---------|----------|-----|-----|---------|
| Heat                   | 0.5445  | 0.0000    | 0.0       | 0.0000 | 0.5899  | 0.0         | 0.3299  | 0.0    | 0.0000  | 0.0000  | ... | 0.0000 | 0.0   | 0.0    | 0.0      | 0.0000  | 0.0000  | 0.4967   | 0.0 | 0.0 | 0.0     |
| GoldenEye              | 0.5619  | 0.6492    | 0.0       | 0.0000 | 0.0000  | 0.0         | 0.0000  | 0.0    | 0.0000  | 0.0000  | ... | 0.0000 | 0.0   | 0.0    | 0.0      | 0.0000  | 0.0000  | 0.5126   | 0.0 | 0.0 | 0.0     |
| Cutthroat Island       | 0.6544  | 0.7561    | 0.0       | 0.0000 | 0.0000  | 0.0         | 0.0000  | 0.0    | 0.0000  | 0.0000  | ... | 0.0000 | 0.0   | 0.0    | 0.0      | 0.0000  | 0.0000  | 0.0000   | 0.0 | 0.0 | 0.0     |
| Casino                 | 0.0000  | 0.0000    | 0.0       | 0.0000 | 0.8728  | 0.0         | 0.4881  | 0.0    | 0.0000  | 0.0000  | ... | 0.0000 | 0.0   | 0.0    | 0.0      | 0.0000  | 0.0000  | 0.0000   | 0.0 | 0.0 | 0.0     |
| Sense and Sensibility | 0.0000  | 0.0000    | 0.0       | 0.0000 | 0.0000  | 0.0         | 0.5161  | 0.0    | 0.0000  | 0.0000  | ... | 0.0000 | 0.0   | 0.0    | 0.0      | 0.8565  | 0.0000  | 0.0000   | 0.0 | 0.0 | 0.0     |

## 4.3 Data Preparation Khusus untuk Collaborative Filtering
Setelah proses data preparation umum dilakukan, tahap selanjutnya mengarah pada persiapan data yang akan digunakan dalam pendekatan collaborative filtering. Di sini, fokusnya adalah pada interaksi pengguna dan item yang akan dianalisis untuk membangun sistem rekomendasi berbasis perilaku pengguna. Adapun tahapannya adalah sebagai berikut:

### 4.3.1 Pemilihan Fitur yang Relevan
**Karena pendekatan Collaborative Filtering berfokus pada pola interaksi antara pengguna dan item (film)**, maka fitur yang dipilih terbatas pada `userId`, `movieId`, dan `rating`. Ketiga fitur ini merepresentasikan hubungan eksplisit yang terjadi antara pengguna dan film melalui rating yang diberikan.

Fitur lain seperti `title` dan `genres` tidak digunakan dalam pendekatan ini karena informasi konten dari film tidak dibutuhkan untuk membangun model collaborative filtering. Model hanya mempelajari pola interaksi dari data rating antar pengguna. Setelah proses pemilihan fitur ini, dataset yang awalnya terdiri dari **44.792 baris dan 5 kolom** menjadi **44.792 baris dan 3 kolom**.

| userId | movieId | rating |
|--------|---------|--------|
| 1      | 2105    | 4.0    |
| 1      | 1405    | 1.0    |
| 1      | 2455    | 2.5    |
| 1      | 2294    | 2.0    |
| 1      | 2193    | 2.0    |

### 4.3.2 Melakukan Encoding pada Kolom `userId` dan `movieId`
Karena model deep learning hanya dapat memproses input dalam bentuk numerik, maka kolom `userId` dan `movieId` perlu diubah menjadi bentuk numerik yang terurut (jika belum dalam format tersebut). Proses ini dilakukan dengan teknik encoding, seperti Label Encoding atau penyesuaian indexing, untuk memastikan setiap pengguna dan film direpresentasikan dengan ID numerik yang unik dan konsisten.

Data Summary :
- **Jumlah Pengguna**: 671
- **Jumlah Film**: 2800
- **Rating Minimum**: 0.5
- **Rating Maksimum**: 5.0

| userId | movieId | rating | user | movie |
|--------|---------|--------|------|-------|
| 11376  | 1       | 4.0    | 0    | 1071  |
| 27973  | 1       | 1.0    | 0    | 725   |
| 31731  | 1       | 2.5    | 0    | 1201  |
| 18245  | 1       | 2.0    | 0    | 1158  |
| 13727  | 1       | 2.0    | 0    | 1121  |

Dapat dilihat bahwa data ini memiliki 671 pengguna, 2800 film, dengan rating minimum 0.5 dan rating maksimum 5.0.

### 4.3.3 Normalisasi Data
Karena pendekatan **Collaborative Filtering** berfokus pada pola interaksi antara pengguna dan item (film), penting untuk melakukan **normalisasi data** sebelum melatih model. Normalisasi membantu menyamakan skala nilai rating yang diberikan oleh pengguna, sehingga model **deep learning** dapat lebih efektif dalam mendeteksi pola. Dalam hal ini, rating awal yang berada dalam rentang **0.5 hingga 5.0** dinormalisasi menjadi skala **0 hingga 1**. Proses ini dilakukan agar model dapat memproses input numerik secara lebih cepat dan efisien saat proses pelatihan model.

### 4.3.4 Pemisahan Data
Setelah tahap persiapan data, data kemudian dipisahkan menjadi tiga subset berdasarkan proporsi yang telah ditentukan: 80% untuk data pelatihan (training), 10% untuk data validasi (validation), dan 10% untuk data pengujian (testing).
  
Pembagian ini dilakukan untuk memastikan model dapat dilatih dengan data yang cukup, diuji dengan data yang belum pernah dilihat, dan dievaluasi dengan data yang terpisah dari proses pelatihan. Hal ini membantu mengurangi overfitting dan memastikan performa model yang lebih general.

**Setelah pemisahan data**, jumlah data yang tersedia adalah sebagai berikut:
  - **Jumlah data untuk pelatihan:** 35,833
  - **Jumlah data untuk validasi:** 4,479
  - **Jumlah data untuk pengujian:** 4,480

# 5. Modeling and Result
## 5.1 Content - Based Filtering
**Content-Based Filtering** merupakan pendekatan sistem rekomendasi yang menyarankan item kepada pengguna berdasarkan karakteristik atau fitur dari item itu sendiri, tanpa memperhitungkan interaksi antar pengguna. Dalam konteks rekomendasi film, fitur yang digunakan bisa berupa genre, sinopsis, aktor, sutradara, dan lain sebagainya [[4](https://doi.org/10.36595/misi.v4i1.250)]. 

Untuk mengukur kesamaan antar item (dalam hal ini film), digunakan teknik berbasis teks seperti **Cosine Similarity**. Teknik ini sangat berguna ketika fitur yang digunakan adalah teks, seperti genre yang telah diproses menjadi representasi numerik melalui **TF-IDF (Term Frequency - Inverse Document Frequency)**. Cosine Similarity mengukur seberapa mirip dua vektor dalam ruang multidimensi dengan menghitung sudut antara keduanya. Vektor yang arahnya semakin mendekati satu sama lain (sudutnya kecil) dianggap lebih mirip [[5](https://doi.org/10.47111/jti.v18i1.12543)].

Adapun kelebihan dan kekurangan content-Based Filtering adalah

**Kelebihan**:
- Rekomendasi lebih personal karena berbasis pada histori pengguna.
- Tidak membutuhkan data dari pengguna lain.
- Cocok untuk pengguna baru yang baru memberikan beberapa rating (*user cold start*).

**Kekurangan**:
- Tidak bisa merekomendasikan item baru yang belum memiliki fitur konten yang jelas (*item cold start*).
- Rekomendasi cenderung monoton karena sangat mirip dengan preferensi sebelumnya.
- Tidak mempertimbangkan komunitas atau tren dari pengguna lain.

Pada proyek ini, **Content-Based Filtering** diimplementasikan menggunakan **Cosine Similarity** dengan hasilnya dapat dilihat dibawah.

**Langkah pertama : Menghitung Cosine Similarity antar Item**

![image](https://github.com/user-attachments/assets/a742c4b6-4b6e-4dde-aef5-f62d7e29f3a1)

**Langkah kedua : Membuat Mapping antara hasil cosine similarity dan item**

![image](https://github.com/user-attachments/assets/62f9000b-69bc-4204-9004-f9a9698754b0)

**Langkah Ketiga : Membuat fungsi rekomendasi film berdasarkan kemiripan genre dengan menerapkan fungsi Top-N rekokemendasi serta menguji dan mengevaluasi model yang dibuat**

### Hasil 
Adapun untuk Hasil pengujian sistem rekomendasi filmnya dapat dilihat dimana dilakukan pencarian dengan film yang mirip dari judul yaitu **The Man with the Golden Arm**

![image](https://github.com/user-attachments/assets/e251d0e6-f98b-450b-b229-fa3f817e2321)

Hasilnya terlihat  beberapa film yang ditampilkan memiliki genre yang sama.

## 5.2 Collaborative Filtering
**Collaborative Filtering (CF)** adalah pendekatan yang digunakan dalam sistem rekomendasi dengan cara memanfaatkan pola interaksi antara pengguna (*user*) dan item (seperti film, lagu, atau produk) [[6](https://doi.org/10.29303/jbegati.v5i1.1193)]. CF tidak memerlukan informasi tambahan tentang item, cukup berdasarkan data historis seperti rating atau perilaku pembelian.

Terdapat dua pendekatan utama [[6](https://doi.org/10.29303/jbegati.v5i1.1193)]:

1. **Memory-Based CF**: 
   - Menggunakan teknik seperti *user-user similarity* atau *item-item similarity* berdasarkan rating historis.
2. **Model-Based CF**: 
   - Menggunakan teknik seperti *Matrix Factorization* atau *Deep Learning* untuk mempelajari representasi laten pengguna dan item.

Adapun kelebihan dan kekurangan Collaborative Filtering adalah

**Kelebihan:**
- **Tidak Memerlukan Data Konteks atau Metadata**
  - CF tidak butuh informasi seperti genre film, deskripsi produk, atau atribut lainnya.
  
- **Rekomendasi Bersifat Personal**
  - Menghasilkan rekomendasi berdasarkan kesamaan perilaku pengguna, sehingga lebih sesuai dengan selera masing-masing individu.

- **Mampu Menangkap Preferensi Tersembunyi**
  - Dapat menemukan hubungan non-trivial antar pengguna dan item dari pola rating yang besar.

- **Cocok untuk Skala Besar**
  - Terutama model-based CF (seperti matrix factorization) sangat cocok untuk dataset besar dan bisa dioptimalkan dengan baik.

**Kekurangan:** 
- **Cold Start Problem**
  - Tidak bisa memberikan rekomendasi yang baik untuk pengguna atau item baru yang belum memiliki interaksi historis.

- **Data Sparsity**
  - Banyak sistem memiliki jumlah interaksi yang kecil dibanding total kemungkinan user-item, membuat hasil rekomendasi menjadi kurang akurat.

- **Scalability untuk Memory-Based**
  - Pada pendekatan memory-based, menghitung kemiripan antar pengguna atau item secara real-time bisa menjadi mahal secara komputasi.

Adapun dalam pengerjaan proyek ini, saya menggunakan pendekatan **Model-Based Collaborative Filtering** yang berbasis **Deep Learning**, khususnya menggunakan **Matrix Factorization** melalui jaringan saraf (*Neural Network*). Pendekatan ini menggunakan teknik **embedding** untuk merepresentasikan *user* dan *movie* dalam vektor berdimensi rendah, kemudian melakukan operasi perkalian antara embedding user dan movie untuk memprediksi rating yang belum diketahui.

### a. Arsitektur Model
### 1. **Embedding Layer untuk User dan Movie**
Pada model ini, dibuatlah embedding terpisah untuk pengguna dan film. Vektor embedding ini akan dipelajari selama proses pelatihan untuk menangkap preferensi pengguna dan karakteristik film.

- **User Embedding**: Mewakili preferensi pengguna dalam bentuk vektor.
- **Movie Embedding**: Mewakili karakteristik film dalam bentuk vektor.

Kedua embedding ini diinisialisasi secara acak dan kemudian dioptimalkan menggunakan teknik pelatihan.

### 2. **Bias Term untuk User dan Movie**
Model ini juga mencakup **bias** untuk setiap pengguna dan film. Bias ini menangkap kecenderungan umum:
- **User Bias**: Bias yang menunjukkan bahwa seorang pengguna cenderung memberikan rating tinggi atau rendah pada semua film.
- **Movie Bias**: Bias yang menunjukkan bahwa film tertentu cenderung mendapatkan rating tinggi atau rendah.

### 3. **Dot Product antara User dan Movie Embedding**
- Setelah embedding dibuat untuk setiap *user* dan *movie*, dilakukan operasi **dot product** antara vektor embedding *user* dan *movie*. 
- Hasil dot product ini menunjukkan **seberapa besar kecocokan** antara pengguna dan film yang bersangkutan.

### 4. **Penjumlahan Bias dan Dot Product**
- **Bias User dan Movie** ditambahkan ke hasil perkalian dot product untuk memberikan skor kecocokan yang lebih akurat. 
- Dengan adanya bias, model bisa lebih fleksibel dalam menangani kecenderungan pengguna dan film.

### 5. **Fungsi Aktivasi Sigmoid**
- Setelah hasil dot product dan bias ditambahkan, kita menggunakan **fungsi aktivasi sigmoid** untuk membatasi output antara **0 dan 1**, sehingga bisa disesuaikan dengan rating yang dinormalisasi.

### 6. **Output Layer**
- Output akhir dari model ini adalah prediksi rating untuk pasangan *user* dan *movie* tertentu. Prediksi ini berada dalam skala 0 hingga 1, karena rating telah dinormalisasi sebelumnya.

![Untitled](https://github.com/user-attachments/assets/875be51f-3898-475f-9bf0-c81dd2b91858)

---

### b. Kompilasi Model
- **Loss Function**: `Mean Squared Error (MSE)` – untuk menghitung selisih antara rating yang diprediksi dan rating asli yang sudah dinormalisasi.
- **Optimizer**: `Adam` – dengan learning rate 0.001.
- **Evaluation Metrics**: 
  - `Mean Absolute Error (MAE)`
  - `Root Mean Squared Error (RMSE)`


### c. Training Model
- **Batch Size**: 32
- **Epochs**: 5

 ### Hasil 
 Adapun untuk Hasil pengujian sistem rekomendasi filmnya dapat dilihat dimana dilakukan pencarian dengan user 294
 
 ![image](https://github.com/user-attachments/assets/34bea7dc-7a78-4e6b-ab94-f8a3498e1033)

# 6. Evaluation
## 6.1 Evaluation Content Based Filtering
Evaluasi kinerja sistem rekomendasi dilakukan untuk mengukur seberapa baik sistem dalam memberikan rekomendasi yang relevan dan sesuai dengan kebutuhan pengguna. Salah satu metrik evaluasi yang  digunakan dalam sistem rekomendasi **content based filtering** adalah **Precision**.

### 6.1.1 Precision
**Precision** adalah ukuran proporsi item relevan di antara semua item yang direkomendasikan oleh sistem. Semakin tinggi nilai precision, maka semakin akurat sistem dalam memberikan rekomendasi yang sesuai dengan preferensi pengguna [[7](https://doi.org/10.1234/jir.v15i2.5678)].

#### Rumus Precision:

$$
\text{Precision} = \frac{\text{Jumlah item relevan yang direkomendasikan}}{\text{Jumlah total item yang direkomendasikan}}
$$

### 6.1.2. Hasil Evaluasi Content-Based Filtering
Kembali ke proyek yang dikerjakan, dari hasil evaluasi dengan menggunakan precision untuk menilai seberapa baik rekomendasi yang diberikan sesuai dengan preferensi genre pengguna, yaitu Crime, Drama, dan Romance. Berdasarkan perhitungan yang dilakukan terhadap data rekomendasi, presisi sistem rekomendasi mencapai 100%. Ini berarti bahwa semua film yang direkomendasikan memenuhi kriteria genre yang diinginkan oleh pengguna.

![image](https://github.com/user-attachments/assets/e3753d9e-c865-40c0-bfa5-041162888756)

## 6.2 Evaluation Collaborative Based Filtering
Evaluasi kinerja sistem rekomendasi dilakukan untuk mengukur seberapa baik sistem dalam memberikan rekomendasi yang relevan dan sesuai dengan kebutuhan pengguna. Adapun metrik evaluasi yang digunakan dalam sistem rekomendasi **Collaborative Filtering** adalah **Mean Absolute Error (MAE)** dan **Root Mean Squared Error (RMSE)**. 

### 6.2.1. **Mean Absolute Error (MAE)**
**MAE** mengukur rata-rata selisih absolut antara rating yang diprediksi oleh sistem dan rating yang sebenarnya diberikan oleh pengguna. MAE memberikan gambaran yang lebih sederhana tentang seberapa besar kesalahan prediksi rata-rata [[8](https://ieeexplore.ieee.org/document/8985340)].

**Rumus MAE**:

$$
\text{MAE} = \frac{1}{N} \sum_{i=1}^{N} |r_i - \hat{r}_i|
$$

Keterangan:
- \( N \) = jumlah total prediksi
- \( ri \) = rating aktual yang diberikan oleh pengguna
- \( r^i \) = rating yang diprediksi oleh sistem

Semakin kecil nilai MAE, semakin baik kemampuan sistem dalam memprediksi rating pengguna.

### 6.2.2. **Root Mean Squared Error (RMSE)**

**RMSE** juga mengukur selisih antara rating yang diprediksi dan rating yang sebenarnya, namun RMSE memberi bobot lebih pada kesalahan yang lebih besar dengan cara mengambil akar kuadrat dari perbedaan antara rating aktual dan yang diprediksi. RMSE sangat berguna ketika kita ingin memberi perhatian lebih pada kesalahan prediksi yang lebih besar [[7](https://arxiv.org/abs/1711.01647)].

**Rumus RMSE**:

$$
\text{RMSE} = \sqrt{\frac{1}{N} \sum_{i=1}^{N} (r_i - \hat{r}_i)^2}
$$

Keterangan:
- \( N \) = jumlah total prediksi
- \( ri \) = rating aktual yang diberikan oleh pengguna
- \( {r^i \) = rating yang diprediksi oleh sistem

Semakin kecil nilai RMSE, semakin baik kemampuan sistem dalam memberikan prediksi yang akurat.

## 6.2.3. Hasil Evaluasi Collaborative Filtering
Kembali ke proyek yang dikerjakan, berdasarkan perhitungan yang dilakukan terhadap data rekomendasi menggunakan Collaborative Filtering, metrik MAE dan RMSE dihitung untuk mengukur seberapa baik model dalam memprediksi rating yang relevan. Visualisasi dari kedua metrik tersebut dapat dilihat pada gambar di bawah ini:

![Untitled](https://github.com/user-attachments/assets/7d1822f5-b0ed-4bfc-8d7a-01c2562ea78b)

![Untitled-1](https://github.com/user-attachments/assets/fcbbbc21-fbdc-4270-9fa8-d4cf0f985dda)

Insight yang didapatkan dari kedua grafik diatas adalah:
  - Berdasarkan hasil evaluasi menggunakan metrik Mean Absolute Error (MAE) dan Root Mean Squared Error (RMSE), model menunjukkan performa yang cukup baik. Setelah 5 epoch pelatihan, nilai MAE pada data pelatihan mencapai sekitar 0.138, sedangkan pada data validasi sebesar 0.155. Begitu pula dengan RMSE yang menunjukkan 0.1538 pada data pelatihan dan sekitar 0.2 pada data validasi. 

  - Performa ini menunjukkan bahwa model cukup efektif dalam menangkap pola interaksi antara pengguna dan item (film). Error yang rendah berarti rekomendasi yang dihasilkan lebih dekat dengan rating yang seharusnya diberikan oleh pengguna, sehingga meningkatkan relevansi rekomendasi. Hal ini dapat berdampak positif terhadap pengalaman pengguna secara keseluruhan, karena sistem akan lebih sering merekomendasikan film yang sesuai dengan selera pengguna berdasarkan historis interaksinya.

## 6.3 Kesimpulan Evaluasi: Dampak terhadap Business Understanding
- Evaluasi dilakukan untuk menilai sejauh mana sistem rekomendasi yang dibangun mampu menjawab problem statement, mencapai goals yang telah ditetapkan, serta membuktikan efektivitas dari solusi yang diterapkan sepanjang proyek.

### 6.3.1 Hubungan Evaluation terhadap Problem Statement dan Goals
- Adapun sistem yang dikembangkan telah menjawab tiga problem statement dan goalsnya:
### 1. Pengolahan Data yang Optimal  
Pengolahan data dilakukan secara sistematis melalui tahapan umum, dilanjutkan dengan penyesuaian khusus untuk pendekatan Content-Based dan Collaborative Filtering, sehingga data siap digunakan untuk membangun sistem rekomendasi yang efektif.

### 2. Rekomendasi Berdasarkan Kemiripan Film (Content-Based)  
Dengan menggunakan metode **Content-Based Filtering** berbasis **Cosine Similarity**, sistem mampu memberikan **10 rekomendasi film** kepada pengguna berdasarkan kemiripan genre film yang disukai sebelumnya, dengan nilai **precision sebesar 100.00%**.

### 3. Rekomendasi Berdasarkan Preferensi Pengguna Lain (Collaborative Filtering)  
Penggunaan model **Deep Learning Collaborative Filtering** memberikan hasil rekomendasi yang lebih akurat dan relevan bagi pengguna. Hal ini dibuktikan dengan hasil pelatihan yang memperoleh nilai **mean absolute error (MAE) sebesar 0.1381** dan **root mean squared error (RMSE) sebesar 0.1788**, serta pada data validasi mencapai **MAE sebesar 0.1538** dan **RMSE sekitar 0.2** pada epoch ke-5.

### 6.3.2 Efektivitas Solusi yang Diterapkan
- Adapun efektivitas Setiap langkah dalam solution statement terhadap hasil akhir:
### 1. Exploratory Data Analysis (EDA) dan Data Preparation
EDA dan data preparation memberikan fondasi penting untuk seluruh proses pemodelan. Dengan memahami struktur data, mengatasi missing values, dan mengubah format data agar sesuai untuk algoritma yang digunakan, kualitas data dapat meningkat. Hal ini secara langsung memengaruhi performa, mengurangi error, dan memastikan bahwa sistem rekomendasi bekerja dengan data yang bersih dan representatif.

### 2. Content-Based Filtering
Metode ini efektif dalam memberikan rekomendasi yang bersifat personal, terutama bagi pengguna baru yang belum banyak memberikan rating. Karena sistem merekomendasikan film berdasarkan konten (misalnya genre) yang disukai pengguna sebelumnya, maka rekomendasi tetap relevan walaupun tidak ada banyak data pengguna lain.

### 3. Model-Based Collaborative Filtering (Deep Learning)
Pendekatan ini memanfaatkan hubungan antar pengguna dalam memberikan rekomendasi. Dengan deep learning, sistem dapat menangkap pola kompleks dalam interaksi pengguna-item dan menghasilkan prediksi rating yang lebih akurat. Dampaknya adalah peningkatan relevansi rekomendasi bagi pengguna aktif dan kontribusi besar dalam menangani variasi selera pengguna yang luas.

---

# Referensi
1. Katadata. (2024). Jumlah Penonton Film Indonesia Tembus 78 Juta, Terbanyak Sepanjang Sejarah. Diakses dari: https://sisiplus.katadata.co.id/berita/LAINNYA/2259/jumlah-penonton-film-indonesia-tembus-78-juta-terbanyak-sepanjang-sejarah
2. Velamentosa, D., & Zuliarso, E. (2025). SISTEM REKOMENDASI FILM MENGGUNAKAN METODE CONTENT-BASED FILTERING. JATI (Jurnal Mahasiswa Teknik Informatika), 9(2), 2918-2922.
3. Ayyiyah, N. M. K., Kusumaningrum, R., & Rismiyati, R. (2023). Film Recommender System Menggunakan Metode Neural Collaborative Filtering. Jurnal Teknologi Informasi Dan Ilmu Komputer, 10(3), 699-708.
4. Larasati, F. B. A., & Februariyanti, H. (2021). Sistem Rekomendasi Product Emina Cosmetics Dengan Menggunakan Metode Content-Based Filtering. Jurnal Manajemen Informatika Dan Sistem Informasi, 4(1), 45-54.
5. Priskila, R., Sari, N. N. K., & Putra, P. B. A. A. (2024). Implementasi Content-Based Filtering Menggunakan Tf-Idf and Cosine Similarity Untuk Sistem Rekomendasi Resep Masakan. Jurnal Teknologi Informasi: Jurnal Keilmuan dan Aplikasi Bidang Teknik Informatika, 18(1), 43-51.
6. Negara, M. S., & Mardiansyah, A. Z. (2024). Implementasi Machine Learning dengan Metode Collaborative Filtering dan Content-Based Filtering pada Aplikasi Mobile Travel (Bangkit Academy). Jurnal Begawe Teknologi Informasi (JBegaTI), 5(1), 126-136.
7. Kose, A., Kanbak, C., & Evirgen, N. (2017, December). Performance comparison of algorithms for movie rating estimation. In 2017 16th IEEE International Conference on Machine Learning and Applications (ICMLA) (pp. 955-959). IEEE.
8. Jonathan, B., Rahim, Z., Barzani, A., & Oktavega, W. (2019, October). Evaluation of mean absolute error in collaborative filtering for sparsity users and items on female daily network. In 2019 International Conference on Informatics, Multimedia, Cyber and Information System (ICIMCIS) (pp. 41-44). IEEE.


    






























