# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Jaya Jaya Maju

## Business Understanding

Jaya Jaya Maju adalah sebuah perusahaan berskala besar yang telah berdiri sejak tahun 2000. Meskipun memiliki lebih dari 1000 karyawan, perusahaan saat ini sedang menghadapi tantangan serius dalam pengelolaan Sumber Daya Manusia (SDM), yaitu tingginya tingkat perputaran karyawan (attrition rate). Banyak karyawan yang memutuskan untuk keluar (resign) dari perusahaan. Jika dibiarkan, hal ini akan menyebabkan pembengkakan biaya rekrutmen, penurunan produktivitas, dan hilangnya knowledge perusahaan. Oleh karena itu, manajer HR menugaskan pembuatan sistem deteksi dini (early warning system) untuk memprediksi karyawan yang berisiko keluar.

## Permasalahan Bisnis

1. Apa saja faktor utama dan karakteristik karyawan yang memengaruhi keputusan untuk keluar (resign) berdasarkan hasil analisis data eksploratif (EDA)?
2. Bagaimana performa model prediksi yang dibangun dan fitur apa saja yang paling berkontribusi dalam memandu model memprediksi attrition?

## Cakupan Proyek

* Data Preprocessing & Exploratory Data Analysis (EDA): Membersihkan data, menangani nilai kosong/duplikat, dan menganalisis pola distribusi serta karakteristik karyawan yang resign.
* Business Dashboard: Membangun dashboard interaktif menggunakan Looker Studio untuk memantau metrik utama HRD.
* Machine Learning Modeling: Membangun model kecerdasan buatan (klasifikasi) dan menangani ketidakseimbangan data (Imbalanced Data) menggunakan teknik SMOTE.
* Deployment: Menyimpan model terbaik dan membuat script prediction.py agar bisa digunakan sebagai early warning system.

## Persiapan

Sumber data: [employee_data.csv](<https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee>)

Setup environment:
Proyek ini dikembangkan menggunakan Python versi 3.13. Berikut adalah panduan langkah demi langkah untuk menyiapkan environment dan menjalankan proyek secara lokal:

1. Membuat Virtual Environment:
Buka Terminal atau Command Prompt, arahkan ke dalam direktori proyek (folder yang berisi file prediction.py dan requirements.txt), lalu jalankan perintah berikut:
`python -m venv env`

2. Mengaktifkan Virtual Environment:
* Untuk pengguna Windows:
`env\Scripts\activate`
* Untuk pengguna Mac/Linux:
`source env/bin/activate`

3. Menginstal Dependencies:
Setelah environment aktif, sangat disarankan untuk memperbarui pip terlebih dahulu, kemudian instal seluruh library yang dibutuhkan melalui file requirements.txt dengan perintah berikut:
`python -m pip install --upgrade pip`
`pip install -r requirements.txt`

4. Menjalankan Berkas Prediksi:
Pastikan Anda masih berada di direktori yang sama dan terdapat folder model/ di dalamnya yang berisi file-file .pkl. Jalankan perintah:
`python prediction.py`

## Business Dashboard

Telah dibuat sebuah Business Dashboard interaktif untuk membantu HRD memantau kondisi karyawan secara *real-time*. Dashboard ini mengambil sumber data dari file `cleaned_employee_data.csv`. Di dalamnya terdapat visualisasi berupa Total Karyawan (1.058 karyawan), Persentase Attrition yang mencapai **16,92%**, serta analisis mendalam mengenai dampak beban lembur (*OverTime*), tingkat *Work-Life Balance*, dan gaji bulanan (*Monthly Income*) terhadap keputusan resign karyawan di berbagai jabatan (*Job Role*).

Link Dashboard Looker Studio: https://lookerstudio.google.com/reporting/4578c193-2ee8-4190-9cfb-bf26dace9d7c

## Conclusion

Berdasarkan proses analisis data dan pemodelan yang telah dilakukan, dapat ditarik dua kesimpulan utama:

1. Kesimpulan Analisis Data Eksploratif (EDA): Berdasarkan hasil eksplorasi data dan visualisasi pada business dashboard, ditemukan bahwa attrition rate perusahaan berada di angka 16,92%. Karakteristik karyawan yang paling banyak memutuskan resign adalah mereka yang memiliki beban lembur (OverTime) tinggi, menerima gaji bulanan (Monthly Income) yang kurang kompetitif dibandingkan rekan kerjanya, serta kelompok karyawan yang memiliki tingkat keseimbangan hidup (Work-Life Balance) di kategori 1 (Buruk).

2. Kesimpulan Model Machine Learning: Model prediksi telah berhasil dibangun dengan performa yang baik menggunakan algoritma Klasifikasi dan penanganan data tidak seimbang (SMOTE). Berdasarkan analisis Feature Importance untuk mengevaluasi kinerja model, fitur yang paling berkontribusi dan berpengaruh besar terhadap keputusan model dalam mendeteksi attrition adalah fitur OverTime (Lembur) dan MonthlyIncome (Gaji Bulanan).

## Rekomendasi Action Items

* Evaluasi Kebijakan Lembur (OverTime): HRD harus memantau departemen atau peran kerja yang paling sering lembur. Perusahaan perlu menerapkan batas maksimal jam lembur bulanan atau memberikan kompensasi ekstra untuk mencegah terjadinya burnout.
* Penyesuaian Skala Gaji (Salary Adjustment): Melakukan peninjauan ulang terhadap gaji bulanan karyawan, terutama di jabatan kritikal yang gajinya berada di bawah rata-rata agar talenta terbaik tidak dibajak oleh kompetitor.
* Penerapan Program One-on-One Preventif: Menggunakan script prediction.py secara berkala untuk mendeteksi karyawan yang tergolong berisiko tinggi. Manajer terkait dapat langsung diinstruksikan untuk melakukan pendekatan secara personal guna mendengarkan keluhan karyawan sebelum mereka benar-benar mengajukan resign.
