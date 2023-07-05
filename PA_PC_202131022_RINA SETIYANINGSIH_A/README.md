
# PROJECT UAS 

## Nama : Rina Setiyaningsih
## NIM : 202131022
## PC : 16
## Matkul : Pengolahan Citra A

## 1. teori terkait dengan deteksi garis pada marka jalan

### Teori Dasar deteksi garis pada marka jalan

Ada beberapa teori dan metode yang digunakan dalam deteksi garis pada marka jalan. Berikut ini adalah beberapa teori yang terkait dengan deteksi garis pada marka jalan dalam pengolahan citra:

1). Transformasi Hough: Transformasi Hough adalah salah satu metode yang umum digunakan dalam deteksi garis pada marka jalan. Metode ini mengubah representasi garis dalam citra dari koordinat kartesian menjadi parameter ruang Hough. Transformasi ini memungkinkan deteksi garis secara efisien bahkan dalam keberadaan noise atau ketidakteraturan pada citra.

2). Operasi Pemfilteran: Metode ini melibatkan penggunaan operasi pemfilteran, seperti filter Sobel, filter Canny, atau filter LoG (Laplacian of Gaussian), untuk menekankan kontur dan tepi pada citra. Dengan menggunakan operasi pemfilteran ini, garis pada marka jalan dapat diidentifikasi dengan lebih jelas.

3). Segmentasi Citra: Pada langkah ini, citra dibagi menjadi beberapa bagian atau region yang memiliki karakteristik yang berbeda. Segmentasi citra dapat digunakan untuk memisahkan marka jalan dari latar belakang atau elemen-elemen lain dalam citra, sehingga memudahkan deteksi garis pada marka jalan.

4). Transformasi Ruang Warna: Deteksi garis pada marka jalan juga dapat ditingkatkan dengan menggunakan transformasi ruang warna, seperti transformasi RGB ke HSV atau transformasi RGB ke grayscale. Dalam beberapa kasus, transformasi ruang warna dapat membantu memisahkan marka jalan dari latar belakang dengan cara mengubah perbedaan warna menjadi perbedaan nilai intensitas yang lebih jelas.

5). Metode Machine Learning: Metode machine learning, seperti penggunaan jaringan saraf tiruan (neural networks) atau metode pembelajaran berbasis pohon keputusan, juga dapat digunakan dalam deteksi garis pada marka jalan. Metode ini melibatkan pelatihan model dengan menggunakan dataset citra yang telah diberi anotasi untuk mengenali dan mempelajari pola-pola garis pada marka jalan.






### adapun Kegunaan deteksi garis pada marka jalan

Berikut ini adalah beberapa kegunaan penting deteksi garis pada marka jalan dalam pengolahan citra:

1). Navigasi Kendaraan Otomatis: Deteksi garis pada marka jalan membantu dalam pengambilan keputusan yang diperlukan untuk mengarahkan kendaraan secara otomatis.

2). Sistem Peringatan Keluar Jalur: Deteksi garis pada marka jalan juga digunakan dalam sistem peringatan keluar jalur (lane departure warning system). Sistem ini dapat mendeteksi apakah kendaraan keluar dari jalur yang ditentukan oleh marka jalan dan memberikan peringatan kepada pengemudi untuk menghindari kecelakaan.

3). Analisis Kondisi Jalan: Deteksi garis pada marka jalan juga digunakan dalam analisis kondisi jalan. Dengan melacak garis pada marka jalan dalam citra, dapat diperoleh informasi tentang kualitas dan kondisi marka jalan, seperti keausan, kerusakan, atau perubahan pola. Informasi ini dapat digunakan untuk perencanaan perawatan jalan atau pengawasan jalan yang lebih efisien.

4). Pengawasan Lalu Lintas: Deteksi garis pada marka jalan juga digunakan dalam sistem pengawasan lalu lintas. Dengan memantau dan menganalisis garis pada marka jalan, dapat dilakukan pemantauan lalu lintas, penghitungan volume kendaraan, atau pengenalan pola lalu lintas untuk tujuan pengaturan lalu lintas yang lebih efektif.

5). Sistem Bantuan Pemandu Parkir: Deteksi garis pada marka jalan juga dapat digunakan dalam sistem bantuan pemandu parkir. Dengan mendeteksi garis pada marka jalan yang menunjukkan tempat parkir, sistem dapat memberikan bantuan visual atau petunjuk suara kepada pengemudi untuk membantu dalam melakukan manuver parkir yang akurat.




### Kelemahan deteksi garis pada marka jalan

Berikut adalah beberapa kelemahan umum dari deteksi garis pada marka jalan dalam pengolahan citra:

1). Sensitivitas terhadap Kondisi Lingkungan: Deteksi garis pada marka jalan dapat menjadi kurang akurat atau terpengaruh oleh kondisi lingkungan yang berubah-ubah, seperti kondisi pencahayaan yang rendah, cuaca buruk (hujan, salju), atau keberadaan bayangan pada marka jalan. Kondisi ini dapat mengurangi kehandalan deteksi garis dan menyebabkan kesalahan dalam pelacakan garis.

2). Keterbatasan pada Marka Jalan yang Kabur atau Buram: Jika marka jalan tidak terlihat dengan jelas, misalnya karena kabur atau buram, deteksi garis pada marka jalan dapat menjadi sulit atau tidak akurat. Garis yang tidak terdefinisi dengan jelas dalam citra dapat mengganggu proses deteksi dan pelacakan.

3. Kerentanan terhadap Noise atau Objek Lain dalam Citra: Deteksi garis pada marka jalan juga dapat terpengaruh oleh noise pada citra atau oleh adanya objek lain yang mungkin ada di sekitar marka jalan. Noise atau objek yang tidak relevan dalam citra dapat menyebabkan kesalahan dalam deteksi atau pelacakan garis, dan mengurangi akurasi deteksi secara keseluruhan.




### Yang perlu diperhatikan  saat deteksi garis pada marka jalan

Dalam langkah deteksi garis pada marka jalan dalam pengolahan citra, ada beberapa hal yang perlu diperhatikan. Berikut adalah beberapa poin penting yang harus dipertimbangkan:

1. Pra-pemrosesan Citra
2. Pemilihan Metode Deteksi
3. Parameter Pengolahan
4. Segmentasi Marka Jalan
5. Penanganan Gangguan dan Noise
6. Evaluasi dan Pemilihan Hasil Deteksi
7. Adaptasi Terhadap Variasi Marka Jalan
8. Validasi dan Pengujian



## 2.  Tahapan pengerjaan project secara rinci

## Import Library 

!pip install pillow
import matplotlib.pyplot as plt #memanggil fungsi dan metode dalam modul matplotlib.pyplot

import numpy as np #sintaks yang digunakan untuk mengimpor modul numpy dan memberikan alias np

from PIL import Image #improve visasi dengan penambahaan libary pillow

from IPython.display import display #fungsi python memasukan fungsi display

import cv2 #mengimport modul cv2

import math #Modul math menyediakan fungsi-fungsi matematika dasar yang berguna untuk melakukan operasi matematika
%matplotlib inline

from skimage.io import imread
#menampilkan visualisasi dari matplotlib di dalam notebook itu sendiri

## Tampilan asli Gambar
citra = imread(fname="original-image.jpg") #membaca nama file gambar 

print(citra.shape) #melakukan proses print ukuran citra

plt.imshow(citra, cmap='gray') #memunculkan gambarnya dgn skala keabuan

img = Image.open("original-image.jpg") #membuka kembali file gambar

pict_arr = np.array(img) #mengkonversi array objek menjadi array numpy

size_pixel = pict_arr.size #mengambil jumlah elemen dalam array NumPy pict_arr dan menyimpannya dalam variabel

print(size_pixel) #untuk mencetak atau menampilkan nilai dari variabel size_pixel ke konsol atau output program

## proses mendeteksi

#guna membaca gambar jalanku
image = cv2.imread('original-image.jpg')

#guna mengubah gambar menjadi skala keabu-abuan
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

#guna menerapkan filter Gaussian untuk mengurangi noise
blur = cv2.GaussianBlur(gray, (5, 5), 0)

#guna adanya transformasi Canny untuk mendeteksi tepi
edges = cv2.Canny(blur, 190, 100)

#guna Menerapkan transformasi Hough untuk mendeteksi garis
lines = cv2.HoughLinesP(edges, 1, np.pi/150, threshold=60, minLineLength=20, maxLineGap=50)

#guna Menggambar garis-garis yang terdeteksi pada gambar asli
if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(image, (x1, y1), (x2, y2), (0, 0, 255), 3)

#guna nya Menampilkan gambar dari hasil deteksi garis pada marka jalan


cv2.imshow('mendeteksi garis marka', image) #menampilkan objek gambar yang sudah dilakukan deteksi garis pada
#jendela windows dengan judul 'mendeteksi garis marka'

cv2.waitKey(0) #digunakan untuk menahan tampilan jendela gambar agar tidak langsung tertutup setelah ditampilkan

cv2.destroyAllWindows() #untuk menutup semua jendela gambar yang telah dibuka.

## hasil output akhir

fig, axs = plt.subplots(1, 2, figsize=(15,5))
#digunakan untuk membuat objek gambar (figure) dan satu set subplot (axes). 
#Argumen pertama 1 menentukan jumlah baris subplot yang diinginkan, argumen kedua 2 menentukan jumlah kolom subplot 
#yang diinginkan, dan argumen figsize=(15,5) menentukan ukuran gambar (lebar, tinggi) dalam inci.

axs[0].imshow(image)
#adalah sintaks yang digunakan untuk menampilkan gambar dalam subplot
#pertama menggunakan fungsi imshow() dari objek subplot dengan indeks 0.

axs[1].plot(color='green')
#adalah sintaks yang digunakan untuk membuat plot garis berwarna hijau di subplot kedua.

plt.show #untuk menampilkan gambar dalam sebuah plot. 

## 3. jurnal terkait

### Resume dari jurnal terkait :

#### Untuk file jurnal terlampirkan dalam attachment file di dalam jawaban assigmentnya.

Latar belakang dibuatkan jurnal dengan judul “Sistem Deteksi Marka Membujur Garis Utuh dan Putus  Menggunakan Metode Thresholding dan Hough Transform Berbasis Raspbery Pi” Adalah masih banyak kecelakaan lalu lintas yang disebabkan tidak konsentrasi dan serta tidak sadar bahwa pengendara dalam posisi yang salah. Sebagai usaha meningkatkan keamanan berkendara yang di padukan dengan teknologi komputer saat ini, maka penelitian ini dibuat sebuah alat yang dapat mendeteksi tipe marka jalan membujur lurus dengan tambahan fitur mengukur posisi kendaraan dengan marka serta memberikan peringatan kepada pengendaraan jika posisi kendaaan dalam posisi yang bahaya atau melanggar marka garis.Masukan dari sistem berupa video yang didapatkan dari penggunaan kamera yang dipasang pada bodi tegah sepeda motor yang sejajar dengan roda depan kendaraan . 


#### metode yang dirancang ialah :

1.)	catu daya sebagai power supply, Power bank memiliki output sebesar 5volt dengan rentang arus sebesar 0,8 - 1 A, pada tengganan dan rentang arus tersebut adalah outputyang aman untuk menyalakan sebuah Raspberry Pi 3 

2.)	Perancangan Papan Notifikasi adalah hubungan antara Raspberry Pi dengan Papannotifikasi, Papan notifikasi berperan sebagai output dari sistem. 

3.)	Perancangan User Interface dengan Laptop antara mikrokontroller dengan laptop berfungsi sebagai media koding dan melihat log progam dari sistem yang dibuat,sehingga data proses dapat di analisis langsung pada laptop. 

4.)	Perancangan Purwarupa  terdapat dua buah rancangan yaitu rancangan sisi dalam perwarupa dan rancangan sisi luar purwarupa. 


#### Selanjutnya adalah perancanaan perangkat lunak:

Dibuatkan suatu perancaanan perangkat lunaknya dalam bentuk Frame, lalu frame tersebut nantinya akan diolah pada proses selanjutnya. Hasil dari frame pada proses sebelumnya akan dilakukan pengolahan citra dimulai dari proses rezise, pada proses ini resolusi dari gambar akan dirubah sesuai yang diminta oleh system. Selanjutnya masuk ketahap pengolahan piksel dengan Teknik liminosty untuk mengetahui kernel, mengikuti rangkain tahapan yang ada sampai pada hasil mengetahui titik koordinat pada marka jalannya