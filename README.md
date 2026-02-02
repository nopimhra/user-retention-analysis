# user-retention-analysis

# User Retention Analysis

Proyek ini bertujuan untuk menganalisis **retensi pengguna (user retention)** berdasarkan data transaksi menggunakan pendekatan **cohort analysis**.  
Analisis ini membantu memahami bagaimana perilaku pengguna setelah transaksi pertama, serta mengidentifikasi periode dengan tingkat churn tertinggi dan pola loyalitas pengguna dari waktu ke waktu.

---

## 🎯 Tujuan Proyek

Tujuan utama dari proyek ini adalah:
- Menganalisis tingkat retensi pengguna berdasarkan bulan transaksi pertama (*first order month*)
- Mengidentifikasi kapan penurunan pengguna paling signifikan terjadi
- Menemukan pola loyalitas pengguna berdasarkan cohort waktu
- Memberikan insight berbasis data yang dapat digunakan untuk strategi retensi pengguna

---

## 📊 Dataset

Dataset yang digunakan merupakan **data transaksi pengguna** yang berisi detail pesanan, produk, waktu transaksi, serta status pesanan.

### Struktur Data

Berikut adalah kolom utama yang digunakan dalam analisis:

| Kolom | Deskripsi |
|------|----------|
| order_id | ID unik untuk setiap pesanan |
| product_code | Kode produk |
| product_name | Nama produk |
| quantity | Jumlah produk yang dipesan |
| order_date | Waktu transaksi |
| price | Harga satuan produk |
| customer_id | ID unik pelanggan |
| year_month | Bulan transaksi (YYYY-MM) |
| order_status | Status pesanan (delivered / cancelled) |
| amount | Total nilai transaksi (quantity × price) |

Dataset diolah pada level **customer** dan **waktu** untuk membentuk cohort berdasarkan bulan transaksi pertama.

---

## 🧠 Metodologi Analisis

Tahapan analisis yang dilakukan dalam proyek ini meliputi:

1. **Data Cleaning**
   - Konversi kolom waktu ke format datetime
   - Filtering transaksi dengan status pesanan valid
   - Penyesuaian format bulan (`year_month`)

2. **Cohort Definition**
   - Menentukan bulan transaksi pertama setiap pengguna (*first order month*)
   - Mengelompokkan pengguna ke dalam cohort berdasarkan bulan tersebut

3. **Cohort Retention Calculation**
   - Menghitung jumlah pengguna aktif di setiap bulan setelah transaksi pertama
   - Mengonversi jumlah tersebut ke bentuk persentase retensi

4. **Visualisasi**
   - Menampilkan hasil analisis dalam bentuk **cohort retention heatmap**
   - Mempermudah identifikasi pola retensi dan churn pengguna

---

## 📈 Insight Utama

Berdasarkan hasil **cohort retention analysis**, diperoleh beberapa insight penting:

- **Penurunan retensi terbesar terjadi pada bulan ke-2**, di mana sebagian besar cohort mengalami penurunan signifikan dari 100% ke kisaran 20–40%.  
  Hal ini menunjukkan bahwa churn paling tinggi terjadi setelah transaksi pertama.

- **Retensi cenderung lebih stabil setelah bulan ke-4**, yang mengindikasikan bahwa pengguna yang bertahan hingga fase ini memiliki kecenderungan menjadi pengguna loyal.

- **Cohort awal (misalnya 2010-01)** menunjukkan tingkat retensi yang relatif lebih tinggi hingga bulan-bulan selanjutnya, yang dapat mengindikasikan perbedaan karakteristik pengguna atau kondisi bisnis pada periode tersebut.

---

## 💡 Business Implication

Beberapa implikasi bisnis yang dapat ditarik dari hasil analisis:
- Perlu adanya strategi onboarding dan engagement yang lebih kuat pada bulan pertama setelah transaksi
- Program loyalitas sebaiknya difokuskan pada pengguna yang berhasil bertahan hingga bulan ke-3 atau ke-4
- Analisis lebih lanjut dapat dilakukan untuk membandingkan cohort berdasarkan produk atau nilai transaksi

---

## 🛠️ Tools & Library

- Python
- Pandas
- NumPy
- Matplotlib / Seaborn
- Jupyter Notebook

---

## 📌 Catatan

Proyek ini bersifat **analisis eksploratif** dan bertujuan untuk memahami pola perilaku pengguna berdasarkan data historis transaksi.  
Hasil analisis dapat dikembangkan lebih lanjut dengan menambahkan segmentasi pengguna atau model prediksi churn.
