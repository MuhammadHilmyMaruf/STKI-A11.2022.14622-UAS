

# 1. Judul / Topik Project dan Identitas Lengkap

### Judul:
**Prediksi Penyakit Diabetes Menggunakan Decision Tree**

### Identitas:
- **Nama**: Muhammad Hilmy Maruf  
- **NIM**: 14622  
- **Mata Kuliah**: Sistem Teknologi Informasi dan Komunikasi (STKI)

---

# 2. Ringkasan dan Permasalahan Project + Tujuan yang Akan Dicapai + Model / Alur Penyelesaian

### Ringkasan:
Proyek ini bertujuan untuk membangun model prediksi penyakit diabetes menggunakan algoritma **Decision Tree**. Data yang digunakan adalah dataset *Pima Indians Diabetes*, yang berisi data faktor risiko diabetes dan target apakah seseorang menderita diabetes atau tidak. Model ini akan digunakan untuk memprediksi kemungkinan seseorang menderita diabetes berdasarkan faktor risiko yang ada.

### Permasalahan:
Diabetes adalah penyakit yang dapat dicegah dengan deteksi dini. Oleh karena itu, menggunakan data faktor risiko, kita bisa membuat model untuk mendeteksi diabetes lebih awal, sehingga memungkinkan langkah pencegahan yang lebih baik.

### Tujuan:
- Mengembangkan model prediksi penyakit diabetes menggunakan algoritma **Decision Tree**.
- Menggunakan dataset *Pima Indians Diabetes* untuk memprediksi kemungkinan seseorang menderita diabetes.
- Mengevaluasi model menggunakan berbagai metrik seperti akurasi, classification report, dan confusion matrix.

### Model / Alur Penyelesaian:
Berikut adalah alur penyelesaian dalam proyek ini:
1. **Membaca dan Preprocessing Data**: Mengimpor dataset, mengecek nilai kosong, dan menyiapkan data untuk model.
2. **Pembuatan Model Decision Tree**: Membangun model dengan kriteria *Gini Impurity* dan kedalaman maksimal 5.
3. **Evaluasi Model**: Menggunakan akurasi, classification report, dan confusion matrix untuk mengevaluasi performa model.
4. **Visualisasi Model**: Menampilkan pohon keputusan yang dihasilkan oleh model.

**Bagan Alur Penyelesaian**:

```plaintext
+-----------------+     +------------------+     +------------------+
| Membaca Data   | --> | Preprocessing     | --> | Membuat Model    |
| dan Statistik  |     | Data dan Split    |     | Decision Tree    |
+-----------------+     +------------------+     +------------------+
          |                       |                      |
          v                       v                      v
+-----------------+     +------------------+     +------------------+
| Evaluasi Model  | --> | Visualisasi Model| --> | Kesimpulan dan   |
| (Akurasi, CM,   |     | Pohon Keputusan  |     | Diskusi          |
| Classification  |     +------------------+     +------------------+
| Report)         |
+-----------------+
```

---

# 3. Penjelasan Dataset, EDA dan Proses Features Dataset

### Dataset:
Dataset yang digunakan dalam proyek ini adalah *Pima Indians Diabetes Dataset*. Dataset ini memiliki 8 fitur yang berhubungan dengan kesehatan dan 1 kolom target yang menunjukkan apakah seseorang menderita diabetes (1) atau tidak (0). Berikut adalah deskripsi kolom-kolom dalam dataset:

- **Pregnancies**: Jumlah kehamilan
- **Glucose**: Kadar glukosa dalam darah
- **BloodPressure**: Tekanan darah
- **SkinThickness**: Ketebalan kulit
- **Insulin**: Kadar insulin
- **BMI**: Indeks Massa Tubuh
- **DiabetesPedigreeFunction**: Sejarah keluarga diabetes
- **Age**: Umur
- **Outcome**: Target variabel (0 = Tidak Diabetes, 1 = Diabetes)

### Eksplorasi Data (EDA):
- **Info dataset** menunjukkan struktur data dan apakah ada nilai yang hilang.
- **Statistik Deskriptif** memberikan gambaran tentang distribusi data seperti nilai rata-rata, deviasi standar, dan nilai minimum/maximum.
- **Preprocessing** dilakukan dengan mengecek apakah terdapat nilai kosong pada dataset menggunakan `isnull().sum()`, yang menghasilkan 0 untuk setiap kolom, artinya tidak ada nilai kosong.

### Proses Feature Selection:
- Kolom `Outcome` digunakan sebagai target variabel.
- Kolom lainnya (seperti `Pregnancies`, `Glucose`, dll) digunakan sebagai fitur untuk model.

---

# 4. Proses Learning / Modeling

### Model yang Digunakan:
Pada proyek ini, **Decision Tree** digunakan untuk membangun model prediksi. Model ini menggunakan kriteria *Gini Impurity* dan memiliki kedalaman maksimal 5 untuk menghindari overfitting.

### Langkah-langkah:
1. **Pembagian Data**: Dataset dibagi menjadi 80% data latih dan 20% data uji menggunakan `train_test_split`.
2. **Pelatihan Model**: Model Decision Tree dilatih menggunakan data latih.
3. **Prediksi**: Setelah model dilatih, data uji digunakan untuk memprediksi hasil dan mengevaluasi model.

---

# 5. Performa Model

### Hasil Evaluasi:
- **Akurasi Model**: 78.13%
- **Classification Report**:
    ```plaintext
              precision    recall  f1-score   support

           0       0.78      0.86      0.82       139
           1       0.78      0.66      0.72       122

    accuracy                           0.78       261
   macro avg       0.78      0.76      0.77       261
weighted avg       0.78      0.78      0.78       261
    ```

- **Confusion Matrix**:
    ```plaintext
              Prediksi
              No Diabetes  Diabetes
    Aktual
    No Diabetes    119       20
    Diabetes       41        81
    ```

Confusion matrix menunjukkan bahwa model berhasil mengklasifikasikan dengan baik kasus *No Diabetes* (119 benar) dan *Diabetes* (81 benar), meskipun ada beberapa kesalahan pada klasifikasi *Diabetes*.

---

# 6. Diskusi Hasil dan Kesimpulan

### Diskusi:
- **Akurasi** model mencapai sekitar 78%, yang menunjukkan bahwa model cukup baik dalam memprediksi apakah seseorang menderita diabetes atau tidak.
- Meskipun model berhasil mengklasifikasikan *No Diabetes* dengan baik, ada kesalahan dalam klasifikasi *Diabetes*, dengan 41 kasus yang terdeteksi sebagai *No Diabetes* (false negatives).
- Evaluasi menggunakan **classification report** dan **confusion matrix** memberikan gambaran yang lebih mendalam mengenai kinerja model, dan dapat digunakan untuk memperbaiki model lebih lanjut.

### Kesimpulan:
- **Decision Tree** memberikan hasil yang cukup baik untuk prediksi diabetes, namun masih dapat diperbaiki lebih lanjut dengan teknik seperti pruning atau hyperparameter tuning.
- Diperlukan lebih banyak eksperimen untuk mengurangi kesalahan klasifikasi, terutama pada *Diabetes*.

---

