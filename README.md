## Analisis Sentimen Ulasan Mobile Legends: Bang Bang
### Ikhtisar
Proyek ini bertujuan untuk melakukan analisis sentimen pada ulasan pengguna dari game mobile populer Mobile Legends: Bang Bang. Analisis ini berfokus pada ulasan berbahasa Indonesia untuk mengidentifikasi sentimen positif dan negatif dari para pemain. Dengan menganalisis ulasan-ulasan tersebut, kita dapat memperoleh wawasan tentang pendapat pemain, mengidentifikasi masalah umum, dan memahami sentimen keseluruhan terhadap game ini.
### Struktur Proyek
```
├── data
│   ├── mlbb.csv
│   └── mlbb.xlsx
|── README.md
├── Notebook.ipynb
└── requirements.txt
```
### Penjelasan Tahapan
#### Pengumpulan data
Data yang digunakan dalam proyek ini adalah data ulasan dari game [Mobile Legends: Bang Bang](https://play.google.com/store/search?q=mobile+legend&c=apps). Data dikumpulkan melalui web scraping dengan fokus pada ulasan yang berlokasi di Indonesia, berbahasa Indonesia, paling relevan, dan representatif. Data ulasan ini disimpan dalam file CSV dan Excel.
#### Pra-pemrosesan Data
Data yang dikumpulkan perlu diproses sebelum digunakan dalam model. Tahapan ini meliputi:
*   **Filter Atribut Penting:** Memilih atribut yang relevan untuk analisis sentimen.
*   **Menghapus Missing Value:** Menghapus data yang tidak lengkap.
*   **Menghapus Duplikat:** Menghapus data yang duplikat.
*   **Pembersihan Teks (Cleaning Text):** Menghapus karakter khusus, tanda baca, dan angka yang tidak relevan.
*   **Case Folding:** Mengubah semua teks menjadi huruf kecil untuk konsistensi.
*   **Tokenisasi Teks (Tokenizing Text):** Membagi teks ulasan menjadi unit-unit yang lebih kecil seperti kata atau frasa.
*   **Filtering Teks:** Menghapus kata-kata umum (stop words) yang tidak membawa makna penting dalam analisis sentimen.
*   **Stemming Teks:** Mengubah kata-kata menjadi bentuk dasarnya.
*   **Membuat Slangword secara Manual:** Menyesuaikan kata-kata slang dalam ulasan agar sesuai dengan makna sebenarnya.
*   **Menggabungkan Teks:** Menggabungkan semua proses di atas ke dalam satu kolom baru.
#### Eksplorasi label
Tahapan ini melibatkan pemberian label [Positif](https://raw.githubusercontent.com/angelmetanosaa/dataset/main/lexicon_positive.csv) dan  [Negatif](https://raw.githubusercontent.com/angelmetanosaa/dataset/main/lexicon_negative.csv) pada data ulasan berdasarkan analisis dari proyek GitHub orang lain. Selanjutnya, dilakukan visualisasi data untuk memahami distribusi sentimen.

![alt text](/image/image.png)<br>
Dari ulasan aplikasi Mobile Legends, terlihat bahwa mayoritas ulasan bersifat negatif sebanyak 68.6%, sedangkan ulasan positif hanya 31.4%.

![alt text](/image/Positif.png)<br>
Visualisasi ini menunjukkan kata-kata yang paling sering digunakan dalam ulasan positif, memberikan gambaran tentang aspek-aspek yang dihargai oleh pengguna.

![alt text](/image/Negatif.png)<br>
Visualisasi ini menunjukkan kata-kata yang paling sering digunakan dalam ulasan negatif, memberikan gambaran tentang aspek-aspek yang dikeluhkan oleh pengguna.
#### Pembagian Data dan Ekstraksi Fitur
Pada tahap ini, data ulasan dibagi menjadi dua set: data pelatihan (80%) dan data pengujian (20%). Selanjutnya, fitur diekstraksi dari teks ulasan menggunakan teknik TF-IDF (Term Frequency-Inverse Document Frequency). Ekstraksi fitur ini bertujuan untuk mengubah teks ulasan menjadi representasi numerik yang dapat digunakan oleh model machine learning.
#### Pelatihan Model
Model Logistic Regression yang dilatih berhasil mencapai akurasi 86% pada data pelatihan dan 85% pada data pengujian. Hasil ini menunjukkan bahwa model mampu mengklasifikasikan sentimen ulasan dengan cukup baik.
### Kontribusi
Kami menyambut kontribusi dari siapa pun yang tertarik untuk memperbaiki proyek ini. Harap baca panduan kontribusi sebelum mengajukan pull request.
### Lisensi
Proyek ini dilisensikan di bawah [Lisensi MIT]().