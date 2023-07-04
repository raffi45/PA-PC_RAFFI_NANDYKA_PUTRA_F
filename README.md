
# DETEKSI PLAT NOMER KENDERAAN

Deskripsi Program:
Sistem "Deteksi Plat Nomor Kendaraan" adalah sebuah aplikasi yang saya rancang untuk membantu pengguna dalam mengenali dan mendeteksi plat nomor kendaraan pada gambar atau video. Aplikasi ini menggunakan teknologi pengolahan citra dan kecerdasan buatan untuk mengidentifikasi serta mengekstrak plat nomor kendaraan dari gambar yang diberikan.
## - 
## TEORI PENGOLAHAN CITRA

1. Preprocessing Citra

Preprocessing citra adalah tahap dalam pengolahan citra di mana dilakukan serangkaian langkah pra-pemrosesan untuk mempersiapkan citra sebelum dilakukan analisis atau pemrosesan lebih lanjut. Tujuan dari preprocessing citra adalah meningkatkan kualitas citra, menghilangkan noise atau gangguan, serta menyesuaikan citra agar lebih sesuai dengan tujuan yang diinginkan, seperti deteksi plat nomor kendaraan.

langkah yang ilakukan dalam preprocessing citra antara lain:
- Pemangkasan atau Penyesuaian Ukuran (Cropping atau Resizing): Kadang-kadang, dilakukan pemangkasan citra untuk memfokuskan pada area yang relevan, seperti plat nomor kendaraan. Selain itu, penyesuaian ukuran juga dapat dilakukan untuk memastikan ukuran citra konsisten dalam proses analisis.
- Normalisasi Citra: Normalisasi citra digunakan untuk mengubah skala intensitas piksel agar lebih konsisten. Hal ini dapat membantu dalam memastikan citra memiliki rentang nilai piksel yang optimal untuk analisis. Misalnya, normalisasi dapat dilakukan untuk mengubah rentang intensitas piksel menjadi 0 hingga 255.

Preprocessing citra penting dalam mempersiapkan citra sebelum menjalankan algoritma deteksi plat nomor atau tahap analisis lanjutan. Dengan melakukan langkah-langkah pra-pemrosesan yang sesuai, kualitas citra dapat ditingkatkan, gangguan dapat dikurangi, dan hasil analisis lebih akurat dan andal.

2. Segmentasi Citra

Segmentasi citra adalah proses pemisahan atau pengelompokan piksel-piksel dalam citra ke dalam kelompok-kelompok yang homogen berdasarkan atribut-atribut tertentu. Tujuannya adalah untuk memisahkan objek atau bagian yang menarik dalam citra dari latar belakang atau objek lain yang tidak diinginkan. Segmentasi citra merupakan tahap awal dalam analisis citra dan merupakan dasar penting dalam banyak aplikasi pengolahan citra, termasuk deteksi plat nomor kendaraan.

Ada beberapa metode yang digunakan dalam segmentasi citra, di antaranya:

- Metode Thresholding: Metode ini membagi piksel-piksel dalam citra menjadi dua kelompok berdasarkan ambang batas (threshold) yang ditentukan. Piksel yang memiliki intensitas di atas atau di bawah ambang batas akan diatribusikan ke kelompok tertentu. Thresholding sederhana sering digunakan untuk memisahkan objek dengan latar belakang yang kontras, misalnya dalam segmentasi plat nomor yang memiliki perbedaan intensitas yang cukup jelas dengan latar belakang.
- Metode Segmentasi Berbasis Wilayah (Region-based Segmentation): Metode ini membagi citra menjadi kelompok wilayah berdasarkan atribut-atribut seperti warna, tekstur, atau ukuran. Wilayah-wilayah tersebut kemudian dapat dianggap sebagai objek atau bagian yang terpisah dalam citra. Metode yang umum digunakan dalam segmentasi berbasis wilayah adalah algoritma pertumbuhan wilayah (region growing) dan pemecahan wilayah (region splitting).

- Metode Deteksi Tepi (Edge Detection): Metode ini mengidentifikasi tepi atau perubahan tajam dalam intensitas piksel untuk memisahkan objek dari latar belakang. Algoritma deteksi tepi seperti Sobel, Canny, atau Laplacian of Gaussian (LoG) sering digunakan untuk menemukan kontur atau tepi objek dalam citra.

- Metode Segmentasi Berbasis Perolehan Warna (Color-based Segmentation): Metode ini mengelompokkan piksel-piksel dalam citra berdasarkan informasi warna yang terkandung dalam citra. Dalam segmentasi plat nomor kendaraan, misalnya, metode ini dapat digunakan untuk memisahkan plat nomor yang umumnya memiliki warna dan kecerahan yang berbeda dengan latar belakang.



3. Contour 

kontur merujuk pada garis atau kurva yang menggambarkan tepi atau batas dari objek yang terdapat dalam citra. Kontur dapat digunakan untuk mengidentifikasi dan memisahkan objek dari latar belakang, serta untuk menganalisis bentuk, ukuran, dan properti geometris objek dalam citra.

adapun penerapan contour pada program ini untuk tujuan :
 -  mengidentifikasi dan memfilter kontur yang memiliki potensi sebagai wilayah plat nomor kendaraan dalam citra.Tujuan akhirnya adalah untuk menghasilkan daftar kandidat plat nomor yang berpotensi di dalam variabel candidate_plates. 

4. transformasi perspektif

digunakan untuk memperbaiki perspektif atau sudut pandang dari plat nomor kendaraan dalam citra. Tujuan utama dari transformasi perspektif adalah untuk mengubah plat nomor dari tampilan miring atau terdistorsi menjadi tampilan lurus dan rata.

Tujuan transformasi perspektif dalam pengolahan deteksi plat nomor:
- Perbaikan Perspektif: Transformasi perspektif digunakan untuk memperbaiki perspektif dari plat nomor dalam citra. Kadang-kadang, plat nomor kendaraan dapat terlihat miring, terdistorsi, atau diambil dari sudut pandang yang tidak ideal. Transformasi perspektif membantu untuk mengoreksi kesalahan perspektif ini dan mengembalikan plat nomor ke tampilan yang sejajar dan lurus.

- Fokus pada Plat Nomor: Dengan melakukan transformasi perspektif, plat nomor dapat diperbesar dan diubah sehingga menjadi objek utama dalam citra. Ini memungkinkan pemrosesan dan analisis selanjutnya pada plat nomor menjadi lebih mudah dan akurat, seperti pengenalan karakter (OCR) atau verifikasi plat nomor.

- Peningkatan Akurasi Deteksi: Transformasi perspektif dapat membantu meningkatkan akurasi deteksi plat nomor. Dengan mengubah sudut pandang atau perspektif plat nomor menjadi tampilan yang lebih lurus dan rata, fitur-fitur plat nomor yang penting menjadi lebih jelas dan terdefinisi dengan baik. Hal ini dapat memudahkan algoritma deteksi plat nomor untuk mengenali dan memisahkan plat nomor dari latar belakang atau objek lain dalam citra.

- Normalisasi Gambar Plat Nomor: Melalui transformasi perspektif, gambar plat nomor dapat dinormalisasi secara geometris. Hal ini berarti ukuran, proporsi, dan orientasi plat nomor dapat diatur menjadi standar atau seragam. Normalisasi ini membantu dalam memperbaiki perbedaan skala, rotasi, atau deformasi pada plat nomor antar citra. Dengan normalisasi yang konsisten, proses pengenalan karakter selanjutnya dapat lebih konsisten dan akurat.



## Screenshots

![App Screenshot](../)

