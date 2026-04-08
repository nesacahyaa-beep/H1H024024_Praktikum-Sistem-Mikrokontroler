# Percobaan 2 – Running LED

Percobaan ini bertujuan mempelajari pengendalian LED menggunakan Arduino Uno. Praktikum ini mencakup empat soal utama mengenai efek LED dan programnya.

---

## 1. Gambarkan rangkaian schematic LED

Rangkaian menggunakan 5 LED yang disusun paralel dengan resistor 220 Ω untuk membatasi arus. Kaki anoda setiap LED dihubungkan ke pin digital Arduino (2–6), sedangkan kaki katoda dihubungkan ke resistor yang kemudian ke GND. Penggunaan resistor memastikan arus aman sehingga LED dan pin mikrokontroler tidak rusak.

![Percobaan 2 – Running LED](images/percobaan2.jpeg)

---

## 2. LED Berjalan dari Kiri ke Kanan

Program Arduino membuat LED terlihat berjalan dari kiri ke kanan menggunakan konsep *running LED*. LED dinyalakan satu per satu dari pin dengan nomor kecil ke besar sehingga terlihat seperti cahaya bergerak. Setiap LED dinyalakan selama jeda tertentu menggunakan fungsi `delay()` sebelum dimatikan, sehingga efek pergerakan dapat diamati dengan jelas. Perulangan `for` memungkinkan kontrol LED secara berurutan tanpa menulis kode untuk setiap pin, membuat program lebih ringkas dan mudah dikembangkan.

---

## 3. LED Berjalan dari Kanan ke Kiri

Setelah LED menyala dari kiri ke kanan, program dapat membalik efek sehingga LED menyala dari kanan ke kiri, menghasilkan efek bolak-balik (*bounce effect*). Hal ini dicapai dengan menggunakan perulangan `for` yang dimulai dari pin dengan nomor terbesar (kanan) menuju pin dengan nomor terkecil (kiri). Setiap LED dinyalakan satu per satu dengan jeda tertentu menggunakan fungsi `delay()`, kemudian dimatikan sebelum pindah ke LED berikutnya. Mekanisme ini menciptakan ilusi pergerakan LED dari kanan ke kiri secara berurutan, sehingga pengguna dapat melihat efek LED bergerak bolak-balik.

---

## 4. LED Tiga Kiri dan Tiga Kanan Bergantian

Program untuk menyalakan tiga LED kiri dan tiga LED kanan secara bergantian memanfaatkan konsep pengelompokan pin LED dalam array dan perulangan `for`. LED pada kelompok kiri dinyalakan satu per satu, diberi jeda agar nyala terlihat jelas, lalu dimatikan secara berurutan. Setelah itu, LED pada kelompok kanan menyala secara bergantian dengan mekanisme yang sama. Proses ini diulang terus-menerus sehingga terlihat efek LED bergantian antara sisi kiri dan kanan. Pendekatan ini efisien karena menggunakan perulangan untuk mengontrol beberapa LED sekaligus tanpa menulis kode individual untuk setiap pin.

---

## Kesimpulan

Dari percobaan ini, dapat disimpulkan bahwa:

- Perulangan `for` memungkinkan LED dikontrol secara sistematis dan efisien, menciptakan efek bergerak dari kiri ke kanan maupun kanan ke kiri.  
- Penggunaan array dan perulangan dapat membuat LED menyala bergantian antara dua kelompok, mempermudah pengaturan tanpa kode berulang.  
- Fungsi `delay()` penting untuk membuat perubahan LED terlihat oleh mata manusia.  
- Praktikum ini menunjukkan hubungan antara logika program dan kerja perangkat keras, yang menjadi dasar pengendalian embedded system menggunakan Arduino.
