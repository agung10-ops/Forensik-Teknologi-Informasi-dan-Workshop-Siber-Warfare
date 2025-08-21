# Protokol Jaringan (Network Protokol)
Protokol jaringan (network protocol) adalah kumpulan aturan dan standar yang mengatur bagaimana data ditransmisikan antara dua perangkat atau lebih dalam sebuah jaringan. 
Protokol ini berfungsi seperti bahasa umum yang memungkinkan perangkat yang berbeda untuk berkomunikasi, bertukar informasi, dan bekerja sama secara efisien.

Tanpa protokol jaringan, perangkat tidak akan tahu bagaimana cara memproses data yang diterima, seperti mengidentifikasi pengirim, 
memastikan data sampai dengan utuh, atau menentukan jalur pengiriman terbaik.

# Jenis-Jenis Protokol Jaringan
Secara umum, protokol jaringan dapat diklasifikasikan berdasarkan fungsinya:

1. Protokol Komunikasi Data: Mengatur transmisi data secara fisik. Contohnya:

* TCP/IP (Transmission Control Protocol/Internet Protocol): Ini adalah protokol utama yang digunakan di internet. TCP bertanggung jawab untuk memecah data menjadi paket-paket kecil dan memastikan semua paket sampai di tujuan dengan benar, sementara IP menangani pengalamatan (addressing) dan routing paket tersebut ke tujuan yang tepat.

* HTTP (Hypertext Transfer Protocol): Protokol yang digunakan untuk mentransfer data di World Wide Web, seperti halaman web, gambar, dan video. HTTPS adalah versi amannya (HTTP Secure) yang menggunakan enkripsi.

* FTP (File Transfer Protocol): Digunakan untuk mentransfer file dari satu komputer ke komputer lain di jaringan.

2. Protokol Routing: Bertugas menemukan jalur terbaik untuk mengirimkan data antar jaringan. Contohnya:

* OSPF (Open Shortest Path First): Digunakan untuk menemukan jalur terpendek dalam jaringan besar.

* BGP (Border Gateway Protocol): Protokol routing utama yang digunakan di internet untuk bertukar informasi routing antara sistem otonom (autonomous systems).

3. Protokol Keamanan: Menjamin keamanan data selama transmisi. Contohnya:

* SSL/TLS (Secure Sockets Layer/Transport Layer Security): Digunakan untuk mengenkripsi data yang dikirimkan melalui internet, seperti saat bertransaksi online.

* SSH (Secure Shell): Digunakan untuk mengamankan koneksi jarak jauh ke server atau perangkat lain.

# Kerangka Kerja Utama Protokol Jaringan (Network Protokol).
* Model OSI (Open Systems Interconnection)
Model OSI adalah model teoretis yang memiliki 7 lapisan. Tujuan utamanya adalah untuk memberikan kerangka kerja universal yang memungkinkan berbagai sistem jaringan dan perangkat untuk berinteraksi, terlepas dari produsennya. Model ini sering digunakan sebagai alat bantu pendidikan dan referensi untuk memahami fungsi setiap proses dalam komunikasi jaringan.

7 Lapisan Model OSI:

1. Physical Layer: Mengatur transmisi fisik data dalam bentuk bit (0 dan 1).

2. Data Link Layer: Mengelola komunikasi antar perangkat dalam satu jaringan lokal (misalnya, dengan menggunakan MAC address).

3. Network Layer: Bertanggung jawab untuk routing paket data antar jaringan yang berbeda menggunakan alamat IP.

4. Transport Layer: Memastikan pengiriman data yang andal dari satu titik ke titik lain. Protokol utamanya adalah TCP dan UDP.

5. Session Layer: Mengelola sesi koneksi, termasuk memulai, mengelola, dan mengakhiri komunikasi antar aplikasi.

6. Presentation Layer: Bertugas menerjemahkan, mengenkripsi, dan mengompresi data untuk memastikan formatnya sesuai bagi aplikasi penerima.

7. Application Layer: Lapisan teratas yang berinteraksi langsung dengan aplikasi pengguna (misalnya, browser web, email).

* Model TCP/IP (Transmission Control Protocol/Internet Protocol)
Model TCP/IP adalah model yang praktis dan digunakan secara luas di internet. Meskipun lebih sederhana dari OSI, model ini sangat efektif karena menggabungkan beberapa fungsi menjadi lapisan yang lebih sedikit. Model ini biasanya digambarkan dengan 4 atau 5 lapisan.

5 Lapisan Model TCP/IP (versi yang paling umum):

1. Network Access Layer (atau Link Layer): Menggabungkan fungsi Lapisan Fisik dan Tautan Data dari model OSI. Mengelola komunikasi dalam jaringan lokal, termasuk penggunaan alamat MAC.

2. Internet Layer: Setara dengan Lapisan Jaringan di model OSI. Bertanggung jawab untuk pengalamatan dan perutean (routing) paket data menggunakan IP.

3. Transport Layer: Sama seperti OSI, memastikan transfer data yang andal dan teratur (menggunakan TCP atau UDP).

4. Application Layer: Menggabungkan fungsi Lapisan Aplikasi, Presentasi, dan Sesi dari model OSI. Lapisan ini menyediakan protokol yang dibutuhkan aplikasi untuk berkomunikasi (contoh: HTTP, FTP, SMTP).

# Perbedaan Utama
* Jumlah Lapisan: OSI memiliki 7 lapisan, sedangkan TCP/IP memiliki 4 atau 4 lapisan.

* Fokus: OSI lebih ke arah teoretis dan konseptual, sedangkan TCP/IP adalah model praktis yang menjadi fondasi internet.

* Lapisan Gabungan: TCP/IP menggabungkan beberapa lapisan dari OSI untuk menyederhanakan proses.

