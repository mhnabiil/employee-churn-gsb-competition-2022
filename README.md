# employee-churn-gsb-competition-2022
EDA and classification modeling on employee churn data from the gsb x data science competition at guided.id 2022.

Analisis Employee Churn adalah sebuah studi terhadap tingkat 'churn' dari karyawan perusahaan. Employee (karyawan) dibilang 'Churn' ketika karyawan tersebut pindah kerja ke kantor lain (berhenti bekerja di kantor asal). Secara garis besar, perusahaan-perusahaan ingin bisa 'memprediksi' employee mana yang akan 'churn', supaya bisa melakukan antisipasi agar employee tersebut tidak jadi 'churn'. Mengapa? Karena...lebih besar ongkos yang dikeluarkan untuk mencari & merekrut karyawan baru, melatih mereka dari 0 lagi, ketimbang mempertahankan employee yang sudah ada. Oleh sebab itu, perusahaan-perusahaan ingin mempelajari faktor-faktor apa saja yang dapat dilihat untuk mengantisipasi 'churn' dari seorang employee.

Penjelasan tiap variabel yang digunakan:
- `office_distance_from_house`: jarak (dalam meter) kantor ke rumah karyawan
- `bonus_salary_percentage`: persentase bonus gaji yang diterima karyawan dalam 6 bulan terakhir
- `job_satisfaction`: tingkat kepuasan kerja karyawan
- `education_level`: tingkat pendidikan karyawan
- `overtime_hour`: lama waktu lembur rata-rata (dalam jam)
- `company_latitude`: koordinat garis lintang kantor pusat perusahaan
- `company_longitude`: koordinat garis bujur kantor pusat perusahaan
- `gender`: apabila 0, berarti perempuan, apabila 1, berarti laki-laki
- `churn`: apabila 1, berarti Churn (si karyawan pindah), apabila 0, berarti tidak Churn (karyawan tidak pindah)

**Key Insights:**
- Saya melakukan perubahan tipe data pada kolom churn, gender, dan job_satisfaction karena tipe data yang seharusnya adalah data kategorik. 
- Kemudian, saya melakukan pengecekan null values pada setiap kolom. Hasil menunjukkan bahwa tidak terdapat null values pada data ini. Selain itu, tidak terdapat duplikasi data.
- False Positive dari kasus ini adalah karyawan yang berpindah perusahaan, namun diprediksikan tidak perindah.
- False Negative dari kasus ini adalah karyawan yang tidak berpindah perusahaan, namun diprediksikan berpindah.
- Dalam kasus ini, tipe 'kesalahan' yang lebih penting untuk diperhatikan adalah  False Negatives (Type 2 Errors) karena tipe error ini dapat merugikan perusahaan ketika seseorang yang menetap diperusahaan diprediksikan berpindah.
- Saya memutuskan untuk memilih Machine Learning Model: Tuned K-Nearest Neighbors Algorithm
- Untuk mengevaluasi model tersebut, saya menggunakan metrik: F1-score, AUC.
- Hasil evaluasi dari model tersebut adalah sebagai berikut:
    - AUC: 96%
    - F1-score accuracy: 93.26%
