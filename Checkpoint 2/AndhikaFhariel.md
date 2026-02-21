<img width="1031" height="576" alt="image" src="https://github.com/user-attachments/assets/d49369f8-889c-4e31-95e3-d95407e8d9fe" />


Struktur Data (Informasi Lanjutan)
1. ProductID: Jumlah baris: 9000 Tipe data: int64 Deskripsi: ID Unik Produk
2. ProductCategory: Jumlah baris: 9000 Tipe data: object Deskripsi: Kategori Produk
3. ProductBrand: Jumlah baris: 9000 Tipe data: object Deskripsi: Merek Produk
4. ProductPrice: Jumlah baris: 9000 Tipe data: float64 Deskripsi: Harga Produk
5. CustomerAge: Jumlah baris: 9000 Tipe data: int64 Deskripsi: Usia Pelanggan
6. CustomerGender: Jumlah baris: 9000 Tipe data: int64 Deskripsi: Jenis Kelamin Pelanggan
7. PurchaseFrequency: Jumlah baris: 9000 Tipe data: int64 Deskripsi: Frekuensi Pembelian
8. CustomerSatisfaction: Jumlah baris: 9000 Tipe data: int64 Deskripsi: Tingkat Kepuasan Pelanggan
9. PurchaseIntent: Jumlah baris: 9000 Tipe data: int64 Deskripsi: Niat Membeli Pelanggan (Target)

Informasi Statistik Deskriptif
1. Count (Kelengkapan Data)
Berdasarkan data, total baris transaksi adalah 9.000. Maka dapat disimpulkan:

Tidak ada data yang hilang pada setiap kolom (seluruh kolom berisi 9.000 data lengkap).

Kesimpulan: Seluruh kolom tidak mengandung missing values, sehingga dataset sudah lengkap dan siap digunakan untuk analisis lebih lanjut.

---

2. Mean vs Median (Distribusi Data)
Kolom ProductPrice

Mean = 1527,43

Median (50%) = 1513,02

Nilai rata-rata sangat mendekati median, menunjukkan distribusi harga produk yang relatif simetris.

Kolom CustomerAge

Mean = 43,35

Median (50%) = 43,00

Rata-rata yang hampir sama dengan median menandakan distribusi usia pelanggan cukup merata tanpa perbedaan ekstrem.

Kolom PurchaseFrequency

Mean = 10,05

Median (50%) = 10,00

Perbedaan yang sangat tipis menunjukkan distribusi frekuensi pembelian yang stabil dan seimbang.

Kesimpulan: Secara keseluruhan, data numerik pada dataset ini cenderung berdistribusi normal/simetris dan tidak menunjukkan skewness yang signifikan.

3. Min dan Max (Validasi Logika)
ProductPrice

Min = 100,38

Max = 2999,85

CustomerAge

Min = 18

Max = 69

CustomerSatisfaction

Min = 1

Max = 5

Kesimpulan:

Rentang ProductPrice (100 hingga 2.999) menunjukkan variasi harga yang luas, mencakup produk ekonomis hingga premium.

Rentang Usia (18–69 tahun) sangat logis untuk target konsumen dewasa.

Nilai Kepuasan berada dalam skala normal 1–5, sehingga tidak ada indikasi kesalahan input data.

4. Standar Deviasi (std) - Variabilitas Data
ProductPrice

Mean = 1527,43

Std = 829,90

PurchaseFrequency

Mean = 10,05

Std = 5,46

Kesimpulan:

Pada kolom ProductPrice, nilai standar deviasi yang besar menunjukkan variasi harga produk yang cukup lebar di dalam katalog.

Pada kolom PurchaseFrequency, standar deviasi sebesar 5,46 mengindikasikan adanya perbedaan yang cukup kontras antara pelanggan jarang (skala rendah) dan pelanggan setia (skala tinggi).

Inconsistent Values
Pada tahap ini, kita perlu mengecek kekonsistenan data, contoh nya dalam penulisan. Hal ini dilakukan agar data tidak terduplikat dengan baris yang sebenarnya sama akan tetapi bisa terduplikat karena tidak konsisten.

Setelah dicek, Saya tidak menemukan data yang tidak konsisten, yang menandakan data ini bersih dari Inconsistent Values,

Missing Values
Pada tahap ini, kita akan melihat seberapa banyak data yang hilang pada seluruh kolom. Dan terlihat bahwa:

Tidak terdapat kolom yang memiliki missing values (0%).

Semua data tidak yang hilang yang menandakan data bersih dari Missing Values.

Duplicated Values
Pada tahap ini, kita akan mengecek duplikasi pada dataset. Hal ini dilakukan agar dataset memiliki insight dan hasil yang bersih.

Terlihat pada dataset ini tidak ada duplikasi. Maka hal ini tidak perlu ditangani, namun jika ingin menangani anda dapat mengetikkan

df = df.drop_duplicates()

Outliers Values
Pada tahap ini, kita akan melihat nilai ekstrem (outliers) pada kolom yang bertipe data numerik. Hal ini dilakukan agar mendapatkan insight yang akurat sehingga dapat memperkuat analisis dan model yang akan kita bangun nantinya.

Setelah di cek dat ini bersih dari Outliers, yang menandakan kita tidak perlu membersihkan data ini dari Outliers.

Comparison(Perbandingan)
Aktivitas: Membandingkan jumlah barang yang laku sesuai umur.

Tujuan: Mengidentifikasi kategori produk mana yang memberikan kontribusi pendapatan terbesar dan membandingkan performa antar kategori secara langsung.

Insight

1. Dominasi Samsung: Samsung memimpin dengan akumulasi umur pelanggan tertinggi (mendekati 80.000). Ini menunjukkan bahwa basis pelanggan Samsung kemungkinan besar adalah yang paling besar atau terdiri dari pelanggan yang sudah setia dalam waktu lama.
2. Distribusi yang Merata: Tidak ada perbedaan yang sangat jomplang antar brand. Kelima kategori (Samsung, HP, Sony, Other Brands, dan Apple) semuanya berada di kisaran akumulasi umur 75.000 hingga 80.000.
3. Apple di Posisi Terendah: Meskipun Apple adalah brand premium, secara akumulasi umur pelanggan dalam dataset ini, mereka berada di posisi paling bawah. Ini bisa berarti jumlah penggunanya lebih sedikit dibanding yang lain, atau banyak pengguna baru (umur berlangganan masih pendek).
4. Potensi "Other Brands": Kategori "Other Brands" memiliki akumulasi yang hampir menyamai brand besar seperti Sony. Ini menandakan pasar produk alternatif cukup kuat.

Action

1. Samsung

a. Loyalty Program: Karena akumulasi umurnya paling tinggi, fokuslah pada program retensi. Berikan apresiasi kepada pelanggan lama agar mereka tidak pindah ke kompetitor.

b. Upselling: Manfaatkan basis pelanggan yang besar ini untuk menawarkan produk flagship terbaru.

2. Apple

a. Acquisition Campaign: Karena akumulasinya paling rendah, Apple perlu kampanye pemasaran yang lebih agresif untuk menarik pengguna baru atau meningkatkan penetrasi pasar.

b. Analisis Churn: Periksa apakah angka yang rendah ini disebabkan oleh pelanggan yang cepat berhenti menggunakan produk (churn) atau memang volume penjualannya yang lebih kecil.

3. Brand Lain ( HP & Sony )

a. Competitive Positioning: Karena posisinya di tengah, mereka harus mencari nilai unik (USP) agar tidak tergerus oleh dominasi Samsung atau daya tarik Apple.

4. Perbaikan Analisis Data

a. Gunakan Rata-rata (Mean): Total akumulasi umur bisa bias jika jumlah pelanggan antar brand berbeda jauh. Disarankan untuk membuat grafik tambahan menggunakan rata-rata umur pelanggan (.mean()) untuk melihat profil demografi usia pengguna sebenarnya di tiap brand.

Visualisasi: Bar Chart (Grafik Batang).

Composition(Komposisi)
Aktivitas :Melihat proporsi atau persentase jenis produk dan umur customer.

Tujuan: Mengetahui kategori produk mana yang paling mendominasi total pembelian pelanggan secara keseluruhan.

Visualisasi: Pie Chart (Grafik Lingkaran).
Insight

1. Distribusi Pasar yang Sangat Merata: Ketiga kategori produk (Smartphones, Smart Watches, dan Laptops) memiliki proporsi yang hampir identik dalam hal kontribusi total umur pelanggan.

Smartphones: 33.5%

Smart Watches: 33.5%

Laptops: 33.0%

2. Keseimbangan Demografis: Total akumulasi umur pelanggan pada ketiga kategori ini sangat seimbang. Ini menunjukkan bahwa basis pelanggan Anda tidak didominasi oleh satu kategori produk saja; ketiga kategori ini memiliki daya tarik yang sama kuatnya dalam menyerap segmen usia pelanggan.

3. Potensi "Cross-Selling" Tinggi: Karena proporsinya hampir sama besar ($1/3$ untuk masing-masing), kemungkinan besar pelanggan yang membeli Laptop juga memiliki ketertarikan yang setara terhadap Smartphone atau Smart Watch, atau sebaliknya.

Action

1. Bundling Strategis: Mengingat proporsinya hampir sama, Anda dapat membuat paket "Product Ecosystem". Misalnya, bundel Smart Watch dengan Smartphone karena keduanya memiliki kontribusi data pelanggan yang identik (33.5%).

2. Personalisasi Marketing berdasarkan Usia: Karena data yang diolah adalah CustomerAge, lakukan analisis lebih lanjut (seperti Mean Age atau Age Grouping). Jika rata-rata usia di kategori Laptop lebih tinggi, sesuaikan gaya bahasa iklan Anda menjadi lebih profesional, sementara untuk Smart Watches bisa lebih mengarah ke gaya hidup aktif.

3. Loyalty Program Terintegrasi: Jangan membatasi program loyalitas hanya pada satu kategori. Buatlah poin yang dapat dikumpulkan dan digunakan di ketiga kategori ini untuk menjaga keseimbangan pasar yang sudah sehat ini.

4. Uji Penetrasi Pasar Laptop: Kategori Laptop sedikit tertinggal (selisih 0.5%). Anda bisa memberikan promo kecil atau cicilan khusus untuk kategori ini agar kontribusinya setara dengan dua kategori lainnya.

Distribution(Distribusi)
Aktivitas: Menganalisis penyebaran umur customer..

Tujuan: Melihat apakah mayoritas transaksi bernilai kecil atau besar, serta mendeteksi adanya kecondongan (skewness) dalam data pembelian pelanggan.

Visualisasi: Histogram.

Insight
1. Distribusi Seragam (Uniform Distribution): Grafik menunjukkan bahwa jumlah pelanggan tersebar cukup merata di berbagai rentang usia, mulai dari sekitar 18 hingga 70 tahun. Tidak ada satu kelompok umur yang mendominasi secara ekstrem.
2. Kehadiran Semua Kelompok Usia: Bisnis Anda memiliki daya tarik yang luas, mencakup Gen Z, Millennials, Gen X, hingga Baby Boomers. Ini menandakan produk atau layanan Anda bersifat umum (general).
3. Stabilitas Volume: Setiap bar (bin) berada di kisaran frekuensi 300 hingga 550. Meskipun ada fluktuasi kecil (misalnya sedikit penurunan di usia 30-an awal dan pertengahan 50-an), secara keseluruhan basis pelanggan Anda sangat stabil lintas generasi.
4. KDE (Kernel Density Estimate): Garis biru yang relatif datar di bagian atas mengonfirmasi bahwa kepadatan populasi pelanggan tidak memiliki "puncak" tunggal yang tajam.

Action
1. Segmentasi Pemasaran

a. Usia Muda (18-30): Fokus pada platform media sosial (TikTok/Instagram) dengan gaya bahasa yang tren dan visual yang dinamis.

b. Usia Senior (50-70): Gunakan saluran komunikasi yang lebih tradisional atau email marketing dengan fokus pada kenyamanan, kualitas, dan layanan purna jual.

2. Analisis Nilai Pelanggan

a. Lakukan cross-check data: "Apakah pelanggan umur 20-an belanja lebih sering, atau pelanggan umur 50-an yang belanja dalam jumlah besar (ticket size tinggi)?

b. Fokuskan anggaran iklan pada segmen yang memiliki Customer Lifetime Value (CLV) tertinggi.

3. Penyesuaian Produk/Layanan

a. Pastikan antarmuka (UI/UX) aplikasi atau toko fisik Anda ramah untuk semua umur (misalnya: ukuran font yang jelas untuk lansia, namun tetap modern untuk anak muda).

4. Strategi Retensi

a. Karena distribusi umur merata, buatlah program loyalitas yang fleksibel. Misalnya, reward yang bisa dipilih (voucher belanja untuk yang muda, atau layanan prioritas/diskon kesehatan untuk yang senior).

Relationship(Hubungan)

Aktivitas : Menganalisis korelasi antara nilai penjualan (Sales) dengan keuntungan (Profit).

Tujuan: Mengetahui apakah pembelian dengan nominal yang lebih tinggi cenderung mendapatkan rating yang lebih baik, serta melihat kekuatan hubungan antara nilai transaksi dan kepuasan pelanggan.

Visualisasi: Heatmap

Insight
1. Nilai Korelasi Sangat Lemah (0.01): Angka 0.01 menunjukkan bahwa hampir tidak ada hubungan linear antara umur pelanggan dengan seberapa sering mereka berbelanja. Secara statistik, nilai ini mendekati nol.
2. Kemandirian Variabel: Ini berarti kamu tidak bisa memprediksi frekuensi belanja seseorang hanya dengan melihat usianya. Pelanggan muda (misal: Gen Z) dan pelanggan tua (misal: Boomers) memiliki pola frekuensi belanja yang serupa atau sangat acak satu sama lain.
3. Distribusi Merata: Produk atau layanan kamu nampaknya dibutuhkan oleh semua rentang usia secara merata, atau faktor yang mendorong orang untuk belanja berulang kali bukanlah faktor demografis usia, melainkan faktor lain (seperti harga, kualitas, atau kebutuhan mendesak).

Action
1. Berhenti Melakukan Segmentasi Berbasis Usia untuk Loyalitas: Jangan membuat program loyalitas yang hanya menargetkan umur tertentu (misal: "Diskon khusus lansia agar rajin belanja"), karena data menunjukkan usia tidak menjamin loyalitas.
2. Cari Variabel Penggerak Lain: Lakukan analisis korelasi ulang dengan variabel lain yang mungkin lebih berpengaruh terhadap frekuensi pembelian, seperti:

Income (Pendapatan)

Distance to Store (Jarak ke toko)

Discounts Applied (Penggunaan promo)

Product Category (Kategori produk yang dibeli)
3. Strategi Pemasaran Inklusif: Karena frekuensi belanja merata di segala usia, gunakan pesan kampanye yang bersifat universal daripada pesan yang terlalu spesifik pada satu kelompok umur.
4. Fokus pada RFM Analysis: Daripada melihat Age, sebaiknya gunakan analisis Recency, Frequency, Monetary (RFM) untuk mengelompokkan pelanggan berdasarkan perilaku belanja nyata mereka.


