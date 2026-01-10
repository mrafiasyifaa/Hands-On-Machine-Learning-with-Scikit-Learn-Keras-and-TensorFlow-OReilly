# Rangkuman Chapter 6: Decision Trees

**Decision Trees** adalah algoritme Machine Learning yang serbaguna karena dapat melakukan tugas **klasifikasi dan regresi**, bahkan tugas dengan banyak output. Mereka merupakan komponen fundamental dari *Random Forests*, yang termasuk salah satu algoritme Machine Learning paling kuat saat ini.

## 1. Melakukan Prediksi
Decision Tree bekerja dengan cara mengajukan serangkaian pertanyaan berdasarkan fitur data. 
*   **Node Akar (Root Node):** Node teratas yang memberikan pertanyaan pertama.
*   **Leaf Node:** Node yang tidak memiliki anak dan memberikan prediksi kelas akhir.
*   **Kelebihan:** Decision Tree membutuhkan **sangat sedikit persiapan data**, bahkan tidak memerlukan penyekalaan fitur (*feature scaling*) atau pemusatan (*centering*).
*   **White Box Model:** Model ini sangat intuitif dan keputusannya mudah diinterpretasikan, berbeda dengan model *black box* seperti Neural Networks yang sulit dijelaskan secara sederhana.

## 2. Mengestimasi Probabilitas Kelas
Decision Tree dapat memperkirakan probabilitas bahwa sebuah instans termasuk dalam kelas tertentu. Prosesnya adalah dengan menemukan *leaf node* untuk instans tersebut, lalu mengembalikan **rasio instans pelatihan dari kelas tersebut** di node tersebut.

## 3. Algoritma Pelatihan CART
Scikit-Learn menggunakan algoritma **Classification and Regression Tree (CART)** untuk melatih Decision Tree. 
*   Algoritma ini bekerja dengan membagi set pelatihan menjadi dua subset menggunakan fitur tunggal $k$ dan ambang batas $t_k$.
*   CART bersifat **greedy algorithm**: ia mencari pembagian optimal di tingkat teratas tanpa memedulikan apakah pembagian tersebut akan menghasilkan ketidakmurnian (*impurity*) terendah di beberapa tingkat di bawahnya.
*   Menemukan pohon yang benar-benar optimal diketahui sebagai masalah **NP-Complete**, sehingga kita harus puas dengan solusi yang "cukup baik".

## 4. Gini Impurity atau Entropy?
Secara default, Keras menggunakan ukuran **Gini impurity**, tetapi Anda dapat memilih ukuran **entropy** dengan mengatur hiperparameter `criterion`. 
*   Keduanya sering kali menghasilkan pohon yang serupa. 
*   Gini impurity sedikit lebih cepat untuk dihitung.
*   Jika berbeda, Gini cenderung mengisolasi kelas yang paling sering dalam cabangnya sendiri, sementara entropy cenderung menghasilkan pohon yang lebih seimbang.

## 5. Hiperparameter Regulasi
Decision Tree adalah **nonparametric model**, artinya jumlah parameternya tidak ditentukan sebelum pelatihan, sehingga strukturnya bebas menempel erat pada data dan berisiko tinggi mengalami **overfitting**. Untuk menghindarinya, Anda perlu membatasi kebebasan Decision Tree:
*   **max_depth:** Mengatur kedalaman maksimum pohon.
*   **min_samples_split:** Jumlah minimum sampel yang harus dimiliki node sebelum dapat dipecah.
*   **min_samples_leaf:** Jumlah minimum sampel yang harus dimiliki sebuah *leaf node*.

## 6. Regresi
Decision Tree juga mampu melakukan tugas regresi menggunakan kelas `DecisionTreeRegressor`. Alih-alih memprediksi kelas di setiap node, ia **memprediksi sebuah nilai** yang merupakan nilai target rata-rata dari instans pelatihan yang terkait dengan node tersebut.

## 7. Instabilitas
Meskipun kuat, Decision Tree memiliki batasan:
*   **Ortogonal:** Decision Tree menyukai batas keputusan ortogonal (tegak lurus terhadap sumbu), yang membuatnya **sensitif terhadap rotasi data**.
*   **Sensitivitas:** Mereka sangat **sensitif terhadap variasi kecil dalam data pelatihan**. Menghapus satu instans saja bisa menghasilkan model yang sangat berbeda.

---

**Analogi Sederhana:**
Bayangkan Decision Tree seperti permainan **"20 Pertanyaan"**. Setiap pertanyaan (misalnya, "Apakah ia memiliki sayap?") membantu Anda mempersempit kemungkinan hingga Anda mencapai jawaban akhir. Namun, jika Anda terlalu spesifik dengan pertanyaan berdasarkan satu pengalaman saja (overfitting), Anda mungkin gagal menebak jawaban yang sedikit berbeda di masa depan.
