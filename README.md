# DAE Reading Interest In Indonesia
📊 Analisis Skrip Python dan Outputnya
Kode Python yang Anda berikan adalah contoh analisis data eksploratif yang bertujuan untuk membersihkan data dari outlier (nilai pencilan) menggunakan metode IQR (Interquartile Range). Mari kita uraikan maksud dari setiap bagian dan analisis hasilnya.

💡 Maksud dari Kode Python
Kode ini melakukan analisis data dasar dengan fokus pada pembersihan data (data cleaning). Prosesnya dapat dibagi menjadi tiga langkah utama:

Eksplorasi Data Awal ✨:

Menggunakan pustaka Pandas untuk membaca dataset. Perintah sep=';' dan decimal=',' disesuaikan untuk membaca data yang menggunakan titik koma sebagai pemisah kolom dan koma sebagai pemisah desimal, format yang umum di Indonesia.

Metode .info() memberikan ringkasan struktur data, seperti jumlah baris (140), nama kolom, tipe data, dan jumlah data yang tidak kosong. Dari sini kita bisa langsung melihat bahwa ada data yang hilang 😱 pada kolom terkait internet.

.describe() memberikan statistik ringkasan (rata-rata, median, min, max, dll.) yang membantu kita memahami distribusi data secara cepat.

Deteksi dan Penghapusan Outlier 🧹:

Skrip ini mendefinisikan sebuah fungsi, remove_outliers_iqr, yang menggunakan metode Interquartile Range (IQR) untuk mendeteksi outlier.

Metode ini bekerja dengan menghitung rentang normal data (antara kuartil pertama Q1 dan ketiga Q3) dan kemudian menetapkan batas atas dan bawah. Nilai apa pun di luar batas ini akan dianggap sebagai outlier dan dihapus.

Visualisasi 📈:

Kode ini menggunakan pustaka Matplotlib untuk memvisualisasikan dampak dari proses pembersihan. Dua histogram dibuat berdampingan.

Histogram sebelum pembersihan menunjukkan distribusi asli data, termasuk nilai-nilai ekstrem (outlier).

Histogram setelah pembersihan menunjukkan distribusi data yang lebih terkonsentrasi, karena nilai-nilai outlier sudah dihapus, memberikan representasi yang lebih akurat dari mayoritas data.

✅ Analisis Hasil Output
Output dari kode memberikan informasi penting tentang dataset dan proses pembersihan:

Ringkasan Data: Data terdiri dari 140 baris dan 9 kolom. Kolom terkait internet memiliki 35 data yang hilang (hanya 105 data yang lengkap).

Deteksi Outlier: Untuk kolom Daily Reading Duration (in minutes), kode ini menghitung batas outlier menggunakan metode IQR. Batas bawahnya adalah 68.25 menit dan batas atasnya 128.65 menit.

Pembersihan Data: Kode ini berhasil mengidentifikasi dan menghapus outlier yang berada di luar rentang tersebut. Dari 140 baris data awal, hanya tersisa 137 baris. Ini berarti ada 3 outlier yang berhasil dihilangkan dari dataset pada kolom tersebut.

Secara keseluruhan, kode ini merupakan langkah awal yang baik dalam analisis data, memastikan bahwa data yang digunakan untuk analisis lebih lanjut sudah bersih dari nilai-nilai ekstrem yang tidak wajar.
