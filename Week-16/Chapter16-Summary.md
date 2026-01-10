# 🧠 Chapter 16: Natural Language Processing with RNNs and Attention

_Buku: Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow — Aurélien Géron_

---

## 📌 Apa Itu NLP?

Natural Language Processing (NLP) adalah cabang AI yang berfokus pada:
- 📄 Pemrosesan teks
- 🎙️ Pemahaman ucapan
- 🧠 Interaksi bahasa alami antara manusia dan mesin

---

## 🔁 Mengapa RNN Cocok untuk NLP?

- RNN dirancang untuk memproses **urutan data** (seperti kalimat).
- Dapat menyimpan **konteks temporal** dan ketergantungan antar kata.
- Cocok untuk:
  - Penerjemahan otomatis
  - Analisis sentimen
  - Generasi teks

---

## 🧱 Representasi Teks

| Teknik                | Penjelasan                                                                 |
|----------------------|----------------------------------------------------------------------------|
| 🧩 **Tokenisasi**    | Memecah teks menjadi kata/sub-kata/karakter.                               |
| 🔤 **Embedding**     | Mengubah token menjadi vektor numerik berdimensi tetap.                     |
| 🚫 **OOV Handling**  | Sub-word tokenization mengurangi kasus _out-of-vocabulary_.                 |

---

## 🔁🧾 Sequence-to-Sequence (Seq2Seq)

Model encoder-decoder berbasis RNN:
- **Encoder**: Membaca seluruh input sequence → menghasilkan _context vector_.
- **Decoder**: Menghasilkan sequence output berdasarkan context tersebut.

✅ Cocok untuk:
- Penerjemahan otomatis
- Chatbot
- Ringkasan teks

---

## 🎯 Attention Mechanism

- **Masalah**: Context vector tunggal membatasi model pada sequence panjang.
- **Solusi**: Attention memberikan bobot pada tiap bagian input saat menghasilkan tiap token output.

### 📌 Manfaat Attention:
- Fokus dinamis pada bagian penting input
- Meningkatkan kualitas output
- Mempercepat konvergensi pelatihan

---

## 🧲 Transformer dan Self-Attention

Transformer = model berbasis **attention penuh**, tanpa RNN.

### 🔍 Self-Attention
- Setiap token memperhatikan **semua token lain**.
- Efektif untuk menangkap dependensi jangka panjang.

### 🚀 Dampak Transformer:
- Fondasi dari model seperti:
  - BERT
  - GPT
  - T5
- Mendominasi NLP modern

---

## 🔄 Transfer Learning & Pretrained Models

- Model besar dilatih pada data masif (pretraining).
- Dapat di-*fine-tune* untuk tugas spesifik (transfer learning).
- Efektif bahkan dengan data spesifik yang terbatas.

---

## ⚙️ Teknik Pelatihan

| Teknik               | Penjelasan                                                                    |
|----------------------|--------------------------------------------------------------------------------|
| 🔁 **BPTT**         | Backpropagation Through Time — digunakan untuk RNN.                            |
| 🎓 **Teacher Forcing** | Menggunakan target aktual sebagai input decoder saat pelatihan.               |

---

## 📚 Aplikasi NLP

- 🌐 Penerjemahan Mesin (Machine Translation)
- 🤖 Chatbots & Virtual Assistants
- 💬 Analisis Sentimen
- 🗣️ Speech Recognition
- 📑 Text Summarization

---

## ✅ Ringkasan

- RNN berguna untuk urutan, tapi **attention** melampaui batasannya.
- **Transformer** mempercepat dan menyederhanakan arsitektur NLP modern.
- Transfer learning dengan **pretrained language models** adalah kunci keberhasilan NLP saat ini.

---
