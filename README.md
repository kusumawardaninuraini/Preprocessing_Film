# Proyek Analisis Data Film: Tahap Preprocessing Data
Repositori ini berisi script Python untuk melakukan pembersihan dan persiapan (preprocessing) data pada dataset film. Proses ini adalah langkah fundamental dalam alur kerja data science untuk memastikan data yang digunakan dalam analisis dan pemodelan berkualitas tinggi, konsisten, dan bebas dari kesalahan.

**Konteks**

Dalam industri perfilman, analisis data memegang peranan krusial untuk memahami faktor-faktor yang menentukan kesuksesan sebuah film. Metrik seperti pendapatan kotor (gross), anggaran (budget), dan rating penonton (skor IMDb) adalah indikator utama. Namun, data mentah yang dikumpulkan seringkali tidak terstruktur, tidak lengkap, dan mengandung banyak inkonsistensi. Tanpa proses pembersihan yang tepat, setiap analisis atau model prediktif yang dibangun akan menghasilkan wawasan yang tidak akurat dan menyesatkan.

**Problem Statement**

Analis data sering dihadapkan pada dataset film mentah yang memiliki berbagai masalah, antara lain:
- Data Hilang (Missing Values): Informasi penting seperti pendapatan dan anggaran.
- Inkonsistensi Data: Kesalahan penulisan atau format yang tidak seragam pada data kategorikal
- Data Tidak Valid: Terdapat nilai yang secara logis tidak mungkin, seperti durasi film negatif, skor IMDb di luar skala 1-10, atau kesalahan ketik pada tahun rilis.
- Outlier: Adanya data dengan nilai ekstrem yang tidak wajar (misalnya, durasi film hanya 5 menit) yang dapat mengganggu hasil analisis statistik.

Masalah-masalah ini harus diatasi sebelum data dapat digunakan untuk tujuan analisis yang lebih dalam, seperti mencari korelasi antara anggaran dan pendapatan, atau memprediksi rating film berdasarkan sutradara dan genre. Kualitas data yang buruk akan menghasilkan kesimpulan yang salah dan keputusan bisnis yang tidak efektif.

**Tujuan**

Tujuan dari proyek ini adalah melakukan preprocessing data pada dataset film untuk mengubahnya dari data mentah menjadi dataset yang bersih, terstruktur, dan siap pakai. Secara spesifik, tujuannya adalah:
- Membersihkan dan menyeragamkan data untuk memastikan akurasi dan konsistensi.
- Mengatasi nilai-nilai yang hilang dan tidak valid untuk menciptakan dataset yang lengkap dan logis.
- Menangani outlier statistik agar analisis di masa depan tidak terdistorsi oleh data yang anomali.
- Menghasilkan file movie_dataset_cleaned.csv yang dapat diandalkan sebagai fondasi untuk analisis deskriptif, visualisasi data, atau pemodelan machine learning.

**Dataset**

Dataset asli (movie_sample_dataset.csv) berisi berbagai informasi tentang film. Variabel-variabel kunci yang menjadi fokus dalam proses pembersihan ini meliputi:

- director_name: Nama sutradara film.
- duration: Durasi film dalam menit.
- gross: Pendapatan kotor film di box office.
- budget: Anggaran produksi film.
- title_year: Tahun rilis film.
- imdb_score: Rating film di IMDb (skala 1-10).
- country: Negara asal produksi film.
- color: Format film (berwarna atau hitam putih).
- genres: Kategori genre film (bisa lebih dari satu).
- language: Bahasa yang digunakan dalam film
- actors: Aktor-aktor dan aktris-aktris yang berakting di film.
- movie_facebook_likes: Banyaknya like film di facebook.
- movie_title: Judul film.

**Metodologi Preprocessing**

Script Python yang disediakan (preprocess_movie.py) melakukan serangkaian langkah pembersihan dan transformasi data secara sistematis:
- Penanganan Nilai Hilang: Menghapus baris yang memiliki data krusial seperti gross dan budget.
- Penanganan Nilai Tidak Valid: Memfilter dan menghapus data dengan nilai di luar rentang logis (misalnya, imdb_score < 1 atau duration < 60).
- Koreksi Data: Memperbaiki kesalahan input, seperti mengubah tahun 205 menjadi 2015 dan 202 menjadi 2012.
- Normalisasi Teks: Melakukan standarisasi semua data teks (seperti director_name, movie_title, language) menjadi format lowercase.
- Transformasi Data: Mengubah tipe data kolom numerik menjadi integer dan memecah kolom genres menjadi beberapa kolom dummy (One-Hot Encoding) untuk analisis lebih lanjut.

**Hasil**

Hasil akhir dari proses ini adalah sebuah file CSV baru bernama movie_dataset_cleaned.csv. Dataset ini secara signifikan lebih bersih, konsisten, dan andal dibandingkan dengan data mentahnya. Semua kolom telah divalidasi, dan masalah umum seperti nilai hilang, kesalahan input, dan data tidak valid.

**Rekomendasi Langkah Selanjutnya**

Dengan dataset yang sudah bersih ini, beberapa analisis lanjutan yang dapat dilakukan antara lain:
- Analisis Statistik Deskriptif: Menghitung korelasi antara anggaran, durasi, dan pendapatan film.
- Visualisasi Data: Membuat grafik untuk melihat tren film berdasarkan tahun, genre, atau sutradara.
- Pemodelan Prediktif: Membangun model machine learning untuk memprediksi pendapatan atau skor IMDb sebuah film berdasarkan fitur-fitur yang ada.
