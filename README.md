*Objectives

- Mampu memperoleh data menggunakan BigQuery.

- Mampu memahami konsep Supervised Learning.

- Mampu mempersiapkan data untuk digunakan dalam model Supervised Learning.

- Mampu mengimplementasikan Supervised Learning dengan data yang diberikan.

- Mampu melakukan Hyperparameter Tuning dan Model Improvement.

---

## Dataset

1. dataset `ml_datasets` dari database bernama `credit_card_default`.

2. Query dengan kriteria sebagai berikut:
   - Pilih **HANYA** kolom `limit_balance, sex, education_level, marital_status, age, pay_0, pay_2, pay_3, pay_4, pay_5, pay_6, bill_amt_1, bill_amt_2, bill_amt_3, bill_amt_4, bill_amt_5, bill_amt_6, pay_amt_1, pay_amt_2, pay_amt_3, pay_amt_4, pay_amt_5, pay_amt_6, default_payment_next_month`.

## Problems

Membuat model Classification untuk memprediksi `default_payment_next_month` menggunakan dataset yang sudah kalian simpan.

---

## Conceptual Problems

_Jawab pertanyaan berikut:_

1. Apa yang dimaksud dengan `criterion` pada Decision Tree ? Jelaskan criterion yang kalian pakai dalam kasus ini !

2. Jelaskan apa yang dimaksud dengan `pruning` pada Tree-based model (alasan, definisi, jenis, dll) !

3. Bagaimana cara memilih `K` yang optimal pada KNN ?

4. Jelaskan apa yang dimaksud dengan `Cross Validation` !

5. Apa yang dimaksud dengan metrics-metrics berikut : `Accuracy`, `Precision`, `Recall`, `F1 Score`, dan kapan waktu yang tepat untuk menggunakannya ?

---

## Project Instruction

Isi _notebook_ harus mengikuti _outline_ di bawah ini:
   1. Perkenalan
      > Bab pengenalan harus diisi dengan identitas, **query yang telah kalian buat pada Google Cloud Platform!**, dan _objective_ yang ingin dicapai.

   2. Query SQL
      > Tulis query yang telah dibuat untuk mengambil data dari Google Cloud Platform di bagian ini.

   3. Import Libraries
      > _Cell_ pertama pada _notebook_ **harus berisi dan hanya berisi** semua _library_ yang digunakan dalam _project_.

   4. Data Loading
      > Bagian ini berisi proses penyiapan data sebelum dilakukan eksplorasi data lebih lanjut. Proses Data Loading dapat berupa memberi nama baru untuk setiap kolom, mengecek ukuran dataset, dll.

   5. Exploratory Data Analysis (EDA)
      > Bagian ini berisi eksplorasi data pada dataset diatas dengan menggunakan query, grouping, visualisasi sederhana, dan lain sebagainya.

   6. Feature Engineering
      > Bagian ini berisi proses penyiapan data untuk proses pelatihan model, seperti pembagian data menjadi train-test, transformasi data (normalisasi, encoding, dll.), dan proses-proses lain yang dibutuhkan.

   7. Model Definition
      > Bagian ini berisi cell untuk mendefinisikan model. Jelaskan alasan menggunakan suatu algoritma/model, hyperparameter yang dipakai, jenis penggunaan metrics yang dipakai, dan hal lain yang terkait dengan model.

   8. Model Training
      > Cell pada bagian ini hanya berisi code untuk melatih model dan output yang dihasilkan. Lakukan beberapa kali proses training dengan hyperparameter yang berbeda untuk melihat hasil yang didapatkan. Analisis dan narasikan hasil ini pada bagian Model Evaluation.

   9. Model Evaluation
      > Pada bagian ini, dilakukan evaluasi model yang harus menunjukkan bagaimana performa model berdasarkan metrics yang dipilih. Hal ini harus dibuktikan dengan visualisasi tren performa dan/atau tingkat kesalahan model. **Lakukan analisis terkait dengan hasil pada model dan tuliskan hasil analisisnya**.

   10. Model Saving
       > Pada bagian ini, dilakukan proses penyimpanan model dan file-file lain yang terkait dengan hasil proses pembuatan model. **Dengan melihat hasil Model Evaluation, pilihlah model terbaik untuk disimpan. Model terbaik ini akan digunakan kembali dalam melakukan Model Inference dan Model Deployment.**
   
   11. Model Inference
       > Model yang sudah dilatih akan dicoba pada data yang bukan termasuk ke dalam train-set ataupun test-set. Data ini harus dalam format yang asli, bukan data yang sudah di-scaled. Gunakan model terbaik berdasarkan hasil Model Evaluation.

   12. Pengambilan Kesimpulan
       > Pada bagian terakhir ini, **harus berisi** kesimpulan yang mencerminkan hasil yang didapat dengan _objective_ yang sudah ditulis di bagian pengenalan.

## Rubrics

### Code Review

| Criteria | Meet Expectations |
| --- | --- |
| SQL | Mampu melakukan query data dengan kriteria yang telah diberikan | 
| Feature Engineering | Mampu melakukan preprocessing dataset sebelum melakukan proses modeling (split data, normalisasi, encoding, dll) |
| Logistic Regression | Mengimplementasikan Logistic Regression dan menentukan hyperparameter yang tepat dengan Scikit-Learn |
| SVM | Mengimplementasikan SVM dan menentukan hyperparameter yang tepat dengan Scikit-Learn |
| Decision Tree | Mengimplementasikan Decision Tree dan menentukan hyperparameter yang tepat dengan Scikit-Learn |
| Random Forest | Mengimplementasikan Random Forest dan menentukan hyperparameter yang tepat dengan Scikit-Learn |
| KNN | Mengimplementasikan KNN dan menentukan hyperparameter yang tepat dengan Scikit-Learn |
| Naive Bayes | Mengimplementasikan Naive Bayes dan menentukan hyperparameter yang tepat dengan Scikit-Learn |
| Other Algorithm | Mengimplementasikan algoritma lain selain yang tersebut diatas dan menentukan hyperparameter yang tepat | 
| Cross Validation | Mengimplementasikan Cross Validation dengan Scikit-Learn |
| Hyperparameter Tuning | Mengimplementasikan Hyperparameter Tuning dengan Scikit-Learn |
| Model Inference | Mencoba model yang telah dibuat dengan data baru |
| Runs Perfectly | Kode berjalan tanpa ada error. Seluruh kode berfungsi dan dibuat dengan benar |

## Conclusion
1. EDA Analysis :
Credit default mostly happen in age 25 until 36
Default credit is more significantly happen in gender Female
Education level University mostly appear as credit_default user, 2nd is Graduated School
2. Feature Scaling :
Chi Square
3. Feature not included for modeling :
sex, education_level, marital_status, age, bill_amt_1, bill_amt_2, bill_amt_3, bill_amt_4, bill_amt_5, bill_amt_6, pay_amt_5 and pay_amt_6

4. Feature selected for modeling :
pay_0, pay_2, pay_3, pay_4, pay_05, pay_06, limit_balance, pay_amt_2, pay_amt_3, pay_amt_1 and pay_amt_4

5. Model Train :
LogisticRegression
SVC
DecisionTreeClassifier
RandomForestClassifier
KNeighborsClassifier
GaussianNB (Naive Bayes)
6. Model selected :
Random Forest Classification
Parameter :
{'model__n_estimators': 90, 'model__max_features': 3, 'model__max_depth': 3, 'model__criterion': 'entropy'}

Model Accuracy 83%
Model Precission 75%
Model F1 Score 45%
Model Recall Score 32%
Cross validation roc_auc mean (10 sample) 83%
7. Model Test New Dataset Result
score 90% from 9/10 new dataset
FINAL CONCLUSION
Random Forest Classification model showed promising results for credit default prediction. It demonstrated high accuracy and F1-scores on both the test dataset and new datasets. The selected features, after excluding certain variables, provided meaningful insights for modeling credit default risk.
