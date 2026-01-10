
# 🎨 Chapter 17: Representation Learning & Generative Learning (Autoencoders & GANs)

_Buku: Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow — Aurélien Géron_

---

## 📌 Apa Itu Representation Learning?

- Tujuan: Menemukan representasi (fitur laten) yang membantu model belajar dan generalisasi lebih baik.
- Biasanya melibatkan **kompresi** informasi penting dalam bentuk **dimensi lebih rendah (latent space)**.
- Sering digunakan dalam _unsupervised learning_, kompresi, dan _generative modeling_.

---

## 🧠 Autoencoders

Autoencoder adalah jaringan saraf untuk belajar representasi kompresi dari data.

### Arsitektur:
- **Encoder**: 📥 Input → 🔒 Latent vector (z)
- **Decoder**: 🔓 Latent vector → 📤 Rekonstruksi output

### Varian:
| Tipe                  | Kegunaan/Keunggulan                                       |
|-----------------------|-----------------------------------------------------------|
| 🔧 Basic Autoencoder  | Kompresi dan rekonstruksi data                            |
| 🎨 Denoising AE       | Menghapus noise dari input                                |
| 📊 Variational AE     | Menghasilkan data baru, berbasis distribusi probabilistik |

---

## 🎲 Variational Autoencoders (VAE)

- Menambahkan **probabilistic modeling** ke latent space.
- Output latent vector berasal dari distribusi (biasanya Gaussian).
- Memungkinkan **sampling** dan **generasi data** yang realistis.
- Latent space menjadi terstruktur → dapat di-*interpolate* dan dimanipulasi secara bermakna.

---

## 🤖 Generative Adversarial Networks (GANs)

Dua jaringan saraf yang saling "berlomba":
- **Generator (G)**: Menghasilkan data palsu dari _random noise_.
- **Discriminator (D)**: Membedakan antara data asli dan buatan.

### Tujuan:
> Generator mengecoh Discriminator, Discriminator berusaha tidak tertipu.

---

## ⚠️ Tantangan dalam Training GAN

| Masalah               | Penjelasan                                                  |
|------------------------|-------------------------------------------------------------|
| 🎭 Mode Collapse       | Generator menghasilkan output terbatas dari semua noise.    |
| 🥊 Unbalanced Training | Salah satu model (G/D) lebih kuat → gagal belajar efektif.  |
| ⚖️ Nash Equilibrium   | Kondisi ideal di mana G dan D seimbang → tidak bisa saling mengalahkan. |

---

## 🧱 DCGAN: Deep Convolutional GAN

- Menggunakan **convolutional layers** di G & D.
- Menghasilkan gambar yang lebih besar dan **lebih realistis**.

### Praktik Terbaik DCGAN:
- Gunakan **strided convolution** (bukan pooling).
- Tambahkan **Batch Normalization**.
- Aktivasi:
  - **ReLU** di Generator
  - **Leaky ReLU** di Discriminator

---

## 🧮 Manipulasi Latent Space

| Teknik                     | Contoh                                               |
|----------------------------|------------------------------------------------------|
| Interpolasi                | Gambar A → Gambar B dengan transisi mulus           |
| Aritmetika Semantik        | (👨+👓) - 👨 = 👓 → 👩 + 👓 = 👩‍🦲 dengan kacamata |

---

## 🧪 Aplikasi Nyata

- 🎨 Pembuatan citra baru (image synthesis)
- 🧬 Augmentasi data training
- 📼 Video & suara sintetik
- 🧠 Transfer learning berbasis representasi laten
- 🤖 Kreativitas generatif (teks, seni, musik, dsb)

---

## ✅ Kesimpulan

> Chapter ini menunjukkan kekuatan representation learning melalui Autoencoder dan generative modeling melalui GANs.

- Autoencoders belajar representasi yang berguna.
- VAEs membawa generasi data ke ranah probabilistik.
- GANs menghasilkan data super-realistis dengan teknik adversarial.
- Kombinasi semua ini membuka jalan untuk AI yang lebih kreatif dan efisien.

---
