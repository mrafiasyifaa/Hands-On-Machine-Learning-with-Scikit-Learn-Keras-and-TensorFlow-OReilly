---

# Chapter 13: Loading and Preprocessing Data with TensorFlow

## 🎯 Gambaran Umum

Chapter ini membahas bagaimana **mengelola pipeline data secara efisien** untuk proyek Machine Learning berskala besar menggunakan **TensorFlow Data API** dan format file **TFRecord**. Fokus utamanya adalah efisiensi pemrosesan, fleksibilitas transformasi data, dan optimalisasi alur input ke model.

---

## 📦 Tantangan Data Skala Besar

* Dataset besar tidak bisa dimuat sekaligus ke dalam memori.
* Dibutuhkan pipeline data yang:

  * Efisien secara I/O
  * Dapat dibaca paralel dari banyak file
  * Mendukung transformasi dan pemrosesan real-time

---

## 🔧 Fitur Utama TensorFlow Data API

* Membaca data dari berbagai sumber:

  * File teks, CSV, gambar, TFRecord
* Mendukung transformasi data seperti:

  * `map()`, `filter()`, `shuffle()`, `batch()`, `repeat()`, `prefetch()`
* Eksekusi paralel untuk efisiensi tinggi:

  * Gunakan `num_parallel_calls=tf.data.AUTOTUNE` untuk tuning otomatis

---

## 🧩 Strategi Penyimpanan Dataset

* **Pecah dataset besar** menjadi banyak file kecil

  * Contoh: 100.000 data → 100 file x 1.000 record
* Tujuan:

  * Shuffle lebih efisien
  * Load paralel
  * Lebih ringan untuk debug dan distribusi

---

## 📁 Format TFRecord

* Format **binary** yang efisien dan mendukung struktur data kompleks
* Setiap record berisi serialized **protobuf `Example`**
* Parsing dengan:

  ```python
  parsed = tf.io.parse_single_example(serialized_example, feature_description)
  ```
* Untuk kebutuhan khusus, gunakan `tf.io.decode_proto()` (lebih rumit)

---

## 🛠️ Preprocessing Offline vs Online

| Offline Preprocessing       | Online Preprocessing               |
| --------------------------- | ---------------------------------- |
| Dilakukan sebelum training  | Dilakukan saat training berjalan   |
| Mengurangi waktu training   | Lebih fleksibel untuk data dinamis |
| Ukuran file bisa diperkecil | Berguna untuk augmentasi real-time |

Kombinasi kedua metode seringkali ideal.

---

## 🔐 Kompresi pada TFRecord

* Jika file diunduh dari jaringan: aktifkan kompresi (`GZIP`, `ZLIB`)
* Jika file lokal: **nonaktifkan kompresi** untuk menghindari beban CPU tambahan

---

## ⚙️ Rekomendasi Sistem dan Hardware

* CPU & RAM besar → untuk decoding dan preprocessing cepat
* Bandwidth I/O tinggi antara disk ↔ GPU → hindari bottleneck training
* Gunakan `prefetch()` di akhir pipeline untuk menyinkronkan data & eksekusi model

---

## ✅ Contoh Alur `tf.data` Pipeline

```python
files = tf.data.Dataset.list_files("data/*.tfrecord")
dataset = files.interleave(tf.data.TFRecordDataset,
                           cycle_length=4, num_parallel_calls=tf.data.AUTOTUNE)
dataset = dataset.map(parse_function, num_parallel_calls=tf.data.AUTOTUNE)
dataset = dataset.shuffle(10000).batch(32).prefetch(tf.data.AUTOTUNE)
```

---

## 🧠 Kesimpulan

Chapter ini menekankan pentingnya **desain pipeline data yang scalable dan efisien**, terutama untuk deep learning berskala besar. TensorFlow Data API dan TFRecord memberi alat fleksibel untuk **mengatur input data dari awal hingga akhir pelatihan model**, sekaligus menjaga efisiensi dan keterbacaan.

---
