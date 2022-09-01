# Laporan Proyek Machine Learning - Ahmad Reinaldi Akbar

## Project Overview

Wine merupakan salah satu jenis minuman beralkohol yang banyak dikonsumsi oleh orang-orang di seluruh dunia. Untuk menentukan kualitas dari wine ada beberapa hal yang perlu diperhatikan seperti kandungan klorida, sulfat, PH, dan lain sebagainya. Proyek ini dibuat untuk menentukan kualitas dari sebuah wine berdasarkan parameter-parameter yang ada. Warning! Proyek ini hanya bertujuan untuk pengujian algoritma machine learning.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Jelaskan mengapa dan bagaimana masalah tersebut harus diselesaikan
- Menyertakan hasil riset terkait atau referensi. Referensi yang diberikan harus berasal dari sumber yang kredibel dan author yang jelas.
  
  Format Referensi: [Judul Referensi](https://scholar.google.com/) 

## Business Understanding

Proyek ini berisi pembuatan analisis prediksi pada dataset wine. Wine akan diprediksi kualitasnya berdasarkan kandungan yang terdapat dalam wine tersebut.

Bagian laporan ini mencakup:

### Problem Statements

Masalah yang akan diselesaikan:
- Metode machine learning apa yang harus digunakan untuk menyelesaikan kasus prediksi kualitas wine?
- Apa Algoritma yang paling sesuai untuk menyelesaikan kasus prediksi kualitas wine tersebut?

### Goals

Tujuan yang ingin dicapai:
- Metode machine learning yang digunakan adalah metode supervised learning regresi karena dataset yang digunakan merupakan dataset yang berlabel dan output yang diinginkan berupa angka prediksi
- Algoritma yang akan dipakai untuk pengujian menggunakan 3 algoritma yaitu KNN, Random Forest, dan Boosting Algorithm. Dan akan dilihat algoritma mana yang paling mendekati hasil prediksinya.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Statement” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution statement. Misalnya, menggunakan dua atau lebih algoritma untuk mencapai solusi yang diinginkan atau melakukan improvement pada baseline model dengan hyperparameter tuning.
    - Solusi yang diberikan harus dapat terukur dengan metrik evaluasi.

## Data Understanding
Dataset yang digunakan pada proyek ini merupakan dataset mengenai kualitas wine yang diunduh dari UCI Machine Learning Repository Link: (https://archive.ics.uci.edu/ml/machine-learning-databases/wine-quality/).
Berikut beberapa variabel yang terdapat di dalam dataset wine quality UCI Machine Learning Repositories:
1 - fixed acidity : kandungan asam organik volatilitas rendah seperti asam malat, laktat, tartarat atau sitrat
2 - volatile acidity : ukuran asam lemak dengan berat molekul rendah (atau dapat disuling dengan uap)
3 - citric acid : kandungan asam organik pada minuman dengan formula HOC(CO2H)
4 - residual sugar : kandungan gula 
5 - chlorides : kandungan klodira
6 - free sulfur dioxide : tingkat kandungan sulfur dioksida
7 - total sulfur dioxide : jumlah sulfur dioksida
8 - density : massa jenis minuman
9 - pH : tingkat keasaman minuman
10 - sulphates : kandungan asam sulfat
11 - alcohol : kandungan alkohol minuman
Variabel Output:
12 - quality (Nilai antara 0 sampai 10)

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Model yang telah dibuat dapat memprediksi nilai dari qualitas wine yang ada pada dataset. Karena pada proyek kali ini menggunakan 3 jenis algoritma, maka akan dibandingkan hasil prediksi dari masing-masing algoritma. Metrik yang digunakan pada setiap algoritma adalah MSE atau mean squared error.

Mse merupakan metrik yang menghitung jumlah selisih kuadrat rata-rata nilai sebenarnya dengan nilai prediksi. MSE didefinisikan dalam persamaan berikut:
Gambar MSE
Keterangan:
N = jumlah dataset
yi = nilai sebenarnya
y_pred = nilai prediksi

Gambar MSE1
Gambar MSE2

Terlihat, berdasarkan gambar prediksi tersebut, algoritma yang memberikan hasil prediksi paling mendekati adalah Boosting Algorithm.
