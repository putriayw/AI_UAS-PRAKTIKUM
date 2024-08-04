# Laporan Akhir Kecerdasan Buatan

**Anggota Kelompok :**

1. Annisa Aisyah A.N.R. - NIM. 3.34.21.3.04
2. Putri Ayu Widyaningrum - NIM. 3.34.21.3.19

## Domain Proyek

*Mobil* di era digital saat ini menjadi kendaraan yang sangat penting dalam kehidupan sehari-hari. Menurut data dari Asosiasi Industri Otomotif (AIO) tahun 2022, mobil merupakan salah satu jenis kendaraan yang paling banyak digunakan di Indonesia, dengan tingkat kepemilikan mencapai 75% dari total penduduk. Dalam memilih mobil, harga menjadi salah satu faktor yang sangat berpengaruh. Oleh karena itu, kemampuan *machine learning* dalam memprediksi harga mobil berdasarkan fitur-fitur tertentu menjadi sangat penting bagi masyarakat yang ingin membeli mobil sesuai dengan kebutuhan dan preferensi mereka.
Terdapat beberapa parameter penting untuk memprediksi harga mobil. Salah satunya adalah performa mesin, efisiensi bahan bakar, keamanan, kenyamanan, fitur-fitur teknologi, dan sebagainya [2]. Algoritma *machine learning* yang sering digunakan untuk melakukan prediksi adalah regresi. Dengan menggunakan regresi, kita dapat memprediksi nilai harga mobil berdasarkan nilai dari beberapa fitur masukan.
Terdapat beberapa penelitian terkait prediksi harga mobil menggunakan *machine learning*. Salah satunya adalah penelitian yang dilakukan oleh Annisa, yang memprediksi harga mobil menggunakan beberapa algoritma seperti Random Forest, Logistic Regression, Decision Tree, Linear Discriminant Analysis, K-Nearest Neighbor, dan Support Vector Machines (SVM). Hasil penelitian tersebut menunjukkan bahwa algoritma SVM memiliki akurasi tertinggi dalam memprediksi harga mobil.
Selanjutnya, penelitian yang dilakukan oleh Putri menggunakan 25 jenis algoritma *machine learning* untuk memprediksi harga mobil. Hasil pengujian menunjukkan bahwa algoritma Neural Network memiliki akurasi terbaik, mencapai 94,70%. Dalam proyek ini, dilakukan prediksi rating mobil menggunakan beberapa algoritma *machine learning*. Sebelum melatih dan mengevaluasi model, akan dilakukan manipulasi dan pembersihan data 

agar model *machine learning* yang dihasilkan memiliki akurasi yang tinggi.

## Business Understanding

Industri otomotif terus menghadirkan berbagai model mobil dengan fitur dan teknologi yang beragam. Perubahan dan peningkatan fitur pada mobil dapat berdampak pada harga jual mobil. Calon pembeli perlu memahami spesifikasi mobil yang diinginkan sesuai dengan anggaran yang tersedia.
Rating atau penilaian mobil memiliki peran penting dalam proses pembelian. Model *machine learning* dapat memprediksi harga mobil berdasarkan fitur-fitur yang dimiliki. Ini membantu calon pembeli memilih mobil dengan harga sesuai preferensi dan anggaran.
Model *machine learning* juga bermanfaat bagi dealer dan produsen mobil. Mereka dapat menawarkan mobil dengan fitur yang sesuai preferensi pelanggan dan menyesuaikan harga berdasarkan harga yang diprediksi. Ini meningkatkan kepuasan pelanggan dan efisiensi bisnis otomotif.

#### Problem Statements

Berdasarkan permasalahan yang telah dijelaskan, *problem statements* dari proyek ini adalah sebagai berikut.

1. Bagaimana mengatasi tantangan dalam mengumpulkan data yang representatif tentang rating mobil, serta memastikan bahwa fitur-fitur yang relevan dan signifikan diidentifikasi dan dimasukkan dalam model machine learning?
2. Bagaimana proses *Pre-Processing* yang dilakukan agar menghasilkan model *machine learning* yang akurat ?
3. Bagaimana membuat atau memilih model *machine learning* yang memiliki akurasi terbaik dalam memprediksi harga mobil ?

#### Goals

Tujuan yang hendak dicapai dari proyek ini adalah sebagai berikut 

1. Mengetahui fitur yang paling berkorelasi dengan penentuan harga *mobil*.
2. Membuat model *machine learning* yang dapat memprediksi harga *mobil*.
3. Memilih model *machine learning* yang menghasilkan prediksi paling akurat berdasarkan proses *preprocessing* yang dilakukan

####  Solution Statements

Solusi yang diajukan untuk menyelesaikan masalah yang telah diuraikan adalah sebagai berikut.

1. Melakukan analisis deskriptif untuk mengetahui informasi tentang rating mobil, dengan cara mengumpulkan data yang representatif, gunakan *Metode Sampling* yang memilih sampel secara acak dari berbagai sumber data. Pastikan sampel mencakup berbagai merek, model, dan kategori mobil sehingga dapat mewakili keseluruhan populasi mobil. seperti situs ulasan otomotif, platform sosial media, atau aplikasi khusus untuk ulasan mobil.
2. Melakukan proses *Data Manipulation* untuk mengidentifikasi fitur - fitur yang paling relevan dan signifikan dalam mempengaruhi rating *mobil*
3. Melakukan Proses Pre-Processing untuk Model Machine Learning yang Akurat:
   - Melakukan transformasi fitur, seperti normalisasi atau standarisasi, untuk memastikan rentang nilai yang seragam dan memudahkan proses pemodelan.
   - Menghapus kolom yang tidak berpengaruh terhadap prediksi harga
   - Melakukan visualisasi data untuk melihat persebaran dan korelasi antar kolom
   - Membagi data menjadi *training* dan *test set*, dengan prosentase 85% banding 15%. Alasan menggunakan 15% karena jumlah data yang digunakan banyak, jadi hanya dengan 15% sudah didapatkan banyak data tes.
   - Melakukan *Encoding* terhadap kolom yang bertipe objek / kategorikal menggunakan fungsi `Map`.
4. Melakukan pemilihan model terbaik menggunakan LazyPredict
   - Memilih 3 algoritma yang menghasilkan model dengan performa terbaik
   - Perfoma model terbaik dilihat dari skor *Mean Square Error* (MSE), *Root Mean Square Error* (RMSE), dan *R Square* (R2).

## Data Understanding

Dataset yang digunakan pada proyek ini diperoleh dari Kaggle. Silahkan kunjungi tautan berikut [New York Cars ~ Big Data (2023) Car_Rates](https://www.kaggle.com/datasets/ahmettalhabektas/new-york-cars-big-data-2023) untuk mengakses dataset yang dipakai. Adapun variabel-variabel yang terdapat pada dataset adalah sebagai berikut :

1. **new&used**= Informasi Apakah Mobil dalam kondisi baru atau bekas
2. **name**: Informasi nama Mobil
3. **money** = Informasi Harga Mobil
4. **Exterior color** = Informasi warna Exterior Mobil
5. **Interior color** = Infromasi Warna Interior Mobil
6. **Drivetrain** = Informasi Jenis Drivetrain yang digunakan
7. **MPG** = Informasi efisiensi mobil dalam menggunakan bahan bakar
8. **Fuel type** = Informasi tipe bahan bakar yang digunakan
9. **Transmission** = Informasi jenis transmisi yang digunakan
10. **Engine** = Informasi mesin yang digunakan 
11. **Mileage** = Informasi jarak tempuh
12. **Convenience** = Informasi teknologi yang diterapkan pada mobil
13. **Entertainment** = Informasi hiburan yang diberikan
14. **Exterior** = Informasi Design Exterior mobil
15. **Safety** = Informasi fitur keselamatan yang ada di mobil
16. **Seating** = Informasi susunan kursi
17. **Accidents or damage** = Informasi apakah mobil pernah kecelakaan atau terkena kerusakan
18. **Clean title** = Informasi legalitas mobil
19. **1-owner vehicle** = Informasi pemilik mobil sebelumnya
20. **Personal use only** = Informasi apakah mobil digunakan untuk keperluan pribadi atau non-komersial
21. **brand** = Informasi Brand mobil
22. **Year** = Informasi Tahun pembuatan mobil
23. **Model** = Informasi Model mobil
24. **currency** = Informasi Nilai mata uang

Pada dataset, terdapat 3 fitur numerikal dan 21 fitur kategorikal. Ringkasan statistik dari data-data numerikal dapat dilihat pada Tabel 1.

<div style="text-align:center">Tabel 1. Ringkasan Statistik Data-Data Numerikal Pada Dataset</div>

|           | money        | Mileage       | Year          |
| --------- | ------------ | ------------- | ------------- |
| **count** | 1.754900e+05 | 175443.000000 | 175490.000000 |
| **mean**  | 3.435422e+04 | 51195.466203  | 2018.551900   |
| **std**   | 2.350952e+04 | 43350.071628  | 3.136994      |
| **min**   | 1.895000e+03 | 0.000000      | 2012.000000   |
| **25%**   | 1.999100e+04 | 15170.500000  | 2016.000000   |
| **50%**   | 2.899000e+04 | 44328.000000  | 2019.000000   |
| **75%**   | 4.199000e+04 | 78484.500000  | 2021.000000   |
| **max**   | 2.200000e+06 | 763474.000000 | 2023.000000   |

Pada tahap *Data Understanding* dilakukan analisis data eksploratif untuk mendapatkan informasi mengenai karakteristik data, memahami struktur data, dan mengidentifikasi potensi masalah atau kesalahan yang mungkin terjadi. Kegiatan Data Understanding yang dilakukan pada Proyek ini antara lain :

- Memberikan informasi seperti jumlah data, *missing value*, duplikasi data, korelasi antar kolom, dan sebaran data.

- Melakukan manipulasi data seperti mengubah nama kolom dan mengubah data kategorik menjadi numerik untuk mengetahui korelasi dengan kolom harga.

- Melakukan Visualisasi data untuk mengetahui korelasi sebaran data. Visualisasi korelasi antar kolom menggunakan diagram heatmap seperti gambar 1. Berdasarkan hasil visualisasi yang didapatkan, terdapat kolom Mileage, dan Year, yang diuji korelasinya dengan kolom Money, dari hasil visualisasi yang didapat, diketahui bahwa kolom Mileage dan kolom Year tidak terlalu berkorelasi dengan kolom Money, sehingga kedua kolom tersebut dapat kita hilangkan.

  ![img](E:\AI\img.png)
  
  <div style="text-align:center">Gambar 1. Visualisasi Korelasi Data dengan Heatmap</div>
  
  Untuk contoh visualisasi dari sebaran data ditunjukan pada Gambar 2, yang menunjukan sebaran data kolom driver dan merek, Visualisasi ditampilkan menggunakan diagram pie untuk mengetahui persentase sebaran data. 
  
  ![img](E:\AI\img2)

<div style="text-align:center">Gambar 2. Visualisasi Data pada Dataset</div>

## Data Preparation

Teknik data preparation yang dilakukan pada proyek ini adalah sebagai berikut : 

1. Feature Selection : Melakukan seleksi fitur untuk menyeleksi kolom yang berperan sebagai data fitur dan kolom yang menjadi data label.

2. Metode Sampling yang Representatif: menggunakan metode sampling dengan memilih sampel secara acak untuk memilih subset data yang representatif, dengan contoh sampel mencakup berbagai merek, model, dan kategori mobil agar dapat mewakili variasi yang ada di pasar.

3. Pembersihan Data: Membersihkan data dari nilai yang hilang, duplikat, atau outlier. Tangani nilai yang hilang dengan teknik seperti imputasi atau penghapusan, dan hapus duplikat yang tidak diperlukan.

   


## Modelling

Pada tahap ini dilakukan proses pelatihan untuk mendapatkan model dengan performa terbaik. Tahapan yang dilakukan pada proses Modelling adalah sebagai berikut:

1. Memprediksi algoritma dengan performa terbaik menggunakan Lazy Predict.
   Lazy Predict adalah library Python yang membantu dalam membuat model *machine learning* dengan cepat dan mudah. Library ini dikembangkan untuk mempercepat proses eksplorasi data dan pemodelan awal. Berikut Hasil dari proses pelatihan yang dilakukan Lazy Predict.Seperti yang ditampilkan pada Tabel 2.

   <div style="text-align:center">Tabel 2. Hasil Perbandingan model menggunakan Lazy Predict</div>

   | Model                         | Adjusted R-Squared | R-Squared | RMSE | Time Taken |
   | ----------------------------- | ------------------ | --------- | ---- | ---------- |
   | HistGradientBoostingRegressor | 0.26               | 0.27      | 0.37 | 1.22       |
   | LGBMRegressor                 | 0.26               | 0.27      | 0.37 | 0.24       |
   | NuSVR                         | 0.26               | 0.26      | 0.37 | 3.60       |
   | SVR                           | 0.26               | 0.26      | 0.37 | 4.56       |
   | XGBRegressor                  | 0.26               | 0.26      | 0.37 | 0.69       |
   | GradientBoostingRegressor     | 0.25               | 0.26      | 0.37 | 0.52       |
   | RandomForestRegressor         | 0.25               | 0.26      | 0.37 | 0.88       |
   | BaggingRegressor              | 0.25               | 0.26      | 0.37 | 0.16       |
   | MLPRegressor                  | 0.25               | 0.26      | 0.37 | 3.98       |
   | ExtraTreesRegressor           | 0.26               | 0.26      | 0.37 | 4.56       |
   | DecisionTreeRegressor         | 0.25               | 0.25      | 0.37 | 0.08       |
   | ExtraTreeRegressor            | 0.25               | 0.25      | 0.37 | 0.07       |
   | ElasticNetCV                  | 0.21               | 0.21      | 0.38 | 0.26       |
   | LassoCV                       | 0.21               | 0.38      | 0.21 | 0.21       |
   | BayesianRidge                 | 0.21               | 0.21      | 0.38 | 0.11       |
   | RidgeCV                       | 0.21               | 0.21      | 0.38 | 0.05       |
   | Ridge                         | 0.21               | 0.21      | 0.38 | 0.06       |
   | LassoLarsIC                   | 0.21               | 0.21      | 0.38 | 0.16       |
   | Lars                          | 0.21               | 0.21      | 0.38 | 0.06       |
   | LinearRegression              | 0.21               | 0.21      | 0.38 | 0.15       |
   | TransformedTargetRegressor    | 0.21               | 0.21      | 0.38 | 0.11       |
   | KernelRidge                   | 0.20               | 0.21      | 0.38 | 4.62       |
   | LassoLarsCV                   | 0.20               | 0.21      | 0.38 | 0.38       |
   | LarsCV                        | 0.20               | 0.21      | 0.38 | 0.15       |
   | LinearSVR                     | 0.20               | 0.20      | 0.38 | 0.52       |
   | KNeighborsRegressor           | 0.20               | 0.20      | 0.38 | 0.30       |
   | HuberRegressor                | 0.19               | 0.20      | 0.38 | 0.42       |
   | OrthogonalMatchingPursuitCV   | 0.19               | 0.20      | 0.38 | 0.08       |
   | AdaBoostRegressor             | 0.19               | 0.19      | 0.38 | 0.19       |
   | PoissonRegressor              | 0.17               | 0.18      | 0.39 | 0.06       |
   | OrthogonalMatchingPursuit     | 0.16               | 0.17      | 0.39 | 0.06       |
   | SGDRegressor                  | 0.14               | 0.15      | 0.40 | 0.08       |
   | TweedieRegressor              | 0.09               | 0.09      | 0.41 | 0.07       |
   | GammaRegressor                | 0.09               | 0.09      | 0.41 | 0.07       |
   | PassiveAggressiveRegressor    | 0.01               | 0.02      | 0.42 | 0.07       |

   Tabel di atas merupakan hasil evaluasi performa beberapa model algoritma berdasarkan metrik evaluasi yang meliputi Adjusted R-Squared, R-Squared, RMSE, dan Time Taken. Setiap baris dalam tabel mewakili satu model algoritma beserta hasil evaluasinya.

2. Membuat pipeline untuk menggabungkan data numerik dan kategorik.
   Hasil penggunakan teknik `ColumnTransformer` disimpan dalam objek feature. Selanjutnya dilakukan proses pipeline untuk menggabungkan dan meng-optimasi kolom numerikal dan kategorikan agar dapat di proses oleh algoritma machine learning.

3. Memilih 3 (tiga) algoritma dengan performa terbaik untuk di evaluasi

   Setelah dilakukan proses pelatihan oleh Lazy Predict, diperoleh 3 algoritma dengan performa terbaik yaitu :

   - **HistGradientBoostingRegressor**

     HistGradientBoostingRegressor. Model ini merupakan implementasi dari algoritma gradient boosting yang efisien dan kuat untuk tugas regresi. Model ini memiliki beberapa hyperparameter seperti l2_regularization, max_depth, dan min_samples_leaf yang telah ditentukan. Ini adalah metode ensambel yang menggabungkan beberapa pohon keputusan untuk membuat model yang lebih kuat. Algoritma HistGradientBoostingRegressor bekerja dengan menggabungkan banyak pohon keputusan sederhana. Setiap pohon yang ditambahkan ke model berusaha untuk memperbaiki kesalahan prediksi yang dihasilkan oleh pohon sebelumnya. Ilustrasi cara kerja HistGradientBoostingRegressor dapat dilihat di Gambar 5.

     **![img](E:\AI\HistGradientBoostingRegressor)

     <div style="text-align:center">Gambar 2. Ilustrasi HistGradientBoostingRegressor  [5]</div>

   - **LGBMRegressor**

     LGBMRegressor adalah implementasi dari algoritma Gradient Boosting yang efisien dan kuat. Model ini memiliki hyperparameter seperti max_features, max_samples, n_estimators, dan random_state yang telah diatur sesuai dengan kebutuhan. Ini adalah metode ensambel yang menggabungkan beberapa pohon keputusan acak untuk membuat model yang lebih kuat. Pada dasarnya,data yang telah ditransformasi akan diteruskan ke tahap model pembelajaran mesin, di mana model LGBMRegressor akan dilatih menggunakan data tersebut. Setelah model dilatih, pipeline siap untuk digunakan untuk melakukan prediksi pada data baru. Ilustrasi cara kerja LGBMRegressor dapat dilihat di Gambar 6.

     ![img](E:\AI\LGBMRegressor)

     <div style="text-align:center">Gambar 3. Ilustrasi LGBMRegressor  [6]</div>

   - **NuSVR**

     NuSVR (Support Vector Regression dengan nu) adalah algoritma pembelajaran mesin yang digunakan untuk tugas regresi. Algoritma ini merupakan salah satu implementasi dari Support Vector Machine (SVM) yang digunakan untuk memodelkan hubungan antara fitur-fitur independen dan variabel dependen yang bersifat kontinu. Dan merupakan salah satu algoritma yang berguna dalam tugas regresi, ketika terdapat outlier dalam data pelatihan atau ketika hubungan antara fitur dan variabel target bersifat nonlinier. Tahap ini menggunakan model NuSVR (Support Vector Regression) untuk melakukan prediksi. Model NuSVR adalah model regresi yang merupakan salah satu implementasi dari Support Vector Machine (SVM) untuk tugas regresi. Model ini menggunakan pendekatan SVM untuk membangun hyperplane yang memisahkan data dengan margin maksimum. Ilustrasi cara kerja NuSVR dapat dilihat di Gambar 7. 

     ![img](E:\AI\NuSVR)

     <div style="text-align:center">Gambar 4. Ilustrasi NuSVR  [7]</div>

4. Menambahkan parameter tunning untuk mengingkatkan performa modelPenambahan parameter menggunakan **Teknik Grid Search**. Sehingga diperoleh hyperparameter dari masing-masing algoritma adalah sebagai berikut.

   - **Parameter HistGradientBoostingRegressor**

     - 12_regularization = 0.1
     - max_depth = 3
     - min_samples_leaf = 10

   - **Parameter LGBMRegressor**

     - max_features = 0.5
     - max_samples = 0.4
     - n_estimators = 90
     - randome_state = 99
     
   - **Parameter NuSVR**

     - Nu = 0.1

       


## Evaluation

- Metrik evaluasi yang digunakan adalah *Mean Square Error* (MSE), *Root Mean Square Error* (RMSE), dan *R Square* (R2 Score)

- MSE melakukan pengurangan nilai data aktual dengan data peramalan dan hasilnya dikuadratkan (*squared*) kemudian dijumlahkan secara keseluruhan dan membaginya dengan banyaknya data yang ada. Rumus dari MSE adalah sebagai berikut 
  $$
  MSE = \frac{1}{n} \Sigma_{i=1}^n({y}-\hat{y})^2
  $$
  Diketahui:

  - n = Jumlah Data
  - yi = *Actual Value* / Nilai Sebenarnya
  - ŷi = *Predicted Value* / Nilai Prediksi

- RMSE adalah jumlah dari kesalahan kuadrat atau selisih antara nilai sebenarnya dengan nilai prediksi yang telah ditentukan. Cara menghitungnya tinggal mengakar kan mse menggunakan fungsi *np.sqrt*. Rumus dari RMSE adalah sebagai berikut.
  $$
  RMSE = \sqrt{(\frac{1}{n})\sum_{i=1}^{n}(y_{i} - x_{i})^{2}}
  $$
  Diketahui:

  - n = Jumlah Data
  - yi = *Actual Value* / Nilai Sebenarnya
  - ŷi = *Predicted Value* / Nilai Prediksi

- R2 Score dijadikan sebagai pengukuran seberapa baik garis regresi mendekati nilai data asli yang dibuat melalui model. Rumus dari R2 Score adalah sebagai berikut.
  $$
  R^2 = 1 - {SS_R \over SS_T} =  1 - {\sum_{i} (y_i - ŷ_p) ^ 2 \over \sum_{i} (y_i - ȳ) ^ 2}
  $$

  - SSR : Kuadrat dari selisih nilai Y prediksi dengan nilai rata-rata Y = ∑ (Ypred – Yrata-rata)²
  - SST : Kuadrat dari selisih nilai Y aktual dengan nilai rata-rata Y = ∑ (Yaktual – Yrata-rata)²

- Setelah melalui tahap pelatihan dan evaluasi menggunakan MSE, RMSE, dan R Square, diperoleh hasil bahwa 3 algoritma, memiliki performa yang kurang baik, Maksud dari performa kurang baik ialah memiliki nilai MSE dan RMSE yang jauh dari nilai 0.

  <div style="text-align:center">Tabel 3. Hasil Pengujian dari 3 Algoritma Teratas</div>

  | Model_Name                    | mse               | r2         | rmse          |
  | ----------------------------- | ----------------- | ---------- | ------------- |
  | HistGradientBoostingRegressor | 242323184.2209985 | 0.1233644  | 15566.7332546 |
  | LGBMRegressor                 | 243028164.7582998 | 0.1208140  | 15589.3606270 |
  | NuSVR                         | 282435596.1913032 | -0.0217475 | 16805.8203070 |

- Membandingkan data sebenarnya dengan hasil prediksi. Hasil perbandingan dapat dilihat pada Tabel 4.

  <div style="text-align:center">Tabel 4. Hasil Perbandingan Data Sebenarnya dengan Hasil Prediksi</div>
  
  | y_true | prediksi_HB | prediksi_LG   | prediksi_NU   |
  | ------ | ----------- | ------------- | ------------- |
  | 91567  | 21774       | 35838.2000000 | 35760.1000000 |
  | 169392 | 27998       | 31513.5000000 | 31680.0000000 |
  | 94297  | 18795       | 23487.3000000 | 23096.1000000 |
  | 89330  | 32998       | 35838.2000000 | 35760.1000000 |
  | 137711 | 24697       | 23487.3000000 | 23096.1000000 |
  | ...    | ...         | ...           | ...           |
  | 96674  | 17861       | 35838.2000000 | 35760.1000000 |
  | 134722 | 37237       | 31513.5000000 | 31680.0000000 |
  | 20812  | 21998       | 23487.3000000 | 23096.1000000 |
  | 144200 | 29895       | 31513.5000000 | 31680.0000000 |
  | 158830 | 41149       | 35838.2000000 | 35760.1000000 |

Dalam contoh yang diberikan, setiap baris pada data tersebut merepresentasikan sebuah sampel data. Kolom "y_true" berisi nilai aktual yang seharusnya diprediksi, sedangkan kolom-kolom prediksi (prediksi_HB, prediksi_LG, dan prediksi_NU) berisi nilai prediksi dari masing-masing algoritma. 

## Conclussion

1. Berdasarkan hasil pengukuran, terdapat 10 kolom atau fitur yang mempengaruhi *Price* yaitu penggunaan, harga, warna_luar, warna_dalam, driver, jenis_bahan_bakar, bagian_luar, tempat_duduk, merek, dan mata_uang.
2. Berdasarkan hasil pengujian model, diperoleh hasil bahwa 3 algoritma, memiliki performa yang kurang baik, Maksud dari performa kurang baik ialah memiliki nilai MSE dan RMSE yang jauh dari nilai 0.3. Meningkatkan performa model dapat dilakukan dengan menambahkan hyperparameter. Pemilihan hyperparameter yang menghasilkan performa terbaik dapat dilakukan menggunakan teknik Grid Search.
3. Meningkatkan performa model dapat dilakukan dengan menambahkan hyperparameter. Pemilihan hyperparameter yang menghasilkan performa terbaik dapat dilakukan menggunakan teknik Grid Search.

## Referensi

[1]   Edi Ismanto, Melly Novalia, “Performance Comparison Between C4.5 Algorithm, Random Forests, and Gradient Boosting for Commodity Classification ,” 2021, doi: [[10.33633/tc.v20i3.4576](http://dx.doi.org/10.33633/tc.v20i3.4576)](http://dx.doi.org/10.33633/tc.v20i3.4576).

[2]   https://datascience.eu/machine-learning/1-what-is-light-gbm/

[3]  https://dqlab.id/kriteria-jenis-teknik-analisis-data-dalam-forecasting

[4]  Fchrul.Rozi, “Pendekatan algoritma LGBM Regressor” 2022, doi: (https://doi.org/10.47709/dsi.v1i1.1169).

[5] [New York Cars ~ Big Data (2023) Car_Rates](https://www.kaggle.com/datasets/ahmettalhabektas/new-york-cars-big-data-2023.

**---Ini adalah bagian akhir laporan---**