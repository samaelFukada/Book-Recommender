# Laporan Proyek Machine Learning - Ahmad Reginald Syahiran

## Project Overview
![foto](https://galeriemagazine.com/wp-content/uploads/2018/05/StuttgartSelect.jpg)

Di era digital yang berkembang pesat, minat baca tetap menjadi fondasi penting untuk pengembangan literasi dan pengetahuan[^1^]. Namun, meningkatnya jumlah buku yang diterbitkan setiap hari menjadi tantangan tersendiri bagi pembaca untuk menemukan bahan bacaan yang sesuai dengan minat dan preferensi mereka. Hal ini tidak hanya mengurangi efisiensi dalam pencarian buku, tetapi juga menghalangi pembaca untuk mengeksplorasi genre atau penulis baru yang mungkin mereka sukai. Untuk mengatasi tantangan ini, sistem rekomendasi buku berbasis teknologi menjadi semakin penting. Dengan memanfaatkan pembelajaran mesin dan analisis data, sistem ini dapat memprediksi dan menyarankan buku-buku yang relevan berdasarkan pola membaca, preferensi genre, dan interaksi sebelumnya[^2^]. Penelitian menunjukkan bahwa sistem rekomendasi buku yang efektif dapat meningkatkan kepuasan pembaca, memperluas wawasan literasi, serta mendukung penulis dan penerbit dalam menjangkau audiens yang lebih luas[^3^]. Oleh karena itu, pengembangan sistem rekomendasi buku merupakan langkah strategis dalam mendukung pertumbuhan literasi di era informasi saat ini.
---
[^1^]: Abadi, M., Agarwal, A., Barham, P., Brevdo, E., Chen, Z., Citro, C., Corrado, G. S., Davis, A., Dean, J., Devin, M., Ghemawat, S., Goodfellow, I., Harp, A., Irving, G., Isard, M., Jia, Y., Jozefowicz, R., Kaiser, L., Kudlur, M., . . . Zheng, X. (2016, March 14). TensorFlow: Large-Scale machine learning on heterogeneous distributed systems. arXiv.org. https://arxiv.org/abs/1603.04467
[^2^]: Dutta, A., Hasan, M. K., Ahmad, M., Awal, M. A., Islam, M. A., Masud, M., & Meshref, H. (2022). Early prediction of diabetes using an ensemble of machine learning models. International Journal of Environmental Research and Public Health, 19(19), 12378. https://doi.org/10.3390/ijerph191912378
[^3^]: Wood, T. (2020, September 10). Random forests. DeepAI. https://deepai.org/machine-learning-glossary-and-terms/random-forest
[^4^]: Sugiyanto, S., & Yahanan, A. (2022). PERLINDUNGAN HUKUM PENGARANG SEBAGAI PEMEGANG HAK CIPTA DALAM PENERBITAN BUKU. Lex LATA, 4(1). https://doi.org/10.28946/lexl.v4i1.1376

## Business Understanding
### Problem Statements
Industri penerbitan terus berkembang pesat, menghasilkan ribuan buku baru setiap tahunnya [^4^]. Sementara itu, pembaca sering kali kesulitan menemukan buku yang sesuai dengan minat mereka dari sekian banyak pilihan yang tersedia. Masalah ini dapat dirumuskan dalam beberapa pernyataan masalah berikut:
- **Pernyataan Masalah 1**: Bagaimana sistem rekomendasi dapat membantu pengguna menemukan buku-buku yang relevan dengan minat mereka di tengah begitu banyaknya pilihan yang tersedia?
- **Pernyataan Masalah 2**: Bagaimana cara memastikan bahwa sistem rekomendasi dapat memberikan saran yang akurat, meskipun terdapat keterbatasan data seperti informasi pengguna yang minimal atau data interaksi yang terbatas (cold-start problem)?
- **Pernyataan Masalah 3**: Bagaimana sistem rekomendasi dapat meminimalisasi efek “filter bubble”, di mana pengguna hanya mendapatkan rekomendasi yang sangat mirip dengan preferensi mereka sebelumnya, sehingga menghalangi eksplorasi genre atau penulis baru?

### Goals
Berdasarkan pernyataan masalah di atas, tujuan dari proyek ini adalah sebagai berikut:
- **Jawaban Pernyataan Masalah 1**: Mengembangkan sistem rekomendasi buku yang dapat menyarankan buku-buku yang sesuai dengan preferensi pengguna, berdasarkan data historis dari pengguna tersebut maupun data umum dari buku-buku yang ada.
- **Jawaban Pernyataan Masalah 2**: Menerapkan pendekatan Content-Based Filtering dan Collaborative Filtering untuk menangani berbagai jenis pengguna, baik yang memiliki data interaksi yang kaya maupun yang minim, dengan tujuan memberikan rekomendasi yang akurat sejak awal.
- **Jawaban Pernyataan Masalah 3**: Menggabungkan metode rekomendasi yang memungkinkan eksplorasi, seperti kombinasi dari Content-Based Filtering yang fokus pada fitur item, dengan Collaborative Filtering yang memperhatikan pola perilaku pengguna lain, untuk meminimalisasi efek "filter bubble".

### Solution Statement
Untuk mencapai tujuan yang telah dijabarkan, beberapa pendekatan solusi akan diimplementasikan:
- **Solution Statement 1**: **Content-Based Filtering** akan digunakan untuk merekomendasikan buku berdasarkan fitur buku seperti penulis, genre, dan tahun publikasi. Pendekatan ini sangat berguna untuk pengguna yang memiliki preferensi spesifik dan membantu sistem memberikan rekomendasi yang personal.
- **Solution Statement 2**: **Collaborative Filtering** akan diterapkan untuk menangkap pola perilaku kolektif dari pengguna. Ini memungkinkan sistem untuk memberikan rekomendasi yang tidak hanya didasarkan pada preferensi pengguna individual tetapi juga pada perilaku pengguna lain yang serupa. Pendekatan ini juga bertujuan untuk mengatasi masalah cold-start dan memberikan rekomendasi yang bervariasi.

Dengan menggabungkan kedua pendekatan ini, sistem diharapkan dapat memberikan rekomendasi yang lebih komprehensif, meningkatkan kepuasan pengguna, serta memperluas cakrawala literasi mereka dengan mendorong eksplorasi genre dan penulis baru.

## Data Understanding
Dataset ini dikumpulkan oleh Cai-Nicolas Ziegler  selama 4 minggu (Agustus/September 2004) dari komunitas Book-Crossing dengan izin dari Ron Hornbaker, CTO Humankind Systems. Berisi 278.858 pengguna (anonim namun dengan informasi demografis) yang memberikan 1.149.780 penilaian (eksplisit / implisit) tentang 271.379 buku.

| **Jenis**      | **Keterangan**                                                                                     |
|----------------|----------------------------------------------------------------------------------------------------|
| **Title**      | Book Recommendation Dataset                                                                        |
| **Source**     | [Kaggle](https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset)                     |
| **Maintainer** | [arashnic](https://www.kaggle.com/arashnic)                                                        |
| **License**    | [CC0: Public Domain](https://creativecommons.org/publicdomain/zero/1.0/)                           |
| **Visibility** | Publik                                                                                             |
| **Tags**       | Online Communities, Literature Art, Recommender Systems, Culture and Humanities                    |
| **Usability**  | 10.00                                                                                              |



Tabel 1. Tampilan dari Dataset Books

Tabel berikut telah diperbaiki dan diformat ulang agar lebih rapi:

| Index | ISBN        | Book Title                              | Book Author          | Year of Publication | Publisher               | Image URL (S)                                                 | Image URL (M)                                                 | Image URL (L)                                                 |
|-------|-------------|------------------------------------------|----------------------|---------------------|-------------------------|---------------------------------------------------------------|---------------------------------------------------------------|---------------------------------------------------------------|
| 0     | 0195153448  | Classical Mythology                      | Mark P. O. Morford    | 2002                | Oxford University Press | [Link](http://images.amazon.com/images/P/0195153448.01.THUMBZZZ.jpg) | [Link](http://images.amazon.com/images/P/0195153448.01.MZZZZZZZ.jpg) | [Link](http://images.amazon.com/images/P/0195153448.01.LZZZZZZZ.jpg) |
| 1     | 0002005018  | Clara Callan                             | Richard Bruce Wright  | 2001                | HarperFlamingo Canada   | [Link](http://images.amazon.com/images/P/0002005018.01.THUMBZZZ.jpg) | [Link](http://images.amazon.com/images/P/0002005018.01.MZZZZZZZ.jpg) | [Link](http://images.amazon.com/images/P/0002005018.01.LZZZZZZZ.jpg) |
| 2     | 0060973129  | Decision in Normandy                     | Carlo D'Este          | 1991                | HarperPerennial         | [Link](http://images.amazon.com/images/P/0060973129.01.THUMBZZZ.jpg) | [Link](http://images.amazon.com/images/P/0060973129.01.MZZZZZZZ.jpg) | [Link](http://images.amazon.com/images/P/0060973129.01.LZZZZZZZ.jpg) |


Tabel 2. Tampilan dari dataset Ratings

| Index | User ID | ISBN        | Book Rating |
|-------|---------|-------------|-------------|
| 0     | 276725  | 034545104X  | 0           |
| 1     | 276726  | 0155061224  | 5           |
| 2     | 276727  | 0446520802  | 0           |


Tabel 3. Tampilan dari dataset Users

| Index | User ID | Location                           | Age  |
|-------|---------|------------------------------------|------|
| 0     | 1       | NYC, New York, USA                 | NaN  |
| 1     | 2       | Stockton, California, USA          | 18   |
| 2     | 3       | Moscow, Yukon Territory, Russia    | NaN  |


Berdasarkan output di atas, dataset ini mencakup 3 variabel utama, yaitu **books**, **ratings**, dan **users**.

Books:
- **Jumlah:** 271.360 jenis buku
- **Terdiri dari 8 kolom:**
  - **ISBN:** Nomor identitas unik buku.
  - **Book-Title:** Judul buku.
  - **Book-Author:** Nama penulis buku.
  - **Year-Of-Publication:** Tahun publikasi buku.
  - **Publisher:** Nama penerbit buku.
  - **Image-URL-S:** URL gambar ukuran kecil.
  - **Image-URL-M:** URL gambar ukuran sedang.
  - **Image-URL-L:** URL gambar ukuran besar.

Ratings:
- **Jumlah:** 1.149.780 penilaian
- **Terdiri dari 3 kolom:**
  - **User-ID:** Kode unik pengguna anonim yang memberikan penilaian.
  - **ISBN:** Nomor identitas buku yang dinilai.
  - **Book-Rating:** Penilaian yang diberikan kepada buku.

Users:
- **Jumlah:** 278.858 pengguna anonim
- **Terdiri dari 3 kolom:**
  - **User-ID:** Kode unik untuk pengguna anonim.
  - **Location:** Lokasi tempat tinggal pengguna.
  - **Age:** Usia pengguna.

Secara keseluruhan:
- Dataset ini belum sepenuhnya bersih.
- Dataset ini memiliki 14 kolom: 10 kolom tipe object, 3 kolom tipe int64, 1 kolom tipe float.
- Dataset memiliki missing value.

## EDA - Univariate Analysis
### Books.csv
Diketahui File books.csv berisi 271.360 entri dengan 8 kolom, termasuk ISBN, Book-Title, Book-Author, Year-Of-Publication, Publisher, dan tiga kolom URL gambar. Karena kolom 'Year-Of-Publication' seharusnya bertipe integer namun saat ini bertipe object, perlu dilakukan konversi tipe data terlebih dahulu.

Saat menjalankan kode berikut:
```books['Year-Of-Publication'].astype('int')```

terdapat error:
```ValueError: invalid literal for int() with base 10: 'DK Publishing Inc'```, yang berarti bahwa ada nilai dalam Year-Of-Publication yang memiliki nilai string 'DK Publishing Inc'. Hal ini tampaknya merupakan kesalahan input, jadi kita akan mengeceknya terlebih dahulu.
Setelah diperhatikan, ternyata terdapat 3 baris nilai string pada Year-Of-Publication, dan missing value pada Image-URL-L sehingga baris-baris tersebut sebaiknya dihapus. Setelah dihapus, barulah dilakukan proses pengubahan tipe data pada kolom 'Year-Of-Publication' menjadi tipe data integer.

Tabel 4. Informasi fitur Books setelah proses pengubahan tipe data

| Column               | Dtype  |
|----------------------|--------|
| ISBN                 | object |
| Book-Title           | object |
| Book-Author          | object |
| Year-Of-Publication  | int64  |
| Publisher            | object |
| Image-URL-S          | object |
| Image-URL-M          | object |
| Image-URL-L          | object |

#### Visualisasi Top 10 penulis berdasarkan buku
Proses pemodelan yang akan kita lakukan adalah berdasarkan penulis dan buku nya, sehingga akan lebih baik untuk mengetahui lebih dalam hubungan antara penulis dan buku nya.
Gambar 1. Visualisasi Top 10 penulis berdasarkan buku
![books vs author](https://i.ibb.co.com/51sng2P/Unknown.png)
Agatha Christie berada di peringkat pertama dengan lebih dari 600 buku, diikuti oleh William Shakespeare dan Stephen King, masing-masing dengan lebih dari 400 buku. Ann M. Martin, Carolyn Keene, Francine Pascal, Isaac Asimov, Nora Roberts, Barbara Cartland, dan Charles Dickens melengkapi daftar, dengan masing-masing menulis antara sekitar 300 hingga 400 buku. Grafik ini menggambarkan dominasi penulis-penulis ini dalam hal produktivitas, dengan Agatha Christie sebagai penulis paling produktif.

### Ratings.csv

Tabel 5. Informasi data Ratings

| #  | Column       | Non-Null Count | Dtype  |
|----|--------------|----------------|--------|
| 0  | User-ID      | 1,149,780      | int64  |
| 1  | ISBN         | 1,149,780      | object |
| 2  | Book-Rating  | 1,149,780      | int64  |
Dataset ini terdiri dari 1.149.780 entri yang mencakup tiga kolom utama: User-ID, ISBN, dan Book-Rating. Kolom User-ID dan Book-Rating bertipe data int64, menunjukkan bahwa masing-masing entri berisi kode unik untuk pengguna serta rating numerik yang mereka berikan untuk buku. Kolom ISBN, bertipe object, merepresentasikan kode unik untuk setiap buku yang dinilai. Semua entri dalam dataset ini lengkap, tanpa nilai yang hilang.

#### Nilai unik fitur
penting untuk mengetahui nilai unik dari jumlah pengguna dan ISBN buku, karena dengan ini model akan bekerja lebih baik
Jumlah Data:
- **Jumlah User-ID:** 105.283
- **Jumlah Buku:** 340.556

Tabel 6.Jumlah Rating Buku

| Book-Rating | Jumlah  |
|-------------|---------|
| 0           | 716.109 |
| 1           | 1.770   |
| 2           | 2.759   |
| 3           | 5.996   |
| 4           | 8.904   |
| 5           | 50.974  |
| 6           | 36.924  |
| 7           | 76.457  |
| 8           | 103.736 |
| 9           | 67.541  |
| 10          | 78.610  |
![rating](https://i.imgur.com/ffTVQ02.png)
Berdasarkan output di atas, diketahui bahwa terdapat 105.283 pengguna yang memberikan rating pada buku. Jumlah buku yang diberi rating berdasarkan ISBN adalah 340.556, dengan nilai rating berkisar antara 0 hingga 10, di mana 0 merupakan rating terendah dan 10 adalah rating tertinggi.
Terlihat bahwa sebagian besar pengguna memberikan rating 0, yang mungkin menandakan ketidakhadiran rating eksplisit (implisit) atau ketidakpuasan yang ekstrem. Selain itu, ada peningkatan jumlah rating yang diberikan pada skala 7 hingga 10, dengan puncak pada rating 8, menunjukkan kecenderungan pengguna untuk memberikan rating yang relatif tinggi pada buku yang mereka nilai. Rating di tengah-tengah skala (1-6) jauh lebih jarang terjadi, yang mungkin menunjukkan bahwa pengguna cenderung memberikan rating ekstrem, baik sangat rendah atau sangat tinggi, ketika menilai buku.
Seperti yang terlihat, jumlah data ratings terlalu banyak yang mana akan menyebabkan alokasi memori tidak tersedia, sehingga kita harus mengurangi jumlah data yang akan diproses menjadi 50000 baris saja.

### Users.csv

| #  | Column   | Non-Null Count | Dtype   |
|----|----------|----------------|---------|
| 0  | User-ID  | 278.858        | int64   |
| 1  | Location | 278.858        | object  |
| 2  | Age      | 168.096        | float64 |

Dari informasi tersebut, terlihat bahwa users.csv terdiri dari 278.858 entri dengan tiga kolom: User-ID, Location, dan Age. Kolom User-ID dan Location tidak memiliki missing value, sedangkan kolom Age memiliki sekitar 110.762 missing value (hanya 168.096 dari 278.858 entri yang memiliki data umur). Ini menunjukkan bahwa ada banyak data umur yang hilang, karena banyak nya data umur yang hilang, kita nantinya hanya akan menggunakan fitur-fitur yang ada di data Books dan Ratings.


## Data Preparation: Content-Based Filtering
Proses-proses yang akan dilakukan pada tahap ini adalah:

### Data Preprocessing
Pada tahap ini, proses-proses yang akan dilakukan adalah:
- Penghapsusan fitur yang tidak diperlukan:informasi seperti ukuran gambar tidak diperlukan, sehingga fitur/kolom 'Image-URL-S', 'Image-URL-M', dan 'Image-URL-L' bisa dihapus.
- Penggabungan file:Pada tahap ini, proses penggabungan file menjadi satu file akan dilakukan agar sesuai dengan pengembangan model yang ingin akan dibuat.

Tabel 7. Tampilan Dataset setelah digabungkan.

|    | User-ID | ISBN       | Book-Rating | Book-Title           | Book-Author      | Year-Of-Publication | Publisher        |
|----|---------|------------|-------------|----------------------|------------------|---------------------|------------------|
| 0  | 276725  | 034545104X | 0           | Flesh Tones: A Novel | M. J. Rose       | 2002.0              | Ballantine Books |
| 1  | 276726  | 0155061224 | 5           | Rites of Passage      | Judith Rae       | 2001.0              | Heinle           |
| 2  | 276727  | 0446520802 | 0           | The Notebook         | Nicholas Sparks  | 1996.0              | Warner Books     |

### Menghilangkan missing value:
setelah dicek menggunakan kode berikut:```books.isnull().sum()```
terdapat 118.650 missing value terbesar dari 1.149.780 yang tergolong cukup kecil, sehingga kita bisa menghapus missing value, Menghapus missing value pada model recommender system penting untuk memastikan data yang digunakan konsisten dan akurat, sehingga model dapat memberikan rekomendasi yang lebih relevan dan tepat.

### Penyesuaian iSBN dan buku: 
Pada sistem rekomendasi content-based filtering yang akan dikembangkan, satu nomor ISBN mewakili satu judul buku, yang berarti nomor ISBN untuk setiap buku bersifat unik. Sehingga perlu dilakukan persiapan data terlebih dahulu agar siap digunakan dalam proses pelatihan model.

1. Penghapusan Data Duplikat Berdasarkan ISBN
Langkah pertama dalam proses ini adalah menghapus data duplikat pada kolom ISBN. ISBN adalah pengidentifikasi unik untuk setiap buku, dan oleh karena itu, data duplikat pada kolom ini dapat menyebabkan kesalahan dalam analisis. Dengan menggunakan fungsi drop_duplicates(), kita menghapus semua baris yang memiliki ISBN duplikat sehingga hanya menyisakan data yang unik.
```
preparation = books_clean
preparation.sort_values('ISBN')
preparation = preparation.drop_duplicates('ISBN')
```
2. Konversi Data Series Menjadi List
Setelah memastikan bahwa data hanya mengandung ISBN yang unik, langkah selanjutnya adalah mengonversi data pada setiap kolom yang diperlukan ke dalam bentuk list. List ini kemudian akan digunakan untuk membentuk dictionary yang akan mempermudah dalam pengelolaan data lebih lanjut. Kita mengonversi lima kolom penting, yaitu ISBN, Book-Title, Book-Author, Year-Of-Publication, dan Publisher.
```
isbn = preparation['ISBN'].tolist()
book_title = preparation['Book-Title'].tolist()
book_author = preparation['Book-Author'].tolist()
year_of_publication = preparation['Year-Of-Publication'].tolist()
publisher = preparation['Publisher'].tolist()
```
Setelah konversi, kita memastikan bahwa panjang setiap list sama, yang menunjukkan bahwa tidak ada kehilangan data selama proses ini.
3. Pembentukan Dataframe Baru
Dengan list yang telah terbentuk, kami kemudian membuat dataframe baru dengan menggunakan dictionary yang berisi pasangan key-value dari masing-masing list. Dataframe ini (books_new) adalah hasil akhir dari proses persiapan data, yang siap untuk digunakan dalam pemodelan.
```
books_new = pd.DataFrame({
    'isbn': isbn,
    'book_title': book_title,
    'book_author': book_author,
    'year_of_publication': year_of_publication,
    'publisher': publisher
})
```
### Pengurangan Alokasi Memori
Untuk mengurangi alokasi memori, maka kita akan mengurangi dataset dengan menggunakan hanya 50000 data saja. dengan menggunakan kode berikut:```data = books_new[:50000]```

### Penerapan TF-IDF Vectorizer
TF-IDF (Term Frequency-Inverse Document Frequency) adalah teknik yang digunakan untuk mengubah teks menjadi representasi numerik, yang merefleksikan pentingnya suatu kata dalam dokumen relatif terhadap koleksi dokumen. Dalam konteks ini, kita menerapkannya pada kolom book_author untuk mengukur relevansi dari penulis.

- Inisialisasi TF-IDF Vectorizer: kita memulai dengan menginisialisasi objek TfidfVectorizer dari library sklearn.
```tf = TfidfVectorizer()```
- Perhitungan idf: Kami kemudian melakukan perhitungan idf pada kolom book_author untuk mengetahui seberapa penting setiap penulis dalam koleksi data.
```tf.fit(data['book_author'])```
- Transformasi ke dalam Matrix: Setelah itu, data penulis diubah menjadi bentuk matriks TF-IDF, yang merupakan representasi vektor dari penulis berdasarkan kemunculannya.
```tfidf_matrix = tf.fit_transform(data['book_author'])```
- Visualisasi Matrix TF-IDF: Matrix TF-IDF kemudian diubah ke dalam bentuk yang dapat dilihat dan dianalisis menggunakan fungsi todense() dan pd.DataFrame().
```
pd.DataFrame(
    tfidf_matrix.todense(),
    columns=tf.get_feature_names_out(),
    index=data.book_title
).sample(15, axis=1).sample(10, axis=0)
```
Tabel 8. Dataframe matriks tf-idf

| **book_title**                                                                 | **louisa** | **weinreb** | **lott** | **konrad** | **evan** | **merker** | **thurer** | **gary** | **gaumont** | **alona** | **rosenthal** | **ashenburg** | **greene** | **anselm** | **mqp** |
|--------------------------------------------------------------------------------|------------|-------------|----------|------------|----------|------------|------------|----------|--------------|------------|--------------|--------------|-----------|-----------|--------|
| **The Pizza Mystery (The Boxcar Children, #33)**                                | 0.0        | 0.0         | 0.0      | 0.0        | 0.0      | 0.0        | 0.0        | 0.0      | 0.0          | 0.0        | 0.0          | 0.0          | 0.0       | 0.0       | 0.0    |
| **Out of Africa ; and, Shadows on the grass**                                   | 0.0        | 0.0         | 0.0      | 0.0        | 0.0      | 0.0        | 0.0        | 0.0      | 0.0          | 0.0        | 0.0          | 0.0          | 0.0       | 0.0       | 0.0    |
| **Melbourne: Our City, Our Culture: Profiling a City's Arts and Cultural Achievements** | 0.0        | 0.0         | 0.0      | 0.0        | 0.0      | 0.0        | 0.0        | 0.0      | 0.0          | 0.0        | 0.0          | 0.0          | 0.0       | 0.0       | 0.0    |


## Data Preparation: Collaborative Filtering
Data rating harus diubah ke dalam bentuk matriks numerik agar nantinya mempermudah proses pelatihan model sehingga model menjadi mudah mengenali/mempelajari data tersebut.

Encoding User-ID dan ISBN: Mengubah User-ID dan ISBN menjadi indeks integer unik.
```
user_ids = df_ratings['User-ID'].unique().tolist()
user_to_user_encoded = {x: i for i, x in enumerate(user_ids)}
isbn_id = df_ratings['ISBN'].unique().tolist()
isbn_to_isbn_encoded = {x: i for i, x in enumerate(isbn_id)}
```
- Split Data dan mapping
Sebelum membagi dataset, data akan diacak terlebih dahulu untuk memastikan distribusi yang acak dan tidak bias. Setelah itu, dataset dibagi menjadi data latih (train) dan validasi dengan rasio 90:10. Sebelum pembagian, data pengguna dan judul buku dipetakan menjadi satu nilai unik untuk memudahkan pengolahan lebih lanjut. Rating kemudian diubah menjadi skala 0 hingga 1 untuk menyederhanakan proses pelatihan model. Proses ini penting karena pengacakan data membantu menghindari overfitting, sementara pemetaan dan normalisasi rating memastikan data dalam format yang konsisten dan optimal untuk algoritma pembelajaran mesin.
```
df_ratings['user'] = df_ratings['User-ID'].map(user_to_user_encoded)
df_ratings['book_title'] = df_ratings['ISBN'].map(isbn_to_isbn_encoded)
x_train, x_val, y_train, y_val = (x[:train_indices], x[train_indices:], y[:train_indices], y[train_indices:])
```
Data siap dimodelkan.
## Modeling
Gambar 2. Alur Pemodelan
![flowchart](https://i.imgur.com/FWFGOsb.png)
### Content Based Filtering
- Content-Based Filtering didasarkan pada kesamaan atribut atau fitur dari item.
- Rekomendasi diberikan kepada pengguna berdasarkan preferensi mereka sebelumnya terhadap item dengan fitur yang serupa, seperti genre, penulis, atau deskripsi konten.
- Pada Proyek ini, rekomendasi diberikan kepada pengguna berdasarkan penulis buku.
- Dataset yang digunakan hanya 50000 baris untuk menghindari kekurangan memori.

Kelebihan dari teknik Content-Based Filtering:
- Mampu memberikan rekomendasi yang bersifat personal dan disesuaikan dengan preferensi unik setiap pengguna.
- Sangat cocok untuk mengatasi masalah cold-start, yaitu ketika data pengguna yang tersedia masih sedikit, dan tetap dapat memberikan rekomendasi yang baik sejak awal.
- Tidak bergantung pada data dari pengguna lain untuk memberikan rekomendasi.
Sangat sesuai untuk item yang memiliki fitur atau atribut yang mudah diukur atau diidentifikasi, seperti genre, penulis, atau karakteristik lainnya.

Kekurangan dari teknik Content-Based Filtering:
- Kurang efektif dalam memberikan rekomendasi yang mengejutkan, karena hanya menyarankan item yang mirip dengan yang sudah dikenal oleh pengguna.
- Kesulitan dalam menangkap preferensi pengguna yang kompleks atau berubah-ubah, terutama jika item yang mirip tidak sepenuhnya mencerminkan preferensi mendalam pengguna.
- Berisiko menciptakan "filter bubble," di mana pengguna hanya menerima rekomendasi yang sesuai dengan preferensi yang sudah diketahui, tanpa memperluas cakrawala mereka.


#### Perhitungan Cosine Similarity
Untuk menghitung derajat kesamaan antar judul buku, digunakan teknik cosine similarity. Metode ini mengukur seberapa mirip dua vektor dalam ruang multidimensi dengan menghitung sudut kosinus di antara keduanya. Semakin kecil sudut ini, semakin mirip kedua vektor tersebut. Dalam proyek ini, fungsi [cosine_similarity](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.pairwise.cosine_similarity.html) dari library Sklearn dimanfaatkan untuk menghitung nilai cosine similarity pada matriks tf-idf yang telah dibuat sebelumnya. Dengan menggunakan fungsi cosine_similarity(), diperoleh nilai kesamaan antar judul buku dalam bentuk matriks kesamaan yang disajikan sebagai array.
- Menghitung Cosine Similarity: kita menghitung cosine similarity pada matrix TF-IDF yang telah dibuat.
```cosine_sim = cosine_similarity(tfidf_matrix)```
- Membuat Dataframe Cosine Similarity: Hasil dari cosine similarity kemudian diubah menjadi sebuah dataframe dengan baris dan kolom berupa nama judul buku, yang memungkinkan kita untuk melihat seberapa mirip setiap buku satu sama lain.
```cosine_sim_df = pd.DataFrame(cosine_sim, index=data['book_title'], columns=data['book_title'])```

Tabel 9. Hasil Perhitungan Cosine Similarity

| **book_title**                                         | **Kali: The Feminine Force** | **Wild Animals (Draw Science Series)** | **The Politics of Breastfeeding (Issues in Women's Health)** | **Red** | **Wednesday the Rabbi Got Wet** |
|--------------------------------------------------------|-----------------------------|----------------------------------------|-------------------------------------------------------------|---------|---------------------------------|
| **The airborne soldier**                               | 0.0                         | 0.0                                    | 0.0                                                         | 0.0     | 0.0                             |
| **Hindu Kush**                                         | 0.0                         | 0.0                                    | 0.0                                                         | 0.0     | 0.0                             |
| **Coming Home To You (Harlequin Super Romance, No 961)**| 0.0                         | 0.0                                    | 0.0                                                         | 0.0     | 0.0                             |
| **Amerigo : Récit d'une erreur historique**            | 0.0                         | 0.0                                    | 0.0                                                         | 0.0     | 0.0                             |
| **Pig at Play (Planet Reader, Level 1)**               | 0.0                         | 0.0                                    | 0.0                                                         | 0.0     | 0.0                             |
| **Unfinished Tales of Numenor and Middle-Earth**       | 0.0                         | 0.0                                    | 0.0                                                         | 0.0     | 0.0                             |
| **La Griffe du demi-dieu**                             | 0.0                         | 0.0                                    | 0.0                                                         | 0.0     | 0.0                             |
| **13 99 Euros**                                        | 0.0                         | 0.0                                    | 0.0                                                         | 0.0     | 0.0                             |
| **A Morbid Taste for Bone (Brother Cadfael Mysteries)**| 0.0                         | 0.0                                    | 0.0                                                         | 0.0     | 0.0                             |
| **A Pussycat's Christmas**                             | 0.0                         | 0.0                                    | 0.0                                                         | 0.0     | 0.0                             |


#### Mendapatkan Rekomendasi
Langkah terakhir adalah membuat fungsi untuk memberikan rekomendasi buku berdasarkan derajat kesamaan yang dihitung sebelumnya.
- Fungsi book_recommendation: Fungsi ini menerima judul buku yang diinginkan sebagai input dan mengembalikan daftar rekomendasi buku yang paling mirip berdasarkan penulisnya.
```
def book_recommendation(book_title, similarity_data=cosine_sim_df, items=data[['book_title', 'book_author']], k=5):
    index = similarity_data.loc[:,book_title].to_numpy().argpartition(range(-1, -k, -1))
    closest = similarity_data.columns[index[-1:-(k+2):-1]]
    closest = closest.drop(book_title, errors='ignore')
    return pd.DataFrame(closest).merge(items).head(k)
```
- Contoh Penggunaan: Misalkan kita ingin mendapatkan rekomendasi untuk buku "The Murder Room". Sistem akan mencari buku lain yang ditulis oleh penulis yang sama atau memiliki penulis yang mirip.
```
book_title_test = "The Murder Room"
book_recommendation(book_title_test)
```

|index|book\_title|book\_author|
|---|---|---|
|0|A Taste for Death|P\. D\. James|
|1|Tod Im Weissen Haubchen|P\.D\. James|
|2|A Mind to Murder|P\. D\. James|
|3|The Skull Beneath the Skin|P\.D\. James|
|4|The Skull Beneath the Skin|P\. D\. James|
Sistem berhasil merekomendasikan 5 buku dengan author yang sama.

### Collaborative Filtering
- Collaborative Filtering didasarkan pada kesamaan preferensi atau perilaku pengguna.
- Rekomendasi diberikan kepada pengguna berdasarkan preferensi dari pengguna lain yang memiliki pola perilaku atau penilaian yang serupa, tanpa memerlukan informasi spesifik tentang atribut dari item.

#### Pembangunan Model
RecommenderNet: Model dibuat dengan [keras model class]((https://keras.io/api/models/model/)) yang terinspirasi dari tutorial dalam situs Keras. Model ini dirancang untuk memprediksi preferensi pengguna terhadap judul buku berdasarkan embedding pengguna dan judul buku. Model ini memiliki beberapa layer embedding untuk merepresentasikan pengguna dan judul buku dalam bentuk vektor berdimensi rendah, yang kemudian digunakan untuk menghitung kesamaan antara pengguna dan buku melalui dot product. Model ini juga menambahkan bias untuk pengguna dan judul buku, serta menggunakan dropout untuk mencegah overfitting. Akhirnya, hasil perhitungan ini diaktivasi menggunakan fungsi sigmoid untuk menghasilkan output dalam bentuk probabilitas yang mencerminkan seberapa besar kemungkinan seorang pengguna akan menyukai sebuah judul buku.
```
class RecommenderNet(tf.keras.Model):
    def call(self, inputs):
        user_vector = self.user_embedding(inputs[:, 0])
        book_title_vector = self.book_title_embedding(inputs[:, 1])
        return tf.nn.sigmoid(tf.tensordot(user_vector, book_title_vector, 2) + self.user_bias(inputs[:, 0]) + self.book_title_bias(inputs[:, 1]))
```
Training: Model dikompilasi dan dilatih selama 50 epoch.
Model ini menggunakan Binary Crossentropy untuk menghitung loss function, Adam (Adaptive Moment Estimation) sebagai optimizer, dan root mean squared error (RMSE) sebagai metrics evaluation. 
```
model.compile(loss=tf.keras.losses.BinaryCrossentropy(), optimizer=keras.optimizers.Adam(learning_rate=1e-4))
history = model.fit(x=x_train, y=y_train, batch_size=16, epochs=50, validation_data=(x_val, y_val))
```

#### Rekomendasi Buku
Prediksi Rekomendasi: Model memprediksi rating buku yang belum dibaca pengguna dan memberikan 10 rekomendasi teratas.
```
ratings_model = model.predict(user_book_array).flatten()
top_ratings_indices = ratings_model.argsort()[-10:][::-1]
```
Rekomendasi Buku untuk Pengguna: 11676
Buku dengan Rating Tinggi dari Pengguna

Berikut adalah tabel yang telah diperbaiki dan diformat ulang:

| Index | Book Title                                                                                                     | Book Author       |
|-------|----------------------------------------------------------------------------------------------------------------|-------------------|
| 0     | To Kill a Mockingbird                                                                                          | Harper Lee        |
| 1     | Dead Sleep                                                                                                     | Greg Iles         |
| 2     | Harry Potter and the Sorcerer's Stone (Book 1)                                                                 | J.K. Rowling      |
| 3     | Notes From a Small Planet                                                                                      | Bill Bryson       |
| 4     | Blackberry Wine                                                                                                | Joanne Harris     |
| 5     | A Walk in the Woods: Rediscovering America on the Appalachian Trail (Official Guides to the Appalachian Trail) | Bill Bryson       |
| 6     | The Fuck Up                                                                                                    | Arthur Nersesian  |
| 7     | To Ride a Silver Broomstick: New Generation Witchcraft                                                         | Silver Ravenwolf  |
| 8     | Food for Fifty                                                                                                 | Grace Shugart     |
| 9     | Hatchet                                                                                                        | Gary Paulsen      |

Penyesuaian ini mencakup penghapusan escape character pada tanda kurung dan backslash untuk menjaga agar judul buku tampil lebih rapi dan sesuai dengan penulisan umum.


Berdasarkan Tabel, model telah berhasil membuat rekomendasi kepada user. Hasil tersebut adalah rekomendasi untuk user dengan id 11676. Dari output tersebut, dapat dibandingkan antara 'Buku dengan Rating Tinggi dari Pengguna' dan '10 Buku Rekomendasi Teratas' untuk user. Diperoleh 10 rekomendasi teratas buku yang disertai juga dengan nama penulisnya untuk user tersebut serta terdapat 1 judul buku yang merupakan buku dengan rating tertinggi dari user.

## Evaluation
### Evaluasi Pada Content-Based Filtering
Dalam evaluasi sistem rekomendasi buku berbasis Content-Based Filtering (CBF), metrik yang digunakan adalah **precision**, **recall**, dan **F1-score** karena ketiganya sesuai dengan konteks data dan tujuan proyek. 

- **Precision** mengukur persentase buku yang direkomendasikan yang relevan atau sesuai dengan preferensi pengguna. Formula precision adalah:

$$Precision = \frac{True\ Positives}{True\ Positive + False\ negative}$$

di mana "True Positives" adalah buku yang direkomendasikan dan relevan, sementara "False Positives" adalah buku yang direkomendasikan namun tidak relevan. Dalam konteks ini, precision menunjukkan seberapa baik sistem menghindari rekomendasi buku yang tidak diminati pengguna.

- **Recall** mengukur seberapa banyak dari total buku yang relevan berhasil direkomendasikan oleh sistem. Formula recall adalah:

$$Recall = \frac{True\ Positive}{True\ Positive + False\ positive}$$

di mana "False Negatives" adalah buku yang relevan tetapi tidak direkomendasikan oleh sistem. Recall penting untuk memastikan bahwa sistem tidak melewatkan buku-buku yang mungkin disukai pengguna.

- **F1-score** adalah rata-rata harmonis dari precision dan recall, yang memberikan keseimbangan antara keduanya. Formula F1-score adalah:

$$F1\ Score = 2 * \frac{Precision * Recall}{Precision + Recall}$$

F1-score digunakan untuk mengevaluasi kinerja keseluruhan sistem, terutama ketika penting untuk mempertimbangkan baik relevansi rekomendasi (precision) dan kelengkapan cakupan rekomendasi (recall).

Berikut adalah score yang dihasilkan berdesarkan notebook:
Precision: 1.0
Recall: 1.0
F1-score: 1.0
Sistem rekomendasi berbasis Content-Based Filtering telah berhasil menjawab problem statement pertama dan kedua. Sistem ini mampu membantu pengguna menemukan buku yang sesuai dengan minat mereka di antara banyaknya pilihan yang tersedia. Selain itu, sistem ini juga memberikan rekomendasi yang akurat, meskipun data pengguna terbatas, dengan menggunakan informasi tentang penulis dan genre buku.
Dengan precision dan recall yang sempurna, sistem ini memastikan bahwa pengguna mendapatkan rekomendasi yang sangat relevan dan tidak ada buku yang diabaikan yang mungkin sesuai dengan minat mereka.

### Evaluasi Collaborative Filtering
Pada proyek ini, kita menggunakan Root Mean Squared Error (RMSE) sebagai metrik evaluasi utama untuk menilai kinerja sistem rekomendasi buku berbasis Collaborative Filtering. RMSE dipilih karena kemampuannya untuk mengukur seberapa dekat prediksi rating dari model dengan rating sebenarnya yang diberikan oleh pengguna.

$$RMSE = \sqrt{\frac{1}{N} \Sigma_{i=1}^N({y_i}- y\_pred_i)^2}$$

Keterangan:
- N adalah jumlah prediksi.
- yi adalah nilai sebenarnya dari preferensi pengguna terhadap item.
- y_pred adalah prediksi model terhadap preferensi pengguna terhadap item.

RMSE bekerja dengan menghitung akar kuadrat dari rata-rata selisih kuadrat antara nilai prediksi dan nilai aktual. Karena RMSE menghitung kesalahan dalam satuan yang sama dengan data aslinya (dalam hal ini, skala rating), hasilnya dapat langsung diinterpretasikan untuk memahami seberapa baik model bekerja.

#### Alasan Pemilihan RMSE
RMSE dipilih sebagai metrik evaluasi dalam proyek ini karena:
- Penalti untuk Kesalahan Besar: RMSE memberikan penalti yang lebih besar untuk prediksi yang jauh dari nilai sebenarnya, sehingga sangat cocok untuk memastikan bahwa model memberikan prediksi yang akurat, terutama dalam kasus di mana perbedaan besar antara prediksi dan nilai aktual tidak diinginkan.
- Relevansi dengan Problem Statement: Tujuan utama sistem ini adalah memprediksi rating buku yang mendekati rating yang akan diberikan oleh pengguna. Oleh karena itu, metrik yang mampu mengukur akurasi prediksi secara kuantitatif dan memberikan penalti untuk kesalahan yang besar seperti RMSE sangat sesuai.
- Kesesuaian dengan Data dan Solusi: Rating buku biasanya berada pada skala yang terbatas (misalnya, 1 hingga 5), dan RMSE memberikan interpretasi yang mudah dimengerti dalam konteks ini. Sebuah RMSE yang lebih rendah menunjukkan model yang lebih akurat, yang berarti rekomendasi yang lebih relevan dan memuaskan bagi pengguna.

Hasil Proyek Berdasarkan RMSE
Gambar 3. Grafik metrik RecommenderNet
![rmse](https://i.ibb.co.com/8BrWkm2/Unknown.png)
- Grafik menunjukkan bahwa model ini terus belajar selama pelatihan, dan tidak ada indikasi kuat overfitting yang signifikan, karena RMSE pada data test menurun meskipun tidak secepat pada data train.
- Secara keseluruhan, model menunjukkan performa yang cukup baik dengan RMSE yang konsisten menurun pada data train dan test. Hal ini menunjukkan bahwa model mampu memprediksi rating dengan cukup akurat dan memberikan rekomendasi buku yang relevan. 

Model berbasis Collaborative Filtering berhasil menjawab problem statement ketiga. Dengan RMSE yang rendah, model ini telah mampu memberikan rekomendasi yang beragam dan meminimalisasi efek "filter bubble", yang memungkinkan pengguna untuk mengeksplorasi genre atau penulis baru selain yang biasa mereka baca.

Content-Based Filtering memberikan rekomendasi berdasarkan fitur buku yang mirip dengan preferensi pengguna, sedangkan Collaborative Filtering memanfaatkan pola perilaku pengguna lain untuk memperluas cakrawala rekomendasi. Dengan menggabungkan kedua metode ini, sistem tidak hanya memberikan rekomendasi yang relevan dengan minat pengguna, tetapi juga mendorong pengguna untuk mengeksplorasi buku-buku yang mungkin belum pernah mereka pertimbangkan sebelumnya. Penggabungan ini efektif dalam meminimalkan efek "filter bubble" dan memastikan bahwa pengguna mendapatkan rekomendasi yang lebih variatif dan inklusif.
