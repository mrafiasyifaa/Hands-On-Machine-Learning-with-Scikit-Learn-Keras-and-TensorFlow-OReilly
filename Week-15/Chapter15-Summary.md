# 📘 Chapter 15: Processing Sequences Using RNNs and CNNs

_Buku: Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow — Aurélien Géron_

---

## 🎯 Ringkasan Bab

Chapter ini menjelaskan cara memproses data **berbentuk urutan/sekuens** (seperti teks, audio, video, dan sinyal waktu) menggunakan dua pendekatan utama: **Recurrent Neural Networks (RNN)** dan **Convolutional Neural Networks (CNN) khusus untuk sequences**.

---

## 🔄 Recurrent Neural Networks (RNNs)

### 🧠 Mengapa RNN?
- Dirancang untuk data urutan/time-series.
- Memiliki **memori internal** yang mempertahankan konteks input sebelumnya.
- Ideal untuk data dengan **ketergantungan jangka pendek** hingga menengah.

### ⚠️ Masalah Umum:
- **Vanishing Gradients**: model gagal belajar hubungan jangka panjang.
- **Exploding Gradients**: pembelajaran menjadi tidak stabil.

---

## 🧬 LSTM dan GRU

| Arsitektur | Ciri Khas |
|------------|-----------|
| **LSTM (Long Short-Term Memory)** | Menggunakan cell state dan tiga gates (input, forget, output) untuk mempertahankan informasi penting. |
| **GRU (Gated Recurrent Unit)** | Versi lebih ringan dari LSTM, dua gates (update dan reset), sering memberikan hasil sebanding. |

✅ Keduanya membantu model mengingat **informasi penting dalam jangka panjang**.

---

## 🔁 Bidirectional RNN

- Memproses urutan dalam **dua arah**: maju dan mundur.
- Cocok untuk NLP, di mana **kata saat ini** dipengaruhi oleh konteks sebelum dan sesudahnya.

---

## 📈 CNN untuk Sequences

- **1D Convolution** dapat digunakan untuk mengenali pola lokal seperti **n-gram** dalam teks.
- Lebih cepat daripada RNN karena:
  - Paralelisasi
  - Struktur tetap (tidak bergantung waktu)
- Baik untuk fitur spasial/statistik lokal, namun kurang dalam modeling dependensi sekuensial jangka panjang.

---

## 🛠️ Training dan Optimasi

| Teknik | Fungsi |
|--------|--------|
| **BPTT (Backpropagation Through Time)** | Metode training RNN dengan menghitung gradien sepanjang waktu. |
| **Regularisasi** | Dropout, recurrent dropout, L2 → mencegah overfitting. |
| **Gradient Clipping** | Mencegah exploding gradient pada RNN. |

---

## 📦 Aplikasi Dunia Nyata

- 🗣️ **Speech Recognition**
- 🌐 **Machine Translation**
- 😊 **Sentiment Analysis**
- 📹 **Video Frame Prediction**
- 🧬 **Bioinformatics (DNA/RNA sequence)**

---

## 📚 Kesimpulan

RNN dan CNN khusus untuk sequences adalah dua pilar penting dalam pemrosesan data berurutan.  
- Gunakan **RNN (LSTM/GRU)** untuk memahami konteks waktu yang panjang.
- Gunakan **1D CNN** untuk menangkap pola lokal secara efisien.
- Gabungan keduanya dapat menghasilkan model yang powerful dan scalable untuk berbagai jenis data sekuensial.

---
