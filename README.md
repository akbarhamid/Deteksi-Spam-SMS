# Deteksi Spam SMS

## Deskripsi
Deteksi SMS Spam merupakan klasifikasi pesan teks pada short message service (sms) untuk mengetahui pesan yang diterima merupakan spam atau bukan. Aplikasi yang dirancang merupakan aplikasi machine learning sederhana berbasis NLP pada pemrograman web yang dibuat menggunakan Flask.

## Dataset
Dataset yang digunakan berasal dari UCI Machine Learning di kaggle.com. Dataset berupa koleksi spam SMS yang diberi tag SMS dan berisi satu set pesan SMS dalam bahasa Inggris yang terdiri dari 5.5.74 pesan dan ditandai sebagai ham (legitimate) atau spam.
> https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset

## Preprocessing
Langkah-langkah yang digunakan dalam preprocessing data adalah sebagai berikut:
1. Cleaning text
- Mengekstrak hanya karakter alfabet dengan menghapus tanda baca dan angka
- Mengubah karakter menjadi huruf kecil
2. Tokenizing the sms
- Memecah data yang kompleks menjadi unit yang lebih kecil yang disebut token. Hal ini dilakukan dengan memecah paragraf menjadi kalimat dan kalimat menjadi kata-kata.
3. Removing the stopwords
- Stopwords adalah kata yang sering muncul (seperti beberapa, is, an, dll). Kata-kata ini memiliki makna dalam struktur kalimat, tetapi tidak banyak berkontribusi pada pemrosesan bahasa di NLP. Untuk tujuan menghilangkan redundansi dalam pemrosesan kami, saya menghapusnya. Pustaka NLTK memiliki satu set stopword default yang akan kami hapus.
4. Stemming the words
- Stemming dan Lemmatization adalah teknik Text Normalization (atau kadang disebut Word Normalization) dalam bidang NLP. Lemmatization adalah proses sampai pada lemma dari sebuah kata. 
5. Joining the stemmed words (Vectorization/TF-IDF)
- Membuat korpus teks lemmatized
- Mengubah korpus dalam bentuk vektor

## Metode Klasifikasi
Metode yang digunakan untuk mendeteksi atau mengklasifikasi spam SMS atau bukan adalah menggunakan metode multinomial naive bayes. Berikut merupakan langkah-langkah yang digunakan:
1. Memasukkan data hasil TF-IDF
2. Hitung Log P(c)
3. Hitung Log P(XK|C) terhadap kelas target
4. Hitung max value dari penjumlahan Log P(c) dan Log P(Xk|C)
5. Hasil klasifikasi spam SMS
m (legitimate) atau spam.
