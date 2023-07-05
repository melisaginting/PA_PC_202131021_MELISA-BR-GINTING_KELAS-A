
# Project Deteksi Buah

Teori yang mendukung project Deteksi Buah adalah :
Segmentasi citra pada objek buah berdasarkan karakteristik warna HSV.

Pada metode segmentasi dengan deteksi warna HSV menurut Giannakupoulos (2008),
dilakukan pemilihan sampel piksel sebagai acuan warna untuk membentuk segmen yang
diinginkan. Citra digital menggunakan model warna RGB sebagai standar acuan warna, oleh
karena itu proses awal pada metode ini memerlukan konversi model warna RGB ke HSV. Untuk
membentuk segmen sesuai dengan warna yang diinginkan maka ditentukan nilai toleransi pada
setiap dimensi warna HSV, kemudian nilai toleransi tersebut digunakan dalam perhitungan
proses adaptive threshold. 

## Tahapan Menyelesaikan Project Deteksi Buah
1. Mengimpor Library 
Impor library yang diperlukan, yaitu cv2 untuk pemrosesan citra, numpy untuk manipulasi array, dan matplotlib.pyplot untuk visualisasi citra.

2.  Fungsi fruit_segmentation 
Memiliki satu parameter buah, yang merupakan jalur file citra buah yang akan di-segmentasi.

3.  Membaca Citra
Di dalam fungsi, citra buah dibaca menggunakan cv2.imread dan disimpan dalam variabel image.

4.  Mengkonversi Citra ke ruang warna HSV
Citra tersebut kemudian dikonversi ke ruang warna HSV menggunakan cv2.cvtColor dengan parameter cv2.COLOR_BGR2HSV. Hal ini memudahkan dalam menentukan rentang warna untuk segmentasi.

5.  Menentukan rentang warna
Rentang warna untuk setiap buah yang ditentukan (apel, mangga hijau, dan jeruk) ditentukan dalam color_ranges sebagai range lower dan upper yang sesuai dengan ruang warna HSV.

6.  Dilakukan loop untuk setiap buah yang ditentukan. Rentang warna buah tersebut diambil dari color_ranges.

7.  Dengan menggunakan cv2.inRange, dilakukan segmentasi citra dengan menerapkan ambang pada citra HSV berdasarkan rentang warna buah.

8.  Untuk memperbaiki hasil segmentasi, dilakukan operasi morfologi dengan menggunakan cv2.morphologyEx. Dalam contoh ini, dilakukan operasi "opening" untuk menghilangkan noise dan mengisi lubang kecil pada mask.

9.  Mask hasil segmentasi diaplikasikan ke citra asli menggunakan cv2.bitwise_and untuk mendapatkan hasil segmentasi buah.

10. Mask dan hasil segmentasi buah untuk setiap buah ditambahkan ke dalam daftar masks dan segmented_images.

11. Akhirnya, citra asli dan hasil segmentasi buah ditampilkan menggunakan matplotlib.pyplot. Citra asli ditampilkan di subplot pertama, dan hasil segmentasi buah ditampilkan di subplot berikutnya sesuai dengan urutan buah yang ditentukan.

12. Setelah selesai, citra-citra tersebut ditampilkan menggunakan plt.show().

13. Dapat menggunakan fungsi fruit_segmentation dengan memberikan jalur file citra buah yang ingin disegmentasikan sebagai argumen buah. Pastikan sudah memiliki citra tersebut dan sesuaikan jalur file dengan nama dan lokasi citra yang dimiliki.


## Jurnal yang Terkait
https://media.neliti.com/media/publications/68819-ID-none.pdf



