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
  
| **gambar 1.** PC1 dengan alamat ip **192.168.1.1** default gateway 192.168.1.10. | **gambar 2.** PC2 dengan alamat ip **192.168.1.2** default gateway 192.168.1.10. |
|------------|------------|
| <img width="877" height="667" alt="gambar 1" src="https://github.com/user-attachments/assets/aa4c83b0-4edd-4e21-9ea5-d12aa3027cb5" /> | <img width="872" height="664" alt="gambar 2" src="https://github.com/user-attachments/assets/4d99ec06-39b8-4b06-98ff-41f93ce519ad" /> |

| **gambar 3.** PC3 dengan alamat ip **192.168.2.1** default gateway 192.168.2.10. | **gambar 4.** PC4 dengan alamat ip **192.168.2.2** default gateway 192.168.2.10. |
|------------|------------|
| <img width="877" height="668" alt="gambar 3" src="https://github.com/user-attachments/assets/56ce40fa-c97b-4a19-aec0-0d3442940be4" /> | <img width="873" height="668" alt="gambar 4" src="https://github.com/user-attachments/assets/4886240a-1d96-4c47-aa19-04e972b44fbd" /> |

| **gambar 5.** PC5 dengan alamat ip **192.168.3.1** default gateway 192.168.3.10. | **gambar 6.** PC6 dengan alamat ip **192.168.3.2** default gateway 192.168.3.10. |
|------------|------------|
| <img width="876" height="665" alt="gambar 5" src="https://github.com/user-attachments/assets/7b413a4a-20b0-4026-b725-d44907ec133e" /> | <img width="877" height="665" alt="gambar 6" src="https://github.com/user-attachments/assets/3b485e60-d9ec-4235-9ba7-e39b44740f13" /> |       

## Konfigurasi Statik Routing

| **gambar 7.** Konfigurasi router 1 Fa0/0  | **gambar 8.** Konfigurasi router 1 S2/0  |
|------------|------------|
| <img width="874" height="589" alt="image" src="https://github.com/user-attachments/assets/156125c2-1dc8-493d-b02c-8d6af3b90283" /> | <img width="877" height="591" alt="image" src="https://github.com/user-attachments/assets/04ffcb0e-9657-4b9c-a6ef-a7d04e1d2e22" /> |              

| **gambar 9.** Konfigurasi router 1 Statik Routing   | **gambar 10.** Konfigurasi router 2 Fa0/0   |
|------------|------------|
| <img width="877" height="590" alt="image" src="https://github.com/user-attachments/assets/d06a0173-462f-452b-922f-75455bfa79a0" /> | <img width="873" height="591" alt="image" src="https://github.com/user-attachments/assets/14bd985e-ca66-4cc7-a6ce-ffddad999980" /> |  

| **gambar 11.** Konfigurasi router 2 S2/0   | **gambar 12.** Konfigurasi router 2 S3/0   |
|------------|------------|
| <img width="874" height="593" alt="image" src="https://github.com/user-attachments/assets/a195a5fa-8c0b-4759-a761-530e238e1d15" /> | <img width="873" height="594" alt="image" src="https://github.com/user-attachments/assets/08267024-3c91-47ef-9172-1429d60924b3" /> |  

| **gambar 13.** Konfigurasi router 2 Statik Routing   | **gambar 14.** Konfigurasi router 3 Fa0/0  |
|------------|------------|
| <img width="871" height="547" alt="image" src="https://github.com/user-attachments/assets/d1f7182d-1807-4de7-8bce-13f509e339d3" /> | <img width="873" height="591" alt="image" src="https://github.com/user-attachments/assets/7c3a6032-2d0b-4afb-9230-edf9bffc6cb5" /> | 

| **gambar 15.** Konfigurasi router 3 S2/0   | **gambar 16.** Konfigurasi router 3 Stattik Routing |
|------------|------------|
| <img width="871" height="591" alt="image" src="https://github.com/user-attachments/assets/d38c8396-a783-4e96-8daf-0351def67438" /> | <img width="872" height="550" alt="image" src="https://github.com/user-attachments/assets/98dc17a7-ad50-452e-bfd6-6af57915b377" /> | 

## 🔎 3. Cara Kerja Static Routing (alur paket)

Misal: PC1 (192.168.1.1) ingin ping ke PC5 (192.168.3.2)

1. PC1 mengirim paket ke gateway Router1 (192.168.1.10).
2. Router1 cek tabel routing:
   - Tujuan 192.168.3.0/24 tidak ada di network langsung (connected).
   - Router1 menemukan static route: 192.168.3.0/24 via 10.10.10.2.
   - Router1 kirim paket ke Router2 (10.10.10.2).
3. Router2 terima paket:
   - Router2 tahu 192.168.3.0/24 harus lewat 20.20.20.2.
   - Router2 forward paket ke Router3.
4. Router3 terima paket:
   - Router3 punya koneksi langsung ke LAN 192.168.3.0/24.
   - Router3 kirim paket ke PC5.
5. PC5 menerima paket, balas echo reply ke PC1 lewat jalur sebaliknya.

## 🔎 Pengujian 

  | Ujicoba Ping PC1 ke PC6 | Ujicoba Ping PC3 ke PC2 |
|------------|------------|
| <img width="874" height="346" alt="image" src="https://github.com/user-attachments/assets/19a09656-6ac4-4f5e-b3b6-0b6d83633bab" /> | <img width="874" height="346" alt="image" src="https://github.com/user-attachments/assets/572b7213-6aef-4e0a-ae85-f74b670f5b92" /> |
| Dari PC1 (192.168.1.1) lakukan ping 192.168.3.2 (PC6). Jalur: PC1 → Switch1 → Router1 → Router2 → Router3 → Switch3 → PC6. | Dari PC3 (192.168.2.1) lakukan ping 192.168.1.2 (PC2). Jalur: PC3 → Router2 → Router1 → PC2. |


## 🔎 5. Kesimpulan Cara Kerja Static Routing

1. Administrator menentukan manual rute untuk jaringan yang tidak langsung terhubung.
2. Router hanya bisa mengirim paket ke jaringan yang ada di tabel routing.
3. Jalur paket tetap sesuai konfigurasi (tidak ada perhitungan otomatis).
4. Jika ada perubahan topologi (misalnya link putus), static routing harus diperbarui manual.
