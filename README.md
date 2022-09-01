# Laporan Proyek Machine Learning - Ahmad Reinaldi Akbar

## Project Overview

Wine merupakan salah satu jenis minuman beralkohol yang banyak dikonsumsi oleh orang-orang di seluruh dunia. Salah satu negara pengekspor wine terbanyak adalah portugal. Untuk mengekspor wine tersebut portugal memerlukan jenis wine yang berkualitas tinggi untuk dijual ke berbagai negara di dunia. Wine yang berkualitas dihasilkan dari sertifikasi dan pengujian yang ketat. Sertifikasi wine umumnya menggunakan pengujian physicochemical dan test sensor seperti kandungan klorida, sulfat, PH, dan lain sebagainya [1]. Data-data pengujian telah banyak didapatkan pada saat pengujian, namun jika ingin menentukan kualitas wine tersebut secara manual maka akan memerlukan waktu yang lama. Sehingga dibuatlah proyek ini untuk menentukan kualitas dari wine berdasarkan data pengujian kualitas wine. Proyek ini menggunakan machine learning dengan metode supervised learning-regresi.
  
[Modeling wine preferences by data mining from physicochemical properties](https://www.sciencedirect.com/science/article/abs/pii/S0167923609001377?via%3Dihub) 

## Business Understanding

Proyek ini berisi pembuatan analisis prediksi pada dataset wine. Wine akan diprediksi kualitasnya berdasarkan kandungan yang terdapat dalam wine tersebut.

### Problem Statements

Masalah yang akan diselesaikan:
- Metode machine learning apa yang harus digunakan untuk menyelesaikan kasus prediksi kualitas wine?
- Apa Algoritma yang paling sesuai untuk menyelesaikan kasus prediksi kualitas wine tersebut?

### Goals

Tujuan yang ingin dicapai:
- Metode machine learning yang digunakan adalah metode supervised learning regresi karena dataset yang digunakan merupakan dataset yang berlabel dan output yang diinginkan berupa angka prediksi
- Algoritma yang akan dipakai untuk pengujian menggunakan 3 algoritma yaitu KNN, Random Forest, dan Boosting Algorithm. Dan akan dilihat algoritma mana yang paling mendekati hasil prediksinya.

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

Untuk lebih jelasnya data yang terdapat pada dataset tersebut dapat dilihat pada gambar berikut:

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Model Machine Learning yang digunakan pada proyek ini ada 2 jenis algoritma yang akan dibandingkan berdasarkan hasil prediksi masing-masing algoritma. Algoritma yang pertama digunakan adalah algoritma random forest dan algoritma boosting.

Pada Algoritma Random Forest, parameter yang digunakan adalah sebagai berikut
- n_estimators=25
- max_depth=32
- random_state=16
- n_jobs=-1
Untuk lebih jelasnya dapat dilihat pada cuplikan kode dibawah ini:
Gambar model random forest

Sedangkan pada Algoritma Boosting, parameter yang digunakan adalah sebagai berikut
- learning rate = 
- random state =
Untuk lebih jelasnya dapat dilihat pada cuplikan kode dibawah ini:
Gambar model Algoritma boosting

## Evaluation
Model yang telah dibuat dapat memprediksi nilai dari qualitas wine yang ada pada dataset. Karena pada proyek kali ini menggunakan 3 jenis algoritma, maka akan dibandingkan hasil prediksi dari masing-masing algoritma. Metrik yang digunakan pada setiap algoritma adalah MSE atau mean squared error.

Mse merupakan metrik yang menghitung jumlah selisih kuadrat rata-rata nilai sebenarnya dengan nilai prediksi. MSE didefinisikan dalam persamaan berikut:

![image](https://user-images.githubusercontent.com/62003049/187825463-410f0055-ac49-4af8-a56b-a5e280e62eda.png)

Keterangan:
N = jumlah dataset
yi = nilai sebenarnya
y_pred = nilai prediksi

![mse1](https://user-images.githubusercontent.com/62003049/187825748-787875ca-c9f2-4c78-9df5-4fc1c48430c3.PNG)

![image](https://user-images.githubusercontent.com/62003049/187825426-a35fd867-e3d8-40bc-943d-2d2c890940f2.png)

Berdasarkan hasil training model, didapatkanlah jumlah error yang paling kecil adalah algoritma Random Forest (RF).

![hasil mse](https://user-images.githubusercontent.com/62003049/187826166-ae928048-1ee1-4eb3-83c9-b8c2a0c4991c.PNG)

Terlihat, berdasarkan gambar prediksi dari 4 data tersebut, algoritma yang memberikan hasil prediksi paling mendekati adalah Random Forest.
