### 📊 Analisis Data Profil TikTok: Lebih Dalam Mengenai Statistik dan Engagement\! ✨

[cite\_start]Analisis ini didasarkan pada file **TikTok profiles dataset (Public web data).csv** yang Anda unggah[cite: 1]. Kami akan menelusuri data untuk mengungkap wawasan tentang profil-profil TikTok yang ada, mulai dari jumlah pengikut hingga tingkat engagement mereka.

-----

### 💻 Penjelasan Kode Python 🧑‍💻

Kode yang Anda lihat di bawah ini merupakan serangkaian langkah untuk membersihkan, menganalisis, dan memvisualisasikan data profil TikTok menggunakan pustaka **pandas**, **matplotlib**, dan **seaborn**.

#### 1\. Memahami dan Membersihkan Data (Bagian 1) 🧹

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the dataset
df = pd.read_csv('TikTok profiles dataset (Public web data).csv')

# Drop irrelevant columns
df = df.drop(columns=['timestamp', 'id', 'top_videos', 'url', 'profile_pic_url', 'create_time'])

# Convert 'is_verified' to a boolean type
df['is_verified'] = df['is_verified'].astype(bool)

# Display the cleaned DataFrame information
print("--- Data Information after Cleaning ---")
print(df.info())
```

  * **`import pandas as pd`, `import matplotlib.pyplot as plt`, `import seaborn as sns`**: Baris-baris ini mengimpor pustaka yang diperlukan untuk analisis data (pandas) dan visualisasi (matplotlib dan seaborn).
  * [cite\_start]**`df = pd.read_csv(...)`**: Kode ini membaca file `.csv` Anda dan menyimpannya ke dalam sebuah objek yang disebut **DataFrame** `df`[cite: 1]. DataFrame adalah tabel yang digunakan di Python untuk menyimpan data dengan struktur baris dan kolom.
  * [cite\_start]**`df.drop(columns=...)`**: Baris ini menghapus kolom-kolom yang tidak relevan dari dataset, seperti `timestamp`, `url`, dan `profile_pic_url`[cite: 1]. Ini dilakukan agar data lebih ringkas dan terfokus pada informasi yang penting untuk analisis.
  * **`df['is_verified'] = df['is_verified'].astype(bool)`**: Kolom `is_verified` aslinya mungkin dalam format teks (`'true'` atau `'false'`). [cite\_start]Baris ini mengubahnya menjadi tipe data `boolean` (True atau False), yang memudahkan proses analisis dan perbandingan[cite: 1].
  * [cite\_start]**`print(df.info())`**: Perintah ini menampilkan ringkasan informasi tentang DataFrame, seperti jumlah baris, kolom, dan tipe data dari setiap kolom[cite: 1]. Ini sangat berguna untuk memastikan bahwa proses pembersihan data berjalan dengan benar.

-----

### 🔍 Analisis Data Eksploratif (EDA) 📈

Bagian ini adalah inti dari riset data, di mana kita mulai menggali wawasan dari data yang telah dibersihkan.

#### 2\. Ringkasan Statistik 📝

```python
# Statistical summary of numerical columns
print("\n--- Statistical Summary ---")
print(df.describe())
```

  * [cite\_start]**`df.describe()`**: Kode ini menghasilkan ringkasan statistik untuk kolom-kolom numerik seperti `followers`, `likes`, dan `videos_count`[cite: 1]. Hasilnya mencakup statistik seperti rata-rata (mean), standar deviasi, nilai minimum dan maksimum, serta kuartil.

#### 3\. Tingkat Engagement Rata-Rata 🎯

```python
# Calculate the average engagement rate
avg_engagement_rate = df['awg_engagement_rate'].mean()
print(f"\nAverage Engagement Rate: {avg_engagement_rate:.4f}")
```

  * [cite\_start]**`df['awg_engagement_rate'].mean()`**: Baris ini menghitung nilai rata-rata dari kolom `awg_engagement_rate` (tingkat engagement rata-rata) di seluruh dataset[cite: 1].

-----

### 🎨 Visualisasi Data 🖼️

Visualisasi membantu kita memahami pola data yang sulit dilihat dalam bentuk tabel.

#### 4\. Distribusi Pengikut dan Jumlah Likes 📊

```python
# ... (kode untuk plotting)
```

  * [cite\_start]**`sns.histplot(...)`**: Kode ini membuat dua histogram[cite: 1]. Histogram pertama menunjukkan distribusi jumlah pengikut, sedangkan yang kedua menampilkan distribusi jumlah likes. Dengan melihat grafik ini, kita bisa mengetahui rentang jumlah pengikut dan likes yang paling umum di dataset.

#### 5\. Engagement Rate Berdasarkan Status Verifikasi ✅

```python
# ... (kode untuk boxplot)
```

  * [cite\_start]**`sns.boxplot(...)`**: Kode ini menghasilkan sebuah boxplot yang membandingkan tingkat engagement dari akun yang **sudah diverifikasi** (`True`) dan yang **belum diverifikasi** (`False`)[cite: 1]. Plot ini berguna untuk melihat apakah ada perbedaan signifikan dalam tingkat engagement antara kedua kelompok tersebut.

-----

### 🔬 Analisis Mendalam 🧐

Bagian terakhir ini berfokus pada hubungan antar variabel dan identifikasi profil-profil terpopuler.

#### 6\. Korelasi Antara Pengikut dan Tingkat Engagement 🤝

```python
# ... (kode untuk scatter plot)
correlation = df['followers'].corr(df['awg_engagement_rate'])
print(f"\nCorrelation between Followers and Engagement Rate: {correlation:.4f}")
```

  * [cite\_start]**`sns.scatterplot(...)`**: Kode ini membuat sebuah scatter plot[cite: 1]. Plot ini menampilkan hubungan antara jumlah pengikut dan tingkat engagement. Setiap titik mewakili satu profil, memungkinkan kita melihat tren, misalnya apakah akun dengan lebih banyak pengikut cenderung memiliki tingkat engagement yang lebih tinggi atau lebih rendah.
  * [cite\_start]**`df['followers'].corr(...)`**: Kode ini menghitung koefisien korelasi Pearson antara dua kolom[cite: 1]. Nilai korelasi ini, yang berkisar antara -1 hingga 1, mengukur seberapa kuat dan ke arah mana hubungan antara jumlah pengikut dan tingkat engagement. Nilai yang mendekati 1 menunjukkan hubungan positif yang kuat (lebih banyak pengikut, lebih tinggi engagement), sedangkan nilai yang mendekati -1 menunjukkan hubungan negatif.

#### 7\. 10 Profil Teratas Berdasarkan Pengikut 👑

```python
# Sort the DataFrame by followers in descending order and display the top 10
top_10_followers = df.sort_values(by='followers', ascending=False).head(10)
print("\n--- Top 10 Profiles by Followers ---")
print(top_10_followers[['nickname', 'followers', 'awg_engagement_rate']])
```

  * [cite\_start]**`df.sort_values(...)`**: Kode ini mengurutkan DataFrame berdasarkan jumlah pengikut (`followers`) dari yang terbesar ke yang terkecil[cite: 1].
  * [cite\_start]**`.head(10)`**: Setelah diurutkan, perintah ini hanya mengambil 10 baris pertama, yaitu 10 profil dengan jumlah pengikut terbanyak[cite: 1].

Semua langkah ini memberikan gambaran menyeluruh tentang data profil TikTok, dari statistik dasar hingga pola-pola yang tersembunyi. Anda bisa menjalankan seluruh kode ini di Jupyter Notebook untuk melihat hasil lengkapnya\! 🚀
