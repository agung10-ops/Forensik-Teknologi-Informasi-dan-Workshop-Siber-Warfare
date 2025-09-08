# 🖧 Topologi Routing Statik (3 Router dan 3 LAN)

<img width="1204" height="632" alt="Screenshot 2025-09-08 120057" src="https://github.com/user-attachments/assets/a5c6688b-23eb-4f77-93e9-4f4477797d7d" />

## Pendahuluan

Routing statis adalah jenis jaringan di mana memerlukan administrator jaringan untuk melakukan konfigurasi secara manual. 
Fungsi static routing untuk memback-up ketika dynamic routing tiba-tiba mati, dapat mengirim informasi dari protokol satu 
ke protokol lainnya serta dapat digunakan ketika cakupannya kecil yang hanya memiliki rute kurang dari 5. 
Lalu bagaimana cara kerja routing statis, berikut akan kami jelaskan 3 cara kerja static routing yaitu :

      - Router dikongfigurasikan oleh networking adminstrator
      - Routing yang dilakukan oleh router mengikuti informasi yang ada dalam tabel routing
      - Umumnya static rounting digunakan untuk melewatkan paket data
      
Router memiliki fungsi utama yaitu untuk memberi jalur terkait informasi atau paket, di mana setiap router memiliki kemampuan routing, 
maksudnya router bisa menentukan jalur tercepat maupun jalur terbaik rute mana yang harus dilewati sehingga informasi sampai ke tempat tujuan. 
Router secara pintar bisa mengirimkan paket meskipun untuk host pada jaringan lain.

## Struktur Jaringan

  Router1 LAN: **192.168.1.10/24** (PC di LAN 192.168.1.0/24)

  Router2 LAN: **192.168.2.10/24** (PC di LAN 192.168.2.0/24)

  Router3 LAN: **192.168.3.10/24** (PC di LAN 192.168.3.0/24)

  Link Router1 ↔ Router2: **10.10.10.0/30** → **Router1:10.10.10.1 ─ Router2:10.10.10.2**

  Link Router2 ↔ Router3: **20.20.20.0/30** → **Router2:20.20.20.1 ─ Router3:20.20.20.2**

## Konfigurasi PC

**Pastikan** setiap PC punya default gateway ke alamat router pada jaringannya 
  
| Topologi 1 | Topologi 2 |
|------------|------------|
| <img width="877" height="667" alt="gambar 1" src="https://github.com/user-attachments/assets/aa4c83b0-4edd-4e21-9ea5-d12aa3027cb5" /> | <img width="872" height="664" alt="gambar 2" src="https://github.com/user-attachments/assets/4d99ec06-39b8-4b06-98ff-41f93ce519ad" />
|
| **gambar 1.** PC1 dengan alamat ip **192.168.1.1** default gateway 192.168.1.10.   | **gambar 2.** PC2 dengan alamat ip **192.168.1.2** default gateway 192.168.1.10.|

          

<img width="877" height="668" alt="image" src="https://github.com/user-attachments/assets/d75123e5-a5cf-4de3-90b4-deaa4011c838" />    <img width="873" height="668" alt="image" src="https://github.com/user-attachments/assets/c7e1980a-b36f-43e2-9ae6-241148bdd5db" />

**gambar 3.** PC3 dengan alamat ip **192.168.2.1** default gateway 192.168.2.10.            **gambar 4.** PC4 dengan alamat ip **192.168.2.2** default gateway 192.168.2.10.

<img width="876" height="665" alt="image" src="https://github.com/user-attachments/assets/66d0faa3-7737-46b1-bb2c-7d46ad914002" />    <img width="877" height="665" alt="image" src="https://github.com/user-attachments/assets/54e66921-5a09-44f0-a75e-0ec3e0657355" />

**gambar 5.** PC5 dengan alamat ip **192.168.3.1** default gateway 192.168.3.10.            **gambar 6.** PC6 dengan alamat ip **192.168.3.2** default gateway 192.168.3.10.

## Konfigurasi Statik Routing

<img width="874" height="589" alt="image" src="https://github.com/user-attachments/assets/156125c2-1dc8-493d-b02c-8d6af3b90283" />    <img width="877" height="591" alt="image" src="https://github.com/user-attachments/assets/04ffcb0e-9657-4b9c-a6ef-a7d04e1d2e22" />

**gambar 7.** Konfigurasi router 1 Fa0/0                  **gambar 8.** Konfigurasi router 1 S2/0  

<img width="877" height="590" alt="image" src="https://github.com/user-attachments/assets/d06a0173-462f-452b-922f-75455bfa79a0" />    <img width="873" height="591" alt="image" src="https://github.com/user-attachments/assets/14bd985e-ca66-4cc7-a6ce-ffddad999980" />

**gambar 9.** Konfigurasi router 1 Statik Routing         **gambar 10.** Konfigurasi router 2 Fa0/0   
