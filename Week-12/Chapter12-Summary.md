---

# Chapter 12: Custom Models and Training with TensorFlow

## 🎯 Gambaran Umum

API tinggi seperti Keras cocok untuk sebagian besar kasus, namun kadang dibutuhkan **fleksibilitas penuh** dalam membangun **arsitektur unik**, **loss function kustom**, atau **training loop khusus**. Chapter ini membahas cara membangun dan melatih model secara manual menggunakan **TensorFlow Core API**.

---

## 🧩 Mengapa Perlu Model dan Training Kustom?

* Membuka fleksibilitas penuh untuk:

  * Arsitektur eksperimental
  * Pelatihan multi-output atau multi-task
  * Algoritma optimisasi kompleks
* Cocok untuk riset dan eksperimen lanjutan

---

## 🧱 Membuat Model Kustom dengan `tf.keras.Model`

* Gunakan **subclassing**:

  ```python
  class MyModel(tf.keras.Model):
      def __init__(self):
          super().__init__()
          self.dense1 = tf.keras.layers.Dense(64, activation='relu')
          self.out = tf.keras.layers.Dense(10)

      def call(self, inputs):
          x = self.dense1(inputs)
          return self.out(x)
  ```
* `__init__()` untuk definisi layer, `call()` untuk forward pass
* Cocok untuk model **non-sekuensial atau cabang kompleks**

---

## 🔄 Custom Training Loop dengan `tf.GradientTape`

* Kendali penuh atas proses pelatihan:

  ```python
  with tf.GradientTape() as tape:
      predictions = model(x_batch)
      loss = loss_fn(y_batch, predictions)
  gradients = tape.gradient(loss, model.trainable_variables)
  optimizer.apply_gradients(zip(gradients, model.trainable_variables))
  ```
* Dapat digunakan untuk:

  * Pelatihan dengan banyak loss
  * Pelatihan dengan banyak optimizer
  * Pelatihan bertahap atau dengan constraint khusus

---

## 🧠 Automatic Differentiation: `tf.GradientTape`

* Merekam operasi tensor saat forward pass
* Hitung turunan secara otomatis saat backward pass
* Inti dari fleksibilitas TensorFlow

---

## 🧱 Membuat Layer Kustom dengan `tf.keras.layers.Layer`

* Digunakan jika ingin membuat **blok reusable**
* Contoh:

  ```python
  class MyLayer(tf.keras.layers.Layer):
      def __init__(self, units):
          super().__init__()
          self.units = units

      def build(self, input_shape):
          self.w = self.add_weight(...)

      def call(self, inputs):
          return tf.matmul(inputs, self.w)
  ```

---

## 📏 Loss dan Metric Kustom

* Cukup buat fungsi:

  ```python
  def custom_loss(y_true, y_pred):
      return tf.reduce_mean(tf.square(y_true - y_pred))
  ```
* Bisa digunakan di `.compile()` atau training loop manual

---

## ⚙️ Komponen dalam `train_step`

* Isi umum:

  1. Forward pass
  2. Hitung loss
  3. Hitung gradien
  4. Update bobot
* Bisa disisipkan logging, regularisasi, update manual, dll

---

## 🐛 Debugging dan Model Dinamis

* Gunakan **eager execution** (default) untuk debugging mudah
* Model dinamis = eksekusi Python langsung (tidak seperti graph mode)
* Debugging jadi intuitif, meskipun **sedikit lebih lambat**

---

## ⚖️ Kelebihan dan Kekurangan Model Kustom

| Kelebihan                       | Kekurangan                           |
| ------------------------------- | ------------------------------------ |
| Fleksibilitas penuh             | Butuh lebih banyak kode              |
| Cocok untuk arsitektur kompleks | Potensi kesalahan manual lebih besar |
| Mudah debugging via Python      | Tidak seefisien mode graph           |

---

## 📘 Latihan dan Contoh Praktik

* Buku menyediakan notebook khusus untuk:

  * Membuat model subclassed
  * Pelatihan manual dengan `GradientTape`
  * Penggunaan layer dan loss custom
* Sangat direkomendasikan untuk eksperimen langsung

---

## 📌 Kesimpulan

Chapter 12 membekali pembaca dengan **kemampuan lanjutan TensorFlow**: membangun **arsitektur neural network yang unik** dan **mengontrol proses pelatihan sepenuhnya**. Ini merupakan **jembatan penting menuju eksperimen riset dan custom deep learning pipelines**.

---
