---

# Chapter 11: Training Deep Neural Networks

## 🎯 Gambaran Umum

**Deep Neural Networks (DNN)** sangat powerful, tetapi pelatihannya menghadapi berbagai tantangan seperti **vanishing gradients**, **exploding gradients**, dan **overfitting**. Chapter ini menyajikan strategi dan praktik terbaik untuk melatih DNN secara **stabil, cepat, dan efektif**.

---

## 🧱 Tantangan dalam Melatih Deep Networks

* **Vanishing gradients**: Gradien menjadi sangat kecil → pelatihan lambat atau terhenti
* **Exploding gradients**: Gradien terlalu besar → model menjadi tidak stabil
* **Overfitting**: Model belajar terlalu spesifik pada data pelatihan, gagal generalisasi

---

## ⚙️ Inisialisasi Bobot yang Efisien

* **He Initialization** → cocok untuk aktivasi ReLU
* **Xavier Initialization** → cocok untuk sigmoid/tanh
* Inisialisasi yang tepat membantu menghindari gradient problems dan mempercepat konvergensi

---

## 🧮 Fungsi Aktivasi Nonlinear

* **ReLU**: Fungsi default karena efisiensi dan kestabilan
* **Leaky ReLU / ELU**: Alternatif yang bisa mengatasi *dying neuron*
* Hindari **sigmoid** / **tanh** untuk lapisan tersembunyi dalam jaringan dalam

---

## 📏 Batch Normalization

* Menormalkan input ke setiap lapisan selama pelatihan
* Manfaat:

  * Mempercepat konvergensi
  * Mengurangi ketergantungan pada inisialisasi bobot
  * Memungkinkan learning rate yang lebih besar
* Implementasi mudah di Keras: `layers.BatchNormalization()`

---

## 🔒 Regularisasi untuk Mencegah Overfitting

* **Dropout**: Menonaktifkan neuron secara acak saat pelatihan
* **L1 / L2 regularization**: Penalti pada bobot besar
* **Early Stopping**: Menghentikan pelatihan saat validasi mulai memburuk

---

## 🚀 Strategi Optimasi Lanjutan

* Optimizer canggih:

  * **Adam**: Kombinasi momentum & adaptif learning rate
  * **RMSProp**, **Momentum**
* **Learning Rate Scheduling**:

  * Menurunkan learning rate secara bertahap → hasil lebih baik
  * Contoh: `ReduceLROnPlateau`, `ExponentialDecay`

---

## 🔧 Gradient Clipping

* Mencegah exploding gradients dengan **membatasi nilai maksimum gradien**
* Khusus penting untuk:

  * **Jaringan dalam**
  * **RNNs / LSTMs**

---

## 📚 Teknik Pelatihan Tambahan

* **Curriculum Learning**: Mulai dari data mudah → ke data sulit
* **Data Augmentation**: Tambahkan variasi data (khususnya citra)
* **Transfer Learning**: Gunakan model pretrained dan fine-tune untuk tugas baru

---

## 🧪 Monitoring dan Debugging

* Gunakan **callbacks** seperti:

  * `EarlyStopping`: menghentikan pelatihan saat overfitting
  * `ModelCheckpoint`: menyimpan model terbaik
* Visualisasi dengan **TensorBoard** atau grafik loss/accuracy
* Selalu siapkan **validation set** untuk evaluasi real-time

---

## ✅ Praktik Terbaik

* Mulai dari **model sederhana**, lalu tambah kompleksitas
* Gunakan kombinasi **Dropout + Batch Normalization**
* Pastikan input terstandarisasi
* Jangan lupakan eksplorasi **hyperparameter tuning**

---

## 📌 Kesimpulan

Chapter 11 membekali pembaca dengan **berbagai teknik krusial** agar dapat melatih deep neural network secara **efisien dan andal**. Dengan menerapkan inisialisasi yang tepat, strategi optimasi canggih, normalisasi batch, serta regularisasi, model DNN bisa **berkinerja optimal dan memiliki generalisasi kuat**.

---
