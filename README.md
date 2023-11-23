# Capstone3_Bank_Marketing-Campaign

1. Business Problem Understanding
   Context
Deposito merupakan produk perbankan di mana seseorang menyetor sejumlah uang ke dalam rekening untuk jangka waktu tertentu dengan tingkat bunga yang tetap. Setelah jangka waktu tersebut berakhir, uang tersebut bersama dengan bunga dapat ditarik.
Sebagai kompensasinya, nasabah akan diberikan bunga tetap sesuai dengan nominal uang yang disetorkan.

Problem Statement
Proses kampanye penawaran deposit memakan waktu dan biaya, jika bank menargetkan semua nasabah tanpa melakukan penyaringan terlebih dahulu, maka akan ada pemborosan dari segi waktu dan biaya. Bank ingin meningkatkan efisiensi proses kampanye dengan menargetkan ke calon nasabah yang memiliki potensi untuk menaruh deposit.

Analytic Approach
Kita akan menganalisis data untuk menemukan pola yang membedakan kandidat nasabah yang akan menaruh deposit atau tidak.
Kemudian, dilanjutkan dengan membangun model klasifikasi yang akan membantu bank untuk dapat memprediksi probabilitas seorang kandidat nasabah akan/ingin menaruh deposit atau tidak.

Evaluation Metric
Type 1 error : False Positive  
Konsekuensi: membuang waktu dan biaya kampanye untuk nasabah yang tidak berpotensial menaruh deposit
Type 2 error : False Negative  
Konsekuensi: kehilangan kandidat nasabah potensial

2. Cost Benefit Analysis :
Cost Estimation
Kita asumsikan setiap nasabah ditelfon sebanyak 6 kali dengan biaya $4 untuk setiap panggilan
- total panggilan x biaya telfon
- = (Jumlah nasabah yang kita tawarkan deposit x biaya perpanggilan)
- = 1225 x 24 = $29.400


Profit estimation
Pendapatan - Biaya
= (Jumlah calon nasabah yang deposit x Profit dari deposit) - ( Jumlah calon nasabah yang kita tawarkan deposit x Biaya panggilan) 
= (669 x $47,5) - (1225 x $24) = $31,777.5 - $29,400 = $2,377.5

Maka keuntungannya sekitar $2,377.5

---------------------------------------------------------
Saat kita menggunakan machine learning, kita hanya menawarkan produk ke calon nasabah yang diprediksi akan term deposit saja.

Jumlah Nasabah untuk dasar perhitungan :
- Calon nasabah yang dihubungi adalah nasabah yang diprediksi  deposit = TP + FP = 515 + 243 = 758 orang
- Calon nasabah yang di prediksi dan actualnya deposit = TP = 515

Profit Estimation
Pendapatan - Biaya
= (Calon nasabah yang di prediksi dan actualnya deposit x Profit deposit) - ( Jumlah calon nasabah yang diprediksi deposit x Biaya panggilan) 
= (515 x $47,5) - (758 x $24) = $24,462.5 - $18,192 = $6,270.5
Maka keuntungannya sekitar $6,270.5

------------------------------------------------------
Peningkatan Profit = profit setelah machine Learning - profit sebelum mengaplikasi machine Learning = $6,270.5 - $2,377.5 = $3,893

Persentase kenaikan = (nilai akhir - nilai awal) / nilai awal x 100%
= $3,893 / $2,377.5 x 100% = 16.37%

Berdasarkan test set, model kita dapat meningkatkan keuntungan hingga 16.37% dalam setahun.


3. CONCLUSION & RECOMMENDATION

Conclusion:
- Model klasifikasi terbaik yang diperoleh untuk memprediksi calon nasabah yang deposit atau tidak pada dataset ini adalah Gradient Boost dengan metriks f1_score sebesar 0.72
- Berdasarkan hasil analisis, nasabah yang cenderung melakukan deposit adalah nasabah yang bekerja sebagai management, nasabah yang tidak mempunyai pinjaman perumahan atau pinjaman pribadi, dan nasabah yang dihubungi melalui seluler.
- Tanpa pemodelan, Bank akan melakukan kampanye terhadap 1225 kandidat nasabah yang mana tidak semuanya adalah kandidat nasabah potensial untuk menaruh deposit. Sedangkan dengan pemodelan, Bank dapat memfokuskan target kampanye menjadi hanya 758 kandidat nasabah potensial saja, yang mana ini akan meningkatkan efisiensi bagi bank baik dari segi finansial maupun waktu.

Recomendation:
- Menambahkan lebih banyak fitur yang kemungkinan bisa meningkatkan score model seperti status pernikahan, jumlah anggota keluarga, income, dan sebagainya.
- Melakukan improvisasi pada model seperti melakukan hyperparameter tuning kembali, atau membuat model dengan algoritma yang lain.
- Menghindari pengisian data dengan nilai 'unknown' atau 'other' karena menyebabkan score model menjadi turun.
- Karena fitur poutcome mengandung nilai 'unknown' dan 'other' yang sangat banyak, fitur tersebut kita hilangkan pada pemodelan ini. Apabila fitur tersebut akan digunakan pada proses modeling selanjutnya, nilai harus diisi dengan 'Success' atau 'Failure' 
- Pada dataset, terlihat bahwa marketing campaign masih dilakukan secara tradisional yaitu melalui telemarketing. Seiring dengan perkembangan zaman, ada baiknya kita bisa mulai meningkatkan kegiatan marketing campaign kita melalui internet (digital marketing) supaya bisa menjangkau calon nasabah secara lebih luas dan lebih efisien.
- Kita bisa memberikan bunga yang lebih kompetitif dibandingkan kompetitor sehingga bisa menarik calon nasabah untuk melakukan term deposit di bank kita.

