# Judul Project
Penerapan Computer Vision untuk menentukan jamur yang beracun dan yang aman untuk di konsumsi.

## Repository Outline
- model_E31.keras - model yang digunakan untuk inference
- P2G7_dwi_adhi.ipynb - notebook utama projek
- P2G7_dwi_adhi_inference.ipynb - notebook untuk melakukan inference
- README.md - Penjelasan gambaran umum project

## Problem Background
Jamur sering dikonsumsi untuk nustrisi dan khasiat obat nya. Tetapi untuk membedakan antara jamur yang dapat dikonsumsi dan yang beracun cukup sulit. Seseorang yang salah mengidentifikasi jamur yang beracun sebagai jamur yang bisa dimakan dapat mengakibatkan konsekuensi kesehatan atau kematian.

## Project Output
Output dari projek ini adalah sebuat halaman yang dapat melakukan prediksi terhadap gambar jamur yang diupload di Hugging Face. Model dapat memprediksi jamur beracun tetapi model belum bisa memprediksi jamur yang tidak beracun.

## Data
Dataset terdiri dari 715 gambar jamur yang aman dikonsumsi dan 860 gambar jamur yang beracun

## Method
Dalam proyek ini, saya melakukan data augment terhadap gambar jamur dan melatih model nya.

Setalah model pertama dibuat, saya melakukan data augment dengan balancing dan mengulahi pelatihan model. Dua model yang dibuat akan dibandingkan bedasarkan nilai recall dimana model dengan performa terbaik akan dipilih sebagai mode terbaik.

## Stacks
- Python
- pandas, numpy, sklearn,seaborn, matplotlib, random, os, cv2, glob, tensorflow_addons, tensorflow
- Google Colab

## Reference
https://www.kaggle.com/datasets/marcosvolpato/edible-and-poisonous-fungi?select=poisonous+mushroom+sporocarp
https://huggingface.co/spaces/DwiA2/mushroom_edibility_detector
---