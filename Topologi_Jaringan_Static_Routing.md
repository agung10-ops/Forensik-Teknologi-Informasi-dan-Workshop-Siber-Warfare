# 🌐Pendahuluan
Perkembangan teknologi informasi yang pesat saat ini menuntut adanya sistem komunikasi data yang cepat, handal, dan aman. 
Salah satu aspek penting dalam komunikasi data adalah topologi jaringan, yaitu gambaran atau pola hubungan antar perangkat dalam sebuah jaringan komputer. 
Topologi jaringan menggambarkan bagaimana komputer, router, switch, maupun perangkat lain dihubungkan satu sama lain serta bagaimana data mengalir di dalam jaringan tersebut. 
Pemilihan topologi jaringan yang tepat sangat berpengaruh terhadap kinerja, skalabilitas, serta tingkat keamanan jaringan.

# Routing Statis
Routing statis adalah metode routing di mana administrator jaringan secara manual memasukkan tabel rute pada perangkat router. 
Dengan kata lain, jalur komunikasi dari satu jaringan ke jaringan lain ditentukan secara tetap (fixed) oleh konfigurasi manual. 
Router tidak akan melakukan perubahan rute secara otomatis meskipun terjadi perubahan pada jaringan, kecuali administrator mengubahnya secara langsung.

# Karakteristik Routing Statis
    1.  Manual – Rute ditambahkan, dihapus, atau diubah secara manual oleh administrator.
    2.	Tetap (Fixed) – Jalur yang telah ditentukan tidak akan berubah kecuali ada konfigurasi ulang.
    3.	Ringan – Tidak membebani CPU dan memori router karena tidak perlu melakukan perhitungan atau pertukaran tabel routing dengan router lain.
    4.	Kontrol penuh – Administrator memiliki kendali penuh terhadap jalur lalu lintas data.

# Perancangan Topologi Jaringan
Dalam perancangan Topologi ini menggunakan: 

    2 buah Router yang saling terhubung.  
    
    PC 1 terhubung ke Router 1.
    
    PC 2 Terhubung ke Router 2. 
    
Kemudian untuk menghubungkan Pc dengan Router menggunakan kabel _Copper Straight-Through_ dan Roter ke Router menggunakan kabel _Copper Cross-Over_

# Konfigurasi IP Address
  💻 **_PC 1_** 
  
      IP Address: 192.168.1.2
      
      Subnet Mask: 255.255.255.0
      
      Default Gateway: 192.168.1.1
      
<img width="874" height="664" alt="Screenshot 2025-08-29 222105" src="https://github.com/user-attachments/assets/ed280932-8a74-4c01-be53-a5772486083a" />

  💻 **_PC 2_** 
  
      IP Address: 192.168.3.2
      
      Subnet Mask: 255.255.255.0
      
      Default Gateway: 192.168.3.1

<img width="874" height="668" alt="Screenshot 2025-08-29 222249" src="https://github.com/user-attachments/assets/f63254d6-c268-4ac9-b115-11ee2a97ca1c" />

  📡 **_Router 1_**
  
**Router 1 terhubung ke PC 1 melalui GigabitEthernet0/0**

<img width="877" height="394" alt="Screenshot 2025-08-29 223806" src="https://github.com/user-attachments/assets/43d753ec-281d-4c4a-99e1-001af8d8b8d3" />

**Router 1 terhubung ke Router 2 melalui GigabitEthernet0/1**

<img width="877" height="388" alt="Screenshot 2025-08-29 223837" src="https://github.com/user-attachments/assets/9e13067e-0c90-4b5b-8e31-f20f0b091f2d" />

**Routing Statis Router 1**

<img width="873" height="591" alt="Screenshot 2025-08-29 225144" src="https://github.com/user-attachments/assets/d554039b-8f98-4466-9a25-b2686cde25cf" />

**Router 2 terhubung ke PC 2 melalui GigabitEthernet0/0**

<img width="870" height="589" alt="Screenshot 2025-08-29 225305" src="https://github.com/user-attachments/assets/b5ac5ee0-4a13-41cb-8613-fb6582dc7bc3" />

 **Router 2 terhubung ke Router 1 melalui GigabitEthernet0/1**

<img width="871" height="589" alt="Screenshot 2025-08-29 225441" src="https://github.com/user-attachments/assets/eb5fbce5-283b-4931-bbc4-6ba5e0a8f4da" />

**Routing Statis Router 2**

<img width="874" height="590" alt="Screenshot 2025-08-29 225631" src="https://github.com/user-attachments/assets/eb800c81-5203-4206-99a7-7ef021ec7aca" />

# Pengujian Koneksi Antar Perangkat
Pengujian kita lakukan dengan ping antar perangkat
  **PC 1 ke PC 2**

<img width="872" height="524" alt="Screenshot 2025-08-29 230122" src="https://github.com/user-attachments/assets/029bc3d9-1688-4f57-bf69-69c13df8c12e" />

  Hasil pengujian ping dari PC 1 ke PC 2 (192.168.3.2) berhasil dengan baik.

  **PC 2 ke PC 1**

<img width="876" height="449" alt="Screenshot 2025-08-29 230430" src="https://github.com/user-attachments/assets/9a0498fb-16c6-4bca-9c48-5ae4b4a7d7f0" />

  Hasil pengujian ping dari PC 2 ke PC 1 (192.168.1.2) berhasil dengan baik.


# Mekanisme Alur
**PC 1 → Router 1**

      •	Src IP (Sumber): 192.168.1.2 (IP PC1)
      
      •	Dest IP (Tujuan): 192.168.3.2 (IP PC2)
      
      •	Paket data keluar dari PC1 menuju default gateway 192.168.1.1 (Router 1).
      
**Router 1 → Router 2**

      •	Saat paket masuk ke Router 1, alamat sumber (Src IP) berubah menjadi IP interface Router 1 yang terhubung ke Router 2, yaitu 192.168.2.1.
      
      •	Dest IP tetap 192.168.3.2 (karena tujuan akhirnya adalah PC2).
      
**Router 2 → PC 2**

      •	Paket diteruskan ke Router 2, dan sekarang Src IP berubah lagi menjadi 192.168.3.1 (IP interface Router 2 yang terhubung ke jaringan PC2).
      
      •	Dest IP tetap 192.168.3.2.
      
**PC 2 menerima paket**

      •	PC2 dengan alamat 192.168.3.2 akhirnya menerima paket tersebut.

# Tampilan Topologi Jaringan

<img width="955" height="740" alt="Screenshot 2025-08-29 233933" src="https://github.com/user-attachments/assets/6798e83f-1077-47ba-9899-9aeb710284bf" />

      
# Kesimpulan
Routing statis merupakan metode routing yang dilakukan dengan cara mengatur jalur komunikasi jaringan secara manual oleh administrator. 
Metode ini sangat cocok digunakan pada jaringan dengan skala kecil hingga menengah karena lebih sederhana, hemat sumber daya, serta memberikan kontrol penuh terhadap aliran data.

berdasarkan pengujian di atas dapat disimpulkan :
Topologi jaringan ini berhasil menghubungkan dua subnet berbeda (192.168.1.0/24 dan 192.168.3.0/24) menggunakan dua router sebagai perantara.

    • Penerapan Routing Statis pada kedua Router berhasil.
    
    • Pastikan Konfigurasi IP Address, Router interface, Default Gateway dan routing statis sudah benar, sehingga setiap perangkat dapat terhubung pada jaringan.
    
    • Hasil ujicoba dengan ping dari PC 1 ke PC 2 (dan sebaliknya) berhasil dengan baik dengan adanya reply dari alamat tujuan.
    
    • Dengan Konfigurasi Routing Statis komunikasi dapat berjalan lancar dan stabil.


# Dibuat Oleh 
Agung Kurniawan 
