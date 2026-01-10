# Rangkuman Chapter 5: Support Vector Machines (SVM)

Support Vector Machine (SVM) adalah model Machine Learning yang sangat kuat dan serbaguna, mampu melakukan klasifikasi linear maupun non-linear, regresi, dan bahkan deteksi pencilan (outlier). Model ini sangat cocok untuk klasifikasi dataset kompleks berukuran kecil atau menengah.

## 1. Klasifikasi SVM Linear
Ide mendasar dari SVM adalah memasang "jalan raya" selebar mungkin di antara dua kelas.
* **Large Margin Classification:** SVM mencoba mencari margin terbesar antara batas keputusan dan instans pelatihan.
* **Support Vectors:** Batas keputusan sepenuhnya ditentukan oleh instans yang berada di tepi "jalan" tersebut; instans ini disebut vektor pendukung.
* **Penyekalaan Fitur:** SVM sangat sensitif terhadap skala fitur. Tanpa penyekalaan (misalnya dengan StandardScaler), fitur dengan skala besar akan mendominasi dan menyebabkan margin yang tidak optimal.

## 2. Soft Margin Classification
* **Hard Margin:** Memaksa semua instans berada di luar "jalan" dan di sisi yang benar. Masalahnya, ini hanya bekerja pada data yang terpisah secara linear dan sangat sensitif terhadap outlier.
* **Soft Margin:** Mencari keseimbangan antara menjaga "jalan" selebar mungkin dan membatasi pelanggaran margin.
* **Hiperparameter C:** Digunakan untuk mengontrol keseimbangan ini. Nilai C yang rendah menghasilkan margin yang lebih lebar tetapi lebih banyak pelanggaran, sedangkan C yang tinggi menghasilkan margin yang lebih sempit dengan lebih sedikit pelanggaran. Jika model mengalami overfitting, Anda bisa mencoba menguranginya dengan mengecilkan nilai C.

## 3. Klasifikasi SVM Non-linear
Untuk menangani dataset yang tidak terpisah secara linear, kita dapat menambahkan fitur tambahan seperti fitur polinomial.
* **Kernel Trick:** Teknik matematika yang memungkinkan kita mendapatkan hasil yang sama seolah-olah telah menambahkan banyak fitur polinomial derajat tinggi tanpa benar-benar harus menambahkannya.
* **Gaussian RBF Kernel:** Menggunakan fungsi kemiripan untuk menangani masalah non-linear.
* **Hiperparameter γ (gamma):** Mengontrol jangkauan pengaruh satu instans pelatihan. Meningkatkan γ membuat kurva lonceng lebih sempit, sehingga batas keputusan menjadi lebih tidak teratur dan berliku-liku di sekitar instans individu.

## 4. Kompleksitas Komputasi
* **LinearSVC:** Berbasis pustaka liblinear, memiliki kompleksitas waktu sekitar O(m×n) dan tidak mendukung kernel trick.
* **SVC:** Berbasis pustaka libsvm, mendukung kernel trick dengan kompleksitas antara O(m²×n) hingga O(m³×n). Hal ini membuatnya menjadi sangat lambat jika jumlah instans pelatihan menjadi besar.

## 5. Regresi SVM
SVM juga mendukung regresi dengan membalikkan tujuannya: alih-alih mencari margin terbesar untuk memisahkan kelas, ia mencoba memasukkan sebanyak mungkin instans ke dalam "jalan" sambil membatasi pelanggaran margin (instans di luar jalan).
* Lebar "jalan" dikontrol oleh hiperparameter **ϵ (epsilon)**.
* Model ini dikatakan **ϵ-insensitive** karena menambahkan lebih banyak instans pelatihan di dalam margin tidak akan memengaruhi prediksi model.

## 6. Detail Teknis (Under the Hood)
* **Fungsi Keputusan:** Model memprediksi kelas dengan menghitung w<sup>T</sup>x + b. Jika hasilnya positif, prediksi adalah kelas 1, jika tidak maka kelas 0.
* **Hinge Loss:** Fungsi kerugian yang digunakan dalam pelatihan SVM, yang bernilai 0 jika instans berada di luar margin dan di sisi yang benar.

---

**Analogi Sederhana:**
Bayangkan Anda ingin memisahkan dua kelompok penonton di lapangan bola menggunakan tali. **Hard Margin** adalah saat Anda bersikeras tidak boleh ada satu pun penonton yang menyentuh tali. **Soft Margin** adalah saat Anda membiarkan satu atau dua orang sedikit menginjak tali agar jalur pemisahnya bisa lebih lebar dan stabil. **Kernel Trick** seperti mengangkat penonton ke udara (dimensi lebih tinggi) agar Anda bisa menarik garis lurus di bawah mereka yang sebelumnya tidak mungkin dilakukan di permukaan tanah.
