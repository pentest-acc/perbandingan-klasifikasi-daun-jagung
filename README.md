# Perbandingan K-Nearest Neighbor dan Random Forest untuk Klasifikasi Penyakit Daun Jagung Berbasis Fitur GLCM-HSV

Repository ini berisi kode program untuk artikel ilmiah dengan judul di atas. Penelitian ini membandingkan algoritma K-Nearest Neighbor (K-NN) dan Random Forest (RF) untuk mengklasifikasikan penyakit daun jagung menggunakan fitur tekstur GLCM dan fitur warna HSV.

## Anggota Kelompok

1. [Stephen Baldwin] - [15241024]
2. [Ilham Maulana] - []
3. [Muhammad Zaid Dhiya'ulhaq] - []

Program Studi [Nama Prodi], Universitas Bina Sarana Informatika

## Dataset

Dataset yang digunakan adalah PlantVillage, yaitu citra daun jagung sebanyak 3.852 citra yang terbagi ke dalam 4 kelas:

1. Bercak daun kelabu (Cercospora leaf spot / Gray leaf spot): 513 citra
2. Karat daun (Common rust): 1.192 citra
3. Hawar daun (Northern Leaf Blight): 985 citra
4. Sehat (Healthy): 1.162 citra

Sumber dataset: https://github.com/spMohanty/PlantVillage-Dataset

Citra dataset tidak disimpan di repository ini karena notebook akan mengunduhnya secara otomatis. Daftar pembagian data latih dan data uji (80:20) dapat dilihat pada file daftar_pembagian_data.csv.

## Isi Repository

- klasifikasi_daun_jagung_glcm_hsv_knn_rf.ipynb : notebook Google Colab untuk preprocessing, ekstraksi fitur, pelatihan model, dan evaluasi
- daftar_pembagian_data.csv : daftar nama file yang masuk ke data latih dan data uji
- web_app/app.py : aplikasi web berbasis Streamlit
- web_app/glcm_features.py : fungsi preprocessing dan ekstraksi fitur GLCM dan HSV
- web_app/requirements.txt : daftar library yang dibutuhkan aplikasi web
- web_app/models/ : model K-NN dan Random Forest yang sudah dilatih

## Cara Menjalankan Notebook

1. Buka file klasifikasi_daun_jagung_glcm_hsv_knn_rf.ipynb di Google Colab.
2. Pilih menu Runtime, lalu Run all.
3. Izinkan akses ke Google Drive saat diminta.
4. Hasil berupa tabel, gambar, dan model akan tersimpan di folder MyDrive/hasil_jagung_glcm.

Runtime CPU sudah cukup, tidak perlu GPU.

## Cara Menjalankan Aplikasi Web

1. Masuk ke folder web_app.
2. Install library yang dibutuhkan dengan perintah:

   pip install -r requirements.txt

3. Jalankan aplikasi dengan perintah:

   streamlit run app.py

4. Buka alamat yang muncul di terminal (biasanya http://localhost:8501), lalu unggah foto daun jagung.

## Ringkasan Hasil

Hasil pengujian pada data uji (771 citra) dengan fitur GLCM dan HSV:

- Random Forest: akurasi 88,33% dan F1-score 84,36%
- K-Nearest Neighbor: akurasi 84,18% dan F1-score 80,18%

Perbedaan kinerja kedua model signifikan secara statistik berdasarkan uji McNemar (p < 0,05).
