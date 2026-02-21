# Earthquake impact management strategy: A predictive system development approach using data mining techniques
## Latar Belakang
Indonesia merupakan salah satu negara yang berada di kawasan Ring of Fire, sehingga memiliki tingkat kerawanan gempa bumi yang tinggi. Dalam kurun waktu 2015–2024, tercatat ribuan kejadian gempa yang tersebar di berbagai wilayah Indonesia. Bencana gempa bumi tidak hanya menimbulkan dampak sosial dan korban jiwa, tetapi juga berdampak signifikan terhadap struktur ekonomi, termasuk modal manusia, infrastruktur, dan sektor perdagangan. Berdasarkan penelitian Vidyatama (2010), komponen-komponen tersebut memiliki pengaruh positif terhadap pertumbuhan Produk Domestik Bruto (PDB), sehingga ketika terjadi gangguan akibat gempa, dampaknya akan langsung dirasakan pada kinerja ekonomi nasional. Bahkan, gempa bumi dapat menjadi faktor penyumbang penurunan PDB Indonesia secara signifikan. Oleh karena itu, diperlukan strategi pengelolaan dampak gempa bumi melalui pengembangan sistem prediktif berbasis teknik data mining guna mendukung mitigasi risiko dan pengambilan keputusan yang lebih responsif dan berbasis data.

## Tujuan
1. Memprediksi kerugian ekonomi dan tingkat korban akibat gempa bumi.
2. Mengidentifikasi faktor-faktor yang menyebabkan kerugian ekonomi dan tingkat korban akibat gempa bumi.
3. Menentukan model terbaik untuk analisis prediktif kerugian ekonomi dan tingkat korban akibat gempa bumi.

## Manfaat
1. Memberikan pemahaman yang lebih dalam tentang bagaimana gempa bumi mempengaruhi perekonomian Indonesia, baik secara langsung maupun tidak langsung.
2. Membantu pemerintah dalam menyusun kebijakan mitigasi yang lebih tepat sasaran dan berbasis data sehingga dapat mengurangi kerugiaan ekonomi akibat gempa bumi.
3. Mendukung upaya untuk mencapai stabilitas ekonomi jangka panjang dengan mengidentifikasi dan mengurangi kerentanan ekonomi akibat gempa bumi.

## Dataset
Digunakan data sekunder yang diakses dari beberapa sumber. Terdapat 4 kategori data berbeda yang akan diintegrasi berdasarkan tahun dan provinsi. 
- Informasi Gempa Bumi: Latitude, Longitude, Depth, Mag, Gap, Dmin, Rms, Provinsi (Sumber: United Stated Geological Survey (USGS))
- Demografi: Tahun, Provinsi, Populasi, Kepadatan, Angka Ketergantungan (Sumber: Badan Pusat Statistik)
- Sosial-Ekonomi: Tahun, Provinsi, PDB, Angka Melek Huruf, Jumlah RS, Jumlah Tempat Tidur RS, Rasio TT (Sumber: Badan Pusat Statistik dan Kementerian Kesehatan)
- Dampak Gempa Bumi: Provinsi, Jiwa Terpapar, Kerugian Fisik, Kerugian Ekonomi (Sumber: Risiko Bencana Indonesia oleh BNPB)

## Variabel
Dipilih 13 variabel prediktor dan 2 variabel target. Variabel prediktor dikategorikan ke dalam 3 dimensi yaitu informasi gempa bumi, demografi, dan indikator sosial-ekonomi. Informasi gempa bumi mewakili bahaya, sedangkan indikator demografi dan sosial-ekonomi mewakili kerentanan. 

<img width="422" height="282" alt="image" src="https://github.com/user-attachments/assets/a9afb866-8cc0-4d0d-ac2b-e3e9533a19ac" />

Variabel Target didefinisikan berdasarkan persamaan berikut:

<img width="358" height="170" alt="image" src="https://github.com/user-attachments/assets/8f40e943-22e9-4e5c-ba04-9db6a31104fa" />

## Tahapan Penelitian
1. **Pengumpulan Data**: Dari badan pemerintah dan database internasional.
2. **Data Preprocessing**: Feature Engineering, Integrasi Data, Mengecek Missing Value & Duplikasi Data, Pembentukan Variabel Target
3. **Modelling**: Regresi Linear, Random Forest Regression, Gradient Boosting Regression
4. **Model Evaluation**: Adjusted R-squared, Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), Cross-Validation

## Hasil
### Exploratory Data Analysis
<img width="535" height="445" alt="image" src="https://github.com/user-attachments/assets/68e28dbb-571e-475d-81fd-ff26e9e1bcab" />

Lokasi geografis dan infrastruktur kesehatan memiliki pengaruh terhadap dampak ekonomi dan tingkat korban dari suatu kejadian.

<img width="444" height="274" alt="image" src="https://github.com/user-attachments/assets/a01b7e92-c7ea-411e-9c29-3717bd2a2a69" />

Mayoritas nilai dampak ekonomi terdistribusi di sekitar nilai 0 hingga 1000.

<img width="416" height="274" alt="image" src="https://github.com/user-attachments/assets/2eee31a9-1a11-4377-b1bb-d101666a625a" />

Sebagian besar nilai tingkat korban terdistribusi di sekitar nilai 1,0.

### Model Regresi Linear
<img width="416" height="185" alt="image" src="https://github.com/user-attachments/assets/3d994fe1-94ed-413d-bc1f-6ba214ab9d37" />

Keterangan:

- Y1: Dampak Ekonomi
- Y2: Tingkat Korban
- X1: Latitude
- X2: Longitude
- X3: Depth
- X4: Mag
- X5: Gap
- X6: Dmin
- X7: Rms
- X8: Kepadatan
- X9: Angka Ketergantungan
- X10: Angka Melek Huruf
- X11: Jumlah RS
- X12: Jumlah Tempat Tidur 
- X13: Rasio Tempat Tidur

<img width="350" height="180" alt="image" src="https://github.com/user-attachments/assets/d127a343-517a-4757-b220-f5a59e93cbe5" />

- Nilai Adjusted R2 sebesar 0,514 menunjukkan model 1 cukup mampu menjelaskan variasi pada dampak ekonomi, tetapi tidak terlalu kuat. 
- Nilai adjusted R2 sebesar 0,065 menunjukkan model 2 sangat lemah dalam menjelaskan variasi pada tingkat korban.

### Model Random Forest
<img width="397" height="184" alt="image" src="https://github.com/user-attachments/assets/907b62bd-5e44-4433-8a03-4e3fdcc6791c" />

Keterangan:

- Model 1: Dampak Ekonomi
- Model 2: Tingkat Korban

### Model Gradient Boosting
<img width="402" height="190" alt="image" src="https://github.com/user-attachments/assets/1f9f2408-6ec7-4c3d-8a09-ebc936cc1e67" />

Keterangan:

- Model 1: Dampak Ekonomi
- Model 2: Tingkat Korban

### Model Terbaik
- Dalam prediksi dampak ekonomi akibat gempa bumi, model gradient boosting memiliki kinerja yang lebih baik dibanding model regresi linear dan random forest, dengan nilai adjusted r-squared sebesar 0,924, nilai RMSE sebesar 276,160, dan nilai MAE sebesar 86,105.
- Dalam prediksi tingkat korban akibat gempa bumi, model gradient boosting memiliki kinerja yang lebih baik dibanding model regresi linear dan random forest, dengan nilai adjusted r-squared sebesar 0,990, nilai RMSE sebesar 0,009, dan nilai MAE sebesar 0,006.

Berikut adalah faktor-faktor yg paling berpengaruh terhadap tingkat korban dan dampak ekonomi akibat gempa bumi berdasarkan model gradient boosting:
- Dampak Ekonomi
  
  <img width="1377" height="701" alt="image" src="https://github.com/user-attachments/assets/6da5333a-eb04-4508-be32-9ee6e3a40617" />

  Lima faktor yang paling berpengaruh terhadap dampak ekonomi adalah kepadatan penduduk, rasio tempat tidur rumah sakit, longitude, latitude, dan angka ketergantungan (dependency ratio)

- Tingkat Korban

  <img width="1377" height="701" alt="image" src="https://github.com/user-attachments/assets/11892f84-cb8d-426c-a9a8-861d3ca63c6f" />

  Lima faktor yang paling berpengaruh terhadap tingkat korban, adalah jumlah rumah sakit, kepadatan penduduk, angka ketergantungan (dependency ratio), rasio tempat tidur rumah sakit, dan longitude.

### Rekomendasi
- Meningkatkan jumlah rumah sakit dan fasilitas kesehatan di daerah dengan kepadatan penduduk tinggi sehingga diharapkan dapat mengurangi tingkat korban.
- Perencanaan pembangunan infrastruktur dan perumahan di daerah rentan gempa bisa dilakukan dengan memperhatikan faktor-faktor yang memiliki pengaruh besar terhadap dampak ekonomi.
