# Laporan Preprocessing Data

## 1. Latar Belakang
Dataset yang digunakan berisi informasi mengenai kebiasaan membaca dan penggunaan internet berdasarkan provinsi dan tahun.  
Sebelum melakukan analisis lebih lanjut, diperlukan preprocessing data untuk:
- Menstandarkan format data,
- Menghapus data yang tidak valid,
- Membersihkan **outlier** agar analisis menjadi lebih akurat.

## 2. Metode Deteksi Outlier (IQR)
Outlier adalah nilai ekstrem yang berbeda jauh dari distribusi normal data.  
Salah satu cara paling umum untuk mendeteksi outlier adalah dengan **Interquartile Range (IQR)**:

- Hitung kuartil bawah (Q1) dan kuartil atas (Q3),
- IQR = Q3 - Q1,
- Data dianggap outlier jika:
  - Nilai < Q1 - 1.5 × IQR
  - Nilai > Q3 + 1.5 × IQR
![iqr] 

## 3. Implementasi
Langkah-langkah preprocessing:
1. Membaca file dataset (`dataset asli.csv`) dari repository.
2. Memilih kolom numerik:
   - Reading Frequency per week  
   - Number of Readings per Quarter  
   - Daily Reading Duration (in minutes)  
   - Internet Access Frequency per Week  
   - Daily Internet Duration (in minutes)  
3. Membuat histogram distribusi data sebelum pembersihan.
4. Menghapus outlier dengan metode IQR.
5. Membuat histogram distribusi data setelah pembersihan.

## 4. Hasil
- **Histogram sebelum pembersihan** menunjukkan adanya nilai ekstrem pada beberapa variabel.  
- Setelah diterapkan metode IQR, data menjadi lebih bersih dan distribusi lebih normal.  
- Jumlah baris data berkurang karena outlier dihapus.

## 5. Kesimpulan
- Penerapan **IQR** berhasil mengurangi outlier tanpa mengubah pola distribusi utama data.  
- Data yang sudah dibersihkan lebih representatif untuk analisis selanjutnya (misalnya perbandingan antar provinsi atau tren tahunan).  
- Langkah preprocessing ini penting agar hasil analisis tidak bias akibat data ekstrem.

---
📂 **File dalam Repository**:
- `dataset asli.csv` → data mentah.  
- `preprocessing.ipynb` → notebook Python untuk preprocessing.  
- `laporan_preprocessing.md` → laporan dokumentasi preprocessing ini.
