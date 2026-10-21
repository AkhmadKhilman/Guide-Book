# 💻 Panduan Lengkap & Praktis Instal Ulang (Inul) Windows 11 (Single Boot)

> **Disusun untuk Semua Merek Laptop, Segala Spesifikasi (Standar hingga Gaming), dan Teroptimasi Penuh (Bebas Bloatware & Hemat RAM).**

---

## 📋 Daftar Isi
1. [Pendahuluan: Persiapan & Backup Data](#1-pendahuluan-persiapan--backup-data)
2. [Poin 1: Mempersiapkan Alat Tempur & Flashdisk Bootable](#poin-1-mempersiapkan-alat-tempur--flashdisk-bootable)
3. [Poin 2: Eksekusi Instalasi Windows 11 (GUI Terbaru)](#poin-2-eksekusi-instalasi-windows-11-gui-terbaru)
4. [Poin 3: Update Driver & Kunci Windows Update Selamanya](#poin-3-update-driver--kunci-windows-update-selamanya)
5. [Poin 4: Debloat & Optimasi Super Bersih Menggunakan WinUtil](#poin-4-debloat--optimasi-super-bersih-menggunakan-winutil)

---

## 1. Pendahuluan: Persiapan & Backup Data

Sebelum memformat laptop, pastikan Anda menyelamatkan data-data penting. 
*   **Pindahkan ke Penyimpanan Eksternal:** Hardisk eksternal, Flashdisk khusus data, atau Google Drive. *(Catatan: Jangan satukan data ke Flashdisk yang akan dijadikan alat inul, karena Flashdisk tersebut akan dihapus total).*
*   **Data Wajib Backup:** Isi folder `Desktop`, `Documents`, `Downloads`, `Pictures`, `Videos`, data Sinkronisasi Browser (Bookmark/Password), serta *file* mentahan proyek koding/desain Anda.
*   **Jika Laptop Memiliki 2 Partisi (Drive C & D) dan Hanya Ingin Inul Drive C:** Pindahkan semua data penting ke Drive D, lalu ubah nama Drive D Anda menjadi **`DATA_JANGAN_DIHAPUS`** (Klik kanan Drive D -> *Rename*) beserta catat ukuran GB-nya agar tidak salah hapus nantinya.

---

## 🛠️ Poin 1: Mempersiapkan Alat Tempur & Flashdisk Bootable

Tahap ini sangat krusial. Pembuatan alat instalasi (Rufus) yang benar menjamin kelancaran inul.

### 1.1. Siapkan Fisik
*   **1 Buah Flashdisk:** Minimal kapasitas **8 GB** (Disarankan 16-32 GB).
*   **Charger Laptop:** Wajib dicolokkan ke listrik selama proses instalasi.
*   **Mouse Eksternal (USB/Wireless):** **[SANGAT PENTING UNTUK LAPTOP KELUARAN 2020 KE ATAS]** Laptop modern (Intel Gen 10+ / AMD Ryzen baru) sering kali mematikan fungsi *touchpad* saat layar instalasi berjalan karena belum ada *driver*. Siapkan *mouse* eksternal untuk berjaga-jaga. *(Jika Anda memakai laptop lawas, touchpad biasanya aman dan langsung berfungsi).*

### 1.2. Unduh 3 Bahan Utama (Klik Langsung pada Tautan)
1.  **File ISO Resmi Windows 11 (64-bit):**
    *   Buka: **[Situs Resmi Download Windows 11](https://www.microsoft.com/software-download/windows11)**
    *   Gulir ke bawah pada opsi ke-3: **Download Windows 11 Disk Image (ISO)**. Pilih `Windows 11 (multi-edition)` -> Klik **Download Now** -> Pilih Bahasa `English (United States)` -> Klik **Confirm** -> Klik tombol biru **64-bit Download**.
2.  **Aplikasi Rufus (Pembuat Bootable):**
    *   Buka: **[Situs Resmi Rufus](https://rufus.ie/)**
    *   Gulir ke bagian unduhan dan klik versi **`rufus-4.x.exe`**.
3.  **Driver Wi-Fi & Touchpad (Sesuai Merek Laptop Anda):**
    *   Buka Google, ketik `Support Driver [Merek & Tipe Laptop Anda]`. Masuk ke situs resminya, lalu unduh *file* instalasi untuk **Wireless LAN / Wi-Fi** dan **Intel Serial IO / Touchpad** (jika ada).
    *   *(Alternatif darurat: Siapkan kabel data HP untuk berbagi koneksi internet via "USB Tethering" jika Wi-Fi mati pasca-inul).*

### 1.3. Membuat Bootable Flashdisk (Menggunakan Rufus)
1.  Colokkan Flashdisk ke laptop. Buka aplikasi **Rufus**.
2.  Pastikan nama Flashdisk Anda terpilih di kolom **Device**.
3.  Klik tombol **SELECT**, lalu cari dan pilih *file* `ISO Windows 11` yang baru saja diunduh.
4.  Pada **Partition scheme**, pilih **GPT** (Standar laptop modern).
5.  Klik tombol **START** di bagian bawah.
6.  **KRUSIAL (Jendela Windows User Experience):** Saat muncul kotak centang, **WAJIB CENTANG 3 OPSI INI**:
    *   ✅ `Remove requirement for 4GB+ RAM, Secure Boot and TPM 2.0` *(Mencegah laptop ditolak).*
    *   ✅ `Remove requirement for an online Microsoft account` *(Mencegah paksaan login akun).*
    *   ✅ `Disable data collection (Skip privacy questions)` *(Mematikan fitur pelacakan).*
    *   Klik **OK** dan tunggu proses hingga tulisan berubah menjadi hijau **READY**. Klik **CLOSE**.
7.  Buka Flashdisk Anda di File Explorer, buat folder bernama **`DRIVER_CADANGAN`**, lalu masukkan *file* unduhan *Driver Wi-Fi* dan *Touchpad* tadi ke dalamnya.

---

## 🚀 Poin 2: Eksekusi Instalasi Windows 11 (GUI Terbaru)

> [!WARNING]
> **Aturan Emas Masuk ke Menu Flashdisk:**
> Anda **WAJIB** masuk menggunakan metode *One-Time Boot Menu* (Menu Boot Sementara). **JANGAN PERNAH** masuk ke dalam BIOS lalu memindahkan posisi Flashdisk menjadi nomor 1 secara permanen. Hal ini untuk mencegah laptop *looping* (mengulang instalasi terus-menerus).

### 2.1. Masuk ke Boot Menu
1.  Matikan laptop sepenuhnya (`Shift` + Klik *Shut down*).
2.  Nyalakan laptop, dan detik itu juga tekan secara cepat/berulang kali tombol **Boot Menu**:
    *   **ASUS:** `Esc` | **Acer / Lenovo / Dell:** `F12` | **HP:** `F9` | **MSI:** `F11`
    *   *(Khusus Lenovo, Anda juga bisa menusuk lubang kecil berlogo panah / Novo Button di samping bodi saat laptop mati).*
3.  Di layar menu yang muncul, pilih baris **`UEFI: [Nama Flashdisk Anda]`** dan tekan `Enter`.

### 2.2. Mengatasi Touchpad Mati Tanpa Mouse (Navigasi Keyboard)
Jika *touchpad* Anda tiba-tiba tidak bisa digerakkan di layar Setup, gunakan kombinasi 5 tombol *keyboard* berikut untuk menyelesaikan seluruh instalasi:
*   **`Tab`**: Memindahkan sorotan kotak ke tombol/menu selanjutnya. *(Tekan `Shift + Tab` untuk mundur).*
*   **`Spasi`**: Memberi atau melepas tanda centang (✅).
*   **`Panah Kiri/Kanan/Atas/Bawah`**: Bergerak antar-menu atau baris partisi.
*   **`Enter`**: Berfungsi sebagai "Klik Kiri" / OK.

### 2.3. Langkah Instalasi (Tampilan Windows 11 24H2 Terbaru)
*Anda akan melihat latar belakang layar penuh berwarna **Biru Tua / Ungu Gelap**, dengan sebuah **Jendela Kotak Berwarna Putih** di tengahnya.*
1.  Pada layar bahasa, biarkan *English (US)* -> Klik **Next**.
2.  Pilih *keyboard US* -> Klik **Next**.
3.  Pilih bulatan **`Install Windows 11`** -> Centang kotak peringatan **`I agree that everything will be deleted...`** -> Klik **Next**.
4.  Jika diminta *Product Key*, klik tulisan **`I don't have a product key`** di bagian bawah. Pilih edisi OS (contoh: *Home Single Language* atau *Pro*) -> **Accept**.

### 2.4. Strategi Tabel Partisi (Sangat Penting)
> [!IMPORTANT]
> Perhatikan kolom sebelah kiri (`Drive 0` / `Drive 1`). Salah satu *Drive* yang berukuran kecil (misal 14GB atau 29GB) adalah Flashdisk Rufus Anda. **JANGAN PERNAH MENGHAPUS FLASHDISK!**

*   **Untuk SSD 256 GB:** Hapus (`Delete Partition`) semua baris milik **Drive 0** satu per satu (termasuk partisi Linux/Dual Boot jika ada) sampai hanya tersisa satu baris **`Drive 0 Unallocated Space`**. Langsung klik **Next**. *(Disarankan 1 partisi C penuh).*
*   **Untuk Inul Drive C Tanpa Menghapus Data Drive D:** Hapus partisi sistem lama (C, System, Recovery, MSR) saja. Biarkan baris bernama **`DATA_JANGAN_DIHAPUS`** utuh. Sorot ruang *Unallocated Space* hasil penghapusan C, lalu klik **Next**.

### 2.5. Aturan Saat Laptop Restart Pertama Kali
Saat instalasi menyalin *file* dan muncul hitung mundur **`Windows needs to restart to continue`**, **BIARKAN SAJA DAN JANGAN CABUT FLASHDISK ANDA!**
Karena kita menggunakan metode *Boot Menu* sementara, laptop akan otomatis mengunci SSD internal sebagai prioritas saat menyala kembali. Flashdisk akan tetap aman di lubang USB untuk keperluan pasang *driver* nanti.

### 2.6. Bypass Layar OOBE (Tanpa Paksaan Akun & Internet)
1.  Pilih *Region Indonesia* -> *Keyboard US* -> *Skip*.
2.  **Layar Wi-Fi:** Jangan konek internet! Lihat ke pojok kanan bawah, klik **`I don't have internet`**.
    *   *(Jika tombol itu tidak ada: Tekan `Shift + F10`, ketik `OOBE\BYPASSNRO` lalu tekan `Enter`. Setelah laptop restart otomatis, tombol "I don't have internet" akan muncul. Klik!)*
3.  Klik **`Continue with limited setup`**.
4.  Masukkan nama Anda (misal: *Budi*). Kosongkan *password*.
5.  Matikan (Off) semua sakelar pengaturan privasi -> **Accept**. Selamat datang di Desktop!

---

## 🔄 Poin 3: Update Driver & Kunci Windows Update Selamanya

### 3.1. Pasang Internet & Update Semua Driver
1.  Jika *touchpad* atau Wi-Fi mati, buka `File Explorer` -> buka Flashdisk -> masuk ke folder `DRIVER_CADANGAN` -> *Install driver* Anda (atau gunakan USB Tethering HP).
2.  Tekan `Windows + I` (Settings) -> **Windows Update** -> **Check for updates**.
3.  Buka **Advanced options** -> **Optional updates** -> Centang **semua** baris *Driver* yang tersedia -> Klik **Download & install**.
4.  Tunggu dan biarkan laptop me-restart berulang kali jika diminta, sampai Windows Update mencentang hijau bertuliskan **You're up to date**.

### 3.2. Jeda Windows Update Secara Paksa (Via Registry Editor)
Agar Windows Update tidak berjalan diam-diam dan menyedot kuota:
1.  Buka `Settings` -> `Windows Update` -> Klik tombol **`Pause for 1 week`** satu kali.
2.  Tekan `Windows + R`, ketik `regedit`, tekan `Enter`.
3.  Tempel (Paste) alamat ini di kotak atas Registry Editor:
    `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsUpdate\UX\Settings`
4.  Di panel kanan, ubah tahun pada 3 *file* berikut ke tanggal masa depan (misal: `2240-10-30T01:03:57Z`):
    *   `PauseFeatureUpdatesEndTime`
    *   `PauseQualityUpdatesEndTime`
    *   `PauseUpdatesExpiryTime`
5.  Cek `Windows Update`, sekarang pembaharuan Anda telah ditunda hingga tahun 2240!

---

## 🧹 Poin 4: Debloat & Optimasi Super Bersih Menggunakan WinUtil

Tahap ini akan menurunkan penggunaan RAM dari 4 GB (idle) menjadi di bawah 2 GB, serta menghilangkan seluruh aplikasi sampah bawaan pabrik.

### 4.1. Membuka WinUtil
1.  Klik Kanan tombol Start (Logo Windows) -> Buka **Terminal (Admin)** atau **PowerShell (Admin)** -> Klik **Yes**.
2.  Salin dan tempel perintah berikut secara persis, lalu tekan `Enter`:
    ```powershell
    irm christitus.com/win | iex
    ```
3.  Tunggu beberapa saat hingga jendela **WinUtil** berlatar gelap terbuka. Klik tab **`Tweaks`** di bagian atas.

### 4.2. Pengaturan Tweak Wajib (Golden Settings)
Jangan gunakan tombol otomatis. Centang kotak-kotak di bawah ini secara manual untuk hasil paling maksimal dan stabil:

**[KOLOM KIRI ATAS] Essential Tweaks:**
✅ `Activity History - Disable`
✅ `ConsumerFeatures - Disable`
✅ `Delivery Optimization - Disable`
✅ `End Task With Right Click - Enable`
✅ `File Explorer Automatic Folder Discovery - Disable`
✅ `Hibernation - Disable` *(Mengembalikan ruang SSD ~4-8GB)*
✅ `Location Tracking - Disable`
✅ `Microsoft Store Recommended Search Results - Disable`
✅ `Prevent Device Companion Apps`
✅ `Restore Point - Create`
✅ `Services - Set to Manual` *(Kunci utama hemat RAM)*
✅ `Telemetry - Disable`
✅ `Temporary Files - Remove`
✅ `Widgets - Remove`
✅ `Windows Platform Binary Table (WPBT) - Disable`

**[KOLOM KIRI BAWAH] Advanced Tweaks - CAUTION:**
✅ `Background Apps - Disable`
✅ `Disable Reserved Storage` *(Mengembalikan ruang 7GB)*
✅ `File Explorer Home and Gallery - Disable`
✅ `Logitech / Razer Software Auto-Install - Disable`
✅ `Microsoft OneDrive - Remove`
✅ `Right-Click Menu Previous Layout - Enable` *(Menu klik kanan gaya Windows 10!)*
✅ `Windows AI - Disable And Remove` *(Hapus Copilot)*

> **PILIHAN UNTUK MICROSOFT EDGE (PILIH SALAH SATU JALUR INI):**
> *   **Jalur A (Anda Pakai Brave/Chrome Saja):** Centang ✅ `Microsoft Edge - Remove` dan ✅ `Brave Browser - Debloat`. *(Catatan: Pastikan Anda sudah mengunduh browser lain terlebih dahulu!).*
> *   **Jalur B (Anda Tetap Butuh Edge Kantoran):** Cukup centang ✅ `Microsoft Edge - Debloat` saja.

**[KOLOM KANAN] Customize Preferences (Sakelar Instan):**
*   **BIRU (Aktifkan):** `Dark Theme`, `Enable Long Paths`, `File Explorer File Extensions`, `Game Mode`, `Lock Screen - Disable`, `Taskbar Centered Icons`, `Window Snapping`.
*   **ABU-ABU (Matikan):** `Mouse Acceleration`, `Start Menu Bing Search` *(Wajib mati agar start menu ngebut!)*, `Start Menu Recommendations`, `Sticky Keys`.

**EKSEKUSI TWEAKS:**
Klik tombol **`Run Tweaks`** di pojok kiri bawah.
> [!TIP]
> **INFO ERROR PALSU (FALSE POSITIVE):** Jika Anda memilih jalur hapus Edge, dan log PowerShell menunjukkan tulisan merah `Cannot find path 'C:\Program Files (x86)\Microsoft\Edge\Application' because it does not exist`, **Anda tidak perlu panik!** Itu artinya skrip berjalan sukses dan Microsoft Edge Anda memang sudah terhapus sempurna sehingga skrip tidak bisa menemukan foldernya lagi. 

### 4.3. Menghapus Aplikasi Bawaan (AppX Removal) yang Sangat Agresif
Banyak aplikasi bawaan Windows yang memakan memori. Klik tombol **`AppX Removal`** di pojok kanan atas jendela *Tweaks*, lalu lakukan pembersihan berikut:

1.  **HAPUS SEMUA (Centang Semua Baris)** pada kategori ini:
    *   **Microsoft Apps** *(Feedback, Microsoft 365 portal, Teams, Outlook)*
    *   **Microsoft Ecosystem** *(Phone Link, Mobile Devices)*
    *   **Bing & Web Services** *(Copilot, News, Weather, dll)*
    *   **Developer Tools** *(Dev Home, Power Automate)*
2.  **Utilities & Productivity (Hapus yang tidak perlu):**
    *   **Centang Hapus:** `Clipchamp`, `Movies & TV`, `Quick Assist`, `Sticky Notes`, `To Do`.
    *   **Hapus Juga (Sangat Direkomendasikan):** `Snipping Tool`, `Paint`, `Media Player`.
    *   *(Jangan Khawatir: Tombol `Win + Shift + S` untuk screenshot akan TETAP BERFUNGSI dan tersimpan otomatis di folder `Pictures > Screenshots`. Aplikasi **Photos** bawaan sudah mencakup fitur pemutaran video dasar (MP4), pemotongan (crop), serta corat-coret gambar, sehingga Paint dan Snipping Tool menjadi sampah yang berlebihan).*
    *   **Biarkan Kosong (Jangan Dihapus):** `Calculator`, `Camera`, `Clock`, `Photos`, `Notepad`, `Sound Recorder`.
3.  **Xbox & Gaming:**
    *   **Jika Anda murni bekerja, pakai Emulator, atau main di Steam:** Centang semuanya *(Hapus seluruh elemen Xbox)*.
    *   **Jika main game dari Microsoft Store (Minecraft/Forza):** Hapus `Solitaire Collection` dan `Xbox App` saja. **Biarkan kosong** `Xbox Identity Provider`, `Game Bar`, dan `TCUI` agar Anda tetap bisa *login* ke dalam *game*.

Klik tombol **`Remove Selected`** di bagian bawah. Setelah selesai, klik `Back to Tweaks`, tutup aplikasi WinUtil, lalu **Restart Laptop Anda**.

**SELAMAT! Windows 11 Anda Kini Telah Berada Pada Kondisi Paling Sempurna, Cepat, dan Bersih.**