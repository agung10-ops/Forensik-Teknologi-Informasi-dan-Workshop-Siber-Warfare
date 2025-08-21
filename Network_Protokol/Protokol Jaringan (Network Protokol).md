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

# Hubungan Antar Kedua Model
Pada dasarnya, model TCP/IP adalah implementasi dari konsep-konsep yang ada di dalam model OSI. Model OSI memberikan panduan teoretis yang terperinci, sementara model TCP/IP adalah praktik nyata yang mendominasi dunia jaringan modern.
<img width="3892" height="3226" alt="image" src="https://github.com/user-attachments/assets/f3f92524-5d6d-4a0a-bdf0-dff9ff0438dc" />
<img width="1536" height="1024" alt="sketsa OSI  TCP IP" src="https://github.com/user-attachments/assets/8fa9842a-1ee0-456f-81f2-e283a8fdb0df" />

# Alur Kerja Internet
Internet bekerja melalui serangkaian tahapan agar data bisa dikirim dari satu perangkat ke perangkat lain di seluruh dunia:

1. Perangkat Pengguna (Client)
  - Misalnya komputer, HP, atau laptop yang digunakan untuk mengakses internet.
  - Saat pengguna mengetik alamat website, perangkat akan membuat permintaan (request).
2. Internet Service Provider (ISP)
  - Permintaan dari perangkat akan dikirim ke penyedia layanan internet (Telkomsel, Indihome, Biznet, dll.).
  - ISP memberikan akses ke jaringan internet global.
3. DNS (Domain Name System)
  - DNS berfungsi menerjemahkan alamat website (misalnya www.google.com) menjadi alamat IP (contoh: 142.250.190.78).
  - Karena komputer berkomunikasi menggunakan IP, bukan nama domain.
4. Router & Jaringan Internet
  - Data akan melewati beberapa router di dalam internet (seperti jalan raya data).
  - Router akan mencari jalur tercepat menuju server tujuan.
5. Server Tujuan
  - Server yang menyimpan data/website menerima permintaan.
  - Server mengolah dan mengirimkan balasan (response) kembali ke client.
6. Perjalanan Balik
  - Data dari server melewati jalur router, ISP, hingga kembali ke perangkat pengguna.
7. Tampilan di Browser
  - Data akhirnya diterima oleh browser (Chrome, Edge, Firefox), lalu ditampilkan dalam bentuk halaman web.

# Diagram Alur Kerja Internet
<img width="1536" height="1024" alt="alur kerja internet" src="https://github.com/user-attachments/assets/3d1edca2-cdf2-4b2e-8379-ba996638bc95" />

# Dibuat Oleh 
  - Agung Kurniawan/Sertu Mar



