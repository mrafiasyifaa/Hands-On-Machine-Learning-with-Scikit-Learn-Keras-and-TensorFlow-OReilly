---

# Chapter 7: Ensemble Learning and Random Forests

## 🧠 Konsep Dasar Ensemble Learning

### • **Apa itu Ensemble Learning?**

Ensemble Learning adalah pendekatan yang menggabungkan **beberapa model prediktif** untuk menghasilkan **prediksi yang lebih akurat dan stabil** dibandingkan model tunggal.

### • **Tujuan**

* Mengurangi **bias** (kesalahan sistematis)
* Mengurangi **varian** (sensitivitas terhadap data)
* Meningkatkan **generalisasi**

### • **Dua Teknik Utama**

* **Bagging (Bootstrap Aggregating)**: model-model dilatih secara independen pada data berbeda.
* **Boosting**: model dilatih secara bertahap, di mana setiap model mencoba memperbaiki kesalahan dari model sebelumnya.

---

## 🌲 Random Forest: Penerapan Bagging pada Decision Trees

### • **Apa itu Random Forest?**

Random Forest adalah algoritma ensemble berbasis **bagging** yang terdiri dari banyak **Decision Tree**. Setiap pohon dilatih pada subset acak data dan subset acak fitur.

### • **Bagaimana Cara Kerjanya?**

1. Setiap pohon dilatih pada data **bootstrap** (random sampling with replacement).
2. Saat memilih split terbaik di tiap node, hanya subset fitur acak yang dipertimbangkan (bukan semua fitur).
3. Prediksi akhir:

   * **Klasifikasi** → voting mayoritas
   * **Regresi** → rata-rata prediksi

---

## ✅ Keunggulan Random Forest

* **Mengurangi overfitting** yang umum terjadi pada Decision Trees tunggal.
* **Handal** di berbagai jenis data, termasuk data numerik, kategorik, dan campuran.
* **Tidak memerlukan scaling fitur**.
* **Dapat mengukur feature importance** secara internal.

---

## ⚙️ Hyperparameter Penting

* `n_estimators`: jumlah pohon (semakin banyak, semakin stabil — sampai titik tertentu).
* `max_depth`: batas kedalaman pohon.
* `max_features`: jumlah fitur acak yang dipertimbangkan di setiap split.
* `min_samples_split`, `min_samples_leaf`: untuk mengontrol pembelahan node dan mencegah overfitting.

---

## 📊 Interpretasi Model

### • **Feature Importance**

Random Forest dapat menunjukkan fitur mana yang paling berkontribusi dalam prediksi dengan menghitung:

* Frekuensi fitur digunakan dalam split
* Rata-rata pengurangan impuritas (mis. Gini atau MSE)

### • **Interpretabilitas**

Meskipun lebih kompleks daripada pohon tunggal, model ini tetap lebih transparan dibanding model black-box seperti deep neural networks.

---

## ⚠️ Keterbatasan Random Forest

* **Ukuran model besar** dan **memakan memori** saat jumlah pohon banyak.
* **Waktu prediksi lambat** jika jumlah pohon sangat banyak.
* **Kurang efektif** untuk data sangat kecil atau dengan sangat sedikit fitur.
* Sulit untuk **diinterpretasi secara keseluruhan** (berbeda dengan Decision Tree tunggal).

---

## 🧪 Praktik dan Implementasi

* Scikit-Learn menyediakan `RandomForestClassifier` dan `RandomForestRegressor`.
* Dapat diterapkan pada banyak dataset seperti **MNIST**, **California Housing**, atau data klasifikasi umum lainnya.
* Parameter dapat di-*tune* menggunakan **Grid Search** atau **Randomized Search**.

---

Chapter 7 memperkenalkan prinsip penting Ensemble Learning dan menjelaskan bagaimana **Random Forest** memanfaatkan kekuatan banyak pohon untuk membentuk prediksi yang lebih baik, stabil, dan andal, dengan tetap mempertahankan fleksibilitas dan interpretabilitas sebagian besar.

---
