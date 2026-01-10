---

# Chapter 9: Unsupervised Learning Techniques

## 🎯 Gambaran Umum

**Unsupervised Learning** adalah pendekatan Machine Learning yang digunakan untuk **menemukan pola, struktur, atau hubungan tersembunyi dalam data tanpa label**.

Berbeda dari supervised learning, unsupervised learning **tidak memiliki target output**, dan cocok untuk:

* **Eksplorasi data**
* **Clustering**
* **Deteksi anomali**
* **Reduksi dimensi**
* **Asosiasi antar item**

---

## 🔍 Jenis-jenis Teknik Unsupervised Learning

### 📌 1. Clustering

Mengelompokkan data ke dalam grup berdasarkan **kemiripan fitur**.

#### 🔹 K-Means

* Membagi data ke dalam *k cluster* berdasarkan centroid.
* Berjalan iteratif dan efisien untuk data besar.
* Cocok untuk cluster **berbentuk bulat/simetris**.

#### 🔹 DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

* Berdasarkan **kepadatan** data.
* Dapat menangkap **bentuk cluster arbitrer** dan mendeteksi **outlier**.
* Tidak perlu menentukan jumlah cluster terlebih dahulu.

#### 🔹 Hierarchical Clustering (HCA)

* Membangun struktur **dendrogram** (hierarki).
* Dapat divisualisasikan sebagai diagram pohon dan **dipotong** untuk membentuk cluster.

---

### ⚠️ 2. Anomaly Detection & Novelty Detection

Menemukan data yang menyimpang jauh dari mayoritas — penting dalam:

* **Fraud detection**
* **Manufaktur & pemeliharaan sistem**
* **Sistem monitoring**

#### 🔹 One-Class SVM

* Belajar dari **data normal** untuk mendeteksi data outlier.

#### 🔹 Isolation Forest

* Mengisolasi data anomali dengan pohon acak.
* Efisien dan scalable untuk dataset besar.

---

### 📉 3. Dimensionality Reduction (Non-Supervised)

Metode seperti:

* **PCA**, **Kernel PCA**
* **Locally Linear Embedding (LLE)**
* **t-SNE**

Digunakan untuk:

* **Visualisasi data** berdimensi tinggi
* **Preprocessing** sebelum supervised learning
* **Mendeteksi struktur data yang tersembunyi**

---

### 🛒 4. Association Rule Learning

Mencari **hubungan menarik** antar item dalam dataset besar.

#### 🔹 Apriori & Eclat

* Digunakan dalam **market basket analysis**:

  * Contoh: “Orang yang membeli roti biasanya membeli susu juga.”
* Menghasilkan **aturan if-then** dari pola pembelian

---

## 🧪 Implementasi & Penggunaan Praktis

* **Segmentasi pelanggan** menggunakan clustering
* **Deteksi data anomali** sebelum training supervised model
* Digunakan dalam **data preprocessing pipeline**
* Implementasi mudah di Scikit-Learn melalui modul:

  * `sklearn.cluster`, `sklearn.manifold`, `sklearn.decomposition`
  * `sklearn.ensemble` untuk Isolation Forest

---

## ⚖️ Evaluasi & Tantangan

* **Tidak ada label ground truth** → sulit mengukur akurasi secara langsung
* Gunakan metrik seperti:

  * **Silhouette Score**
  * **Calinski-Harabasz Index**
  * **Davies-Bouldin Score**
* Validasi juga dibantu dengan **visualisasi** dan **pemahaman domain**

---

## 📌 Kesimpulan

Unsupervised Learning memungkinkan kita untuk menggali pola **tanpa supervisi** dan memiliki aplikasi luas — dari segmentasi pengguna hingga deteksi fraud dan visualisasi data.

Chapter ini memperkenalkan algoritma utama serta memberikan panduan praktis tentang kapan dan bagaimana teknik ini digunakan dalam pipeline data science modern.

---
