# LAPORAN JHASIL SCANNING NMAP PADA METASPLOITABLE2

## Informasi Target Metasploitable2

IP Address : **192.168.100.11 target**

Hostname : **target**

**Command : `_nmap -n -Pn target_**

<img width="941" height="542" alt="Screenshot 2025-11-18 152238" src="https://github.com/user-attachments/assets/69d4dc07-aa3b-4473-869f-9edb8cecae5c" />

**Analisis Hasil Scanning Nmap**
- Nmap mendeteksi banyak port terbuka pada IP 192.168.100.11, menunjukkan bahwa target adalah Metasploitable 2, sebuah VM yang memang dirancang untuk tujuan belajar keamanan dan penetrasi.

- Setiap baris menunjukkan nomor port, Penjelasan Port yang Terbuka :
  
1. 21/tcp (FTP): Menggunakan protokol File Transfer Protocol untuk transfer file antara client dan server. Port 21 digunakan sebagai channel kontrol perintah untuk login dan manipulasi file.​

2. 22/tcp (SSH): Secure Shell adalah protokol remote secara terenkripsi, biasanya untuk login ke shell/terminal server dengan keamanan lebih baik dibanding Telnet.​

3. 23/tcp (Telnet): Protokol remote shell tanpa enkripsi, sehingga data login bisa mudah diambil/diintip oleh attacker. Sering tidak direkomendasikan di jaringan publik.​

4. 25/tcp (SMTP): Protokol untuk transfer email melalui Simple Mail Transfer Protocol.

5. 53/tcp (DNS): Domain Name System untuk resolusi nama menjadi IP.

6. 80/tcp (HTTP): Protokol web untuk akses website dan aplikasi berbasis browser.

7. 111/tcp (RPCbind): Digunakan untuk remote procedure call, biasanya pendukung NFS.

8. 139/tcp (NetBIOS-SSN): Protokol file sharing di jaringan Windows (NetBIOS Session Service).

9. 445/tcp (Microsoft-DS): Digunakan untuk layanan SMB (Server Message Block) versi terbaru, sering jadi target exploitasi ransomware.

10. 512/tcp (exec): Protokol eksekusi perintah secara remote, biasanya pada sistem UNIX lama.

11. 513/tcp (login): Digunakan untuk layanan login remote pada UNIX.

12. 514/tcp (shell): Protokol shell remote untuk eksekusi perintah sistem.

13. 1099/tcp (RMIRegistry): Java Remote Method Invocation Registry, sering digunakan di lingkungan Java.

14. 1524/tcp (Ingreslock): Port default untuk database Ingres.

15. 2121/tcp (ccproxy-ftp): Alternatif FTP server pada port selain 21.

16. 3306/tcp (MySQL): Port standar untuk database MySQL.

17. 5432/tcp (PostgreSQL): Port standar untuk database PostgreSQL.

18. 5900/tcp (VNC): Untuk remote desktop menggunakan Virtual Network Computing.

19. 6000/tcp (X11): Protokol untuk graphical remote session X11.

20. 6667/tcp (IRC): Internet Relay Chat, server untuk komunikasi chat secara real-time.

21. 8009/tcp (ajp13): Protokol Apache JServ untuk komunikasi Java servlet.

22. 8180/tcp (HTTP alternatif/unknown): Biasanya digunakan untuk aplikasi web pada port selain 80.

# ⚠ Kesimpulan Keamanan

Target *192.168.100.11* memilikibanyak port yang dan hampir seluruh *service* menggunakan versi lama (Outdated). Setiap port di atas mengindikasikan layanan tertentu yang bisa menjadi target eksploitasi sesuai skenario pembelajaran cyber security dan penetration testing. Ini adalah ciri khas **Metasploitable2**, sebuah sistem yang dirancang secara *vulnerable* untuk tujuan pelatihan *penetration testing* dan edukasi keamanan. 

**Command : `_nmap -n -Pn -p- -A target_**

<img width="1293" height="807" alt="Screenshot 2025-11-18 152318" src="https://github.com/user-attachments/assets/c214e444-31ba-4f59-96dc-dc6803bf8484" />
<img width="1392" height="835" alt="Screenshot 2025-11-18 152337" src="https://github.com/user-attachments/assets/5a107389-1b43-4ac2-96e6-71d4f3b01d4d" />

**Penjelasan Masing-masing Port (Metasploitable 2)**
**FTP & Auth**
**21/tcp – FTP (vsFTPd 2.3.4)**
- Layanan untuk transfer file.
- Versi 2.3.4 punya backdoor bug yang terkenal → celah eksploit.

**22/tcp – SSH (OpenSSH 4.7p1)**
- Remote login ke server.
- Versi lama, banyak vulnerability.

**Remote Shell / Remote Access**
**23/tcp – Telnet**
- Remote login tanpa enkripsi.
- Sangat tidak aman.

**512/tcp, 513/tcp, 514/tcp – rlogin / rexec / rsh**
- Protokol remote command jadul.
- Tidak terenkripsi → mudah di-sniff.

**5900/tcp – VNC**
- Akses remote desktop.
- Versi lama (proto 3.3) → rentan.

**Web Services**
**80/tcp – HTTP (Apache 2.2.8 + DAV2)**
- Server web utama.
- Banyak CVE untuk versi ini.

**8180/tcp – Apache Tomcat 5.5**
- Menjalankan JSP & aplikasi Java.
- Tomcat 5.5 memiliki default creds: tomcat:tomcat (sering jadi pintu masuk).

**8009/tcp – AJP13 (Apache Jserv Protocol)**
- Protokol internal Tomcat.
- Pernah populer dengan bug “Ghostcat”.

**Database**
**3306/tcp – MySQL 5.0.51a**
- Database SQL.
- Sering dipakai untuk eksploit SQL injection atau default password.

**5432/tcp – PostgreSQL 8.3**
- Database lain.
- Versi lama dengan banyak auth flaw.

**3632/tcp – distccd**
- Distributed compiler service.
- Sangat rentan (CVE-2004-2687) → RCE gampang.

**Mail Services**
**25/tcp – SMTP (Postfix)**
- Layanan pengiriman email.
- Berguna untuk eksploit enumerasi user.

**DNS**
**53/tcp – BIND 9.4.2**
- Server DNS.
- Banyak bug buffer overflow di versi lama.

**RPC Services**
**111/tcp – rpcbind**
- Mengatur layanan RPC.
- Sering dieksploit untuk NFS atau RCE.

**32764/tcp – mountd**
- Bagian dari NFS.
- Bisa digunakan untuk enumerate credential.

**IRC**
**6667/tcp & 6697/tcp – UnrealIRCd**
- Server IRC.
- UnrealIRCd versi ini memiliki RCE backdoor (sangat terkenal).

**Java / Ruby / RMI**
**8787/tcp – Ruby DRb**
- Distributed Ruby.
- Sangat terbuka untuk RCE.

**8000–9000 range – Java RMI / jmx / rmiregistry**
- Bisa dipakai untuk remote Java object injection.

# Kesimpulan Port Paling Berbahaya


  --------------------------------------------------------------------------------
  Peringkat   Port          Layanan      Tingkat Bahaya     Alasan Kerentanan
  ----------- ------------- ------------ ------------------ ----------------------
  1           6667          UnrealIRCd   Sangat Kritis      Memiliki backdoor
                                                            bawaan → RCE instan

  2           21            vsFTPd 2.3.4 Sangat Kritis      Login ":)" membuka
                                                            shell backdoor
                                                            otomatis

  3           3632          distccd      Sangat Kritis      RCE mudah dengan satu
                                                            perintah/metasploit

  4           8180          Apache       Kritis             Default credentials
                            Tomcat                          memungkinkan upload
                                                            shell

  5           139/445       Samba        Kritis             Vulnerability usermap
                                                            script → root shell

  6           512/513/514   rlogin/rsh   Tinggi             Autentikasi lemah,
                                                            bisa login tanpa
                                                            password

  7           3306          MySQL        Tinggi             Password default /
                                                            kosong, akses DB penuh

  8           5432          PostgreSQL   Tinggi             Konfigurasi lama →
                                                            default credential

  9           80            Apache Web   Sedang             Banyak aplikasi
                            Server                          vulnerable
                                                            (DVWA/Mutillidae)

  10          5900          VNC          Sedang             Kadang tanpa password,
                                                            remote desktop terbuka

  11          22            SSH          Rendah             Versi lama, namun
                                                            tidak mudah
                                                            dieksploitasi
  --------------------------------------------------------------------------------
---

Hasil pemindaian terhadap Metasploitable 2 menunjukkan bahwa sistem memiliki banyak layanan lama dan rentan yang terbuka, sehingga menciptakan permukaan serangan yang sangat luas. Beberapa port seperti UnrealIRCd (6667), vsFTPd 2.3.4 (21), dan distccd (3632) termasuk yang paling kritis karena memungkinkan eksekusi perintah jarak jauh secara langsung tanpa autentikasi yang kuat. Layanan lain seperti Tomcat Manager, Samba, serta database MySQL dan PostgreSQL juga terbuka dengan konfigurasi lemah sehingga mudah disalahgunakan. Temuan ini menegaskan bahwa Metasploitable 2 berada dalam kondisi yang sangat tidak aman dan dapat dieksploitasi dengan berbagai teknik, sehingga cocok digunakan sebagai lingkungan pembelajaran terhadap analisis kerentanan dan eksploitasi sistem.

---
# Directed by: Agung Kurniawan
