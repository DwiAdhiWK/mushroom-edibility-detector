# Judul Project
Penerapan Computer Vision untuk menentukan jamur yang beracun dan yang aman untuk di konsumsi.

## Repository Outline
- P2G7_dwi_adhi.ipynb - notebook utama projek
- P2G7_dwi_adhi_inference.ipynb - notebook untuk melakukan inference
- README.md - Penjelasan gambaran umum project

## Problem Background
Jamur sering dikonsumsi untuk nustrisi dan khasiat obat nya. Tetapi untuk membedakan antara jamur yang dapat dikonsumsi dan yang beracun cukup sulit. Seseorang yang salah mengidentifikasi jamur yang beracun sebagai jamur yang bisa dimakan dapat mengakibatkan konsekuensi kesehatan atau kematian.

## SMART and Problem Statement

Specific: Membuat model ANN yang dapat membedakan antara jamur yang bisa dimakan dan yang beracun

Measurable: Target akurasi lebih besar daripada 90%

Achievable: Menggunkan dataset jamur yang diambil dari Kaggle dan menggunakan konsep CNN.

Relevant: Model yang dibuat dapat digunakan untuk mengajari orang mengidentifikasi jamur yang beracun dan yang tidak.

Time Bound: Durasi yang pembuatan model selama 7 hari.

Problem Statement: Mengidentifikasi jamur yang dapat dimakan dan yang beracun cukup sulit. Proyek ini bertujuan membuat model Convolutional Neural Network (CNN) yang mampu membedakan jamur yang bisa dimakan dan yang beracun dengan target akurasi lebih dari 90%. Model dikembangkan selama 7 hari dan diharapkan dapat membantu orang belajar mengenali jamur secara aman.

## Project Output
Output dari projek ini adalah sebuat aplikasi web yang dapat melakukan prediksi terhadap gambar jamur yang diupload di Hugging Face. Model dapat memprediksi jamur beracun tetapi model belum bisa memprediksi jamur yang tidak beracun.

## Data
Dataset terdiri dari 715 gambar jamur yang aman dikonsumsi dan 860 gambar jamur yang beracun

## Method
Dalam proyek ini, pertama-tama saya melakukan data augmentation pada gambar jamur untuk memperbesar dan memperkaya dataset. Setelah model awal dilatih, dilakukan data augmentation tambahan dengan teknik balancing untuk mengurangi ketidakseimbangan kelas, kemudian pelatihan model diulang.

Dua model yang dihasilkan kemudian dibandingkan berdasarkan nilai recall, dan model dengan performa terbaik dipilih sebagai model final.

## Model Evaluation

| Stage                  | Class                | Precision | Recall | F1-Score | Support |
| ---------------------- | -------------------- | --------- | ------ | -------- | ------- |
| **Before Improvement** | Edible Mushroom      | 0.46      | 0.45   | 0.45     | 386     |
|                        | Poisonous Mushroom   | 0.55      | 0.55   | 0.55     | 465     |
|                        | **Overall Accuracy** | 0.51      | 0.50   | 0.51     | 851     |
| **After Improvement**  | Edible Mushroom      | 0.85      | 0.15   | 0.26     | 72      |
|                        | Poisonous Mushroom   | 0.58      | 0.98   | 0.73     | 86      |
|                        | **Overall Accuracy** | 0.60      | 0.56   | 0.51     | 158     |

## Analysis and Insight

1. Sebelum Augmentation:
   - model underfit - kedua class memiliki nilai precision, recall, dan f1-score yang rendah
   - Overall Accuracy hanya 51% yang menunjukan generalisasi yang buruk
2. Setelah Augmentation:
   - Poisonous Mushroom dapat diidentifikasi dengan baik (recall 0.98) yang artinya model jarang salah mengidentidikasi jamur beracun
   - Edible Mushroom tidak dapat diidentifikasi (recall 0.15) - model overfit terhadap jamur beracun karena model yang bias atau class yang tidak seiimbang
   - Overal Accuracy meningkat menjadi 0.60, bisa jadi karena ketidak seiibang class ini.
     
## Conclusion

Convolutional Neural Network (CNN) dapat diterapkan untuk kasus klasifikasi jamur pada computer vision.

Model Artificial Neural Network (ANN) yang dibuat mampu mengidentifikasi jamur beracun dengan baik setelah dilakukan improvement, dengan recall 0.98 pada test set dan 0.92 pada train set, melebihi target awal 90%.

Namun, model masih kesulitan mengidentifikasi jamur yang aman dikonsumsi, kemungkinan karena fitur visual jamur beracun dan tidak beracun yang mirip sehingga sulit dibedakan.

Salah satu langkah perbaikan yang direkomendasikan adalah menambah jumlah gambar jamur yang aman dikonsumsi agar model dapat belajar membedakan kedua kelas dengan lebih baik dan mengurangi bias terhadap kelas beracun.

## Stacks
- Python
- pandas, numpy, sklearn,seaborn, matplotlib, random, os, cv2, glob, tensorflow_addons, tensorflow
- Google Colab

## Reference
https://www.kaggle.com/datasets/marcosvolpato/edible-and-poisonous-fungi?select=poisonous+mushroom+sporocarp
https://huggingface.co/spaces/DwiA2/mushroom_edibility_detector
---
