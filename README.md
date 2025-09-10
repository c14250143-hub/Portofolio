## Analisis Data Eksplorasi Titanic 🚢
--------------------------------------------
Analisis ini membantu kita memahami karakteristik utama dari para penumpang yang ada. 🕵️‍♀️

Analisis Utama Berdasarkan Kode 💻
Struktur dan Tampilan Data 📊

Dataset Titanic dimuat dari library Seaborn.

Penggunaan head() dan tail() memberikan gambaran awal data, seperti kolom-kolom yang tersedia (survived, pclass, sex, age, dll.).

titanic.info() menunjukkan struktur data, termasuk 891 baris dan 15 kolom. Ini juga mengungkapkan adanya nilai yang hilang (Age, deck, embarked, embark_town). 🧐

Statistik Deskriptif 📈
-------------------------------------

Fungsi titanic.describe() memberikan ringkasan statistik untuk kolom numerik.

Usia rata-rata penumpang sekitar 29.7 tahun. 👶👴

Variasi harga tiket (fare) sangat besar, dengan harga dari 0 hingga lebih dari 512. 💰

Penanganan Nilai yang Hilang (Missing Values) ❓

Analisis titanic.isnull().sum() mengonfirmasi bahwa kolom Age dan deck memiliki banyak nilai yang hilang.

Kolom deck adalah yang paling parah, dengan 688 nilai yang hilang dari total 891. 🗑️

Analisis Visual 🖼️
-------------------------------------

Distribusi Usia: Histogram menunjukkan bahwa mayoritas penumpang berada dalam rentang usia 20-an hingga 30-an. 🧑

Distribusi Tarif: Sebagian besar tiket dijual dengan harga murah, dengan beberapa tiket berharga sangat mahal. 💸

Jumlah Penumpang per Kelas: Bar plot menunjukkan bahwa Kelas 3 adalah kelas dengan jumlah penumpang terbanyak. 🎫

Analisis Bertahan Hidup: 🆘
----------------------------------

Bar plot menunjukkan bahwa lebih banyak penumpang yang tidak selamat daripada yang selamat.

Analisis survived berdasarkan sex adalah temuan paling penting: wanita memiliki tingkat kelangsungan hidup yang jauh lebih tinggi daripada pria. Ini menunjukkan prioritas dalam penyelamatan. 👩‍🦳➡️ ✅, 👨‍🦳➡️ ❌

Penumpang Kelas 1 juga memiliki tingkat kelangsungan hidup tertinggi. 🥇

Kesimpulan dan Temuan Kunci 🌟
------------------------------------------------------------------------------
Analisis ini memberikan wawasan yang kuat tentang dataset Titanic. Beberapa temuan paling signifikan meliputi:

Tingkat kelangsungan hidup wanita jauh lebih tinggi daripada pria. 👩‍🔬

Penumpang di kelas yang lebih tinggi (kelas 1) memiliki kemungkinan lebih besar untuk selamat. 👑

Dataset memiliki nilai yang hilang yang signifikan yang perlu ditangani. ⚠️

Langkah selanjutnya setelah EDA ini adalah melakukan pra-pemrosesan data, merekayasa fitur, dan membangun model machine learning untuk memprediksi siapa yang akan selamat. 🤖
