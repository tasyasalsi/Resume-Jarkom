# Resume Materi Jaringan Komputer Lanjut

Disusun oleh:  
**Natasya Salsi Anugrah**  
NIM: **20210801158**  

---

## Daftar Isi

1. [Pengulangan Mengenai IP](#pengulangan-mengenai-ip)
2. [Model OSI](#model-osi)
3. [Subnetting](#subnetting)
4. [Routing dengan Mikrotik](#routing-dengan-mikrotik)
    - [Routing Statis](#routing-statis)
    - [Routing DHCP](#routing-dhcp)
5. [Network Address Translation (NAT)](#network-address-translation-nat)
6. [Firewall](#firewall)
7. [Bridge](#bridge)
8. [Dynamic Routing](#dynamic-routing)

---

## Pengulangan Mengenai IP

Pada awal perkuliahan, materi yang dibahas adalah pengulangan konsep dasar mengenai IP Address. Pembahasan mencakup:

- **IPv4**: Memiliki format 32-bit.
- **IPv6**: Memiliki format 128-bit.
- Konsep kelas IP (A, B, C, D, dan E).

---

## Model OSI

![image](https://github.com/user-attachments/assets/d9c0c573-1bf2-4e30-bfcf-340e9c011554)

Pada pertemuan berikutnya, dosen membahas mengenai **OSI Model** yang terdiri dari 7 lapisan. Setiap lapisan memiliki fungsi spesifik, seperti mengirim data secara fisik pada lapisan pertama, dan lain-lain. Pemahaman tentang model ini sangat penting untuk memahami bagaimana cara data berpindah melalui jaringan.

---

## Subnetting

Subnetting adalah teknik untuk membagi jaringan besar menjadi jaringan yang lebih kecil. Materi ini melibatkan:

- Penggunaan **CIDR (Classless Inter-Domain Routing)** untuk alokasi IP Address.
- Rumus-rumus seperti perhitungan jumlah subnet dan host per-subnet.

---

## Routing dengan Mikrotik

### Routing Statis

Implementasi routing statis pada Mikrotik menggunakan WinBox:

1. Buka menu **Addresses** di WinBox:
    - Masuk ke WinBox dan pastikan perangkat Mikrotik sudah terhubung melalui kabel LAN.
    - Buka menu **IP** > **Addresses**.
2. Tambahkan IP Address baru:
    - Klik tombol **Add** untuk menambahkan Address baru.

### Routing DHCP

Implementasi routing DHCP pada Mikrotik:

1. **Menambahkan IP Address di Mikrotik**:
    - Dalam WinBox > **IP** > **Addresses**.
    - Tambahkan IP Address baru (contoh: `192.168.10.1/24`).
    - Sesuaikan interface dengan port **ether** yang digunakan.
2. **Pengaturan IP di Laptop**:
    - Buka **Control Panel** > **Network and Internet** > **Network and Sharing Center** > **Ethernet** > **Properties**.
    - Ubah pengaturan IPv4 ke **Obtain an IP Address automatically**.
3. **Menambahkan DHCP Server di Mikrotik**:
    - Dalam WinBox > **IP** > **DHCP Server**.
    - Pilih **DHCP Setup**.
    - Sesuaikan interface dengan port yang digunakan dan ikuti langkah-langkah hingga selesai.
4. **Mengecek Alokasi IP di DHCP Server**:
    - Lihat bagian **Leases** di menu DHCP Server.
    - Lakukan **Ping** ke IP Address aktif melalui Terminal WinBox.

---

## Network Address Translation (NAT)

NAT adalah teknik untuk menerjemahkan **IP privat** menjadi **IP publik** saat perangkat dalam jaringan lokal mengakses internet. Manfaat NAT:

- Menghemat alamat IP yang terbatas.
- Meningkatkan keamanan jaringan.

---

## Firewall

**Firewall** adalah komponen penting untuk melindungi jaringan dari ancaman dengan mengontrol lalu lintas data.

---

## Bridge

### Deskripsi

Bridge adalah jaringan yang menghubungkan dua atau lebih segmen jaringan, sehingga perangkat di jaringan yang berbeda bisa berkomunikasi dalam satu jaringan yang sama.

### Implementasi Bridge di Mikrotik

1. **Menambahkan Bridge Baru**:
    - Dalam WinBox > **Bridge** > Tambahkan Bridge baru > **Apply** > **OK**.
2. **Menambahkan Bridge Port**:
    - Sesuaikan interface dengan port **ether** yang digunakan.
    - Hubungkan dengan Bridge yang sudah dibuat.
3. **Menetapkan IP Address pada Bridge**:
    - Tambahkan IP Address baru.
    - Ubah interface ke Bridge yang dibuat.
4. **Menambahkan DHCP untuk Bridge**:
    - Tambahkan DHCP Server dengan DHCP Setup.
    - Sesuaikan interface dengan Bridge yang dibuat.
    - Ubah DNS Servers ke `8.8.8.8`.
5. **Menguji Koneksi Antar Laptop**:
    - Lihat **IPv4 Address** melalui Command Prompt dengan perintah `ipconfig`.
    - Lakukan **Ping** antar perangkat.
6. **Mengakses Web XAMPP**:
    - Nyalakan server web XAMPP.
    - Gunakan IP Address laptop untuk mengakses web melalui jaringan yang sama.

---

## Dynamic Routing

**Dynamic Routing** adalah teknik yang digunakan untuk memilih jalur terbaik secara otomatis dalam pengiriman data melalui jaringan. Mahasiswa belajar mengimplementasikan protokol routing dinamis pada Mikrotik untuk otomatis memilih jalur terbaik.

---

Terima kasih telah membaca resume ini! Jangan ragu untuk memberikan saran dan masukan.

