# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

## Business Understanding
Jaya Jaya Maju adalah perusahaan multinasional yang telah beroperasi sejak tahun 2000 dan memiliki lebih dari 1.000 karyawan yang tersebar di berbagai wilayah. Meskipun perusahaan ini telah berkembang pesat, mereka masih menghadapi tantangan besar dalam pengelolaan sumber daya manusia. Salah satu masalah utama yang dihadapi adalah tingginya tingkat keluar-masuk karyawan (attrition rate), yang melebihi 10%. Angka ini menunjukkan bahwa perusahaan mengalami kesulitan dalam mempertahankan karyawannya, yang dapat berdampak negatif pada produktivitas, meningkatkan biaya rekrutmen, serta mengganggu stabilitas operasional.

### Permasalahan Bisnis

1. Seberapa tinggi tingkat attrition di perusahaan ini?
2. Apa saja faktor utama yang mempengaruhi keputusan karyawan untuk berhenti bekerja?
3. Apakah terdapat perbedaan tingkat pengunduran diri berdasarkan jabatan atau departemen tertentu?
4. Sejauh mana dampak lembur terhadap keputusan karyawan untuk mengundurkan diri?

### Cakupan Proyek

- **Analisis Data :** Memanfaatkan data karyawan untuk mengidentifikasi faktor-faktor utama yang berkontribusi terhadap tingkat pengunduran diri.
- **Visualisasi & Pelaporan :** Membuat dashboard bisnis interaktif yang memungkinkan manajer HR memantau dan menganalisis faktor-faktor penyebab attrition secara visual.
- **Rekomendasi & Intervensi :** Menyusun rekomendasi strategis berdasarkan hasil analisis untuk menekan tingkat attrition dan meningkatkan kepuasan kerja karyawan.

### Persiapan

Sumber data: dataset yang digunakan merupakan dataset [Jaya Jaya Maju](https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee).

* Setup conda environment:

    ```
    conda create --name myenv python=3.9
    conda activate myenv #MacOS
    conda activate myenv  # Windows
    ```
* Install requirements:
    ```
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
    * Klik new project
    * Copy URI pada database setting
    * Kirim dataset menggunakan sqlalchemy 
    ```python
    from sqlalchemy import create_engine
 
    URL = "DATABASE_URL"
    
    engine = create_engine(URL)
    dataset.to_sql('dataset', engine)
    ```

## Business Dashboard

Dashboard ini dibuat untuk memberikan pemahaman mendalam kepada tim HR mengenai faktor-faktor yang mempengaruhi keputusan karyawan dalam meninggalkan perusahaan. Dengan menggunakan dashboard ini, tim HR dapat:

- Menemukan departemen atau area dengan tingkat pengunduran diri yang tinggi.
- Menganalisis faktor-faktor seperti jam lembur, kepuasan kerja, serta karakteristik demografis yang berpengaruh terhadap attrition.
- Mengambil langkah-langkah preventif guna meningkatkan retensi karyawan dan menekan biaya akibat pergantian karyawan.
<img width="1197" alt="Screenshot 2025-02-06 at 02 49 22" src="https://github.com/user-attachments/assets/45b7deb2-fc98-4586-ad7f-652f0ad1a0a7" />


## Conclusion

1. Seberapa tinggi tingkat attrition di perusahaan ini?
* **Jawaban :** Tingkat attrition di perusahaan ini mencapai sekitar 17%, yang berarti bahwa dalam periode tertentu, satu dari enam karyawan mengundurkan diri. Angka ini menunjukkan bahwa tingkat pergantian karyawan cukup tinggi.
  <img width="300" alt="Screenshot 2025-02-06 at 03 33 23" src="https://github.com/user-attachments/assets/f3aa0e6f-de90-43eb-97d8-3c6ddfcdbce7" />

2. Apa saja faktor utama yang mempengaruhi keputusan karyawan untuk berhenti bekerja? 
- **Jawaban :** Beberapa faktor utama yang mempengaruhi keputusan karyawan untuk meninggalkan perusahaan meliputi:
  * Lembur (Overtime): Karyawan yang sering bekerja lembur memiliki kecenderungan lebih tinggi untuk meninggalkan perusahaan.
  * Status Perkawinan: Karyawan yang masih lajang cenderung memiliki tingkat attrition lebih tinggi, kemungkinan karena mereka lebih fleksibel dan terbuka terhadap peluang kerja baru.
  <img width="936" alt="Screenshot 2025-02-06 at 03 31 28" src="https://github.com/user-attachments/assets/2202955c-38d7-4baa-af49-ade4b18413b6" />

3. Apakah terdapat perbedaan tingkat pengunduran diri berdasarkan jabatan atau departemen tertentu?
- **Jawaban :** Ya, tingkat pengunduran diri bervariasi berdasarkan peran dan departemen. Misalnya, posisi seperti Sales Representative serta departemen Sales memiliki tingkat pengunduran diri yang lebih tinggi dibandingkan dengan yang lain. Hal ini mengindikasikan bahwa faktor seperti beban kerja, tekanan, dan struktur kompensasi di departemen tersebut dapat mempengaruhi keputusan karyawan untuk keluar dari perusahaan.
  <img width="1154" alt="Screenshot 2025-02-06 at 03 28 37" src="https://github.com/user-attachments/assets/f1536050-32e3-4e28-8db8-572807dd33d9" />
  <img width="1160" alt="Screenshot 2025-02-06 at 03 29 13" src="https://github.com/user-attachments/assets/fe0a1568-b274-4938-bce0-8f440210970a" />

4. Sejauh mana dampak lembur terhadap keputusan karyawan untuk mengundurkan diri?
- **Jawaban :** Lembur berperan besar dalam mempengaruhi keputusan karyawan untuk keluar dari perusahaan. Data menunjukkan bahwa karyawan yang sering bekerja lembur cenderung memiliki tingkat attrition yang lebih tinggi. Hal ini kemungkinan disebabkan oleh meningkatnya stres dan kurangnya keseimbangan antara kehidupan kerja dan pribadi.
    <img width="937" alt="Screenshot 2025-02-06 at 02 54 32" src="https://github.com/user-attachments/assets/066a54d5-6a06-480e-beec-ededc8ef1202" />

### Rekomendasi Action Items

Berikut beberapa rekomendasi tindakan yang dapat diambil perusahaan untuk mengatasi masalah atau mencapai tujuan mereka :
1. **Mengelola dan Mengurangi Lembur**
- Tinjau dan sesuaikan beban kerja untuk mengurangi lembur yang berlebihan, yang dapat memengaruhi keseimbangan kehidupan kerja dan meningkatkan tingkat attrition.
2. **Meningkatkan Kepuasan Kerja dan Lingkungan Kerja**
- Terapkan program yang fokus pada peningkatan kepuasan kerja dan ciptakan lingkungan kerja yang lebih positif untuk menjaga keterlibatan serta retensi karyawan.
3. **Strategi Retensi di Departemen Kritis**
- Prioritaskan upaya retensi di departemen dan peran dengan tingkat attrition tinggi, seperti Sales. Program retensi yang disesuaikan bisa mencakup insentif, penghargaan, dan pengembangan jalur karir yang jelas.
4. **Penilaian dan Tindakan Berkelanjutan**
- Secara terus-menerus pantau faktor-faktor yang mempengaruhi attrition melalui dashboard, dan segera lakukan tindakan preventif saat masalah mulai teridentifikasi.

Dengan mengikuti langkah-langkah ini, perusahaan diharapkan dapat menurunkan tingkat attrition, meningkatkan retensi karyawan, serta memperkuat stabilitas dan efisiensi operasional secara keseluruhan.

Link Dashboard : [Jaya Jaya Maju Dashboard](https://lookerstudio.google.com/reporting/042df78c-83c7-484c-ac89-691f5be6f510)
