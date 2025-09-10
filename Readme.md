# Analisis Data Eksplorasi (EDA) Dataset Titanic

Analisis ini didasarkan pada notebook Jupyter yang melakukan eksplorasi data pada dataset Titanic, yang bertujuan untuk memahami struktur, distribusi, dan hubungan antar variabel.

---

## 1. Ikhtisar Dataset

* **Pemuatan Data:** Dataset dimuat dari library `seaborn`.
* **Struktur Data:** Dataset terdiri dari **891 baris** dan **15 kolom**.
* **Ringkasan Informasi:**
    * Kolom `Age`, `deck`, `embarked`, dan `embark_town` memiliki nilai yang hilang (missing values).
    * Tipe data beragam, termasuk numerik (`age`, `fare`) dan kategorikal (`sex`, `pclass`).

---

## 2. Statistik Deskriptif

Ringkasan statistik menunjukkan karakteristik utama dari kolom numerik:

* **Usia (Age):** Rata-rata usia penumpang adalah sekitar **29,7 tahun**. Rentang usia sangat bervariasi, dari 0,42 hingga 80 tahun.
* **Tarif (Fare):** Harga tiket memiliki variasi yang sangat besar, dengan sebagian besar tiket berharga rendah dan beberapa tiket sangat mahal (maksimum **512,33**).
* **Penanganan Nilai Hilang:** Kolom **`deck`** memiliki jumlah nilai yang hilang paling banyak, yaitu **688 dari 891**.

---

## 3. Temuan dan Analisis Kunci (Berdasarkan Visualisasi)

### Distribusi Penumpang

* **Kelas Penumpang (Pclass):** Kelas **3** memiliki jumlah penumpang terbanyak, diikuti oleh Kelas 1 dan Kelas 2.
* **Distribusi Usia:** Distribusi usia cenderung terkonsentrasi pada rentang **20-an hingga 30-an**.

### Faktor Kelangsungan Hidup (Survival)

* **Kelangsungan Hidup Keseluruhan:** Lebih banyak penumpang yang **tidak selamat** dibandingkan yang selamat.
* **Jenis Kelamin:** **Perempuan memiliki tingkat kelangsungan hidup yang jauh lebih tinggi** dibandingkan laki-laki. Ini adalah temuan paling signifikan, yang menunjukkan bahwa operasi penyelamatan memprioritaskan wanita.
* **Kelas Penumpang:** Penumpang di **Kelas 1** memiliki kemungkinan bertahan hidup yang lebih besar dibandingkan penumpang di Kelas 2 dan Kelas 3. Hal ini mengindikasikan bahwa kelas sosial merupakan faktor penentu kelangsungan hidup.

---

## 4. Kesimpulan

Analisis ini berhasil mengidentifikasi pola-pola utama dalam dataset Titanic. Temuan-temuan ini memberikan dasar yang kuat untuk langkah selanjutnya, seperti pembersihan data, rekayasa fitur, dan pembangunan model *machine learning* untuk memprediksi kelangsungan hidup.
