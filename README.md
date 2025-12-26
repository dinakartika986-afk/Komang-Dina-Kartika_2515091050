# PROJECT AKHIR STATISTIKA DAN PROBABILITAS 
## IDENTITAS:
- Nama: Komang Dina Kartika
- NIM: 2515091050
- Program Studi: Sistem Informasi
- Mata Kuliah: Statistika dan Probabilitas
- Dosen Pengampu: I Nyoman Indhi Wiradika

## DESKRIPSI DATASET
Dataset yang digunakan merupakan data startup SaaS yang terdiri dari 650 observasi dan 6 variabel. Anaslisis yang saya lakukan yaitu untuk mencari tahu hubungan antara Pendapatan_Tahunan_Miliar_IDR dan Nilai_Pelanggan_Juta_IDR.

## STRUKTUR PROJECT
- data/ -> berisi dataset
- scripts/ -> berisi file R
- results/ -> berisi grafik dan output
- README.md -> dokumentasi project

## CARA MENJALANKAN PROGRAM
1. Instalasi package: install.packages(c("tidyverse", "ggplot2", "readr"))
2. urutan menjalankan Script: 
- 01_data_preparation.R
- 02_analisis_deskriptif.R
- 03_uji_asumsi.R
- 04_analisis_korelasi.R
- 05_analisis_regresi.R

## HASIL ANALISIS DAN INTERPRETASI
### Statistik deskriptif 
Variabel: Pendapatan_Tahunan_Miliar_IDR
- Mean: 31.88
- Median: 31.30
- Modus: 1.87
- Standar Deviasi: 19.79
- Range: 1.00-66.89
- Kuartil(Q1-Q3): 14.31-49.04
Interpretasi:
- Nilai Mean dan Median hampir sama, menunjukan distribusi relatif simetris.
- Histogram menunjukkan distribusi pendapatan cenderung miring ke kanan, dengan banyak startup berpendapatan rendah dan beberapa outlier dengan pendapatan tinggi.
- Boxplot mengonfirmasi adanya outlier di ekor kanan, menunjukkan beberapa startup dengan pendapatan sangat tinggi.
### Uji normalitas 
1. Q-Q plot: titik-titik tidak mengikuti garis diagonal secara sempurna
2. Statistik W: 0.94664
3. p-value = 1.497e-14 (≈ 0)
Interpretasi: Karena p-value ≤ 0.05, maka H₀ ditolak. Artinya Data Pendapatan_Tahunan_Miliar_IDR tidak terdistribusi normal
### Analisis Korelasi 
Variabel:
- X: Pendapatan_Tahunan_Miliar_IDR
- Y: Nilai_Pelanggan_Juta_IDR
Hasil:
- Koefisien korelasi (r) = 0.997
- Arah hubungan: Positif
- Kekuatan: Kuat
- p-value =  2.2e-16 (≈ 0)(signifikan)
Interpretasi: Terdapat korelasi positif sangat kuat dan signifikan antara nilai pelanggan, semakin tinggi nilai pelanggan, semakin besar pendapatan tahunan startup.
### Analisis Regresi
Model reresi linear: 
Pendapatan= −0.99 + 0.33 x Nilai_Pelanggan
Hasil Utama:
Slope (b₁) = 0.33
Adjusted R² = 0.994 (99.4%)
Interpretasi:
- Setiap kenaikan 1 juta rupiah nilai pelanggan akan meningkatkan pendapatan tahunan sekitar 0.33 miliar rupiah.
- Model mampu menjelaskan 99.4% variasi pendapatan, menunjukkan model sangat kuat dan akurat.

## Kesimpulan 
1. Data pendapatan startup SaaS tidak terdistribusi normal, dengan sebaran yang luas dan adanya outlier pendapatan tinggi.
2. Hubungan Pendapatan dan Nilai Pelanggan Terdapat hubungan positif yang sangat kuat dan signifikan antara pendapatan tahunan dan nilai pelanggan (r = 0.997).
3. Nilai pelanggan dapat digunakan untuk memprediksi pendapatan dengan akurasi sangat tinggi (R² = 99.4%). Setiap kenaikan 1 juta IDR nilai pelanggan, pendapatan diprediksi meningkat 0.33 miliar IDR.
4. Analisis ini membuktikan bahwa peningkatan nilai pelanggan sangat berpengaruh terhadap performa finansial startup SaaS.
