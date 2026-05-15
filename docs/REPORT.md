# Laporan Kelompok — ANN Bake-Off

> Isi semua bagian di bawah. Hapus _italic placeholder_ setelah diisi.

## Identitas Kelompok

- **Nama Kelompok:** Vinnzene Fernando Karim
- **Anggota:**
  1. Nici Andreas — 32230173 — relu
  2. Steven Sebastian — 32230125 — tanh
  3. Christiano Gracia Levi — 32230131 — single layer
  4. Hendy Tandika — 32230129 — sigmoid

---

## 1. Ringkasan Hasil Eksperimen

_Tabel hasil akhir dari notebook `05_comparison.ipynb`. Boleh copy-paste tabel markdown atau screenshot._

| Varian | Arsitektur | Aktivasi | Test Accuracy | Test Loss | Jumlah Parameter |
|---|---|---|---|---|---|
| 01 | Single layer | — | 0.750000 | 0.543707 | 30 |
| 02 | 1 hidden (16) | Sigmoid | 0.958333 | 0.308569 | 530 |
| 03 | 1 hidden (16) | Tanh | 0.958333 | 0.126471 | 530 |
| 04 | 2 hidden (32→16) | ReLU | 0.958333 | 0.080660 | 1650 |


---

## 2. Analisis & Diskusi

Pilih **minimal 3 pertanyaan** dari daftar pertanyaan diskusi di `README.md` dan jawab di sini.

### 2.1 Apakah single-layer mampu mencapai akurasi yang sebanding dengan multi-layer? Mengapa?

Hal ini dikarenakan **Universal Approximation Theorem**. MLP memiliki hidden layer dengan fungsi aktivasi non-linear yang memungkinkan model untuk mempelajari batas keputusan (decision boundary) yang kompleks dan non-linear. Single layer hanya bisa mempelajari fungsi linear, sehingga akurasinya terbatas pada 75%.

### 2.2 Pada dataset ini, apakah ReLU benar-benar konvergen lebih cepat dibanding Sigmoid? Buktikan dengan grafik loss.

Berdasarkan grafik loss, **ReLU** mencapai loss rendah lebih cepat dibandingkan Sigmoid. Hal ini terjadi karena Sigmoid mengalami masalah *vanishing gradient* (gradien mendekati nol saat input sangat besar/kecil), sedangkan ReLU menjaga gradien tetap ada untuk input positif, mempercepat proses update bobot.

### 2.3 Jika kelompok menambah hidden layer ke 3 atau 4, apakah akurasi terus naik? Lakukan eksperimen tambahan.

Tidak selalu, namun dalam kasus ini, peningkatan dari Single Layer ke MLP (yang menambah parameter secara signifikan) memberikan lonjakan akurasi yang besar. Namun, antara MLP ReLU (1650 parameter) dan MLP Tanh (530 parameter), akurasi akhirnya sama (95.83%), menunjukkan adanya titik di mana penambahan parameter memberikan *diminishing returns*.

---

## 3. Refleksi Proses Kerja Kelompok

Proses kerja kelompok kami dimulai dengan pembagian tugas berdasarkan varian model. Nici mengerjakan ReLU, Steven mengerjakan Tanh, Christiano mengerjakan Single Layer, dan Hendy mengerjakan Sigmoid. Kami menggunakan Git untuk mengelola kode secara kolaboratif. Kesulitan utama yang muncul adalah memastikan format output CSV history seragam agar bisa digabungkan di notebook final. Kami mengatasinya dengan menentukan standardisasi nama kolom (accuracy, loss, epoch, variant) sebelum masing-masing anggota melakukan export data. Pelajaran penting untuk proyek berikutnya adalah pentingnya komunikasi awal mengenai struktur data agar proses integrasi berjalan lancar.

---

## 4. Kontribusi Tiap Anggota

| Anggota | Kontribusi Konkret | % Effort |
|---|---|---|
| Nici Andreas | Eksperimen MLP ReLU & Integrasi | 25% |
| Steven Sebastian | Eksperimen MLP Tanh & Notebook Perbandingan | 25% |
| Christiano Gracia Levi | Eksperimen Single Layer & Analisis Teori | 25% |
| Hendy Tandika | Eksperimen MLP Sigmoid & Report | 25% |

_Total harus 100%._

---

## 5. Referensi

- Slide Kuliah PB12MAT+ Machine Learning Week 11: Artificial Neural Networks.
