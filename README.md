# Tugas Analisis Statistik: Deskriptif, Korelasi, dan Regresi

## 1. Informasi Penyusun

- **Nama:** `[I GUSTI AGUNG WIDHYAMERTA]`
- **NIM:** `[2515091085]`
- **Program Studi:** `[SISTEM INFORMASI]`
- **Mata Kuliah:** Statistika dan Probabilitas

---

## 2. Deskripsi Proyek

Pada bagian ini, jelaskan secara singkat dataset yang Anda gunakan. Apa saja variabel di dalamnya? Apa tujuan dari analisis yang Anda lakukan?

> Dataset yang digunakan adalah data `data_startup_saas.csv` yang berisi informasi tentang `"Nama_Startup","Kategori_Layanan","Pendapatan_Tahunan_Miliar_IDR","Biaya_Akuisisi_Pelanggan_Juta_IDR","Nilai_Pelanggan_Juta_IDR","Tingkat_Churn_Persen"`. Variabel kunci dalam dataset ini meliputi `variabel_A`, `variabel_B`, dan `variabel_C`.Tujuan dari analisis ini adalah untuk memahami karakteristik data melalui analisis statistik deskriptif, menguji kekuatan dan arah hubungan antara pendapatan tahunan dan nilai pelanggan melalui analisis korelasi, serta membangun model regresi linear untuk memprediksi nilai pelanggan berdasarkan pendapatan tahunan perusahaan.
---

## 3. Struktur Proyek

Proyek ini diorganisir ke dalam beberapa folder:
- `/data`: Berisi dataset mentah yang digunakan untuk analisis.
- `/scripts`: Berisi semua skrip R yang digunakan dalam analisis, diurutkan berdasarkan alur kerja.
- `/results`: Berisi output dari analisis, seperti plot, gambar, atau tabel ringkasan.

---

## 4. Cara Menjalankan Analisis

Untuk mereproduksi hasil analisis ini, ikuti langkah-langkah berikut:
1. Pastikan Anda memiliki R dan RStudio terinstal.
2. Buka proyek R ini di RStudio.
3. Instal paket yang diperlukan dengan menjalankan perintah berikut di konsol R:
   ```R
   # install.packages(c("tidyverse", "corrplot", "knitr"))
   ```
4. Jalankan skrip di dalam folder `/scripts` secara berurutan, mulai dari `01_data_preparation.R` hingga `05_analisis_regresi.R`.

---

## 5. Hasil dan Interpretasi

Di bagian ini, mahasiswa diharapkan untuk menyajikan dan menginterpretasikan hasil dari setiap tahap analisis.

### 5.1. Statistik Deskriptif
- **Ukuran Pemusatan (Mean, Median, Modus):**
  - *Tabel atau ringkasan...*
     jawaban : "Mean dari Pendapatan_Tahunan_Miliar_IDR : 31.88","Median dari Pendapatan_Tahunan_Miliar_IDR : 31.3","Modus dari Pendapatan_Tahunan_Miliar_IDR : 1.8
  - *Interpretasi:* Jelaskan apa arti dari nilai-nilai tersebut terkait dengan data Anda.
     jawaban : kolom yang saya analisis dari dataset adalah pendapatan_tahunan_miliar_IDR.mean adalah rata rata yang dimana rata rata kolom pendapatan_tahunan_miliar_IDR adalah 31.88.median adalah nilai tengah yang mendapatkan hasil 31.3.nilai yang paling sering muncul      atau modus dalam pendapatan_tahunan_miliar_IDR adalah 1.87.
- **Ukuran Sebaran (Standar Deviasi, Range, Kuartil):**
  - *Tabel atau ringkasan...*
     jawaban : "Standar Deviasi dari Pendapatan_Tahunan_Miliar_IDR : 19.79", "Range dari Pendapatan_Tahunan_Miliar_IDR : 1 - 66.89", "Ringkasan 5 Angka untuk Pendapatan_Tahunan_Miliar_IDR :Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
                                                                                                                                                                                             1.00   14.31   31.30   31.88   49.04   66.89 
  - *Interpretasi:* Jelaskan seberapa menyebar data Anda berdasarkan nilai-nilai ini.
     jawaban : berdasarkan nilai standar deviasi,data menyebar 19.79. berdasarkan nilai range,data menyebar 1-66.89.berdasarkan kuartil,data menyebar min:1.00 , 1st Qu:14.31 , median:31.30 , mean 3rd Qu:31.88 49.04 , max:66.89.
- **Visualisasi (Histogram/Boxplot):**
  - *Sematkan gambar plot dari folder /results...*
     jawaban : ![alt text](https://github.com/agungwidhyamerta/Project_Akhir_Statistika-dan-Probabilitas-I-GUSTI-AGUNG-WIDHYAMERTA-2515091085/blob/main/results/boxplot_Pendapatan_Tahunan_Miliar_IDR.png)
               ![alt text](https://github.com/agungwidhyamerta/Project_Akhir_Statistika-dan-Probabilitas-I-GUSTI-AGUNG-WIDHYAMERTA-2515091085/blob/main/results/histogram_Pendapatan_Tahunan_Miliar_IDR.png)
  - *Interpretasi:* Jelaskan wawasan apa yang Anda dapatkan dari bentuk distribusi data.
     jawaban : Berdasarkan boxplot dan histogram pendapatan tahunan (dalam miliar IDR), terlihat bahwa sebaran data pendapatan cenderung merata dari nilai rendah hingga tinggi, tanpa adanya penumpukan data yang ekstrem pada satu rentang tertentu. Histogram menunjukkan        batang yang relatif seimbang di seluruh rentang nilai, sementara garis rata-rata (mean) berada di sekitar 31,88 miliar IDR dan terletak di tengah distribusi, yang menandakan bahwa pendapatan tidak condong ke sisi rendah maupun tinggi. Boxplot juga memperlihatkan        median yang berada di sekitar nilai tengah dengan jarak antar kuartil yang cukup lebar, menandakan adanya variasi pendapatan yang cukup besar antar entitas. Selain itu, tidak terlihat outlier yang mencolok, sehingga dapat disimpulkan bahwa data pendapatan ini           stabil, representatif, dan layak digunakan untuk analisis lanjutan karena tidak menunjukkan pola yang menyimpang atau bias ekstrem.

### 5.2. Uji Normalitas
- **Hasil Uji Shapiro-Wilk:**
  - *Nilai p-value...*
    jawababn : Nilai p-value = 1.497e-14
  - *Interpretasi:* Apakah data Anda terdistribusi normal berdasarkan hasil uji? Apa implikasinya?
    jawaban : Karena Interpretasi: p-value = 0 <= 0.05. Data kemungkinan besar TIDAK terdistribusi normal. Jika data tidak terdistribusi normal maka implikasinya hasil analisis bisa menjadi kurang akurat, terutama pada jumlah data yang terbatas. Selain itu, nilai rata-     rata dan standar deviasi juga bisa kurang mewakili kondisi data yang sebenarnya, sehingga median dan rentang antar kuartil sering kali lebih tepat digunakan. Data yang tidak normal juga cenderung memiliki sebaran yang tidak simetris atau mengandung nilai ekstrem,       yang dapat memengaruhi hasil model. Oleh karena itu, diperlukan penyesuaian seperti melakukan transformasi data atau menggunakan metode statistik non-parametrik agar analisis tetap valid dan hasil yang diperoleh dapat dipercaya.
- **Plot Q-Q:**
  - *Sematkan gambar plot dari folder /results...*
    jawaban : ![alt text](https://github.com/agungwidhyamerta/Project_Akhir_Statistika-dan-Probabilitas-I-GUSTI-AGUNG-WIDHYAMERTA-2515091085/blob/main/results/qqplot_Pendapatan_Tahunan_Miliar_IDR.png)
  - *Interpretasi:* Apakah titik-titik data mengikuti garis lurus? Apa artinya?
    jawaban : Titik-titik data pada Q–Q plot tidak sepenuhnya mengikuti garis lurus, karena meskipun di bagian tengah terlihat cukup dekat dengan garis, pada bagian bawah dan terutama bagian atas terjadi penyimpangan yang jelas membentuk pola melengkung. Hal ini            menunjukkan bahwa data pendapatan tahunan tidak berdistribusi normal, khususnya pada nilai ekstrem. Dengan demikian, asumsi normalitas tidak terpenuhi, sehingga dalam analisis lanjutan perlu dipertimbangkan penggunaan transformasi data atau metode statistik             alternatif yang tidak mengharuskan data berdistribusi normal.

### 5.3. Analisis Korelasi
- **Nilai Koefisien Korelasi:**
  - *Nilai r...*
    jawaban : Nilai Koefisien Korelasi (r) = 0.995
  - *Interpretasi:* Seberapa kuat dan apa arah hubungan antara dua variabel yang Anda uji? (misalnya, korelasi positif kuat, negatif lemah, atau tidak ada korelasi).
    jawaban : Berdasarkan analisa saya, ini menunjukkan adanya korelasi positif kuat antara Pendapatan_Tahunan_Miliar_IDR dan Biaya_Akuisisi_Pelanggan_Juta_IDR
- **Visualisasi (Scatter Plot):**
  - *Sematkan gambar plot dari folder /results...*
    jawaban : ![alt text](https://github.com/agungwidhyamerta/Project_Akhir_Statistika-dan-Probabilitas-I-GUSTI-AGUNG-WIDHYAMERTA-2515091085/blob/main/results/scatterplot_Pendapatan_Tahunan_Miliar_IDR_vs_Biaya_Akuisisi_Pelanggan_Juta_IDR.png)
  - *Interpretasi:* Apakah pola pada scatter plot mendukung hasil koefisien korelasi?
    jawaban : Ya, pola pada scatter plot mendukung hasil koefisien korelasi. Titik-titik data terlihat membentuk pola yang cenderung naik dan mengikuti arah garis tren linear, yang menunjukkan hubungan positif antara pendapatan tahunan dan biaya akuisisi pelanggan.         artinya, ketika pendapatan meningkat biaya akuisisi pelanggan juga cenderung ikut meningkat. Meskipun terdapat beberapa titik yang menyebar dan tidak persis berada di garis, pola keseluruhan tetap konsisten dan searah sehingga secara visual memperkuat bahwa           hubungan yang ditunjukkan oleh koefisien korelasi memang nyata dan bukan kebetulan.

### 5.4. Analisis Regresi
- **Model Regresi:**
  - *Persamaan regresi: Y = b0 + b1*X*
    jawaban : Y : 1.37 + 1.01*X* 
  - *Interpretasi:* Jelaskan arti dari koefisien intercept (b0) dan slope (b1) dalam konteks data Anda.
    jawaban : 
- **Evaluasi Model (R-squared):**
  - *Nilai R-squared...*
    jawaban : nilai R-squared = 0.991 atau 99.1 %"
  - *Interpretasi:* Berapa persen variasi dari variabel dependen yang dapat dijelaskan oleh model regresi Anda?
    jawaban : 99.1 %, Artinya, 99.1 % variasi pada Biaya_Akuisisi_Pelanggan_Juta_IDR dapat dijelaskan oleh Pendapatan_Tahunan_Miliar_IDR melalui model ini.
- **Visualisasi (Garis Regresi pada Scatter Plot):**
  - *Sematkan gambar plot dari folder /results...*
    jawaban : ![alt text](https://github.com/agungwidhyamerta/Project_Akhir_Statistika-dan-Probabilitas-I-GUSTI-AGUNG-WIDHYAMERTA-2515091085/blob/main/results/scatterplot_Pendapatan_Tahunan_Miliar_IDR_vs_Biaya_Akuisisi_Pelanggan_Juta_IDR.png)
  - *Interpretasi:* Jelaskan bagaimana garis regresi merepresentasikan hubungan antara variabel.
    jawaban : Garis regresi pada grafik ini merepresentasikan hubungan linear yang sangat kuat antara pendapatan tahunan dan biaya akuisisi pelanggan, di mana garis yang menanjak menunjukkan bahwa setiap peningkatan pendapatan tahunan diikuti oleh peningkatan biaya         akuisisi pelanggan. Posisi garis yang sangat dekat dengan titik-titik data menandakan bahwa model mampu menjelaskan pola hubungan antar variabel dengan sangat baik, yang juga diperkuat oleh nilai adjusted R-squared sebesar 0,991. Artinya, hampir seluruh variasi         biaya akuisisi pelanggan dapat dijelaskan oleh perubahan pendapatan tahunan, sehingga hubungan yang ditunjukkan bukan sekadar kebetulan, melainkan pola yang konsisten dan dapat diandalkan untuk memahami maupun memprediksi perilaku data.

---

## 6. Kesimpulan

Rangkum temuan utama dari analisis Anda dalam beberapa kalimat. Apa wawasan paling penting yang Anda peroleh?




