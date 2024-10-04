# Laporan Proyek Machine Learning - M. Gymnastiar

## Domain Proyek : Lingkungan

![Image Emission C02](https://png.pngtree.com/png-clipart/20230925/original/pngtree-the-vehicle-emits-copious-amounts-of-co2-a-harmful-greenhouse-gas-png-image_12784556.png)

Perubahan iklim global telah menjadi masalah penting yang berdampak pada ekosistem, kesehatan manusia, dan ekonomi di seluruh dunia. Salah satu penyebab utama perubahan iklim adalah emisi gas rumah kaca, khususnya karbon dioksida (CO2), yang dihasilkan oleh berbagai kegiatan manusia, termasuk sektor transportasi [_(Jainal et al., 2022)_](https://jurnal.ugn.ac.id/index.php/jurnalnauli/article/view/921/701). Kendaraan bermotor adalah penyumbang utama emisi CO2, terutama di daerah perkotaan yang memiliki lalu lintas yang padat. Oleh karena itu, pengukuran yang tepat dan efisien terhadap jumlah emisi CO2 dari kendaraan bermotor sangat penting untuk merumuskan strategi mitigasi yang sesuai [_(Dita et al., 2019)_](https://purejournal.ub.ac.id/index.php/pure/article/view/385).

Melalui Analisis yang dilakukan ini, diharapkan dapat ditemukan model yang tidak hanya akurat tetapi juga mudah diimplementasikan  di  berbagai  konteks,  membantu dalam  upaya  global untuk mengurangi emisi CO2 kendaraan. Analisis ini juga akan menyoroti pentingnya pemahaman mendalam tentang faktor-faktor yang mempengaruhi emisi kendaraan, memberikan wawasan yang berharga untuk pengembangan kebijakan lingkungan yang lebih efektif.

## Business Understanding

### Problem Statements

Rumusan masalah dari masalah latar belakang diatas adalah :
- Dari berbagai fitur yang ada, fitur mana yang paling berpengaruh terhadap emisi CO2 yang dihasilkan oleh kendaraan?
- Bagaimana mengetahui banyak emisi CO2 yang dihasilkan oleh kendaraan berdasarkan riwayat dari fitur-fitur yang ada?

### Goals

tujuan untuk menyelesaikan permasalahan diatas adalah:
- Mengetahui fitur yang paling berkorelasi dengan emisi CO2 yang dihasilkan oleh kendaraan.
- Membuat model machine learning yang dapat memprediksi seberapa banyak emisi CO2 yang dihasilkan oleh kendaraan secara akurat berdasarkan fitur-fitur yang ada.


    ### Solution statements
    - Melakukan analisis pada data untuk memahami fitur-fitur yang mempengaruhi emisi CO2, dengan menerapkan teknik visualisasi data guna mengetahui korelasi antar fitur dan memahami hubungan antara data target (label) dan fitur lainnya.
    - Menggunakan berbagai algoritma machine learning untuk membandingkan performa model, dengan tujuan mendapatkan model atau algoritma yang memiliki akurasi prediksi tertinggi dalam memperkirakan jumlah emisi CO2 yang dihasilkan oleh kendaraan.-

## Data Understanding
di website kaggle diketahui bahwa Dataset ini menangkap detail bagaimana emisi CO2 dari kendaraan dapat bervariasi dengan fitur-fitdr yang berbeda. Dataset ini diambil dari situs data terbuka resmi Pemerintah Kanada. Ini adalah versi yang telah dikompilasi dan berisi data selama 7 tahun. Terdapat total 7385 baris dan 12 kolom. Ada beberapa singkatan yang digunakan untuk menggambarkan fitur-fitur. Saya mencantumkannya di sini, dan hal yang sama dapat ditemukan di lembar Deskripsi Data.

**Informasi Datasets**

| Jenis | Keterangan |
| ------ | ------ |
| Title | CO2 Emission by Vehicles |
| Source | [Kaggle](https://www.kaggle.com/datasets/debajyotipodder/co2-emission-by-vehicles) |
| Owner | [Debajyoti Podder](https://www.kaggle.com/debajyotipodder) |
| License | Database: Open Database, Contents |
| Visibility | Publik |
| Tags | Business, Earth and Nature, Computer Science, Automobiles and Vehicles, Regression, Environment, Linear Regression, Pollution |
| Usability | 10.00 |

### Variabel-variabel pada CO2 Emission by Vehicles dataset adalah sebagai berikut:
- **Make** : Perusahaan yang membuat kendaraan
- **Model** : Model dari kendaraan
- **Vehicle Class** : Kelas dari kendaraan berdasarkan utilitas, kapasitas dan berat
- **Engine Size (L)** : Ukuran dari mesin dalam satuan liter (L)
- **Cylinders** : Jumlah silinder kendaraan (ruang naiknya piston)
- **Transmission** : Tipe transmisi dengan jumlah gigi kendaraan
  - A = Otomatis
  - AM = Manual Otomatis
  - AS = Otomatis dengan pilihan shift
  - AV = Variabel kontinu
  - M = Manual
  - X = Angka dari gigi
- **Fuel Type** : Tipe bahan bakar
  - X = Bensin Reguler
  - Z = Bensin Premium
  - D = Disel
  - E = Ethanol (E85)
  - N = Gas Natural
- **Fuel Consumption City (L/100 km)** : Jumlah konsumsi bahan bakar dijalanan kota dalam satuan (L/100 km)
- **Fuel Consumption City (L/100 km)** : Jumlah konsumsi bahan bakar dijalanan raya dalam satuan (L/100 km)
- **Fuel Consumption Comb (L/100 km)** : Jumlah konsumsi bahan bakar (55% kota. 45% jalan raya) dalam satuan (L/100 km)
- **CO2 Emissions(g/km)** : Emisi knalpot karbon dioksida dalam gram/kilometer (g/km) dari gabungan berkendara pada jalanan kota dan jalan raya-

### Exploratory Data Analysis - Deskripsi Variabel 

| #  | Column                            | Non-Null Count | Dtype   |
|----|------------------------------------|----------------|---------|
| 0  | Make                              | 7385 non-null   | object  |
| 1  | Model                             | 7385 non-null   | object  |
| 2  | Vehicle Class                     | 7385 non-null   | object  |
| 3  | Engine Size(L)                    | 7385 non-null   | float64 |
| 4  | Cylinders                         | 7385 non-null   | int64   |
| 5  | Transmission                      | 7385 non-null   | object  |
| 6  | Fuel Type                         | 7385 non-null   | object  |
| 7  | Fuel Consumption City (L/100 km)  | 7385 non-null   | float64 |
| 8  | Fuel Consumption Hwy (L/100 km)   | 7385 non-null   | float64 |
| 9  | Fuel Consumption Comb (L/100 km)  | 7385 non-null   | float64 |
| 10 | Fuel Consumption Comb (mpg)       | 7385 non-null   | int64   |
| 11 | CO2 Emissions(g/km)               | 7385 non-null   | int64   |


Dari tabel diatas didapat informasi banyak fitur categorical dan numerik :
   - Terdapat 5 fitur dengan tipe categorical atau object yaitu Make, Model, Vehicle Class, Transmission, dan Fuel Type

   - Terdapat 7 feature dengan tipe numeric terdiri dari 4 float64 yaitu Engine Size(L), Fuel Consumption City (L/100 km), Fuel Consumption Hwy (L/100 km), Fuel Consumption Comb (L/100 km), dan 3 bertipe int64 yaitu Cylinders, Fuel Consumption Comb (mpg) dan CO2 Emissions(g/km)

Menghapus data yang dianggap tidak terlalu penting, terdiri dari 3 data categorical yaitu:

- Make: Fitur ini dihapus karena hanya berisi informasi mengenai nama perusahaan pembuat kendaraan.

- Model: Fitur ini dihapus karena hanya menjelaskan model dari kendaraan tersebut.

- Vehicle Class: Fitur ini dihapus karena hanya mengkategorikan model berdasarkan utilitas, kapasitas, dan dimensi kursi penumpang.

|       | Engine Size(L) |  Cylinders  | Fuel Consumption City (L/100 km) | Fuel Consumption Hwy (L/100 km) | Fuel Consumption Comb (L/100 km) | Fuel Consumption Comb (mpg) | CO2 Emissions(g/km) |
|:-----:|:--------------:|:-----------:|:--------------------------------:|:-------------------------------:|:--------------------------------:|:---------------------------:|:-------------------:|
| count |   7385.000000  | 7385.000000 |            7385.000000           |           7385.000000           |            7385.000000           |         7385.000000         |     7385.000000     |
|  mean |    3.160068    |   5.615030  |             12.556534            |             9.041706            |             10.975071            |          27.481652          |      250.584699     |
|  std  |    1.354170    |   1.828307  |             3.500274             |             2.224456            |             2.892506             |           7.231879          |      58.512679      |
|  min  |    0.900000    |   3.000000  |             4.200000             |             4.000000            |             4.100000             |          11.000000          |      96.000000      |
|  25%  |    2.000000    |   4.000000  |             10.100000            |             7.500000            |             8.900000             |          22.000000          |      208.000000     |
|  50%  |    3.000000    |   6.000000  |             12.100000            |             8.700000            |             10.600000            |          27.000000          |      246.000000     |
|  75%  |    3.700000    |   6.000000  |             14.600000            |            10.200000            |             12.600000            |          32.000000          |      288.000000     |
|  max  |    8.400000    |  16.000000  |             30.600000            |            20.600000            |             26.100000            |          69.000000          |      522.000000     |

Table diatas memberikan informasi statistik pada masing-masing kolom, antara lain:

- Count adalah jumlah sampel pada data.

- Mean adalah nilai rata-rata.
- Std adalah standar deviasi.
- Min yaitu nilai minimum setiap kolom.
- 25% adalah kuartil pertama. Kuartil adalah nilai yang menandai batas interval - dalam empat bagian sebaran yang sama.
- 50% adalah kuartil kedua, atau biasa juga disebut median (nilai tengah).
- 75% adalah kuartil ketiga.
- Max adalah nilai maksimum.

| Jumah Baris                           | Jumlah Kolom |
|---------------------------------------|--------------|
| 7385                                  | 9   |


### Exploratory Data Analysis - Missing Value & Outlier

**Mengecek missing value, Duplikat dan data yang dianggap memiliki kejanggalan.**

| Data Dupliat                        |
|-------------------------------------|
| 2819                                |

- Sebanyaak 2819 data akan dihapus karena duplikat

  | Column                              | Value |
  |-------------------------------------|-------|
  | Engine Size(L)                      | 0     |
  | Cylinders                           | 0     |
  | Transmission                        | 0     |
  | Fuel Type                           | 0     |
  | Fuel Consumption City (L/100 km)    | 0     |
  | Fuel Consumption Hwy (L/100 km)     | 0     |
  | Fuel Consumption Comb (L/100 km)    | 0     |
  | Fuel Consumption Comb (mpg)         | 0     |
  | CO2 Emissions(g/km)                 | 0     |

- Pada tabel diatas didapati bahwa tidak terdapat missing value pada dataset.

  | Column                                      | Value |
  |---------------------------------------------|-------|
  | Nilai 0 di kolom Engine Size(L) ada         | 0     |
  | Nilai 0 di kolom Cylinders                  | 0     |
  | Nilai 0 di kolom Transmission ada           | 0     |
  | Nilai 0 di kolom Fuel Type ada              | 0     |
  | Nilai 0 di kolom Fuel Consumption City (L/100 km) ada | 0 |
  | Nilai 0 di kolom Fuel Consumption Hwy (L/100 km) ada  | 0 |
  | Nilai 0 di kolom Fuel Consumption Comb (L/100 km) ada | 0 |
  | Nilai 0 di kolom Fuel Consumption Comb (mpg) ada      | 0 |
  | Nilai 0 di kolom CO2 Emissions(g/km) ada    | 0     |

- kemudian juga tidak terdapat kolum yang bernilai 0 pada table diatas.

**Melakukan visualisasi data dengan boxplot pada tipa numerik** 

- Untuk mengetahui apakah data dapat dikatakan outlier dapat dilihat menggunakan teknik visualisasi, yaitu jenis boxplot.

- Gambar dibawah adalah ilustrasi dan penjelasan nilai statistik pada boxplot.
     
  ![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-4.png?raw=true)
     
   - Pada gambar terlihat, apabila data melebihi rentang Minimum atau Maximum, maka dapat dikatakan outlier.

- Outlier merupakan rentang nilai yang melebihi batas Minimum dan Maximum. Berdasarkan hasil dari visualisasi boxplot yang dilakukan dapat dilihat:

   ![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-5.png?raw=true)

   ![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-6.png?raw=true)  
        
   ![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-7.png?raw=true)

   ![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-8.png?raw=true)
        
        
    - Berdasarkan gambar diatas dapat disimpulkan bahwa semua fitur mulai dari Engine Size(L), Cylinders, Fuel Consumption City(L/100 km), Fuel Consumption Hwy(L/100 km), Fuel Consumption Comb(mpg), dan CO2 Emission(g/km) memiliki data outlier karena ada data yang diluar rentang nilai maximum. 
    - Setelah dipastikan ada data outlier, selanjutnya menerapakan IQR Method untuk menghapus outlier tersebut.

### Exploratory Data Analysis - Univariate Analysis

- univariate analysis bertujuan untuk memvisualisasikan dan menganalisis setiap fitur atau variabel secara individual dalam dataset, sehingga dapat memberikan pemahaman mendalam tentang distribusi dan karakteristik data pada masing-masing fitur tersebut.

**Univariate Analysis - Fitur Kategori**

![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-9.png?raw=true)

Terdapat 27 kategori fitur untuk transmisi yang dapat disimpulkan sebagai berikut:

- Transmisi AS (Otomatis dengan pilihan shift): sebanyak 45.0% dari total sampel.
- Transmisi A (Otomatis): sebanyak 19.2% dari total sampel.
- Transmisi M (Manual): sebanyak 12.3% dari total sampel.
- Transmisi AM (Manual Otomatis): sebanyak 7.7% dari total sampel.
- Transmisi AV (Variabel kontinu): sebanyak 8.3% dari total sampel.

Dapat disimpulkan bahwa hampir setengah dari total kendaraan menggunakan tipe transmisi AS (Otomatis dengan pilihan shift), dengan proporsi mencapai 45.0%.

![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-10.png?raw=true)

Pada jenis bahan bakar, terdapat lima kategori, yaitu X, Z, E, D, dan N. Dapat disimpulkan bahwa sebagian besar kendaraan menggunakan bahan bakar jenis X dan Z, yaitu Bensin Reguler dan Bensin Premium, yang memiliki persentase mencapai 92,6%.

**Univariate Analysis - Fitur Numerik**

![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-11.png?raw=true)

![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-12.png?raw=true)

![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-13.png?raw=true)

Pada histogram diatas dapat disimpulkan bahwa:

- Peningkatan emisi CO2 sejalan dengan meningkatnya jumlah sampel. Hal ini terlihat dari histogram fitur "Emisi CO2" yang menunjukkan peningkatan seiring bertambahnya sampel.
- Kadar emisi CO2 yang dihasilkan mencapai dua kali lipat dari batas normal, yaitu 522 g/km.
- Setengah dari kadar emisi CO2 berada dalam rentang 246 g/km.
- Mayoritas kadar emisi CO2 terletak pada kuartil pertama hingga kuartil ketiga.
- Distribusi emisi CO2 cenderung miring ke kanan (left-skewed), yang menunjukkan bahwa nilai median (nilai tengah) berada di kuartil ketiga dan lebih tinggi daripada nilai rata-rata.

### Exploratory Data Analysis - Multivariate Analysis

multivariate analysis bertujuan untuk memvisualisasikan data guna memahami hubungan antara dua atau lebih fitur dalam dataset. Teknik ini membantu mengidentifikasi pola, korelasi, atau interaksi antar fitur yang dapat memberikan wawasan lebih mendalam tentang struktur data.

**Multivariate Analysis - Fitur Kategori**

![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-14.png?raw=true)

![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-15.png?raw=true)

Pada visualisasi terhadap fitur kategori, dapat disimpulkan:

- Rentang Emisi CO2 (g/km) untuk setiap jenis transmisi berkisar antara 140 hingga 300. Distribusi data tidak menunjukkan penurunan atau peningkatan yang signifikan, yang menunjukkan bahwa fitur transmisi memiliki dampak kecil terhadap Emisi CO2 (g/km).

- Sedangkan untuk tipe bahan bakar, rentang Emisi CO2 (g/km) berada antara 200 hingga 250, dengan setiap jenis bahan bakar menunjukkan kemiripan dan perbedaan rentang yang tidak terlalu besar. Hal ini menunjukkan bahwa fitur tipe bahan bakar juga memiliki pengaruh kecil terhadap Emisi CO2 (g/km).

**Multivariate Analysis - Fitur Numerik**

Untuk mengamati hubungan antara fitur numerik, kita akan menggunakan fungsi pairplot(). Kita juga akan mengobservasi korelasi antara fitur numerik dengan fitur target menggunakan fungsi corr().

![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-16.png?raw=true)

Pada visualisasi diatas dapat disimpulkan:

- Engine Size (L) vs CO2 Emissions (g/km): Terlihat hubungan linear yang kuat antara ukuran mesin dan emisi CO2. Semakin besar ukuran mesin, semakin tinggi pula emisi CO2 yang dihasilkan. Ini menunjukkan bahwa fitur ukuran mesin memiliki pengaruh signifikan terhadap emisi CO2.

- Fuel Consumption City (L/100 km) vs CO2 Emissions (g/km): Ada korelasi yang jelas antara konsumsi bahan bakar di dalam kota dan emisi CO2. Semakin tinggi konsumsi bahan bakar di dalam kota, semakin tinggi pula emisi CO2.

- Fuel Consumption Hwy (L/100 km) vs CO2 Emissions (g/km): Sama halnya dengan konsumsi bahan bakar di jalan raya, hubungan linear juga terlihat di sini, dengan peningkatan konsumsi bahan bakar di jalan raya berbanding lurus dengan peningkatan emisi CO2.

- Fuel Consumption Comb (L/100 km) vs CO2 Emissions (g/km): Konsumsi bahan bakar gabungan juga memiliki korelasi positif dengan emisi CO2. Semakin tinggi konsumsi bahan bakar, semakin tinggi emisi CO2 yang dihasilkan.

- Fuel Consumption Comb (mpg) vs CO2 Emissions (g/km): Dalam grafik ini, terlihat bahwa semakin tinggi (mpg), semakin rendah emisi CO2. Ini menunjukkan bahwa efisiensi bahan bakar yang lebih baik (mpg lebih tinggi) menghasilkan emisi CO2 yang lebih rendah.

untuk lebih jelasnya kita akan melihat dengan correlation matrix pada gambar dibawah.

![alt text](image-17.png)

Berdasarkan matriks korelasi untuk fitur numerik yang ditampilkan:

- Engine Size (L) memiliki korelasi yang kuat dengan CO2 Emissions (g/km) sebesar 0.82. Ini menunjukkan bahwa semakin besar ukuran mesin, semakin tinggi emisi CO2. Selain itu, Engine Size (L) juga memiliki korelasi tinggi dengan jumlah Cylinders (0.94), yang cukup logis mengingat mesin yang lebih besar cenderung memiliki lebih banyak silinder.

- Cylinders juga memiliki korelasi yang tinggi dengan CO2 Emissions (g/km) (0.8), menunjukkan bahwa kendaraan dengan lebih banyak silinder cenderung menghasilkan lebih banyak emisi.

- Fuel Consumption (L/100 km), baik dalam kota (City), di jalan raya (Hwy), maupun gabungan (Comb), semuanya memiliki korelasi sangat tinggi dengan CO2 Emissions (g/km), masing-masing 0.91, 0.9, dan 0.92. Ini mengindikasikan bahwa konsumsi bahan bakar merupakan faktor utama yang mempengaruhi emisi CO2.

- Sebaliknya, Fuel Consumption Comb (mpg) menunjukkan korelasi negatif yang kuat dengan CO2 Emissions (g/km) (-0.92). Ini berarti bahwa kendaraan dengan efisiensi bahan bakar yang lebih tinggi (mpg lebih tinggi) menghasilkan emisi CO2 yang lebih rendah, sesuai dengan ekspektasi.

- Korelasi antara Fuel Consumption City (L/100 km) dan Fuel Consumption Hwy (L/100 km) adalah sangat tinggi (0.94), begitu juga antara keduanya dengan Fuel Consumption Comb (L/100 km) yang masing-masing 0.99 dan 0.97. Ini menunjukkan bahwa ketiga variabel ini sangat terkait satu sama lain dan cenderung memberikan informasi yang serupa.

## Data Preparation

Pada bagian ini ada empat tahap persiapan data yang dilakukan, yaitu:

- Encoding fitur kategori.
- Reduksi dimensi dengan Principal Component Analysis (PCA).
- Pembagian dataset dengan fungsi train_test_split dari library sklearn.
- Standarisasi.

**Encoding fitur kategori**

pada dataset kita terdapat 2 fitur categorical yang akan diubah menjadi data numerik yaitu: 

- pertama adalah fitur Transmission akan diubah menggunakan LabelEncoder.
- dan fitur Fuel Type diubah menggunakan OneHotEncoder.

Fitur kategori perlu diubah menjadi data numerik karena sebagian besar algoritma machine learning tidak dapat bekerja secara langsung dengan data non-numerik. Model seperti SVM, dan jaringan saraf, misalnya, memerlukan input numerik untuk menghitung jarak, korelasi, atau melakukan operasi matematika lainnya. 

**Reduksi Dimensi dengan PCA**

teknik PCA digunakan untuk mereduksi variabel asli menjadi sejumlah kecil variabel baru yang tidak berkorelasi linier, disebut komponen utama (PC). Komponen utama ini dapat menangkap sebagian besar varians dalam variabel asli. Sehingga, saat teknik PCA diterapkan pada data, ia hanya akan menggunakan komponen utama dan mengabaikan sisanya. 

Berikut penjelasan untuk masing-masing komponen utama (PC):

- PC pertama mewakili arah varians maksimum dalam data. Ia paling banyak menangkap informasi dari semua fitur dalam data. 
- PC kedua menangkap sebagian besar informasi yang tersisa setelah PC pertama. 
- PC ketiga menangkap sebagian besar informasi yang tersisa setelah PC pertama, PC kedua, dst.

![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-18.png?raw=true)

pada pairplot diatas terlihat kalau ketiga feature yaitu Fuel Consumption City (L/100 km), Fuel Consumption Hwy (L/100 km) dan Fuel Consumption Comb (L/100 km) memiliki korelasi yang cukup tinggi sehingga dapat dilakukan proses reduksi dimensi

- Setelah diketahui ketiga fitur tersebut berkorelasi dilakukan reduksi dimensi dengan PCA, membuat fitur baru yaitu Fuel Consumption untuk menggantikan ketiga fitur tersebut.


**Train-Test-Split**

Sebelum melakukan train-test-split, langkah awalnya adalah memisahkan antara fitur dan label. Variabel x digunakan untuk menyimpan fitur yang terdiri dari:

- Engine Size(L)
- Cylinders
- Transmission
- Fuel Consumption Comb (mpg)
- Fuel_Type_D
- Fuel_Type_E
- Fuel_Type_N
- Fuel_Type_X
- Fuel_Type_Z
- Fuel Consumption

Sedangkan variabel y digunakan untuk menyimpan label yaitu CO2 Emissions (g/km).

Selanjutnya, dilakukan train-test-split dengan pembagian data sebesar 90:10 antara data latih (train) dan data uji (test). Dari total 4107 data, setelah dilakukan pembagian, data terbagi menjadi 3696 untuk data latih dan 411 untuk data uji.

**Standarisasi**

Algoritma machine learning memiliki performa lebih baik dan konvergen lebih cepat ketika dimodelkan pada data dengan skala relatif sama atau mendekati distribusi normal. Proses scaling dan standarisasi membantu untuk membuat fitur data menjadi bentuk yang lebih mudah diolah oleh algoritma. 

Selanjutnya dilakukan standarisasi dengan MinMaxScaler pada 4 fitur yaitu:

- Engine Size(L)	
- Cylinders	
- Transmission	
- Fuel Consumption Comb (mpg)

Nantinya standarisasi MinMaxScaler menghasilkan distribusi data yang ada pada rentang 0 dan 1.

**Jadi mengapa perlu dilakukan data prepration?**

- Perlu dilakukan proses encoding pada data categorical karena sebagian besar algoritma machine learning tidak dapat bekerja secara langsung dengan data non-numerik.

- Reduksi dimensi bermanfaat untuk menyederhanakan data, mempercepat pelatihan model, dan mengurangi risiko overfitting serta masalah multikolinearitas.

- Memisahkan data menjadi set pelatihan dan pengujian memungkinkan kita untuk mengevaluasi kinerja model pada data yang tidak pernah dilihat sebelumnya. Ini memberikan gambaran yang lebih akurat tentang seberapa baik model dapat menggeneralisasi ke data baru.

- Proses standarisasi membantu untuk membuat fitur data menjadi bentuk yang lebih mudah diolah karena algoritma machine learning memiliki performa lebih baik dan konvergen lebih cepat ketika dimodelkan pada data dengan skala relatif sama atau mendekati distribusi normal.

## Modeling

Model machine learning yang digunakan untuk masalah ini terdiri dari 5 model yaitu:

- DecisionTreeRegressor dengan parameter sebagai berikut:

  - max_depth = None :  Kedalaman maksimum pohon (default: None, yang berarti pohon akan terus tumbuh hingga semua daun murni atau hingga semua daun memiliki kurang dari min_samples_split sampel).

  - min_samples_split = Jumlah minimum sampel yang diperlukan untuk membagi simpul (default: 2).

  - min_samples_leaf = Jumlah minimum sampel yang diperlukan untuk berada di simpul daun (default: 1).

  - max_features = Jumlah maksimum fitur yang dipertimbangkan untuk pemisahan terbaik (default: None, yang berarti semua fitur dipertimbangkan).

  - random_state =  Menentukan generator bilangan acak untuk memastikan hasil yang dapat direproduksi (default: None).

- K-Nearest Neighbor dengan parameter sebagai berikut:

  - n_neighbors = 10 : jumlah tetangga yang digunakan untuk mengukur jarak

- LinearRegression dengan parameter sebagai berikut:

  - fit_intercept = True: Menentukan apakah model akan menghitung intercept (konstanta) dari regresi. Jika diatur ke True, model akan memasukkan intercept dalam perhitungan.

  - n_jobs = None: Menentukan jumlah pekerjaan paralel untuk menghitung (fit) model. None berarti menggunakan satu inti; jika diatur ke -1, akan menggunakan semua inti yang tersedia.

  - positive = False: Menentukan apakah koefisien regresi harus dibatasi menjadi nilai positif. Jika diatur ke True, model akan memaksa semua koefisien menjadi non-negatif.

- Support Vector Regression dengan parameter sebagai berikut:

  - C = 1.0: Parameter regulasi yang mengontrol trade-off antara minimisasi kesalahan pelatihan dan kompleksitas model. Nilai yang lebih tinggi akan menghasilkan model yang lebih kompleks, sedangkan nilai yang lebih rendah dapat menghasilkan model yang lebih sederhana.

  - epsilon = 0.1: Menentukan margin toleransi di sekitar garis prediksi. Ini berarti bahwa kesalahan di dalam margin ini tidak akan dikenakan penalti. Dengan kata lain, model tidak akan berusaha untuk memperbaiki kesalahan di dalam radius epsilon.

  - gamma = 'scale': Mengontrol pengaruh titik pelatihan individu. Jika diatur ke 'scale', gamma akan dihitung sebagai 1 / (n_features * X.var()). Ini menentukan seberapa jauh pengaruh dari titik data.

  - kernel = 'rbf': Menggunakan kernel Radial Basis Function (RBF) untuk mengubah data menjadi dimensi yang lebih tinggi, memungkinkan pemisahan yang lebih kompleks. Kernel ini adalah pilihan umum dalam SVM karena kemampuannya untuk menangkap hubungan non-linear.

- RandomForestRegressor dengan parameter sebagai berikut:

  - n_estimators = 50: Menentukan jumlah pohon keputusan (trees) dalam hutan (forest). Semakin banyak pohon yang digunakan, model biasanya akan lebih kuat dan lebih robust, meskipun waktu pelatihan dan prediksi akan meningkat.

  - max_depth = 16: Menentukan kedalaman maksimum setiap pohon dalam hutan. Ini digunakan untuk menghindari overfitting. Semakin dalam pohon, semakin banyak informasi yang dapat dipelajari, tetapi juga meningkatkan risiko model terlalu kompleks.

  - random_state = 55: Parameter ini digunakan untuk memastikan reproduktifitas hasil. Dengan mengatur random_state, Anda akan mendapatkan hasil yang sama setiap kali Anda menjalankan kode.

  - n_jobs = -1: Menentukan jumlah inti (cores) yang digunakan untuk menghitung. Jika diatur ke -1, model akan menggunakan semua inti yang tersedia, sehingga mempercepat proses pelatihan.

- AdaBoostRegressor dengan parameter sebagai berikut:

  - estimator =  RF Menentukan model dasar yang digunakan sebagai estimator. Dalam hal ini, model dasar yang digunakan adalah RandomForestRegressor (yang telah didefinisikan sebelumnya dengan nama RF).

  - learning_rate = 0.05 Parameter ini mengontrol kontribusi setiap estimator ke model akhir. Dalam hal ini, learning rate diatur menjadi 0.05.

  - random_state = 55 Parameter ini digunakan untuk memastikan bahwa hasil dapat direproduksi. Dengan menetapkan nilai acak, Anda akan mendapatkan hasil yang sama setiap kali Anda menjalankan kode.

**Kelebihan dan Kekurangan 6 model tersebut?**.

- **Decision Tree Regressor**
  - **Kelebihan:**
    - Mudah dipahami dan diinterpretasikan.
    - Tidak memerlukan normalisasi data.
    - Dapat menangani data dengan hubungan non-linear dan interaksi antar fitur.
    - Menyediakan representasi grafis yang jelas dan mudah dimengerti.

  - **Kekurangan:**
    - Rentan terhadap overfitting, terutama jika pohon terlalu dalam.
    - Sensitif terhadap perubahan kecil dalam data.
    - Tidak dapat menggeneralisasi dengan baik pada data yang tidak terlihat.

- **K-Nearest Neighbor (KNN)**
  - **Kelebihan:**
    - Sederhana dan intuitif.
    - Tidak memerlukan asumsi tentang distribusi data.
    - Dapat digunakan untuk regresi dan klasifikasi.

  - **Kekurangan:**
    - Kinerja dapat menurun pada dataset yang besar karena memerlukan pencarian tetangga terdekat untuk setiap prediksi.
    - Sensitif terhadap fitur yang tidak relevan dan skala variabel.
    - Memerlukan penyimpanan seluruh dataset untuk melakukan prediksi.

- **Linear Regression**
  - **Kelebihan:**
    - Mudah diinterpretasikan dan dimplementasikan.
    - Cepat dalam pelatihan dan prediksi.
    - Bagus untuk hubungan linier antara variabel independen dan dependen.

  - **Kekurangan:**
    - Tidak dapat menangani hubungan non-linear tanpa transformasi data.
    - Sensitif terhadap outlier, yang dapat mempengaruhi akurasi model.
    - Membuat asumsi bahwa ada hubungan linier antara variabel.

- **Support Vector Regression (SVR)**
  - **Kelebihan:**
    - Kuat dalam menangani dataset dengan dimensi tinggi.
    - Dapat menangkap hubungan non-linear melalui penggunaan kernel.
    - Fleksibilitas dalam pengaturan parameter seperti C, epsilon, dan gamma.

  - **Kekurangan:**
    - Memerlukan tuning parameter yang tepat, yang dapat mempengaruhi kinerja model.
    - Lebih lambat dalam pelatihan dibandingkan model lainnya, terutama pada dataset yang besar.
    - Sulit untuk diinterpretasikan dibandingkan model lain.

- **Random Forest Regressor**
  - **Kelebihan:**
    - Menggabungkan hasil dari banyak pohon keputusan untuk menghasilkan prediksi yang lebih akurat dan robust.
    - Memiliki mekanisme built-in untuk menangani overfitting.
    - Dapat menangani data yang hilang dengan baik.

  - **Kekurangan:**
    - Lebih lambat dalam pelatihan dan prediksi dibandingkan model sederhana seperti linear regression.
    - Model yang dihasilkan sulit untuk diinterpretasikan secara langsung.
    - Memerlukan lebih banyak memori dibandingkan model yang lebih sederhana.

- **AdaBoostRegressor**
  - **Kelebihan:**
    - Menggabungkan kekuatan dari beberapa estimator lemah untuk membentuk model yang lebih kuat.
    - Meningkatkan akurasi prediksi dengan memberi bobot lebih pada kesalahan.
    - Dapat meningkatkan model yang sudah ada (seperti Random Forest) untuk hasil yang lebih baik.

  - **Kekurangan:**
    - Sensitif terhadap outlier, yang dapat mempengaruhi hasil akhir.
    - Mungkin memerlukan tuning parameter untuk mendapatkan hasil terbaik.
    - Tidak dapat menangani data yang sangat besar dengan efisiensi yang sama seperti model lainnya.

**Mengapa menggunakan 6 model tersebut?**.

- Decision Tree Regressor Model ini mudah dipahami dan diinterpretasikan. Decision Tree dapat menangani data dengan hubungan non-linear dan interaksi antar fitur tanpa perlu transformasi fitur. Selain itu, ia tidak memerlukan normalisasi data.

- K-Nearest Neighbor (KNN) model non-parametrik yang sederhana dan efektif. Ia mengklasifikasikan atau melakukan regresi berdasarkan kedekatan ke tetangga terdekat, sehingga sangat intuitif.

- Linear Regression adalah dasar dari banyak teknik regresi dan mudah untuk diinterpretasikan. Ia memberikan wawasan langsung tentang hubungan linier antara variabel independen dan dependen.

- Support Vector Regression (SVR) sangat kuat dalam menangani dataset dengan dimensi tinggi dan dapat menangkap hubungan non-linear melalui kernel. Pengaturan parameter seperti C, epsilon, dan gamma memungkinkan fleksibilitas dalam model.

- Random Forest Regressor menggabungkan hasil dari banyak pohon keputusan untuk menghasilkan prediksi yang lebih akurat dan robust. Ia juga memiliki mekanisme built-in untuk menangani overfitting dan dapat menangani data yang hilang dengan baik.

- AdaBoostRegressor model ini menggabungkan kekuatan dari beberapa estimator lemah (dalam hal ini, Random Forest) untuk membentuk model yang lebih kuat. Dengan menekankan kesalahan dari estimator sebelumnya, AdaBoost meningkatkan akurasi prediksi secara keseluruhan. Proses ini dilakukan dengan memberikan bobot lebih pada data yang salah diprediksi oleh model sebelumnya, sehingga model lebih fokus pada memperbaiki kesalahan tersebut. 


## Evaluation

Metrik evaluasi yang digunakan dalam analisis ini adalah Mean Squared Error (MSE), yang berfungsi untuk mengukur seberapa besar kesalahan antara nilai aktual dan nilai yang diprediksi oleh model. MSE dihitung dengan cara mengkuadratkan selisih antara nilai aktual dan nilai prediksi, kemudian menghitung rata-ratanya.

- Berikut adalah hasil yang diperoleh dari metrik ini, diurutkan dari kesalahan terkecil hingga terbesar:

  | Model              | Train MSE | Test MSE  |
  |--------------------|-----------|-----------|
  | Decision Tree      | 0.00136   | 0.013918  |
  | K-Nearest Neighbor  | 0.011688  | 0.009706  |
  | Linear Regression   | 0.015147  | 0.012832  |
  | Support Vector Reg. | 0.197193  | 0.200042  |
  | Random Forest      | 0.002827  | 0.009253  |
  | AdaBoost with RF   | 0.002292  | 0.009014  |


  ![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-22.png?raw=true)

  | y_true | prediksi_KNN | prediksi_DecisionTree | prediksi_LinearRegression | prediksi_SVR | prediksi_RF | prediksi_boosting_RF |
  |--------|---------------|-----------------------|---------------------------|---------------|-------------|-----------------------|
  | 3880   | 313           | 310.2                 | 317.0                     | 310.0         | 312.2       | 314.7                 |
  | 873    | 242           | 245.3                 | 246.0                     | 245.3         | 245.5       | 243.8                 |
  | 1094   | 198           | 202.1                 | 201.0                     | 200.7         | 201.7       | 201.3                 |
  | 1778   | 170           | 170.4                 | 172.0                     | 169.1         | 170.7       | 170.9                 |
  | 4785   | 291           | 293.5                 | 293.0                     | 292.3         | 293.9       | 291.7                 |


  - Dari tabel di atas, dapat dilihat bahwa setiap model menghasilkan prediksi yang bervariasi untuk setiap nilai aktual (y_true). Model K-Nearest Neighbor (KNN) dan Decision Tree memberikan prediksi yang cukup dekat dengan nilai aktual pada beberapa data, sementara Linear Regression dan Random Forest juga menunjukkan hasil yang kompetitif. Model AdaBoost dengan Random Forest (boosting_RF) tampaknya menghasilkan prediksi yang lebih konsisten, dengan kesalahan relatif yang lebih kecil pada nilai prediksi dibandingkan dengan beberapa model lainnya. Secara keseluruhan, performa model dapat bervariasi tergantung pada karakteristik data dan hubungan yang ada antara fitur dan target.

**Formula Mean Squared Error dan cara Mean Squared Error bekerja** 

formula Mean Squared Error :

![alt text](https://github.com/Agim-dudu/Predictive-Analytic---CO2-Emission/blob/main/Assets/image-21.png?raw=true)


**Bagaimana cara Mean Squared Error bekerja?**

Metrik yang akan kita gunakan pada prediksi ini adalah MSE atau Mean Squared Error yang menghitung jumlah selisih kuadrat rata-rata nilai sebenarnya dengan nilai prediksi.

- MSE mengukur rata-rata dari kuadrat selisih antara nilai yang diprediksi oleh model dan nilai aktual (ground truth). Rumus MSE pada gambar diatas.


Keterangan:

N = jumlah dataset

yi = nilai sebenarnya

y_pred = nilai prediksi



