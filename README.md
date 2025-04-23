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










