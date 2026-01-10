
---

# Chapter 10: Introduction to Artificial Neural Networks with Keras

## 🧠 Pengantar Jaringan Saraf Tiruan (Artificial Neural Networks)

* **Artificial Neural Networks (ANN)** meniru cara kerja otak manusia dengan **neuron buatan** yang saling terhubung dalam lapisan.
* ANN mampu **memodelkan hubungan nonlinier kompleks** dalam data.
* Digunakan untuk **klasifikasi**, **regresi**, **deteksi pola**, dan **pengolahan data sekuensial**.

---

## 🧱 Komponen Dasar ANN

### 🔹 Neuron / Dense Layer

* Menghitung kombinasi linier dari input: `z = w·x + b`
* Output neuron diteruskan ke fungsi aktivasi

### 🔹 Fungsi Aktivasi

* Menambahkan **nonlinearitas** ke jaringan
* Fungsi umum:

  * **ReLU**: standar untuk hidden layer
  * **Sigmoid**: untuk klasifikasi biner
  * **Softmax**: untuk klasifikasi multikelas
  * **Linear**: untuk regresi

### 🔹 Arsitektur Jaringan

* **Input Layer** → satu atau lebih **Hidden Layer** → **Output Layer**
* Arsitektur (jumlah lapisan & neuron) mempengaruhi kapasitas model

---

## ➡️ Forward Propagation

* Proses data **mengalir maju** dari input ke output
* Setiap neuron mengeluarkan nilai berdasarkan input dari lapisan sebelumnya
* Output akhir digunakan sebagai **prediksi model**

---

## 📉 Fungsi Loss dan Optimizer

### 🔹 Fungsi Loss

* Mengukur selisih prediksi dan label sebenarnya:

  * **Mean Squared Error** (regresi)
  * **Binary Cross-Entropy** (klasifikasi biner)
  * **Categorical Cross-Entropy** (klasifikasi multikelas)

### 🔹 Optimizer

* Mengupdate bobot dengan **menurunkan loss**
* Contoh: **Stochastic Gradient Descent (SGD)**, **Adam**

---

## 🛠️ Implementasi dengan Keras

### 🔹 API `Sequential`

* Digunakan untuk membangun model lapis demi lapis

```python
from tensorflow import keras
from tensorflow.keras import layers

model = keras.models.Sequential([
    layers.Dense(10, activation="relu", input_shape=[X.shape[1]]),
    layers.Dense(1, activation="sigmoid")
])
```

### 🔹 Kompilasi & Pelatihan

```python
model.compile(loss="binary_crossentropy", optimizer="adam", metrics=["accuracy"])
model.fit(X_train, y_train, epochs=20, validation_data=(X_val, y_val))
```

---

## 📊 Evaluasi & Pengujian Model

* Model diuji pada data yang **tidak dilihat saat training**
* Metrik evaluasi bergantung pada konteks:

  * **Akurasi, Precision, Recall, F1-Score**
* Digunakan untuk mengukur **generalization performance**

---

## ✅ Praktik Baik & Tips

* Gunakan **Dropout** atau **Regularization** (L1/L2) untuk menghindari overfitting
* Lakukan **eksperimen arsitektur** untuk menyesuaikan model dengan data
* **Normalisasi data input** dapat meningkatkan stabilitas pelatihan
* Pertimbangkan **early stopping** agar pelatihan berhenti saat model tidak membaik lagi

---

## 📌 Kesimpulan

Chapter 10 memperkenalkan dasar teori dan praktik dari **jaringan saraf tiruan sederhana**, serta membimbing pembaca dalam **membangun, melatih, dan mengevaluasi ANN menggunakan Keras**. Ini menjadi fondasi penting sebelum melangkah ke model **Deep Learning** yang lebih kompleks seperti CNN dan RNN.

---
