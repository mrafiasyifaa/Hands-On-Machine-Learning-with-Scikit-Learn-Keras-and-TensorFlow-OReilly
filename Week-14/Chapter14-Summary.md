---

# Chapter 14: Deep Computer Vision Using Convolutional Neural Networks (CNNs)

## 🎯 Gambaran Umum

Chapter ini membahas bagaimana **Convolutional Neural Networks (CNNs)** mampu merevolusi pemrosesan gambar dalam Deep Learning. CNN dirancang khusus untuk memanfaatkan **struktur spasial gambar**, menghasilkan model yang efisien, akurat, dan mampu mengenali fitur visual secara bertingkat.

---

## 🏆 Keunggulan CNN dibanding DNN Biasa

* **🔗 Parameter Lebih Sedikit:**
  CNN menggunakan koneksi lokal dan weight sharing, mengurangi jumlah parameter secara drastis dibanding DNN fully connected.

* **🌍 Invarian Lokasi Fitur:**
  Kernel CNN mendeteksi fitur visual (seperti tepi atau bentuk) di mana pun lokasinya dalam gambar.

* **🧠 Hirarki Fitur Otomatis:**
  CNN mengenali pola dari level rendah (tekstur) ke tinggi (objek) dengan struktur bertumpuk konvolusi dan pooling.

---

## 📐 Menghitung Jumlah Parameter CNN

* Misal: layer konvolusi pertama

  * Kernel: 3×3
  * Channel input: 3 (RGB)
  * Jumlah filter: 64

👉 Maka:
`3 × 3 × 3 × 64 + 64 (bias) = 1.792 parameter`

* Setiap filter belajar mendeteksi fitur spesifik dan menghasilkan 1 feature map.

---

## 🏗️ CNN Lebih Dalam dan Kompleks

* CNN modern terdiri dari:

  * Beberapa blok konvolusi → pooling
  * Diakhiri dense layer atau global pooling
* Setiap layer mengekstrak representasi visual yang lebih kompleks dari layer sebelumnya

---

## 🧱 Fully Convolutional Networks (FCN)

* FCN = semua layer adalah **konvolusi + pooling**, **tanpa dense**
* Keunggulan:

  * Bisa input gambar ukuran berapa pun
  * Efisien untuk **deteksi objek** dan **segmentasi semantik**
* Dense layer bisa diubah menjadi konvolusi dengan kernel yang ukurannya sama dengan input

---

## 🧪 Arsitektur CNN Terkenal

| Arsitektur    | Ciri Khas                                       |
| ------------- | ----------------------------------------------- |
| **LeNet-5**   | CNN awal untuk digit (MNIST)                    |
| **AlexNet**   | Lebih dalam dari LeNet, batch norm & ReLU       |
| **GoogLeNet** | Inception module → banyak jalur filter          |
| **ResNet**    | Skip connections → 100+ layers tanpa degradasi  |
| **SENet**     | SE blocks → skala pentingnya fitur tiap channel |
| **Xception**  | Depthwise separable convolutions                |

---

## 💡 Rangkuman Konsep CNN

| Komponen            | Fungsi                                 |
| ------------------- | -------------------------------------- |
| Convolution Layer   | Ekstrak fitur lokal                    |
| Pooling Layer       | Reduksi dimensi, ekstrak fitur penting |
| Activation Function | Non-linearitas (ReLU, LeakyReLU)       |
| Fully Connected     | Final klasifikasi atau regresi         |
| Dropout/BN          | Regularisasi dan stabilisasi           |

---

## 🧠 Kesimpulan

CNN adalah fondasi dari kemajuan **deep learning di bidang computer vision**. Dengan efisiensi parameter, struktur hierarki, dan kemampuan mendeteksi fitur visual kompleks, CNN menjadi pilihan utama untuk tugas seperti klasifikasi gambar, deteksi objek, dan segmentasi semantik.

---
