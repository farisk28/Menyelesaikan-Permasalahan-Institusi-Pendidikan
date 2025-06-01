# 📊Analisis Dropout Mahasiswa Jaya Jaya Institut

## 🔍 A. Business Understanding
Jaya Jaya Institut adalah sebuah institusi pendidikan tinggi yang telah berdiri sejak tahun 2000 dan memiliki reputasi baik dalam menghasilkan lulusan berkualitas. Namun, terdapat tantangan serius yang dihadapi, yaitu tingginya jumlah mahasiswa yang dropout (tidak menyelesaikan studi mereka).

Masalah ini berdampak pada reputasi institusi, efektivitas proses pembelajaran, serta efisiensi penggunaan sumber daya. Oleh karena itu, penting bagi manajemen untuk dapat mengidentifikasi pola dan faktor-faktor utama yang menyebabkan dropout agar dapat dilakukan intervensi sedini mungkin.

## B. Permasalahan Bisnis
Permasalahan bisnis yang akan diselesaikan yaitu:
- Tingginya presentase mahasiswa yang dropout.
- Belum adanya sebuah alat visualisasi yang komprehensif untuk membantu dalam memonitor dan menganalisis mahasiswa dropout.
- Dibutuhkan identifikasi untuk mengetahui apa saja yang menjadi faktor-faktor yang mempengaruhi mahasiswa untuk dropout.

## C. Cakupan Proyek
Proyek ini mencakup:
- Eksplorasi data terkait seluruh performa mahasiswa, baik yang Graduated, Enrolled, dan Dropout.
- Analisis faktor-faktor utama yang berkorelasi terhadap mahasiswa dropout.
- Pembuatan dashboard interaktif untuk pemantauan performa mahasiswa secara berkala.
- Menerapkan sistem prediksi melalui sebuah aplikasi berbasis web dengan streamlit.
- Pemberian rekomendasi berdasarkan hasil analisis.

## ⚙️ D. Persiapan
1. Sumber data yang digunakan yaitu: [Sumber Data](https://github.com/dicodingacademy/dicoding_dataset/blob/main/students_performance/data.csv)
2. Setup environment:
* Setup Environment - Anaconda:
    ```
   conda create --name main-ds python=3.9
    conda activate main-ds
    pip install -r requirements.txt
    ```
* Setup Environment - Shell/Terminal:
  ```
  pip install pipenv
  pipenv install
  pipenv shell
  pip install -r requirements.txt
  ```
  
* Setup metabase:
    ```
    docker pull metabase/metabase:v0.46.4
    docker run -p 3000:3000 --name metabase metabase/metabase
    ```
    Akses metabase pada http://localhost:3000/setup dan lakukan setup.
  * Setup database (supabase):

    * Buat akun dan login https://supabase.com/dashboard/sign-in.
    * Buat new project
    * Copy URI pada database setting
    * Kirim dataset menggunakan sqlalchemy 
    ```python
    from sqlalchemy import create_engine
 
    URL = "DATABASE_URL"
    
    engine = create_engine(URL)
    df.to_sql('data', engine)
    
## 🔐 Informasi Login (Metabase Lokal)

- Email: `farisfurqon2881@gmail.com`
- Password: `Awan_mfk7012`
---

## 📊 E. Business Dashboard

Dashboard yang telah dibuat memvisualisasikan berbagai aspek penting terkait mahasiswa yang dropout, antara lain:
- Jumlah total mahasiswa, mahasiswa dropout, dan persentase dropout.
- Distribusi mahasiswa berdasarkan status akademik (graduate, dropout, enrolled).
- Dropout berdasarkan status pernikahan, jenis kelamin, kepemilikan hutang, dan kewarganegaraan.
- Distribusi dropout per jurusan.
- Distribusi dropout berdasarkan admission grade
- Hubungan antara penerima beasiswa dan rata-rata nilai penerimaan.

### Cuplikan Dashboard:
![Image](https://github.com/user-attachments/assets/681e92c8-142f-44fb-ac6b-66d5bf0270da)
![Image](https://github.com/user-attachments/assets/c633eeaf-ccfd-4afd-968a-fd518030947b)

## 📊 F. Menjalankan Sistem Machine Learning

Setup Streamlit, Joblib, Scikit-learn:
* Setup Streamlit (on Terminal VSCode):
    ```
    pip install streamlit
    ```
* Setup Joblib:
    ```
    pip install joblib
    ```
* Setup Scikit-learn:
    ```
    pip install scikit-learn
    ```

Running the program (prediction.py):
* Running the program (on Terminal VSCode):
    ```
    streamlit run prediction.py
    ```
---

## 📌 G. Conclusion
Hasil analisis menunjukkan bahwa faktor-faktor berikut berkontribusi signifikan terhadap mahasiswa dropout:
- Presentase mahasiswa yang dropout sebesar 30%-an.
- Mayoritas mahasiswa yang dropout adalah mahasiswa yang lajang dan tidak menerima beasiswa.
- 3 Jurusan yang memiliki presentase mahasiswa dropout terbesar adalah: Biofuel Production Technologies, Equinculture, dan  Informatics Engineering.
- Jurusan Biofuel Production Technologies adalah jurusan yang memiliki jumlah mahasiswa terendah
- Mahasiswa yang memiliki admission grade dibawah 100 cenderung lebih banyak untuk melakukan dropout.
- Mahasiswa dengan hutang memiliki risiko dropout yang lebih tinggi.
- Mahasiswa tanpa beasiswa cenderung memiliki nilai rata-rata penerimaan yang lebih rendah.
- Faktor-faktor yang mempengaruhi mahasiswa untuk dropout adalah sebagai berikut:
![Image](https://github.com/user-attachments/assets/c1e428da-b4ad-42f3-bcc2-1b8cbefcb2a6)

## 💡 F. Rekomendasi Action Items

Berdasarkan hasil di atas, berikut adalah beberapa langkah yang dapat diambil oleh Jaya Jaya Institut:
- Program Intervensi Dini: Prioritaskan dukungan akademik atau finansial pada jurusan dengan dropout tinggi (seperti Biofuel Production Technologies, Equinculture, dan  Informatics Engineering).
- Evaluasi Beasiswa: Pertimbangkan perluasan akses beasiswa untuk meningkatkan retensi mahasiswa yang ingin melakukan droput.
- Pendekatan Personal: Tawarkan bimbingan psikologis/akademik khusus bagi mahasiswa dengan tekanan ekonomi atau sosial.
- Fleksibilitas Jadwal Kuliah: Menawarakan berbagai macam pilihan jadwal kuliah untuk mahasiswa dengan keterbatasan waktu (misalnya, mahasiswa sambil bekerja).

---

## 📁 Struktur Proyek

1. `awan_rmn-dashboard1.jpg` - Gambar dashboard
2. `awan_rmn-dashboard2.jpg` - Gambar dashboard
3. `notebook_Menyelesaikan_Permasalahan_Institusi_Pendidikan.ipynb` - Notebook pengolahan & analisis data
4. `model.joblib` - Model machine learning
5. `prediction.py` - Penerapan model machine learning untuk dapat diterapkan dengan streamlit
6. `metabase.db.mv.db` - File database SQLite
7. `requirements.txt` - Library dependencies
