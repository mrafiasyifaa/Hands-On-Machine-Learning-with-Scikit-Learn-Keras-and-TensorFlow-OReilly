# 🎮 Chapter 18: Reinforcement Learning (RL)

_Buku: Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow — Aurélien Géron_

---

## 🧭 Apa Itu Reinforcement Learning?

- Paradigma pembelajaran di mana **agen** belajar melalui interaksi dengan **lingkungan**.
- Agen menerima **reward** sebagai umpan balik untuk setiap aksi yang diambil.
- Tujuan: ✅ _Maksimalkan kumulatif reward_ jangka panjang.
- Beda dari supervised learning: **tidak ada label tetap** dan melibatkan **keputusan sekuensial**.

---

## 🔁 Markov Decision Processes (MDP)

Model matematis dasar dalam RL, terdiri dari:
- **State (S)**: Kondisi sistem saat ini
- **Action (A)**: Pilihan aksi yang bisa diambil agen
- **Reward (R)**: Feedback setelah aksi
- **Transition**: Perubahan state akibat aksi
- Asumsi Markov: Masa depan hanya bergantung pada state saat ini.

---

## 🧠 Policy dan Value Function

| Komponen            | Penjelasan                                                                 |
|---------------------|----------------------------------------------------------------------------|
| 🧩 Policy (π)        | Strategi agen dalam memilih aksi                                           |
| 📈 Value Function    | Ekspektasi reward masa depan dari state (V(s)) atau state-action pair (Q(s,a)) |
| 🧮 Q-Learning        | Metode untuk belajar Q-value optimal secara iteratif                       |

---

## 🧠 Deep Reinforcement Learning

### Deep Q-Networks (DQN)
- Menggabungkan Q-Learning + Deep Neural Networks.
- Cocok untuk state dan action space besar.
- Teknik stabilisasi:
  - 📦 **Experience Replay**
  - 📌 **Fixed Q-target**
  - 💡 **Double DQN**
  - ⚔️ **Dueling DQN**

### Approximate Q-Learning
- Gunakan neural nets atau function approximators saat state/action terlalu banyak.

---

## 📉 Policy Gradient Methods

- Mengoptimalkan **policy langsung** alih-alih value function.
- Cocok untuk:
  - 🎯 Action space kontinu
  - 🔄 Model kompleks
- Contoh algoritma: **REINFORCE**, **Actor-Critic**

---

## 🛠️ TF-Agents (TensorFlow Agents)

- Framework RL dari TensorFlow.
- Dukung banyak algoritma modern dan scalable training.
- Contoh penerapan: bermain **Breakout**, **CartPole**, dll.
- Komponen utama:
  - Environment
  - Agent
  - Policy
  - Replay Buffer
  - Driver loop

---

## 🔍 Curiosity-Driven Exploration

> "Agen yang ingin tahu lebih cerdas!"

- Menggerakkan agen untuk menjelajah state yang **tidak bisa diprediksi** oleh modelnya sendiri.
- Solusi untuk:
  - **Reward sparsity**
  - Lingkungan yang kompleks
- Terinspirasi dari prinsip pembelajaran manusia.

---

## ⚠️ Tantangan dalam RL

| Masalah                    | Penjelasan                                                     |
|----------------------------|----------------------------------------------------------------|
| 💣 Catastrophic Forgetting | Pelatihan pada state baru merusak pengetahuan state lama       |
| 🎲 Ketidakstabilan         | Training sangat sensitif terhadap hyperparameter dan random seed |
| 🧩 Credit Assignment       | Sulit melacak aksi mana yang memberi reward tertentu          |

---

## 🧪 Latihan dan Eksperimen

- Memahami:
  - 💡 Definisi reward dan discount factor
  - 🔁 Replay buffer
  - 🎯 Credit assignment problem
- Disertai kode eksperimen dan contoh implementasi.

---

## 🏁 Kesimpulan

> Chapter ini membuka pintu menuju pembelajaran berbasis interaksi aktif.

- Reinforcement Learning memberi fleksibilitas bagi AI untuk **belajar dari pengalaman**.
- Diperlukan pemahaman kuat tentang nilai, strategi, dan dinamika eksplorasi.
- RL modern: perpaduan antara **matematika MDP klasik** dan **kekuatan neural network** dalam DQN, TF-Agents, dan beyond.

---
