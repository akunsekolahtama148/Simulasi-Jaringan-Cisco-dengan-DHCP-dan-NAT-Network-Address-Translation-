# 🌐 Simulasi Jaringan Cisco: DHCP & NAT

**Simulasi Jaringan Cisco Menggunakan DHCP dan NAT dengan Cisco Packet Tracer**

## 📌 Deskripsi Project

Project ini merupakan simulasi jaringan komputer menggunakan Cisco Packet Tracer dengan menerapkan teknologi **DHCP (Dynamic Host Configuration Protocol)** dan **NAT (Network Address Translation)**.

Simulasi ini bertujuan untuk memahami proses pembagian IP Address secara otomatis kepada perangkat komputer serta proses penerjemahan IP Private menjadi IP Public agar jaringan lokal dapat berkomunikasi dengan jaringan luar.

## 🎯 Tujuan Project

1. Memahami konsep dasar jaringan komputer.
2. Mengimplementasikan DHCP Server untuk pembagian IP otomatis.
3. Mengonfigurasi NAT Overload (PAT).
4. Menghubungkan jaringan LAN dengan jaringan ISP.
5. Memahami konfigurasi dasar perangkat Cisco Router dan Switch.
6. Melakukan pengujian konektivitas menggunakan perintah Ping.

## 🖥️ Perangkat yang Digunakan

| Perangkat | Jumlah |
|---|---:|
| Cisco Router 2911 | 2 |
| Cisco Switch 2960 | 1 |
| PC | 2 |

## 🗺️ Topologi Jaringan

Topologi jaringan menggunakan dua router, satu switch, dan dua PC.

- **Router 1:** Berfungsi sebagai DHCP Server dan NAT Router.
- **Router 2:** Berfungsi sebagai simulasi ISP.
- **Switch:** Menghubungkan perangkat dalam jaringan LAN.
- **PC 1 dan PC 2:** Client yang memperoleh IP Address secara otomatis melalui DHCP.

## 📡 IP Addressing

| Perangkat | Interface | IP Address |
|---|---|---|
| R1 | G0/0 | 192.168.10.1/24 |
| R1 | G0/1 | 203.0.113.2/30 |
| R2 | G0/0 | 203.0.113.1/30 |
| R2 | Loopback0 | 8.8.8.8/32 |
| PC 1 | DHCP | Automatic |
| PC 2 | DHCP | Automatic |

### Network Information

- LAN Network: `192.168.10.0/24`
- Default Gateway: `192.168.10.1`
- WAN Network: `203.0.113.0/30`
- NAT Public IP: `203.0.113.2`
- DNS Server: `8.8.8.8`

## ⚙️ Teknologi yang Digunakan

**1. DHCP (Dynamic Host Configuration Protocol)**

Digunakan untuk memberikan IP Address, Subnet Mask, Default Gateway, dan DNS Server secara otomatis kepada komputer client.

**2. NAT (Network Address Translation)**

Digunakan untuk menerjemahkan IP Private menjadi IP Public agar perangkat dalam jaringan lokal dapat berkomunikasi dengan jaringan luar.

**3. NAT Overload (PAT)**

Memungkinkan beberapa perangkat menggunakan satu IP Public secara bersamaan dengan membedakan koneksi berdasarkan nomor port.

**4. Static Routing**

Digunakan untuk menentukan jalur komunikasi dari jaringan lokal menuju jaringan ISP.

## 💻 Konfigurasi Jaringan

Konfigurasi utama yang diterapkan pada project ini meliputi:

- Konfigurasi interface Router.
- Pemberian IP Address pada interface.
- Konfigurasi DHCP Pool.
- Konfigurasi NAT Inside dan NAT Outside.
- Konfigurasi NAT Overload.
- Konfigurasi Access Control List (ACL).
- Konfigurasi Default Route.

File konfigurasi tersedia pada folder `Configuration/`.

## 🧪 Pengujian Jaringan

Pengujian dilakukan untuk memastikan seluruh konfigurasi berjalan dengan baik.

Perintah yang digunakan:

```bash
ipconfig
ping 192.168.10.1
ping 192.168.10.22
ping 203.0.113.1
ping 8.8.8.8
```

Pemeriksaan pada Router:

```cisco
show ip dhcp binding
show ip nat translations
show ip nat statistics
show ip route
```

## 📁 Struktur Repository

```text
cisco-dhcp-nat-simulation/
│
├── Configuration/
│   ├── router1-dhcp-nat.txt
│   └── router2-isp.txt
│
├── Documentation/
│   ├── topology.png
│   └── testing.png
│
├── cisco-dhcp-nat.pkt
│
└── README.md
```

## 📊 Hasil Project

Hasil yang diharapkan dari simulasi ini:

- PC mendapatkan IP Address secara otomatis melalui DHCP.
- PC dapat berkomunikasi dengan Default Gateway.
- PC dapat melakukan komunikasi antarperangkat.
- NAT Overload dapat menerjemahkan alamat IP Private.
- PC dapat melakukan Ping ke jaringan ISP melalui Router.

**Catatan:** IP `8.8.8.8` merupakan Loopback pada router ISP untuk simulasi jaringan luar, bukan akses internet sungguhan.

## 🛠️ Software

- Cisco Packet Tracer
- GitHub

## 👨‍💻 Author

**Nama:** Muhammad Ziyan Fadlan  
**Kelas:** [Isi Kelas]  
**Jurusan:** TJKT  
**Mata Pelajaran:** Administrasi Infrastruktur Jaringan (AIJ)

---

⭐ *Project ini dibuat sebagai media pembelajaran dan penerapan konfigurasi jaringan komputer menggunakan Cisco Packet Tracer.*
