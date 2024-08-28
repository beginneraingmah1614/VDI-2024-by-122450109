## Pengantar: Artikel ini mengulas teknik-teknik yang membuat visualisasi data lebih efisien dan efektif.
1.	Spesifikasi Visualisasi: Menentukan bagaimana pengguna dapat menyatakan kebutuhan mereka untuk menghasilkan visualisasi.
2.	Pendekatan Efisien untuk Visualisasi Data: Memproses data dan spesifikasi visualisasi dengan tujuan utama menghasilkan visualisasi yang efisien dan dapat diakses dengan kecepatan interaktif.
3.	Rekomendasi Visualisasi Data: Melengkapi spesifikasi yang belum lengkap atau menemukan visualisasi yang lebih menarik berdasarkan visualisasi referensi.

## A. Alur Visualisasi Data:
1.	Impor Data: Mengambil data yang diperlukan dari sumber data yang diinginkan.
2.	Persiapan Data: Menyiapkan data yang diimpor untuk visualisasi, misalnya dengan normalisasi nilai, koreksi entri yang salah, dan interpolasi nilai yang hilang.
3.	Manipulasi Data: Memilih data yang akan divisualisasikan (juga dikenal sebagai proses penyaringan dalam komunitas visualisasi) dan mungkin dilakukan operasi lain seperti penggabungan dan pengelompokan.
4.	Pemetaan Data: Memetakan data yang diperoleh dari proses di atas ke bentuk geometris (misalnya titik dan garis), beserta atribut-atributnya (seperti warna, posisi, dan ukuran).
5.	Rendering: Mengubah data geometris di atas menjadi representasi visual.

## #Berdasarkan alur di atas, ada tiga arah yang membuat visualisasi data lebih efisien dan efektif, terutama relevan bagi peneliti basis data:
1.	Spesifikasi Visualisasi: Spesifikasi visualisasi memberikan berbagai cara bagi pengguna untuk menyatakan apa yang mereka inginkan. Studi mengenai spesifikasi visualisasi telah banyak dilakukan oleh komunitas visualisasi [1,2,14–16] dan komunitas basis data [3,17–19]. Kami memasukkannya dalam survei ini dengan dua alasan: 
o	Kesempurnaan Diri: Penting bagi pembaca untuk mengetahui cara menghasilkan visualisasi data.
o	Perspektif Desain Bahasa: Ini terutama berkaitan dengan komponen “Pemetaan” dalam alur, dengan menentukan bagaimana menghubungkan informasi yang berbeda ke elemen visual.
2.	Pendekatan Efisien untuk Visualisasi Data: Proses pembuatan visualisasi data harus efisien dan dapat diakses oleh pengguna, terutama untuk komponen “Manipulasi Data” dan “Pemetaan”.
3.	Rekomendasi Visualisasi Data: Menentukan visualisasi secara tepat sulit, bahkan bagi para ahli, karena pemahaman tentang data apa yang harus divisualisasikan, cerita apa yang ingin disampaikan, dan bagaimana cara visualisasi adalah proses uji coba.

## B. Spesifikasi Visualisasi:
1.	Spesifikasi Visualisasi Data: Secara umum, bahasa visualisasi data terdiri dari tiga bagian: data, tanda (atau petunjuk visual), dan pemetaan antara keduanya. 
o	Data: Catatan data yang perlu divisualisasikan.
o	Transformasi: Operasi seperti pengelompokan, pengelompokan interval, penyaringan, dan pengurutan digunakan untuk mengubah catatan data yang telah ditentukan.

## B.1.2. Tanda (atau Petunjuk Visual):
•	Jenis: Representasi visual untuk catatan data, seperti batang, garis, atau titik.
•	Ukuran: Lebar dan tinggi visualisasi.
•	Legenda: Informasi legenda.
•	Lain-lain: Properti lain, seperti lebar dan warna batang.
## B.1.3. Pemetaan: Pemetaan menghubungkan data ke tanda-tanda visual yang sesuai.

## 2.2 Kategorisasi Bahasa Visualisasi Data:
•	Bahasa Tingkat Rendah: Bahasa yang lebih rinci.
•	Bahasa Tingkat Tinggi: Bahasa yang lebih abstrak. Perlu dicatat bahwa sebagian besar bahasa tingkat rendah dan tinggi yang tercantum dalam survei adalah bahasa deklaratif (di mana pengguna hanya perlu menyatakan “apa” yang mereka inginkan), kecuali Prefuse dan Flare. Prefuse dan Flare adalah bahasa prosedural karena mereka adalah perpustakaan visualisasi berbasis Java, dan pengguna harus menginisialisasi panel, menambahkan elemen visual, dll.

## 2.3 Operasi Visual Berbasis Antarmuka Pengguna (GUI) 
Dibandingkan dengan menggunakan bahasa visualisasi deklaratif seperti yang telah dibahas, cara yang lebih ramah pengguna untuk memberikan spesifikasi adalah dengan mengikuti “prinsip manipulasi langsung”, sebuah konsep yang banyak digunakan dalam aspek interaksi manusia-komputer.
Visualisasi Data Interaktif: Rasional di balik visualisasi data interaktif adalah bahwa dalam banyak kasus, visualisasi data adalah proses eksplorasi, di mana pengguna perlu terus memperbaiki spesifikasi (misalnya menambah/menghapus/mengubah atribut, mengganti jenis grafik) dari visualisasi yang sedang dieksplorasi hingga mendapatkan visualisasi yang diinginkan dalam proses eksplorasi.

## 2.4 Spesifikasi yang Kurang Terspesifikasi
Secara umum, untuk spesifikasi yang kurang terspesifikasi, pengguna hanya memberikan beberapa “petunjuk”, dan tugas sistem visualisasi adalah mengartikan masukan yang kurang terspesifikasi tersebut dengan cara yang berbeda-beda.
•	Jenis pertama petunjuk adalah “berbasis referensi”, di mana pengguna memberikan visualisasi referensi sebagai dasar, dan sistem menyarankan visualisasi berdasarkan referensi tersebut.
•	Jenis kedua petunjuk adalah “berbasis kata kunci”, seperti pada gaya pencarian Google. Alat serupa yang mendukung masukan berbasis kata kunci, yang disebut “Ask Data”, baru-baru ini dirilis oleh Tableau, yang memungkinkan pengguna mendapatkan jawaban tanpa perlu mengetahui struktur data secara detail, misalnya “apa rata-rata harga berdasarkan variasi”.
•	Jenis ketiga petunjuk adalah “berbasis bahasa alami”, yang mempertimbangkan konteks masukan pengguna dan status sistem dalam siklus eksplorasi data, bukan hanya satu kali seperti pada petunjuk “berbasis kata kunci”.

## 3 Pendekatan Efisien untuk Visualisasi Data
## 3.1 Visualisasi Data yang Akurat:
•	Terjemahan Kueri: Cara alami untuk memanfaatkan banyak sistem (DBMS) yang sudah matang adalah dengan menerjemahkan kueri visualisasi menjadi kueri yang diterima oleh sistem-sistem tersebut.
•	Integrasi Sistem Visualisasi dengan DBMS: Meskipun penggunaan terjemahan kueri adalah cara yang alami, ada beberapa kekurangan. Salah satu masalah utamanya adalah banyak fungsionalitas yang diulang, menghasilkan teknik optimisasi yang tidak terpadu dengan asumsi dan kinerja yang berbeda di sisi server (yaitu, sisi basis data) dan klien (yaitu, sisi visualisasi), sehingga mengacaukan pengembang dalam memilih teknik optimisasi yang sesuai.

Penyimpanan Berbasis Kolom: Dalam manajemen data, faktor kinerja kunci adalah tata letak data, misalnya tata letak berbasis baris dan berbasis kolom, yang dapat memiliki perbedaan kinerja yang signifikan untuk aplikasi OLAP. Dalam konteks visualisasi data, pengguna biasanya hanya tertarik pada beberapa kolom. Secara alami, penyimpanan berbasis kolom dapat mencapai kinerja yang lebih baik dibandingkan dengan penyimpanan berbasis baris. 
Indeks: Indeks secara luas digunakan untuk meningkatkan kinerja pencarian dengan mengurangi jumlah catatan/baris dalam tabel yang perlu diperiksa. 
Komputasi Paralel: Komputasi paralel juga telah banyak digunakan untuk pemrosesan kueri dalam sistem visualisasi data. Arsitektur ini mempertahankan utas aplikasi utama untuk menangkap permintaan interaksi pengguna dan beberapa utas visualisasi untuk setiap visualisasi guna memproses visualisasi dari utas tersebut. Selain itu, apakah utas utama dan utas visualisasi bersifat asinkron atau sinkron tergantung pada jenis permintaan interaksi pengguna. 
Prediksi dan Prefetching: Satu langkah penting dalam visualisasi data adalah eksplorasi data—pengguna terus-menerus menjelajahi visualisasi yang menarik bagi mereka untuk mendapatkan gambaran tentang apa yang akan divisualisasikan. Seringkali, visualisasi yang sedang dieksplorasi saat ini terinspirasi dari visualisasi sebelumnya. Dengan kata lain, pengguna dapat mendapatkan visualisasi berikutnya dengan mengubah parameter visualisasi saat ini atau melakukan zoom in/out untuk mendapatkan informasi lebih rinci/keseluruhan, dan sebagainya. 
Dikategorikan teknologi prefetch dan prediksi menjadi dua jenis, berdasarkan: visualisasi yang sedang dieksplorasi saat ini atau data historis. Optimisasi Mesin Data (TDE): TDE mengoptimalkan mesin data terutama dari perspektif berikut:
1.	Penyimpanan Berbasis Kolom dan Kompresi
2.	Pengurutan Operator
3.	Pengurangan Kardinalitas

## Kesimpulan
Visualisasi data adalah bidang yang berkembang pesat dengan banyak hasil penelitian baru dan sistem inovatif yang dikembangkan belakangan ini. Peneliti dan praktisi dari berbagai bidang telah berkontribusi pada kesuksesan luar biasa visualisasi data, yang didorong oleh hampir semua domain dan aplikasi. Artikel ini terutama mengulas karya-karya visualisasi data terkini dari perspektif manajemen data. Khususnya, kami telah secara komprehensif menggambarkan karya-karya dalam spesifikasi visualisasi, metode efisien untuk visualisasi data, dan rekomendasi visualisasi. Seperti yang disebutkan sebelumnya, sebagian besar sistem visualisasi data komersial baik dalam hal kemudahan penggunaan spesifikasi visualisasi.
