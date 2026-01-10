---

# Chapter 8: Dimensionality Reduction

## 🎯 Gambaran Umum

**Dimensionality Reduction** adalah proses mengurangi jumlah fitur dalam dataset sambil mempertahankan **informasi penting** sebanyak mungkin. Teknik ini penting untuk:

* Mengatasi *curse of dimensionality*
* Mengurangi noise
* Mempercepat komputasi
* Membantu visualisasi data berdimensi tinggi

### • Dua Pendekatan Umum:

* **Feature Selection**: Memilih subset dari fitur asli
* **Feature Extraction**: Membuat fitur baru dari kombinasi fitur lama

---

## ❓ Mengapa Perlu Dimensionality Reduction?

* Data berdimensi tinggi sering memiliki fitur yang **redundan atau tidak relevan**
* Model Machine Learning bisa menjadi **kompleks dan rawan overfitting**
* Reduksi dimensi dapat membantu **menemukan struktur tersembunyi** dalam data

---

## 🛠️ Metode Utama Dimensionality Reduction

### 🔹 1. Principal Component Analysis (PCA)

* Metode linier yang **menemukan kombinasi fitur** untuk menangkap **varians terbesar**
* **Langkah utama**:

  1. Hitung **covariance matrix**
  2. Temukan **eigenvector dan eigenvalue**
  3. Pilih komponen utama (principal components) berdasarkan eigenvalue terbesar
* Hasilnya adalah fitur baru yang **saling ortogonal**
* **Cocok untuk data linier**

### 🔹 2. Kernel PCA

* Perluasan PCA dengan **kernel trick** untuk menangani **hubungan non-linear**
* Memetakan data ke ruang berdimensi tinggi sebelum menerapkan PCA

### 🔹 3. Locally Linear Embedding (LLE)

* Teknik **manifold learning** untuk data non-linier
* Menjaga **hubungan lokal antar titik** saat memproyeksikan ke ruang berdimensi rendah

### 🔹 4. t-Distributed Stochastic Neighbor Embedding (t-SNE)

* Khusus untuk **visualisasi** data berdimensi tinggi
* Mengkonversi jarak antar titik ke **probabilitas**, dan menjaga struktur lokal dalam 2D/3D
* Sangat efektif untuk **eksplorasi dan analisis clustering**

---

## 🧪 Implementasi di Scikit-Learn

* PCA dan KernelPCA tersedia di: `sklearn.decomposition`
* LLE dan t-SNE tersedia di: `sklearn.manifold`
* Biasanya digunakan dalam **pipeline preprocessing** sebelum training model

---

## 📝 Tips & Pertimbangan

* **Standardisasi fitur** sangat penting sebelum PCA (karena PCA sensitif terhadap skala)
* Pilih jumlah komponen yang **mempertahankan ≥95% varians**
* Cocok untuk data dengan **jumlah fitur besar dan noisy**
* Gunakan hasil reduksi dimensi untuk:

  * **Mempercepat pelatihan**
  * **Mengurangi penggunaan memori**
  * **Visualisasi** dan **pemahaman struktur data**

---

## 🧠 Kesimpulan

Dimensionality Reduction adalah **alat penting dalam data science** untuk menyederhanakan data kompleks tanpa kehilangan informasi utama. Chapter ini membekali pembaca dengan teori dan praktik dari berbagai teknik populer seperti **PCA, Kernel PCA, LLE, dan t-SNE** — baik untuk tujuan optimisasi model maupun eksplorasi visual.

---
