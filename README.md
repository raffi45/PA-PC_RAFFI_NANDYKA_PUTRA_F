
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



## TAHAPAN PEMBUATAN PROJEK
1. Menentukan citra yang akan dideteksi
   menantukan gambar yang akan di olah dalam format digital dan bisa dibaca dalam program nantinya
2. Menentukan library apa saja yang akan di gunakan
   - cv2: Library utama untuk pengolahan gambar menggunakan OpenCV.
   - numpy (diimport sebagai np): Library untuk operasi matematika dan array multidimensi.
   - matplotlib.pyplot (diimport sebagai plt): Library untuk visualisasi gambar.
3. Melakukan pra-pemrosesan citra
   - Mengubah gambar menjadi citra skala abu-abu (grayscale) menggunakan cv2.cvtColor().
   - Menerapkan operasi filter (seperti Gaussian blur atau median blur) untuk mengurangi noise pada citra.
   - Melakukan segmentasi untuk memisahkan area plat nomor dari latar belakang.
   - Menyesuaikan kontras dan kecerahan citra agar informasi plat nomor lebih jelas dan mudah dideteksi.
 4. Deteksi plat nomor
    - Menggunakan teknik deteksi tepi (seperti Canny edge detection) untuk menemukan tepi kontur pada citra.
    - Menerapkan teknik segmentasi atau pendeteksian objek untuk menemukan dan memisahkan kontur yang berpotensi sebagai plat nomor kendaraan.
    - Melakukan pemfilteran dan seleksi kontur berdasarkan ukuran dan rasio aspek untuk memilih kontur yang paling mirip dengan bentuk plat nomor.
 5. Visualisasi dan output
    - Menampilkan gambar asli dengan kontur atau bounding box yang mengelilingi plat nomor.
    - Menampilkan hasil ekstraksi karakter pada plat nomor.
    - Menyimpan hasil deteksi dan ekstraksi karakter dalam bentuk output yang sesuai (binery,edges image).
   
## GAMBAR 
![image.JPEG]( {../image/WhatsApp Image 2023-07-05 at 08.20.04.jpeg} )

## PENJELASAN PROGRAM
- Import Library
  ```bash
  import cv2
  import numpy as np
  import matplotlib.pyplot as plt
  ```
    - cv2: Library utama untuk pengolahan gambar menggunakan OpenCV.
    - numpy (diimport sebagai np): Library untuk operasi matematika dan array multidimensi.
    - matplotlib.pyplot (diimport sebagai plt): Library untuk visualisasi gambar.
 
     
- Membuat Fungi deteksi_plat

```bash
def deteksi_plat1(image_path):
    # Load image
    image = cv2.imread(image_path)
    
    # Convert image to grayscale
    gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
    
    # Perform edge detection
    edges = cv2.Canny(gray, 255,15)
    
    # Find contours of the potential license plate regions
    contours, _ = cv2.findContours(edges, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)
    
    # Filter contours based on area and aspect ratio
    min_area = 0.001  # Minimum area of a contour to be considered as a license plate
    min_aspect_ratio = 0.1  # Minimum aspect ratio of a contour to be considered as a license plate
    
    candidate_plates = []
    
    for contour in contours:
        x, y, w, h = cv2.boundingRect(contour)
        aspect_ratio = w / float(h)
        area = cv2.contourArea(contour)
        
        if area > min_area and aspect_ratio > min_aspect_ratio:
            candidate_plates.append(contour)
            
    # Sort candidate plates by size in descending order
    candidate_plates = sorted(candidate_plates, key=cv2.contourArea, reverse=True)
    
    if len(candidate_plates) > 0:
        # Select the largest candidate plate
        largest_plate = candidate_plates[0]
        
        # Draw a bounding rectangle around the plate
        x, y, w, h = cv2.boundingRect(largest_plate)
        cv2.rectangle(image, (x, y), (x + w, y + h), (0, 255, 0), 2)
        
        # Apply perspective transform to zoom into the plate
        src_pts = np.float32([[x, y], [x + w, y], [x, y + h], [x + w, y + h]])
        dst_pts = np.float32([[0,0], [300, 10], [0, 100], [300, 100]])  # Destination points for perspective transform
        
        matrix = cv2.getPerspectiveTransform(src_pts, dst_pts)
        result = cv2.warpPerspective(image, matrix, (300, 70))

        edges = cv2.Canny(result, 50, 255, L2gradient=False)
        
        gray_result = cv2.cvtColor(result, cv2.COLOR_BGR2GRAY)
        _, binary_result = cv2.threshold(gray_result, 127, 255, cv2.THRESH_BINARY)
        
        # Create a figure with four subplots
        fig, axes = plt.subplots(2, 2, figsize=(12, 10))
        ax = axes.ravel()

        # Original image
        ax[0].imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
        ax[0].set_title("gambar asli")

        # Detected license plate
        ax[1].imshow(cv2.cvtColor(result, cv2.COLOR_BGR2RGB))
        ax[1].set_title("Plat terdeteksi")

        # Binary image
        ax[2].imshow(binary_result, cmap='gray')
        ax[2].set_title("Binary Image")

        # Edges image
        ax[3].imshow(edges, cmap='gray')
        ax[3].set_title("Edges Image")

        plt.tight_layout()
        plt.show()
    else:
        print("No license plate found.")


```
- Penjelasan
  ```bash
    image = cv2.imread(image_path)
    
    # Convert image to grayscale
    gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
    
    # Perform edge detection
    edges = cv2.Canny(gray, 255,15)
    
    # Find contours of the potential license plate regions
    contours, _ = cv2.findContours(edges, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)
    
    # Filter contours based on area and aspect ratio
    min_area = 0.001  # Minimum area of a contour to be considered as a license plate
    min_aspect_ratio = 0.1  # Minimum aspect ratio of a contour to be considered as a license plate
    
    candidate_plates = []
  ```
    - Membaca gambar menggunakan cv2.imread() dan menyimpannya dalam variabel image.
    - Mengubah gambar menjadi citra skala abu-abu (grayscale) menggunakan cv2.cvtColor() dengan parameter cv2.COLOR_BGR2GRAY. Hasilnya disimpan dalam variabel gray
    - Melakukan deteksi tepi pada citra skala abu-abu menggunakan cv2.Canny(). Parameter pertama adalah citra input, dan parameter kedua dan ketiga adalah batas bawah dan atas untuk deteksi tepi. Hasil deteksi tepi disimpan dalam variabel edges.
    - Mencari kontur pada daerah potensial plat nomor menggunakan cv2.findContours(). Parameter pertama adalah citra tepi yang telah didapatkan sebelumnya, parameter kedua adalah mode retrieval kontur, dan parameter ketiga adalah metode approksimasi kontur. Hasil kontur disimpan dalam variabel contours
    - Menerapkan filter pada kontur berdasarkan luas dan rasio aspek. Terdapat dua variabel yang digunakan sebagai filter, yaitu min_area dan min_aspect_ratio. Kontur yang memenuhi syarat akan disimpan dalam list candidate_plates.
    - Melakukan pengurutan kontur plat potensial berdasarkan ukuran dalam urutan menurun menggunakan fungsi sorted() dengan parameter cv2.contourArea sebagai kunci pengurutan. Hasil pengurutan disimpan dalam variabel candidate_plates.
    - Jika terdapat kontur plat potensial (panjang candidate_plates lebih dari 0), maka program akan melanjutkan ke langkah berikutnya. Jika tidak, program akan mencetak pesan "No license plate found." dan berakhir.
    - Memilih plat terbesar dari candidate_plates sebagai plat yang akan ditampilkan. Plat terbesar ini diperoleh dengan mengambil elemen pertama dari candidate_plates karena telah diurutkan sebelumnya.

```bash
for contour in contours:
        x, y, w, h = cv2.boundingRect(contour)
        aspect_ratio = w / float(h)
        area = cv2.contourArea(contour)
        
        if area > min_area and aspect_ratio > min_aspect_ratio:
            candidate_plates.append(contour)
```

   - Menggambar persegi pembatas (bounding rectangle) pada plat yang terdeteksi menggunakan cv2.rectangle(). Parameter pertama adalah citra input, parameter kedua dan ketiga adalah titik kiri atas dan titik kanan bawah persegi pembatas, parameter keempat adalah warna garis (dalam format BGR), dan parameter kelima adalah ketebalan garis. Hasilnya ditampilkan pada gambar asli.

```bash
for contour in contours:
        x, y, w, h = cv2.boundingRect(contour)
        aspect_ratio = w / float(h)
        area = cv2.contourArea(contour)
        
        if area > min_area and aspect_ratio > min_aspect_ratio:
            candidate_plates.append(contour)
```

```bash
 candidate_plates = sorted(candidate_plates, key=cv2.contourArea, reverse=True)
```

   - Menerapkan filter pada kontur berdasarkan luas dan rasio aspek. Terdapat dua variabel yang digunakan sebagai filter, yaitu min_area dan min_aspect_ratio. Kontur yang memenuhi syarat akan disimpan dalam list candidate_plates

```bash
 if len(candidate_plates) > 0:
        # Select the largest candidate plate
        largest_plate = candidate_plates[0]
        
        # Draw a bounding rectangle around the plate
        x, y, w, h = cv2.boundingRect(largest_plate)
        cv2.rectangle(image, (x, y), (x + w, y + h), (0, 255, 0), 2)
        
        # Apply perspective transform to zoom into the plate
        src_pts = np.float32([[x, y], [x + w, y], [x, y + h], [x + w, y + h]])
        dst_pts = np.float32([[0,0], [300, 10], [0, 100], [300, 100]])  # Destination points for perspective transform
        
        matrix = cv2.getPerspectiveTransform(src_pts, dst_pts)
        result = cv2.warpPerspective(image, matrix, (300, 70))

        edges = cv2.Canny(result, 50, 255, L2gradient=False)
        
        gray_result = cv2.cvtColor(result, cv2.COLOR_BGR2GRAY)
        _, binary_result = cv2.threshold(gray_result, 127, 255, cv2.THRESH_BINARY)
```
  - Memilih plat terbesar dari candidate_plates sebagai plat yang akan diproses lebih lanjut. Plat terbesar ini diperoleh dengan mengambil elemen pertama dari candidate_plates karena telah diurutkan sebelumnya.

  - Menggambar persegi pembatas (bounding rectangle) di sekitar plat menggunakan cv2.rectangle(). Koordinat titik kiri atas dan titik kanan bawah dari persegi pembatas diperoleh dari x, y, w, dan h yang merupakan hasil dari fungsi cv2.boundingRect(largest_plate). Garis persegi pembatas ini digambar pada gambar asli (image) dengan warna (0, 255, 0) dan ketebalan 2.
  
  - Menerapkan transformasi perspektif (perspective transform) pada plat untuk memperbesar dan meratakan perspektifnya menggunakan cv2.getPerspectiveTransform() dan cv2.warpPerspective(). Titik sumber (source points) untuk transformasi perspektif diperoleh dari x, y, w, dan h yang telah didapatkan sebelumnya. Titik tujuan (destination points) ditentukan secara manual pada dst_pts. Matriks transformasi diperoleh dari cv2.getPerspectiveTransform() dengan menggunakan titik sumber dan titik tujuan, dan digunakan untuk melakukan transformasi perspektif pada image menggunakan cv2.warpPerspective(). Hasil transformasi perspektif disimpan dalam variabel result.
  
  - Melakukan deteksi tepi pada citra hasil transformasi (result) menggunakan cv2.Canny(). Parameter pertama adalah citra input, dan parameter kedua dan ketiga adalah batas bawah dan atas untuk deteksi tepi. Hasil deteksi tepi disimpan dalam variabel edges.
  
  - Mengubah citra hasil transformasi (result) menjadi citra skala abu-abu (grayscale) menggunakan cv2.cvtColor() dengan parameter cv2.COLOR_BGR2GRAY. Hasilnya disimpan dalam variabel gray_result.
  
  - Membuat citra biner (binary image) menggunakan cv2.threshold(). Parameter pertama adalah citra skala abu-abu (gray_result), parameter kedua adalah nilai ambang (threshold), parameter ketiga adalah nilai maksimum yang diberikan untuk piksel yang melampaui ambang, dan parameter keempat adalah jenis metode thresholding yang digunakan. Hasil citra biner disimpan dalam variabel binary_result.

```bash
fig, axes = plt.subplots(2, 2, figsize=(12, 10))
        ax = axes.ravel()

        # Original image
        ax[0].imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
        ax[0].set_title("gambar asli")

        # Detected license plate
        ax[1].imshow(cv2.cvtColor(result, cv2.COLOR_BGR2RGB))
        ax[1].set_title("Plat terdeteksi")

        # Binary image
        ax[2].imshow(binary_result, cmap='gray')
        ax[2].set_title("Binary Image")

        # Edges image
        ax[3].imshow(edges, cmap='gray')
        ax[3].set_title("Edges Image")

        plt.tight_layout()
        plt.show()
```
   - Membuat objek subplot dengan menggunakan plt.subplots() dengan parameter 2, 2 untuk membuat matriks subplot berukuran 2x2, dan figsize=(12, 10) untuk mengatur ukuran gambar keseluruhan. Hasilnya disimpan dalam variabel fig dan axes.
   
   - Meratakan matriks subplot menjadi array 1 dimensi menggunakan axes.ravel(). Hasilnya disimpan dalam variabel ax.
   
   - Menampilkan gambar asli pada subplot pertama dengan menggunakan ax[0].imshow() dan mengonversi citra dari format BGR ke RGB menggunakan cv2.cvtColor(). Selanjutnya, memberikan judul subplot pertama dengan menggunakan ax[0].set_title().
   
   - Menampilkan gambar plat terdeteksi pada subplot kedua dengan menggunakan ax[1].imshow() dan mengonversi citra dari format BGR ke RGB menggunakan cv2.cvtColor(). Selanjutnya, memberikan judul subplot kedua dengan menggunakan ax[1].set_title().
   
   - Menampilkan citra biner (binary image) pada subplot ketiga dengan menggunakan ax[2].imshow() dan menggunakan colormap 'gray' dengan cmap='gray' untuk menampilkan citra biner dalam skala abu-abu. Selanjutnya, memberikan judul subplot ketiga dengan menggunakan ax[2].set_title().
   
   - Menampilkan citra tepi (edges image) pada subplot keempat dengan menggunakan ax[3].imshow() dan menggunakan colormap 'gray' dengan cmap='gray' untuk menampilkan citra tepi dalam skala abu-abu. Selanjutnya, memberikan judul subplot keempat dengan menggunakan ax[3].set_title().
   
   - Mengatur tata letak tampilan subplot menggunakan plt.tight_layout() untuk menghindari tumpang tindih antar subplot.
   
   - Menampilkan plot dengan menggunakan plt.show() untuk memperlihatkan subplot-subplot yang telah diatur.
