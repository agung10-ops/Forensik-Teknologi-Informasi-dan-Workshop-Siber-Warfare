# 🖧 Topologi Routing RIP (3 Router, 3 LAN)
## Pendahuluan

    RIP (Routing Information Protocol) adalah protokol routing yang digunakan untuk bertukar informasi 
routing antara router dinamis pada Protokol IP atau IPX. Routing Information Protocol (RIP) adalah salah satu Routing
    Protocol yang menggunakan Distance Vector, oleh karena itu RIP menggunakan jumlah Hop untuk menentukan 
cara terbaik ke sebuah alamat jaringan tertentu, tetapi RIP secara default memiliki jumlah hop maksimum yaitu 15 Hop. 
Oleh karena itu, Hop ke-16 dan seterusnya akan dianggap tidak terjangkau (Unreachable). 
Oleh karena itu juga, RIP dapat bekerja dengan baik di jenis jaringan yang kecil, 
tetapi RIP tidak efisien pada network yang besar atau pada jaringan yang memiliki jumlah Router yang banyak.

# ⚙️ Routing yang Digunakan: RIP (Routing Information Protocol)

RIP adalah protokol distance-vector routing.
Masing-masing router akan bertukar tabel routing dengan router tetangganya secara periodik.
Metode yang dipakai: hop count (jumlah lompatan) untuk menentukan jalur terpendek.
Maksimum hop di RIP adalah 15 → lebih dari itu dianggap unreachable.

# 🔎 Struktur Jaringan

**Router 1**
* Terhubung ke LAN 192.168.1.0/24
    PC1: 192.168.1.1
    PC2: 192.168.1.2
    Gateway (Router1): 192.168.1.100
* Terhubung ke Router 2 lewat link serial dengan IP:
    Router1: 10.10.10.1
    Router2: 10.10.10.2
  
**Router 2 (tengah)**
* Terhubung ke LAN 192.168.2.0/24
    PC3: 192.168.2.1
    PC4: 192.168.2.2
    Gateway (Router2): 192.168.2.100
* Terhubung ke Router 1 via 10.10.10.2
* Terhubung ke Router 3 via 20.20.20.2
  
**Router 3**
* Terhubung ke LAN 192.168.3.0/24
    PC5: 192.168.3.1
    PC6: 192.168.3.2
    Gateway (Router3): 192.168.3.100
* Terhubung ke Router 2 lewat link serial dengan IP:
    Router3: 20.20.20.1
    Router2: 20.20.20.2
  
# 🛠️ Konfigurasi RIP di Router

<img width="881" height="442" alt="image" src="https://github.com/user-attachments/assets/8f2e0976-a060-41c5-9329-5fd7105baeb3" />

**gambar 1.** Konfigurasi router 1 Fa0/0

<img width="880" height="456" alt="image" src="https://github.com/user-attachments/assets/c8dd8132-b9d0-4999-bb30-f96de55099ae" />

**gambar 2.** Konfigurasi router 1 S2/0

<img width="873" height="585" alt="image" src="https://github.com/user-attachments/assets/e899a624-3e56-43f3-b5f5-41624879aecf" />

**gambar 3.** Konfigurasi router 1 RIP Routing

<img width="881" height="459" alt="image" src="https://github.com/user-attachments/assets/0640a9e2-3c58-4f3d-9d0b-0b5148506e12" />

**gambar 4.** konfigurasi router 2 Fa0/0

<img width="874" height="475" alt="image" src="https://github.com/user-attachments/assets/dccd6fc0-b74c-4af1-b729-9e4019f6876f" />

**gambar 5.** Konfigurasi router 2 S2/0

<img width="878" height="451" alt="image" src="https://github.com/user-attachments/assets/faf3bb00-e5ef-43a3-8ec4-9ee1ab3ded4d" />

**gambar 6.** Konfigurasi router 2 S3/0

<img width="877" height="469" alt="image" src="https://github.com/user-attachments/assets/367814e8-590d-4fe2-a6d1-05415bb88cfb" />

**gambar 7**. Konfigurasi router 2 RIP Routing

<img width="879" height="459" alt="image" src="https://github.com/user-attachments/assets/eae16b51-22eb-4a00-9be2-8349c7b67a32" />

**gambar 8.** Konfigurasi router 3 Fa0/0

<img width="879" height="470" alt="image" src="https://github.com/user-attachments/assets/59fbe0ea-e3dd-42ed-8ed0-ed6d625b237e" />

**gambar 9**. Konfigurasi router 3 S3/0

<img width="879" height="464" alt="image" src="https://github.com/user-attachments/assets/caf2c6a0-b96c-4bc5-9525-4bfa6e8e43ce" />

**gambar 10.** Konfigurasi router 3 RIP Routing

# 📡 Cara Kerja Routing RIP

1. Router1 hanya tahu **192.168.1.0/24** dan **10.10.10.0/30.**
  → Dengan RIP, ia akan diberitahu bahwa ada jaringan **192.168.2.0/24** dan **192.168.3.0/24** lewat Router2.

2. Router2 bertindak sebagai hub yang menghubungkan semua jaringan.
  → Ia tahu semua subnet: **192.168.1.0, 192.168.2.0, 192.168.3.0.**

3. Router3 hanya tahu **192.168.3.0/24** dan **20.20.20.0/30.**
  → Dengan RIP, ia akan belajar tentang **192.168.1.0/24** dan **192.168.2.0/24** lewat Router2.

4. RIP akan **secara otomatis update routing table setiap 30 detik,** sehingga jika ada perubahan, rute baru bisa didistribusikan.

# 🔍 Pengujian

  * Dari **PC1 (192.168.1.1)** lakukan ping **192.168.3.2 (PC6).**
    Jalur: PC1 → Switch1 → Router1 → Router2 → Router3 → Switch3 → PC6.

    <img width="878" height="420" alt="image" src="https://github.com/user-attachments/assets/729a429d-8e16-4684-a54a-210c0c20a260" />

    **gambar 11.** Ujicoba Ping dari PC1 ke PC6


  * Dari PC3 (192.168.2.1) lakukan ping 192.168.1.2 (PC2).
    Jalur: PC3 → Router2 → Router1 → PC2.

    <img width="878" height="406" alt="image" src="https://github.com/user-attachments/assets/4bba83fe-ce4c-4060-b48b-ce7770bb6d17" />

    **gambar 12.** Ujicoba Ping dari PC3 ke PC2

  * Semua harus saling terhubung jika konfigurasi benar.

# ✅ Kesimpulan

1. Topologi ini menggunakan 3 router dengan RIP sebagai protokol routing dinamis.
2. Tujuannya agar semua jaringan LAN **(192.168.1.0, 192.168.2.0, 192.168.3.0)** bisa saling terhubung.
3. RIP mempermudah manajemen karena tidak perlu memasukkan routing manual.

# ✍️️ Author
_RIP Routing Oleh Agung Kurniawan_
