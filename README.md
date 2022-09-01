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
- fixed acidity : kandungan asam organik volatilitas rendah seperti asam malat, laktat, tartarat atau sitrat
- volatile acidity : ukuran asam lemak dengan berat molekul rendah (atau dapat disuling dengan uap)
- citric acid : kandungan asam organik pada minuman dengan formula HOC(CO2H)
- residual sugar : kandungan gula 
- chlorides : kandungan klodira
- free sulfur dioxide : tingkat kandungan sulfur dioksida
- total sulfur dioxide : jumlah sulfur dioksida
- density : massa jenis minuman
- pH : tingkat keasaman minuman
- sulphates : kandungan asam sulfat
- alcohol : kandungan alkohol minuman
Variabel Output:
- quality (Nilai antara 0 sampai 10)

Untuk lebih jelasnya data yang terdapat pada dataset tersebut dapat dilihat pada gambar berikut:
![image](https://user-images.githubusercontent.com/62003049/187919809-943dce52-d80d-4dca-84b9-4e2a1cd86bbc.png)

Untuk melihat sebaran data pada dataset, dapat kita lihat melalui data histogram di bawah ini:
![image](https://user-images.githubusercontent.com/62003049/187924117-82c8740e-92dc-4411-8216-d92f82c4608f.png)

Berdasarkan data histogram 'quality' yang merupakan fitur target (label), informasi yang dapat diperoleh yaitu:
- Wine yang terdapat pada dataset didominasi oleh wine yang memiliki kualitas bernilai 5 dan 6
- Distribusi kualitas miring ke kanan (right-skewed). Hal ini akan berimplikasi pada model.

## Data Preparation
Pada proyek ini dilakukan proses data preparation yaitu:
   Pembagian dataset dengan fungsi train_test_split dari library sklearn
   Proses pembagian dataset ini bertujuan untuk memisahkan antara data yang akan dilakukan proses training dan data yang akan
   akan digunakan untuk pengujian. Tentunya data yang digunakan untuk proses pengujian haruslah data yang belum pernah dilihat    oleh model sebelumnya, sehingga proses pemisahan data ini sangat penting.
   Berikut ini program yang digunakan pada proses splitting data:
   ![image](https://user-images.githubusercontent.com/62003049/187921201-9c296291-28aa-42c0-a01d-cb8dd769b8ff.png)

## Modeling
Model Machine Learning yang digunakan pada proyek ini ada 2 jenis algoritma yang akan dibandingkan berdasarkan hasil prediksi masing-masing algoritma. Algoritma yang pertama digunakan adalah algoritma random forest dan algoritma boosting.

Pada Algoritma Random Forest, parameter yang digunakan adalah sebagai berikut
- n_estimators=25
- max_depth=32
- random_state=16
- n_jobs=-1
Untuk lebih jelasnya dapat dilihat pada cuplikan kode dibawah ini:
![image](https://user-images.githubusercontent.com/62003049/187921844-cf1c7d27-99dd-4cae-a8ee-86bbd6f497a6.png)

Sedangkan pada Algoritma Boosting, parameter yang digunakan adalah sebagai berikut
- learning rate = 0.05
- random state = 16
Untuk lebih jelasnya dapat dilihat pada cuplikan kode dibawah ini:
![image](https://user-images.githubusercontent.com/62003049/187921949-c2d1929a-f16c-4980-ae0c-d086ec53fa0f.png)

## Evaluation
Model yang telah dibuat dapat memprediksi nilai dari qualitas wine yang ada pada dataset. Karena pada proyek kali ini menggunakan 3 jenis algoritma, maka akan dibandingkan hasil prediksi dari masing-masing algoritma. Metrik yang digunakan pada setiap algoritma adalah MSE atau mean squared error.

Mse merupakan metrik yang menghitung jumlah selisih kuadrat rata-rata nilai sebenarnya dengan nilai prediksi. MSE didefinisikan dalam persamaan berikut:

![image](https://user-images.githubusercontent.com/62003049/187825463-410f0055-ac49-4af8-a56b-a5e280e62eda.png)

Keterangan:
N = jumlah dataset
yi = nilai sebenarnya
y_pred = nilai prediksi

![image](https://user-images.githubusercontent.com/62003049/187925940-3528f511-4845-43e1-a1ac-ba94198998ec.png)

Berdasarkan hasil training model, didapatkanlah jumlah error yang paling kecil adalah Boosting Algorithm.

![image](https://user-images.githubusercontent.com/62003049/187925821-d12192c4-b4c6-434d-b272-935a66e8af40.png)

Terlihat, berdasarkan gambar prediksi dari 4 data tersebut, algoritma yang memberikan hasil prediksi paling mendekati adalah Boosting Algorithm.
