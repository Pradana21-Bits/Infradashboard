<img width="1768" height="901" alt="Tampilan awal" src="https://github.com/user-attachments/assets/3a0ea2e1-7ed7-41b4-9d33-6d669e94045d" />


# 🌐 Infradashboard

Sebuah dashboard monitoring infrastruktur modern dan minimalis yang dibangun menggunakan platform [Homepage](https://gethomepage.dev/). Proyek ini berfungsi sebagai pusat kendali terpadu untuk memantau perangkat jaringan lokal, server virtualisasi (hypervisor), serta menyediakan akses cepat ke berbagai pintasan layanan (*bookmarks*) lab mandiri (*homelab*).

---

## 📸 Dokumentasi Dashboard

### 1. Versi Stabil Final
Tampilan dashboard yang sudah dioptimalkan sepenuhnya dan berfungsi normal, menampilkan statistik *real-time* dari router utama dan server hypervisor secara berdampingan:

### 2. Progres Troubleshooting (Riwayat Error)
Selama proses pengembangan dan integrasi API, dashboard ini sempat melewati beberapa fase perbaikan keamanan dan routing jaringan:

* **Isolasi Masalah CORS & API Encodings:** Menyelesaikan masalah kendala `HTTP Error 401` (Unauthorized) saat pertama kali menghubungkan modul API Proxmox VE.
* **Pengamanan Validasi Host:** Menerapkan aturan parameter `HOMEPAGE_ALLOWED_HOSTS` yang tepat untuk mengamankan akses dashboard dari IP lokal maupun melalui Reverse Proxy eksternal.

---

## 🛠️ Integrasi Infrastruktur Utama

Dashboard ini terhubung dan menarik data secara langsung dari beberapa tumpukan teknologi berikut:
* **MikroTik RouterOS API:** Memantau waktu aktif sistem (*uptime*), beban kerja CPU, penggunaan RAM, dan akumulasi jumlah DHCP Leases yang aktif.
* **Proxmox VE Cluster API:** Menggunakan kustomisasi request REST API (*customapi*) untuk membaca metrik performa komputasi inti (*compute load*) serta kapasitas penyimpanan server secara akurat.
* **Pintasan Layanan (Bookmarks):** Akses cepat yang dikelompokkan ke dalam kategori spesifik seperti alat *Developer*, media *Social*, dan platform *Entertainment*.

---

## 🚀 Memulai Instalasi

### Prasyarat
* Sudah menginstal Docker dan Docker Compose di mesin server Anda.
* Memiliki akses jaringan ke API perangkat lokal (Port 80/443 untuk REST API MikroTik, Port 8006 untuk API Proxmox VE).

### Struktur Direktori Proyek
1. Klon repositori ini ke dalam direktori server lokal Anda:
   ```bash
   git clone [https://github.com/Pradana21-Bits/Infradashboard.git](https://github.com/Pradana21-Bits/Infradashboard.git)
   cd Infradashboard
