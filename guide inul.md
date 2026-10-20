# 💻 Panduan Lengkap (Guidebook) Instal Ulang Windows 11 (Single Boot)

> **Untuk Semua Merek Laptop, Segala Spesifikasi (Laptop Kentang, Standar, hingga Gaming), Berbagai Ukuran Penyimpanan, dan Semua Kalangan Pengguna.**

---

## 📋 Daftar Isi
1. [Pendahuluan: Peringatan, Fungsi, Kelebihan, Kekurangan, & Efek Samping Inul](#-pendahuluan-peringatan-fungsi-kelebihan-kekurangan--efek-samping-inul)
2. [Poin 1: Persiapan & Backup Data di Berbagai Kondisi](#-poin-1-persiapan--backup-data-di-berbagai-kondisi)
3. [Poin 2: Mempersiapkan Alat Tempur Inul (Tahap Paling Krusial)](#-poin-2-mempersiapkan-alat-tempur-inul-tahap-paling-krusial)
4. [Poin 3: Eksekusi Inul, Pembagian Partisi, Update Driver, & Kunci Windows Update Selamanya](#-poin-3-eksekusi-inul-pembagian-partisi-update-driver--kunci-windows-update-selamanya)
5. [Poin 4: Panduan Detail Debloat Windows 11 Menggunakan WinUtil Versi Terbaru](#-poin-4-panduan-detail-debloat-windows-11-menggunakan-winutil-versi-terbaru)
6. [Penutup: Tabel Verifikasi Hasil Akhir (Berhasil vs Gagal) & Kesimpulan](#-penutup-tabel-verifikasi-hasil-akhir-berhasil-vs-gagal--kesimpulan)

---

## 📖 PENDAHULUAN: Peringatan, Fungsi, Kelebihan, Kekurangan, & Efek Samping Inul

**Instal Ulang (Inul)** adalah proses menghapus sistem operasi lama beserta seluruh pengaturannya dan menggantinya dengan sistem operasi Windows 11 baru yang bersih dari nol (*clean install*). Sebelum memutuskan untuk melakukan inul, pahami terlebih dahulu fungsi serta konsekuensinya.

### 1. Fungsi Utama Inul
* Mengatur ulang (*reset*) jembatan komunikasi antara perangkat keras (*hardware*) dan perangkat lunak (*software*) ke kondisi paling segar.
* Menata ulang pembagian ruang penyimpanan (partisi SSD/HDD), misalnya melebur sistem *dual boot* (Windows + Linux) menjadi satu OS Windows saja, atau merombak ukuran partisi C dan D.
* Memperbaiki kerusakan sistem yang sudah tidak bisa disembuhkan dengan cara biasa, seperti layar biru (*Blue Screen of Death* / BSOD), sistem gagal masuk Windows (*bootloop*), atau *file* inti Windows yang rusak (*corrupt*).

### 2. Kelebihan Inul (Dampak Positif)
* **Performa Kembali Maksimal:** Menghapus ribuan *file* sampah (*cache*), sisa aplikasi yang sudah dihapus, dan pengaturan *registry* yang menumpuk selama berbulan-bulan atau bertahun-tahun.
* **Konsumsi RAM & CPU Jauh Lebih Ringan:** Terutama jika dipadukan dengan proses *debloat* (pembersihan aplikasi dan layanan bawaan yang tidak penting), laptop berspesifikasi rendah ("laptop kentang") maupun laptop *gaming* akan mendapatkan ruang RAM kosong yang jauh lebih lega.
* **Bebas dari Virus & Malware Tersembunyi:** Memformat partisi sistem akan memusnahkan *malware*, *adware*, atau *trojan* yang bersembunyi di dalam folder sistem Windows.
* **Ruang Penyimpanan Kembali Lega:** Menghapus tumpukan pembaruan sistem (*Windows Update*) lama yang sering memakan ruang 20 GB hingga 50 GB secara diam-diam.

### 3. Kekurangan & Efek Samping Inul (Risiko yang Harus Diantisipasi)
* **Risiko Kehilangan Data Permanen:** Semua data yang berada di partisi sistem (`Local Disk C:`)—termasuk folder *Desktop*, *Documents*, *Downloads*, *Pictures*, dan *Music*—akan **terhapus bersih**. Jika salah memilih partisi saat proses instalasi, data di partisi lain (seperti Drive D atau E) juga bisa ikut terformat.
* **Waktu Persiapan Kembali (*Downtime*):** Proses inul Windows 11 di SSD hanya memakan waktu sekitar 10–20 menit. Namun, proses menginstal ulang aplikasi kerja, *game*, *driver*, dan masuk (*login*) kembali ke akun-akun Anda bisa memakan waktu beberapa jam.
* **Risiko Lisensi Aplikasi Pihak Ketiga Hangus:** Lisensi Windows 11 bawaan pabrik aman karena tertanam di mesin (*motherboard*). Akan tetapi, aplikasi berbayar tambahan (seperti Microsoft Office pembelian terpisah, Adobe, CorelDRAW, atau aplikasi akuntansi/kerja) bisa meminta kode aktivasi ulang setelah inul.
* **Siklus Tulis SSD (*Terabytes Written* / TBW):** Setiap kali inul, SSD akan menulis ulang sekitar 30–60 GB data. Ini menggunakan sekitar **0,04%** dari total umur SSD modern. Efek ini sangat kecil dan aman selama Anda tidak melakukan inul setiap hari.

> [!WARNING]
> **Himbauan Wajib Sebelum Memulai:**
> Jangan pernah memulai proses inul dalam keadaan terburu-buru atau baterai laptop sekarat. Pastikan Anda memiliki waktu luang minimal 2 jam, koneksi internet yang stabil (Wi-Fi atau tethering HP), charger laptop yang tercolok ke listrik, dan penyimpanan cadangan untuk memindahkan data penting.

---

## 📦 POIN 1: Persiapan & Backup Data di Berbagai Kondisi

Tahap pertama adalah menyelamatkan seluruh data penting Anda ke **penyimpanan eksternal** (Hardisk Eksternal, Flashdisk khusus data, atau *Cloud Storage* seperti Google Drive). **Jangan** menyimpan data *backup* di dalam Flashdisk yang akan dijadikan alat penginstal Windows karena Flashdisk tersebut nantinya akan diformat habis.

### 1.1. Menampilkan File Tersembunyi (Hidden Items)
Banyak data aplikasi, pengaturan, dan *save data game* disimpan di dalam folder yang disembunyikan oleh Windows.
* **Apa yang harus dilakukan:** Buka **File Explorer** (klik ikon map kuning di bagian bawah layar atau tekan tombol `Windows + E` di *keyboard*).
* **Bagaimana caranya:**
  * **Jika saat ini memakai Windows 11:** Lihat ke deretan menu di **bagian atas tengah** jendela File Explorer → klik tulisan **View** → arahkan kursor ke menu **Show** (paling bawah) → klik **Hidden items** dan **File name extensions** hingga muncul tanda centang di sebelah kirinya.
  * **Jika saat ini memakai Windows 10:** Lihat ke **bagian atas** jendela File Explorer → klik tab **View** → lihat ke kotak pengaturan di **sebelah kanan atas**, lalu beri tanda centang pada kotak **Hidden items** dan **File name extensions**.
* **Indikator Berhasil:** Ketika Anda membuka `Local Disk (C:)` → `Users` → `[NamaAnda]`, Anda akan melihat folder bernama **`AppData`** yang warnanya sedikit transparan/pudar.
* **Jika Gagal:** Jika menu **View** tidak terlihat, perbesar jendela File Explorer dengan mengklik ikon **Kotak (Maximize)** di **pojok kanan atas** (di sebelah kiri tombol silang merah `X`).

### 1.2. Daftar Data yang Wajib Diselamatkan (Sesuai Profesi & Penggunaan)
Periksa dan salin (*Copy-Paste*) data berikut ke penyimpanan eksternal Anda:
1. **Pengguna Umum, Pelajar, & Pekerja Kantoran:**
   * Seluruh isi folder **Desktop**, **Documents**, **Downloads**, **Pictures**, **Music**, dan **Videos**.
   * **Data Browser (Bookmark & Password):** Buka browser (Chrome/Edge/Brave) → lihat ke **pojok kanan atas** di bawah tombol silang `X` → klik ikon **Profil** (bulatan foto) → pastikan fitur **Sync is On (Sinkronisasi Aktif)** sudah menyala dengan akun email Anda, atau ekspor *password* ke file cadangan.
   * **Font Tambahan (Bagi Admin/Desainer):** Jika pernah menginstal *font* khusus, buka `Local Disk (C:)` → `Windows` → `Fonts`, lalu salin *font* penting Anda.
2. **Gamer:**
   * Game dari *Steam*, *Epic Games*, atau *Riot* umumnya menyimpan progres di internet (*Cloud Save*). Namun, untuk *game offline* atau *emulator*, salin folder **`AppData\Roaming`**, **`AppData\LocalLow`**, dan folder **`Documents\My Games`** (terletak di `C:\Users\[NamaAnda]\`).
3. **Kreator Konten, Editor Video, & Desainer:**
   * Salin file mentahan proyek, *preset* warna (*LUTs*), *brush* Photoshop/Illustrator, serta pastikan Anda mencatat *email* dan *password* akun lisensi perangkat lunak Anda (pilih menu *Sign Out / Deactivate* di dalam aplikasi tersebut agar lisensinya tidak nyangkut di sistem lama).
4. **Programmer / Teknisi IT:**
   * Salin folder proyek koding Anda (**Wajib hapus dulu** folder `node_modules`, `vendor`, atau `build` di dalam proyek sebelum disalin agar proses *copy* tidak macet berjam-jam).
   * Ekspor *database* lokal (MySQL/PostgreSQL) menjadi file `.sql`, dan salin folder `.ssh` serta `.gitconfig` di `C:\Users\[NamaAnda]\`.

### 1.3. Strategi Backup Berdasarkan Kondisi Awal Laptop Anda
Pilih skenario yang sesuai dengan kondisi laptop Anda saat ini:

* **Kondisi A: Laptop Masih Bawaan Pabrik / Single Boot (Hanya 1 Partisi C)**
  * Anda **wajib** menyalin semua data penting keluar dari laptop menuju Hardisk Eksternal, Flashdisk ke-2, atau Google Drive, karena seluruh isi Drive C akan dihapus bersih.
* **Kondisi B: Laptop Memiliki Partisi C dan Partisi D (Single Boot) & Tidak Ingin Mengubah Ukuran Partisi**
  * Pindahkan semua data penting dari folder *Desktop*, *Documents*, *Downloads* (yang semuanya berada di Drive C) ke dalam **Drive D (`Data`)**.
  * **Sangat Penting:** Ubah nama Drive D Anda menjadi **`DATA_JANGAN_DIHAPUS`** (buka `This PC` → klik kanan pada `Drive D:` → pilih **Rename** → ketik `DATA_JANGAN_DIHAPUS` → tekan Enter) dan **catat ukuran total GB-nya** di kertas agar saat di layar inul nanti Anda tidak salah menghapus partisi.
* **Kondisi C: Ingin Merombak Ulang Ukuran Partisi (Misal: Menggabungkan C dan D, atau Memecah C menjadi C dan D)**
  * Merombak ukuran partisi dari menu instalasi Windows mengharuskan penghapusan partisi yang bersangkutan. Pindahkan **seluruh isi Drive C dan Drive D** ke Hardisk Eksternal terlebih dahulu.
* **Kondisi D: Laptop Dual Boot (Windows + Linux) yang Ingin Dilebur Menjadi 1 OS Windows 11 Saja**
  * Pertama, masuk ke Windows dan salin semua data dari Drive C serta Partisi Penyimpanan Bersama ke Hardisk Eksternal.
  * Kedua, *restart* laptop dan masuk ke sistem operasi **Linux**. Colokkan Hardisk Eksternal, buka *File Manager* Linux, lalu salin semua data yang ada di dalam folder `/home/[nama_user]` (seperti *Documents*, *Downloads*, *Pictures* versi Linux) ke Hardisk Eksternal karena seluruh partisi Linux akan dihapus dan digabungkan ke Windows.

### 1.4. Penanganan Error Umum Saat Proses Backup
* **Error 1: Muncul pesan `"The file '[nama_file]' is too large for the destination file system"` padahal Flashdisk/Hardisk Eksternal masih kosong banyak.**
  * *Penyebab:* Flashdisk/Hardisk Eksternal menggunakan format lama (**FAT32**) yang tidak bisa menampung 1 buah file berukuran di atas **4 GB**.
  * *Solusi:* Buka `This PC` → klik kanan pada Flashdisk/Hardisk Eksternal tersebut (pastikan isinya masih kosong karena langkah ini akan menghapus isinya) → klik **Format...** → pada bagian **File system**, ubah dari `FAT32` menjadi **`NTFS`** atau **`exFAT`** → centang **Quick Format** → klik **Start**.
* **Error 2: Proses Copy-Paste macet di 0% atau muncul pesan `"Destination Path Too Long"`.**
  * *Penyebab:* Ada folder di dalam folder yang berlapis terlalu dalam (lebih dari 260 karakter).
  * *Solusi:* Klik kanan pada folder utama yang ingin disalin → pilih **Compress to ZIP file** (atau *Send to* → *Compressed (zipped) folder*). Setelah berubah menjadi 1 file `.zip`, barulah salin file `.zip` tersebut ke penyimpanan eksternal.

---

## 🛠️ POIN 2: Mempersiapkan Alat Tempur Inul (Tahap Paling Krusial)

Jika pembuatan alat instalasi di tahap ini salah pengaturan, maka saat proses inul berjalan Anda akan menemui jalan buntu (seperti SSD tidak bisa diklik *Next* atau laptop menolak masuk ke menu instalasi).

### 2.1. Persiapan Alat Fisik
1. **1 Buah USB Flashdisk:**
   * **Kapasitas Minimum:** Wajib minimal **8 GB** (Sangat disarankan menggunakan ukuran **16 GB atau 32 GB** agar leluasa menyimpan file *driver* cadangan).
   * **Perhatian:** Seluruh isi di dalam Flashdisk ini akan **terhapus total** saat dijadikan alat instalasi (*bootable*).
2. **Charger Laptop:** Wajib disiapkan untuk dicolokkan selama proses berlangsung.

### 2.2. Mengecek Skema Partisi Laptop Anda Saat Ini (MBR vs GPT)
Sebelum membuat *bootable* Flashdisk, cek apakah penyimpanan laptop Anda menggunakan skema **GPT** (standar laptop modern keluaran 2015 ke atas) atau **MBR** (laptop lawas):
1. **Apa yang harus dilakukan:** Klik kanan pada tombol **Start** (ikon logo Windows di bagian bawah layar) → pilih **Disk Management**.
2. **Bagaimana caranya:**
   * Lihat ke **bagian bawah kiri** jendela *Disk Management*, terdapat kotak abu-abu bertuliskan **`Disk 0`** (tempat Drive C berada).
   * **Klik kanan** tepat pada tulisan **`Disk 0`** tersebut (bukan pada kotak biru `C:` di sebelahnya) → pilih **Properties**.
   * Pada jendela kecil yang muncul, lihat ke deretan tab di **bagian paling atas**, lalu klik tab ke-3 bernama **`Volumes`**.
   * Lihat baris ke-4 yang bertuliskan **`Partition style:`**.
3. **Indikator Berhasil:** Di sebelah kanan `Partition style:` akan tertulis **`GUID Partition Table (GPT)`** atau **`Master Boot Record (MBR)`**. Catat tulisan tersebut (95% laptop yang mendukung Windows 11 menggunakan **GPT**). Tutup jendela *Disk Management*.

### 2.3. Mengunduh 4 Bahan Utama (Wajib Diunduh Sebelum Inul!)
Simpan keempat file unduhan ini di folder `Downloads` laptop Anda terlebih dahulu:

1. **File ISO Resmi Windows 11 (64-bit) dari Microsoft:**
   * Buka browser, kunjungi alamat resmi: `https://www.microsoft.com/software-download/windows11`
   * Gulir halaman ke bawah sampai menemukan judul bagian ke-3: **"Download Windows 11 Disk Image (ISO) for x64 devices"**.
   * Klik kotak *dropdown* **`Select Download`**, pilih **`Windows 11 (multi-edition ISO for x64 devices)`**, lalu klik tombol biru **`Download Now`**.
   * Pilih bahasa **`English (United States)`** atau **`English International`**, klik tombol biru **`Confirm`**, lalu klik tombol biru **`64-bit Download`**.
   * **Indikator Berhasil:** Browser mulai mengunduh file berakhiran **`.iso`** berukuran sekitar **5,2 GB hingga 6,5 GB**. Pastikan unduhan selesai 100%.
   * **Jika Gagal (Muncul pesan merah *"Error: We encountered a problem processing your request"*):** Matikan VPN atau pemblokir iklan (*AdBlock*), atau buka halaman tersebut menggunakan mode penyamaran (*Incognito Window* dengan menekan `Ctrl + Shift + N`).
2. **Aplikasi Pembuat Bootable (Rufus):**
   * Kunjungi: `https://rufus.ie` → gulir ke bagian **Download** di tengah halaman → klik tautan paling atas bertuliskan **`rufus-4.x.exe`** (Standard Windows x64).
3. **Driver Wi-Fi (Wireless LAN) Sesuai Merek Laptop Anda (SANGAT KRUSIAL):**
   * *Mengapa ini wajib?* Installer Windows 11 murni sering kali belum memiliki *driver* Wi-Fi bawaan untuk laptop keluaran terbaru. Tanpa ini, setelah inul selesai Anda tidak bisa menyambung ke Wi-Fi.
   * **Cara Mengunduh:** Buka Google, ketik **`Support Driver [Merek dan Tipe Lengkap Laptop Anda]`** (Contoh: *Support Driver ASUS Vivobook A1404*, *Support Driver Acer Aspire 5 A514*, atau *Support Driver Lenovo IdeaPad Slim 3*). Masuk ke situs resmi merek laptop tersebut → pilih sistem operasi **Windows 11 64-bit** → cari kategori **Networking / Wireless LAN / Wi-Fi** → unduh file `.exe` atau `.zip` *driver* Wi-Fi-nya.
   * **Alternatif Mudah (USB Tethering HP):** Pastikan Anda memiliki **kabel data charger HP**. Jika Wi-Fi laptop belum terdeteksi seusai inul, colokkan HP ke laptop dengan kabel USB dan nyalakan fitur **Penambatan USB (*USB Tethering*)** di pengaturan Hotspot HP untuk menyalurkan internet ke laptop.
4. **Khusus Pengguna Laptop Prosesor Intel Generasi 11, 12, 13, dan 14 (Opsional):**
   * Saat di halaman unduhan *driver* resmi laptop Anda tadi, Anda juga bisa mengunduh **Intel Rapid Storage Technology (IRST / VMD) Driver** pada kategori *Storage/Chipset*. *(Namun di Poin 3.3 C nanti juga dijelaskan cara mengatasi SSD tidak terbaca langsung dari BIOS tanpa perlu driver ini).*

### 2.4. Membuat Bootable Flashdisk Menggunakan Rufus
1. **Colokkan Flashdisk** (minimal 8 GB) ke lubang USB laptop.
2. Buka folder `Downloads`, klik dua kali pada file **`rufus-4.x.exe`** → klik **Yes** jika muncul jendela konfirmasi.
3. Di dalam jendela Rufus, perhatikan pengaturannya **dari atas ke bawah**:
   * **1. Device (Kotak Paling Atas):** Pastikan terpilih **nama dan ukuran Flashdisk Anda**.
   * **2. Boot selection (Baris Kedua):** Klik tombol **`SELECT`** di sebelah kanan → pilih file **`Win11_..._x64.iso`** di folder `Downloads` → klik **`Open`**.
   * **3. Image option (Baris Ketiga):** Biarkan **`Standard Windows installation`**.
   * **4. Partition scheme (Bagian Tengah Kiri):** Pilih **`GPT`** (atau **`MBR`** sesuai hasil pengecekan di Langkah 2.2).
   * **5. Target system (Bagian Tengah Kanan):** Otomatis mengikuti pilihan *Partition scheme* (`UEFI (non CSM)` untuk GPT).
4. Klik tombol **`START`** di **pojok kanan bawah** (di sebelah kiri tombol *CLOSE*).
5. **Krusial — Mengatur Pop-up "Windows User Experience":**
   Akan muncul kotak putih kecil di tengah layar dengan beberapa kotak centang. **Untuk SEMUA Jenis Laptop (Kentang, Standar, maupun Gaming), WAJIB CENTANG 3 KOTAK INI:**
   * [x] **`Remove requirement for 4GB+ RAM, Secure Boot and TPM 2.0`** *(Memastikan laptop kentang/lawas maupun laptop baru terhindar dari blokir instalasi Windows 11).*
   * [x] **`Remove requirement for an online Microsoft account`** *(Memastikan Anda tidak dipaksa login akun Microsoft dan terhindar dari jebakan sinkronisasi otomatis OneDrive).*
   * [x] **`Disable data collection (Skip privacy questions)`** *(Mematikan pertanyaan pelacakan data sejak awal).*
   * Klik tombol **`OK`** di kanan bawah kotak kecil tersebut → klik **`OK`** lagi pada peringatan penghapusan data Flashdisk.
6. **Indikator Berhasil:** Tunggu 5–20 menit hingga bar di bagian bawah berubah menjadi **Hijau Penuh 100%** bertuliskan **`READY`**. Klik **`CLOSE`**.
7. **Menyimpan Driver Wi-Fi ke Dalam Flashdisk:**
   * Buka **File Explorer** → buka Flashdisk *installer* yang baru selesai dibuat → buat folder baru bernama **`DRIVER_CADANGAN`** → salin file **Installer Driver Wi-Fi** ke dalam folder tersebut.

### 2.5. Penanganan Error Umum di Rufus
* **Error: Proses berhenti dan bar berubah menjadi MERAH (`Error: Write error` atau `Undetermined error while formatting`).**
  * *Penyebab:* Antivirus (Windows Defender / Smadav / Avast) memblokir Rufus saat menyalin file sistem ke USB, atau Flashdisk mengalami kerusakan fisik.
  * *Solusi:* Matikan sementara Antivirus Anda, cabut dan pindahkan Flashdisk ke lubang USB lain, lalu klik **START** lagi di Rufus.

---

## 🚀 POIN 3: Eksekusi Inul, Pembagian Partisi, Update Driver, & Kunci Windows Update Selamanya

Sebelum memulai, **colokkan charger laptop ke listrik**, pastikan Flashdisk *bootable* menancap di lubang USB, dan **cabut semua Hardisk Eksternal / Flashdisk data cadangan**.

### 3.1. Masuk ke Boot Menu & BIOS di Berbagai Merek Laptop
1. **Matikan Laptop Sepenuhnya (Full Shutdown):**
   * Klik menu **Start** → klik ikon **Power** → **Tekan dan tahan tombol `Shift`** di *keyboard* sambil mengklik **Shut down**. Tunggu sampai lampu indikator laptop benar-benar mati.
2. **Nyalakan Laptop dan Masuk ke Boot Menu Sesuai Merek Laptop Anda:**
   * Tekan tombol **Power** satu kali, lalu **detik itu juga (sebelum logo muncul)** tekan-tekan secara cepat dan berulang kali (*spam*) tombol **Boot Menu** sesuai tabel di bawah ini:

| Merek Laptop | Tombol Boot Menu (Langsung Pilih Flashdisk) | Tombol Masuk BIOS (Jika Perlu Ubah Pengaturan) | Catatan Khusus |
| :--- | :--- | :--- | :--- |
| **ASUS** (Vivobook, TUF, ROG, Zenbook) | **`Esc`** (atau **`F8`**) | **`F2`** (atau `Del`) | Tekan-tekan `Esc` begitu tombol Power ditekan hingga muncul kotak pilihan di tengah layar. |
| **Acer** (Aspire, Swift, Nitro, Predator) | **`F12`** | **`F2`** | **Penting untuk Acer:** Jika ditekan `F12` tidak muncul apa-apa, matikan laptop → tekan-tekan **`F2`** masuk BIOS → pindah ke tab **Main** → ubah **`F12 Boot Menu`** menjadi **`Enabled`** → tekan **`F10`** (*Save & Exit*). |
| **Lenovo** (IdeaPad, Yoga, LOQ, Legion, ThinkPad) | **`F12`** (atau **`Fn + F12`**) atau **Lubang Novo Button** | **`F2`** (atau `Fn + F2`, atau **`F1`** khusus ThinkPad) | Pada seri IdeaPad, terdapat **lubang kecil** di samping bodi laptop dengan ikon panah melengkung. Tusuk lubang itu dengan jarum SIM *ejector* saat laptop **mati**, lalu pilih **Boot Menu**. |
| **HP** (Pavilion, Victus, Omen, Envy, ProBook) | **`F9`** (atau **`Esc`** lalu tekan **`F9`**) | **`F10`** (atau `Esc` lalu `F10`) | Tekan-tekan `Esc` saat nyala hingga muncul *Startup Menu*, lalu tekan `F9` untuk *Boot Device Options*. |
| **MSI** (Modern, Thin, Katana, Cyborg, Bravo) | **`F11`** | **`Del`** (Delete) | Tekan-tekan tombol `F11` begitu lampu tombol Power menyala. |
| **Dell** (Inspiron, Latitude, XPS, Vostro, Alienware) | **`F12`** | **`F2`** | Tekan-tekan `F12` saat logo bulat Dell muncul. |
| **Axioo, Advan, Infinix, Zyrex, Chuwi** | **`F7`** atau **`F11`** atau **`F12`** | **`Esc`** atau **`Del`** atau **`F2`** | Mayoritas laptop merek lokal/Tionghoa menggunakan tombol **`F7`** atau **`F11`** untuk memunculkan Boot Menu. |

3. **Memilih Flashdisk di Layar Boot Menu:**
   * Gunakan tombol **Panah Atas / Bawah** di *keyboard* untuk memilih baris **`UEFI: [Merek Flashdisk Anda]`** atau **`USB HDD: [Merek Flashdisk Anda]`** → tekan **`Enter`**.
4. **Indikator Berhasil:** Layar menampilkan logo laptop/Windows sebentar, lalu masuk ke **jendela pengaturan awal instalasi Windows 11**.
5. **Jika Gagal (Muncul pesan merah/biru `"Secure Boot Violation - Invalid signature detected"`):**
   * *Solusi:* Tekan `Enter` → matikan laptop → masuk ke **BIOS** (`F2`/`Del`) → masuk ke tab **Security** atau **Boot** → ubah **`Secure Boot`** menjadi **`Disabled`** → tekan **`F10`** (*Save & Exit*) → ulangi masuk ke Boot Menu.

---

### 3.2. Memulai Instalasi Windows 11 (Tampilan Lama vs Tampilan Baru)
Ikuti langkah yang sesuai dengan tampilan di layar Anda:

* **Tampilan A (Latar Belakang Ungu/Biru Tua — Windows 11 22H2 / 23H2):**
  1. Pastikan *Keyboard or input method* adalah **`US`** → klik **`Next`** di **pojok kanan bawah** → klik **`Install now`** di **tengah layar**.
  2. Jika muncul jendela *Product Key*, klik tulisan kecil **`I don't have a product key`** di **bagian bawah tengah** → pilih edisi Windows Anda (umumnya *Windows 11 Home Single Language* atau *Windows 11 Pro*) → klik **`Next`**. *(Jika lisensi sudah tertanam di motherboard, layar ini otomatis dilewati).*
  3. Centang **`I accept the Microsoft Software License Terms`** di **pojok kiri bawah** → klik **`Next`** di **pojok kanan bawah**.
  4. Klik kotak pilihan nomor 2 (bagian bawah): **`Custom: Install Windows only (advanced)`**.

* **Tampilan B (Latar Belakang Putih/Abu-abu — Windows 11 24H2 Terbaru):**
  1. Pilih bahasa `English (United States)` → klik **`Next`** → pilih keyboard **`US`** → klik **`Next`**.
  2. Pilih bulatan **`Install Windows 11`**, lalu **centang kotak** **`I agree that everything will be deleted including files, apps, and settings`** → klik **`Next`**.
  3. Jika diminta *Product Key*, klik **`I don't have a product key`** di bagian bawah → pilih edisi Windows → klik **`Accept`** pada halaman lisensi hingga tiba di **Tabel Partisi**.

---

### 3.3. Strategi & Eksekusi Pembagian Partisi untuk Segala Ukuran Storage

> [!IMPORTANT]
> **Aturan Emas Sebelum Menyentuh Tabel Partisi:**
> Perhatikan kolom nama di sebelah kiri tabel partisi (`Drive 0`, `Drive 1`, `Drive 2`). Salah satu dari nomor Drive tersebut (yang ukurannya kecil sekitar 14 GB atau 29 GB sesuai ukuran Flashdisk Anda) adalah **Flashdisk Installer Anda**—JANGAN PERNAH menghapus partisi milik Flashdisk tersebut!

#### A. Panduan Rekomendasi Pembagian Partisi Berdasarkan Ukuran Penyimpanan
| Ukuran & Jenis Penyimpanan | Kapasitas Asli Terbaca di Layar | Rekomendasi Pembagian Terbaik | Alasan Teknis |
| :--- | :--- | :--- | :--- |
| **SSD 128 GB atau 256 GB** | ~119 GB atau ~238 GB | **1 Partisi Saja (`Local Disk C:` Penuh)** | Jika dibagi menjadi C dan D, masing-masing partisi akan terlalu sempit. Saat menginstal aplikasi besar atau *game*, Drive C akan cepat penuh merah dan membuat SSD melambat drastis. Pisahkan data pribadi cukup menggunakan Folder di dalam C. |
| **SSD 512 GB** | ~476 GB | **Opsi 1:** 1 Partisi C Penuh (~476 GB)<br>**Opsi 2 (2 Partisi):**<br>• **Drive C:** 200 GB – 250 GB<br>• **Drive D:** Sisanya (~226 GB – 276 GB) | Ukuran 200–250 GB untuk Drive C sudah sangat aman untuk menampung Windows 11, aplikasi kerja berat, dan beberapa *game*, sementara Drive D aman untuk menyimpan dokumen jangka panjang. |
| **SSD 1 TB (1000 GB) atau 2 TB** | ~931 GB atau ~1862 GB | **2 Partisi (C dan D):**<br>• **Drive C:** 250 GB – 400 GB<br>• **Drive D:** Sisanya (~530 GB – 1400 GB) | Pada ukuran besar, memisahkan Drive C (Sistem + Aplikasi) dan Drive D (Data + Koleksi Game Besar) sangat disarankan agar kelak jika ingin inul lagi tidak perlu memindahkan ratusan GB data di Drive D. |
| **Dual Storage (2 Keping: SSD + HDD / SSD + SSD)** | Muncul sebagai **`Drive 0`** dan **`Drive 1`** (selain Flashdisk) | • **SSD Utama:** Jadikan 1 Partisi C Penuh untuk Windows & Aplikasi.<br>• **SSD Ke-2 / HDD:** Jadikan 1 Partisi D Penuh untuk Data & Game. | Perhatikan baik-baik ukuran GB masing-masing Drive. Hanya hapus partisi pada Drive yang ingin dijadikan tempat Windows (`Drive C`). Biarkan Drive yang berisi data cadangan tidak disentuh sama sekali! |

#### B. Cara Eksekusi di Tabel Partisi (Pilih Sesuai Kasus Anda)

**KASUS 1: Menyapu Bersih Seluruh Storage (Termasuk Menghapus Dual Boot Linux+Windows) Menjadi 1 Partisi C Utuh (Sangat Disarankan untuk SSD 256 GB)**
1. Klik baris paling atas yang bernama **`Drive 0 Partition 1`**.
2. Klik tombol **`Delete`** (di **bagian bawah tabel** pada tampilan lama, atau **`Delete Partition`** di **bagian atas tabel** pada tampilan baru) → klik **`OK`**.
3. Ulangi langkah tersebut untuk **SEMUA baris yang bernama `Drive 0 Partition ...`** satu per satu sampai habis!
4. **Indikator Berhasil:** Seluruh baris `Drive 0` melebur menjadi **SATU baris tunggal** bernama **`Drive 0 Unallocated Space`** (dengan angka *Total Size* dan *Free Space* sama persis, misal `238.5 GB`).
5. Klik satu kali pada baris **`Drive 0 Unallocated Space`** tersebut, lalu **langsung klik tombol `Next` di pojok kanan bawah** (tanpa perlu menekan tombol *New*).

**KASUS 2: Membagi Storage Menjadi 2 Partisi Baru (Drive C dan Drive D) dari Nol (Untuk SSD 512 GB / 1 TB / 2 TB)**
1. Lakukan langkah 1 sampai 4 pada **Kasus 1** hingga seluruh `Drive 0` menyatu menjadi satu baris **`Drive 0 Unallocated Space`**.
2. Klik baris **`Drive 0 Unallocated Space`** tersebut → klik tombol **`New`** (atau **`Create Partition`**).
3. Pada kotak **`Size (in MB)`**, ketik ukuran untuk Drive C:
   * Untuk **Drive C sebesar 200 GB**, ketik: **`204900`**
   * Untuk **Drive C sebesar 250 GB**, ketik: **`256100`**
   * Untuk **Drive C sebesar 300 GB**, ketik: **`307300`**
4. Klik **`Apply`** → klik **`OK`**.
5. **Mengaktifkan sisa ruang untuk Drive D:** Klik baris **`Drive 0 Unallocated Space`** yang tersisa di paling bawah → klik tombol **`New`** → biarkan angkanya penuh → klik **`Apply`**.
6. **Memilih Tempat Instal Windows:** Klik satu kali pada baris **`Primary` urutan pertama** (yang ukurannya sesuai jatah Drive C Anda tadi, misal `200.0 GB` atau `250.0 GB`) → klik tombol **`Next`** di **pojok kanan bawah**.

**KASUS 3: Hanya Inul Drive C Saja, Tanpa Menghapus Data di Drive D Lama**
1. Cari baris yang bernama **`DATA_JANGAN_DIHAPUS`** (atau yang ukurannya sama persis dengan ukuran Drive D Anda). **JANGAN PERNAH menekan Delete atau Format pada baris ini!**
2. Hapus (**`Delete`**) hanya partisi-partisi sistem Windows lama (partisi *EFI System*, *MSR*, *Primary/Windows C*, dan *Recovery*) hingga menyatu menjadi satu baris **`Drive 0 Unallocated Space`**.
3. Klik satu kali pada baris **`Drive 0 Unallocated Space`** tersebut → klik tombol **`Next`** di **pojok kanan bawah**.

#### C. Penanganan Error Umum di Layar Partisi
* **Error 1: Tabel Partisi Kosong Melompong (SSD Tidak Terbaca Sama Sekali)!**
  * *Penyebab:* Fitur *Intel VMD Controller* pada laptop prosesor **Intel Generasi 11 ke atas** aktif di BIOS.
  * *Solusi Lewat BIOS:* Tutup instalasi → matikan laptop → masuk ke **BIOS** (`F2` atau `Del`):
    * **Lenovo:** Tab **Configuration** → ubah **`Intel VMD Controller`** menjadi **`Disabled`**.
    * **ASUS:** Tekan `F7` (*Advanced Mode*) → tab **Advanced** → **`VMD Setup Menu`** → ubah *Enable VMD controller* menjadi **`Disabled`**.
    * **Acer:** Tab **Main** → tekan **`Ctrl + S`** di *keyboard* → ubah **`VMD Controller`** yang baru muncul menjadi **`Disabled`**.
    * **HP / MSI:** Tab **Advanced** → cari pengaturan **VMD / Intel Rapid Storage** → ubah menjadi **`Disabled`**.
    * Tekan **`F10`** (*Save & Exit*) → ulangi masuk ke Boot Menu Flashdisk.
* **Error 2: Tombol "Next" Abu-abu dan Muncul Pesan `"Windows cannot be installed to this disk. The selected disk has an MBR partition table..."` (atau sebaliknya `"GPT"`).**
  * *Solusi Cepat (Khusus jika seluruh isi disk sudah di-backup ke luar):* Tekan **`Shift + F10`** (atau **`Fn + Shift + F10`**) → ketik `diskpart` (Enter) → `list disk` (Enter) → `select disk 0` (Enter) → `clean` (Enter) → `convert gpt` (Enter) → `exit` (Enter) → tutup jendela hitam → klik tombol **`Refresh`** di tabel partisi.

---

### 3.4. Proses Instalasi & Setup Awal (OOBE) Tanpa Akun Microsoft / Tanpa Paksaan Internet

1. Tunggu proses **Installing Windows** berjalan dari 0% hingga 100% (sekitar 5–15 menit).
2. **PENTING SAAT RESTART PERTAMA:** Saat muncul hitung mundur **`Windows needs to restart to continue`**, **CABUT FLASHDISK DARI LUBANG USB SEKARANG JUGA** agar tidak mengulang instalasi dari awal.
3. Setelah *restart* 1–2 kali, Anda akan tiba di **Layar Sambutan Windows 11 (OOBE)**:
   * Pilih negara **`Indonesia`** → klik **`Yes`** → pilih keyboard **`US`** → klik **`Yes`** → klik **`Skip`**.
   * **Layar Wi-Fi ("Let's connect you to a network") — JANGAN KONEK INTERNET DULU!**
     * Lihat ke **pojok kanan bawah**, klik tulisan **`I don't have internet`**.
     * **Jika tulisan "I don't have internet" TIDAK ADA:** Tekan **`Shift + F10`** (atau **`Fn + Shift + F10`**) → di jendela hitam yang muncul, ketik:
       ```text
       OOBE\BYPASSNRO
       ```
       Tekan **`Enter`**. Setelah laptop *restart* otomatis, tombol **`I don't have internet`** akan muncul di **pojok kanan bawah**. Klik tombol tersebut!
   * Klik **`Continue with limited setup`** di **pojok kanan bawah**.
   * **Nama Pengguna:** Ketik nama Anda (**disarankan 1 kata tanpa spasi**, misal: `Budi` atau `Admin`) → klik **`Next`**.
   * **Password:** Isi *password* atau biarkan kosong → klik **`Next`**.
   * **Pengaturan Privasi:** Geser **semua sakelar menjadi `Off` (No)** dari atas ke bawah → klik **`Accept`**. Tunggu 1–2 menit hingga masuk ke **Desktop Windows 11**.

---

### 3.5. Memasang Driver & Menuntaskan Windows Update (Beserta Mengatasi Anomali Update)

#### A. Menyambungkan Internet & Memulai Windows Update
1. Klik ikon **Jaringan/Suara** di **pojok kanan bawah taskbar** → sambungkan ke Wi-Fi. *(Jika ikon Wi-Fi belum muncul, colokkan Flashdisk Anda → buka folder `DRIVER_CADANGAN` → instal Driver Wi-Fi Anda, atau gunakan USB Tethering HP).*
2. Tekan **`Windows + I`** untuk membuka **Settings** → klik **`Windows Update`** di bilah kiri paling bawah → klik **`Check for updates`** di kanan atas.
3. **Menginstal Driver Lengkap (Optional Updates):** Klik menu **`Advanced options`** → klik **`Optional updates`** → buka **`Driver updates`** → **centang SEMUA daftar driver yang muncul** → klik **`Download & install`**.
4. Kembali ke halaman **`Windows Update`** dan tunggu hingga semua unduhan serta instalasi selesai 100%.

#### B. Mengatasi 3 Kondisi Anomali Saat Windows Update
* **Anomali 1: Laptop Meminta Restart Lebih dari 3 Kali**
  * *Cara Membedakan:* Jika setiap selesai *restart* kode nama pembaruannya berbeda, itu **normal** karena pembaruan dipasang secara berantai (*prerequisite*). Ikuti saja sampai habis. Namun, jika kode pembaruan yang sama persis terus meminta diinstal berulang-ulang disertai pesan *Retry/Error*, lakukan langkah di **Anomali 2**.
* **Anomali 2: Proses Download / Install Update Stuck (Macet Tidak Bergerak di Persentase Tertentu Selama >30 Menit)**
  * *Solusi Reset Antrean Update:* Klik kanan tombol **Start** → klik **`Terminal (Admin)`** → ketik baris perintah ini satu per satu (tekan **`Enter`** di tiap baris):
    ```cmd
    net stop wuauserv
    net stop cryptSvc
    net stop bits
    net stop msiserver
    ren C:\Windows\SoftwareDistribution SoftwareDistribution.old
    net start wuauserv
    net start cryptSvc
    net start bits
    net start msiserver
    ```
  * Tutup jendela Terminal, **Restart laptop**, lalu buka lagi `Windows Update` → klik **`Check for updates`**.
* **Anomali 3: Layar Hitam Bertuliskan *"Please do not turn off your computer - Updating BIOS / Firmware"* Saat Restart**
  * *Tindakan Wajib:* **JANGAN PERNAH mencabut charger atau mematikan paksa laptop!** Kipas akan berputar kencang selama 2–5 menit karena Windows sedang memperbarui sistem mesin (*firmware*) resmi pabrik. Tunggu sampai masuk kembali ke Windows secara normal.

#### C. Indikator Windows Update Sudah Mentok (100% Tuntas)
Saat Anda mengklik **`Check for updates`**, muncul lingkaran hijau bertanda centang dengan tulisan **`You're up to date`** (dan di dalam *Optional updates* sudah tertulis `0 available`).

---

### 3.6. Cara Mengunci / Menunda Windows Update "Selamanya" dengan Mengganti Tahun, Bulan, & Tanggal Secara Paksa di Sistem

Setelah semua *driver* dan pembaruan mentok paling baru, kita akan membekukan *Windows Update* agar tidak pernah berjalan sendiri di latar belakang. Alih-alih membuat file baru di sistem, cara yang paling mudah dan langsung berhasil adalah **menjeda update 1 minggu terlebih dahulu di Settings agar file tanggalnya muncul, lalu mengganti angka tahun, bulan, dan tanggalnya secara paksa di Registry Editor** (misalnya langsung diubah ke tahun **2240** atau **2099**)[cite: 3].

**Ikuti 4 langkah mudah berikut:**

1. **Langkah 1 — Munculkan File Tanggal dengan Klik "Pause for 1 week" di Settings:**
   * Buka **`Settings`** (`Windows + I`) → klik **`Windows Update`** di bilah kiri.
   * Pada baris **`Pause updates`**, klik tombol **`Pause for 1 week`** satu kali saja.
   * *(Mengapa harus diklik dulu? Karena saat tombol itu diklik, Windows otomatis menciptakan file teks berisi tanggal mulai dan tanggal berakhirnya penundaan di dalam Registry sistem sehingga kita tinggal mengubah angkanya saja tanpa perlu membuat file baru!)*[cite: 3]

2. **Langkah 2 — Buka Registry Editor Menuju Folder Pengaturan Update:**
   * Tekan kombinasi tombol **`Windows + R`** di *keyboard* → ketik **`regedit`** → tekan **`Enter`** → klik **`Yes`**.
   * Lihat ke **kotak alamat panjang di bagian paling atas** jendela *Registry Editor* (di bawah menu *File, Edit, View, Favorites, Help*)[cite: 3].
   * Hapus tulisan di kotak alamat atas tersebut, lalu **salin dan tempelkan (*Copy-Paste*)** alamat ini ke dalamnya[cite: 3]:
     ```text
     Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsUpdate\UX\Settings
     ```
   * Tekan tombol **`Enter`**[cite: 3].

3. **Langkah 3 — Ganti Tahun, Bulan, atau Tanggal Secara Paksa pada 3 File `EndTime / ExpiryTime`:**
   * Sekarang lihat ke **panel besar di sebelah kanan**[cite: 3]. Karena tadi Anda sudah menekan *Pause for 1 week*, di sana sudah tersedia deretan file berikon **`ab`** (bertipe `REG_SZ`) yang berawalan kata **`Pause...`**[cite: 3].
   * Anda cukup mencari dan mengubah **3 baris file penentu batas akhir waktu** berikut ini (abaikan yang berakhiran *StartTime*)[cite: 3]:
     1. **`PauseFeatureUpdatesEndTime`**[cite: 3]
     2. **`PauseQualityUpdatesEndTime`**[cite: 3]
     3. **`PauseUpdatesExpiryTime`**[cite: 3]
   * **Cara Mengubahnya:**
     * **Klik dua kali** pada **`PauseFeatureUpdatesEndTime`**[cite: 3].
     * Di dalam kotak *Value data* yang muncul, Anda akan melihat format tanggal `Tahun-Bulan-Tanggal` beserta jam di belakangnya (contoh: `2026-08-03T01:03:57Z`)[cite: 3].
     * **Cukup ubah angka Tahun, Bulan, dan Tanggal di bagian depannya saja** menjadi tahun puluhan atau ratusan tahun ke depan (jangan hapus huruf `T` dan angka jam `Z` di belakangnya!)[cite: 3]. Contohnya ubah menjadi **`2240-10-30T01:03:57Z`** (Tahun 2240, Bulan 10, Tanggal 30)[cite: 3] atau **`2099-12-31T01:03:57Z`**, lalu klik **`OK`**.
     * Selanjutnya, **klik dua kali** pada **`PauseQualityUpdatesEndTime`**, samakan isinya menjadi **`2240-10-30T01:03:57Z`**[cite: 3] → klik **`OK`**.
     * Terakhir, **klik dua kali** pada **`PauseUpdatesExpiryTime`**, samakan juga isinya menjadi **`2240-10-30T01:03:57Z`**[cite: 3] → klik **`OK`**.

4. **Langkah 4 — Cek Hasilnya (Indikator Berhasil):**
   * Pastikan di kolom **Data** sebelah kanan pada *Registry Editor*, ketiga baris tersebut (`PauseFeatureUpdatesEndTime`, `PauseQualityUpdatesEndTime`, dan `PauseUpdatesExpiryTime`) kini sudah menampilkan tanggal masa depan Anda (misalnya `2240-10-30T01:03:57Z`)[cite: 3].
   * Tutup jendela *Registry Editor* (klik silang `X` di pojok kanan atas)[cite: 3], lalu buka kembali **`Settings`** (`Windows + I`) → **`Windows Update`**.
   * **Tanda Berhasil:** Di bagian atas halaman *Windows Update* sekarang tertulis bahwa pembaruan Windows Anda telah dijeda hingga tahun tersebut (**2240** / **2099**)!
   * **Peringatan Penting:** Selama Anda tidak menekan tombol biru *Resume updates* di halaman *Windows Update*, maka Windows Update akan terkunci selamanya pada tanggal tersebut. Jika suatu hari Anda tidak sengaja menekan *Resume updates*, Anda cukup mengulangi penggantian angka tahun di 3 baris tadi[cite: 3].

---

## 🧹 POIN 4: Panduan Detail Debloat Windows 11 Menggunakan WinUtil Versi Terbaru

Agar Windows 11 menjadi sangat bersih, hemat RAM, dan bebas dari layanan mata-mata (*telemetry*) maupun aplikasi sampah bawaan pabrik (*bloatware*), kita menggunakan **Chris Titus Tech WinUtil versi terbaru**[cite: 1, 2]. Tampilan aplikasi ini akan **100% sama di semua laptop** karena diambil langsung dari server terbaru saat perintah dijalankan[cite: 1, 2].

### 4.1. Cara Membuka Aplikasi Chris Titus WinUtil
1. Pastikan laptop masih terhubung ke internet.
2. **Klik Kanan** pada tombol **Start** (ikon logo Windows di taskbar bawah) → pilih **`Terminal (Admin)`** atau **`PowerShell (Admin)`** → klik **`Yes`**.
3. Di dalam jendela hitam yang terbuka, ketik atau *Copy-Paste* perintah ini:
   ```powershell
   irm [christitus.com/win](https://christitus.com/win) | iex
   ```
4. Tekan **`Enter`**. Tunggu sekitar 5–20 detik hingga muncul **jendela aplikasi berlatar gelap (WinUtil)**[cite: 1].
5. Lihat ke **barisan menu paling atas**, terdapat 5 tombol tab utama: **`Install`**, **`Tweaks`**, **`Config`**, **`Updates`**, dan **`Win11 Creator`**[cite: 1, 2].
6. **Klik tombol ke-2 bernama `Tweaks`** hingga garis bawahnya menyala biru[cite: 1]!

---

### 4.2. Memahami 3 Pilihan Preset di Baris Atas (`Standard` vs `Minimal` vs `Advanced`)

Di bagian atas di bawah tulisan biru **`Recommended Selections:`**, terdapat deretan tombol memanjang dari kiri ke kanan: **`Standard`**, **`Minimal`**, **`Advanced`**, **`Clear`**, **`Select Installed Tweaks`**, dan **`AppX Removal`**[cite: 1].

Sebelum Anda memilih, pahami perbedaan 3 tombol preset utama di sebelah kiri (`Standard`, `Minimal`, `Advanced`) agar Anda bisa memilih yang paling sesuai dengan kebutuhan Anda[cite: 1]:

| Nama Tombol Preset | Apa yang Otomatis Dicentang? | Untuk Siapa Pilihan Ini? | Efek Samping & Konsekuensi |
| :--- | :--- | :--- | :--- |
| **1. `Minimal`**[cite: 1] | Hanya mencentang **4 opsi paling dasar** di bagian *Essential Tweaks*: mematikan iklan instal otomatis (*ConsumerFeatures - Disable*), mengubah layanan ke manual (*Services - Set to Manual*), mematikan pelacakan (*Telemetry - Disable*), dan mematikan injeksi bloatware BIOS (*WPBT - Disable*)[cite: 1]. | Pengguna yang sangat konservatif atau laptop kantor yang tidak boleh banyak diubah pengaturan sistemnya. | **Sangat Aman (Nol Efek Samping):** Menghemat pemakaian RAM dan CPU di latar belakang, namun fitur *Hibernation*, *Widgets*, dan *Location Tracking* masih tetap aktif[cite: 1]. |
| **2. `Standard`** *(Paling Direkomendasikan)*[cite: 1] | Mencentang semua yang ada di *Minimal* **ditambah** pembersihan menyeluruh di *Essential Tweaks* (seperti *Activity History - Disable*, *Delivery Optimization - Disable*, *Hibernation - Disable*, *Location Tracking - Disable*, *Widgets - Remove*, dan membuat *Restore Point*)[cite: 1]. | **90% Pengguna (Pelajar, Pekerja, Gamer, Programmer, maupun Pengguna Laptop Kentang).** | **Aman & Paling Optimal:** Kuota internet tidak tersedot untuk membagikan update (*Delivery Optimization* mati), ruang SSD bertambah lega beberapa GB karena *Hibernation* dimatikan, dan RAM jauh lebih ringan[cite: 1]. *(Catatan: Karena Location Tracking ikut dimatikan, fitur deteksi lokasi otomatis di aplikasi Cuaca/Maps akan nonaktif kecuali Anda melepas centang `Location Tracking - Disable`)*[cite: 1]. |
| **3. `Advanced`**[cite: 1] | Mencentang *Essential Tweaks* **sekaligus mencentang beberapa opsi di bagian bawah (`Advanced Tweaks - CAUTION`)**, seperti mematikan seluruh aplikasi latar belakang (*Background Apps - Disable*) dan mengubah prioritas jaringan (*IPv6 - Set IPv4 as Preferred*)[cite: 1]. | Pengguna tingkat lanjut (*Power User*) atau pemilik "laptop kentang" yang ingin memeras performa dan penghematan RAM paling ekstrem. | **Perlu Perhatian:** Karena *Background Apps* dimatikan total, aplikasi dari Microsoft Store (seperti *Alarm*, *WhatsApp versi Store*, atau *Mail*) tidak akan berbunyi/memberi notifikasi saat jendelanya ditutup/diminimize[cite: 1]. |

> [!TIP]
> Jika Anda salah klik dan ingin mengosongkan semua centang untuk memilih ulang dari awal, cukup klik tombol **`Clear`** di tengah atas[cite: 1].

---

### 4.3. Penjelasan Lengkap Isi Kolom Kiri (`Essential Tweaks` & `Advanced Tweaks`) dan Kolom Kanan (`Customize Preferences`)

Setelah Anda mengklik salah satu tombol preset di atas (disarankan klik **`Standard`** atau **`Minimal`** lalu disesuaikan manual)[cite: 1], Anda bebas menambah atau mengurangi tanda centang sesuai panduan fungsi dan efek samping di bawah ini:

#### A. Kolom Kiri Atas: `Essential Tweaks` (Opsi Penting yang Aman)[cite: 1]
* **`Activity History - Disable` & `Telemetry - Disable`:** ✅ **Wajib Centang.** Mematikan pengiriman riwayat aktivitas dan data mata-mata penggunaan laptop ke server Microsoft[cite: 1].
* **`ConsumerFeatures - Disable` & `Prevent Device Companion Apps`:** ✅ **Wajib Centang.** Mencegah Windows mengunduh aplikasi iklan/sponsor (seperti *Candy Crush* atau *TikTok*) secara diam-diam saat ada internet[cite: 1].
* **`Delivery Optimization - Disable`:** ✅ **Wajib Centang.** Mencegah laptop Anda dipakai oleh Microsoft untuk mengunggah file update ke komputer orang lain di internet (sangat menghemat kuota dan *bandwidth*)[cite: 1].
* **`End Task With Right Click - Enable`:** ✅ **Sangat Disarankan Dicentang.** Menambahkan tombol *"End Task"* saat Anda mengklik kanan ikon aplikasi yang macet (*Not Responding*) langsung di Taskbar bawah, tanpa perlu repot membuka *Task Manager*[cite: 1]!
* **`Hibernation - Disable`:** ✅ **Centang jika memakai SSD (terutama 128GB/256GB).** Mematikan fitur hibernasi dan langsung menghapus file `hiberfil.sys`, sehingga **mengembalikan ruang kosong SSD sebesar 4 GB hingga 8 GB secara instan**[cite: 1]. *(Jangan dicentang hanya jika Anda terbiasa membiarkan laptop hidup berhari-hari tanpa charger dengan menutup layarnya).*
* **`Services - Set to Manual`:** ✅ **Wajib Centang.** Mengubah puluhan layanan latar belakang Windows agar hanya menyala saat dibutuhkan saja, bukan menyala terus-menerus sejak laptop dihidupkan (kunci utama penghemat RAM!)[cite: 1].
* **`Widgets - Remove`:** ✅ **Aman Dicentang.** Menghapus papan berita/iklan cuaca di pojok kiri taskbar yang memakan RAM di latar belakang[cite: 1].
* **`Disk Cleanup - Run` & `Temporary Files - Remove`:** ✅ **Aman Dicentang.** Membersihkan file sampah sisa instalasi dan pembaruan Windows[cite: 1].

#### B. Kolom Kiri Bawah: `Advanced Tweaks - CAUTION` (Pilihan Ekstra Sesuai Kebutuhan)[cite: 1]
Jangan asal mencentang semua yang ada di bagian ini[cite: 1]. Centang **HANYA** yang Anda butuhkan berdasarkan penjelasan efek samping berikut:

* **`Microsoft OneDrive - Remove`:** ✅ **Sangat Direkomendasikan Dicentang** (kecuali Anda wajib memakai aplikasi OneDrive untuk kantor)[cite: 1]. Mencopot OneDrive sampai bersih agar tidak menyedot kuota internet dan RAM[cite: 1].
* **`Disable Reserved Storage`:** ✅ **Sangat Direkomendasikan Dicentang (Terutama untuk SSD 128GB / 256GB).** Mengambil kembali ruang penyimpanan sekitar **7 GB** yang dikunci secara paksa oleh Windows untuk cadangan pembaruan sistem[cite: 1].
* **`Brave Browser - Debloat` & `Microsoft Edge - Debloat`:** ✅ **Aman Dicentang.** Mematikan fitur promosi mengganggu di dalam browser Brave dan Edge (seperti dompet kripto bawaan, VPN berbayar, kupon belanja, dan telemetri browser) tanpa menghapus browsernya[cite: 1].
* **`Microsoft Edge - Remove`:** ⚠️ **Opsional (Aman di WinUtil Terbaru dengan Syarat):** Pada WinUtil versi terbaru ini, mencentang *Microsoft Edge - Remove* hanya menghapus aplikasi browser Edge saja dan **tidak merusak** komponen *Edge WebView2 Runtime* yang dibutuhkan oleh Microsoft Office maupun aplikasi development[cite: 1].
  * *Syarat Wajib:* Sebelum mencentang ini, **pastikan Anda sudah mengunduh/menginstal browser lain** (seperti *Brave* atau *Google Chrome*) terlebih dahulu agar Anda tetap punya browser untuk membuka internet[cite: 1]!
  * *Efek Samping:* Beberapa tautan bantuan di dalam menu *Settings* Windows yang diprogram khusus memanggil `microsoft-edge://` tidak akan terbuka jika diklik.
* **`Background Apps - Disable`:** ⚠️ **Centang jika ingin hemat RAM maksimal di Laptop Kentang**, tetapi pahami efek sampingnya: aplikasi yang diunduh dari Microsoft Store (seperti *Alarm/Clock* atau *WhatsApp Store*) tidak akan memberi notifikasi saat diminimize[cite: 1].
* **`Adobe URL Block List - Enable`:** Memblokir koneksi telemetri server lisensi Adobe[cite: 1]. *(Jangan dicentang jika Anda pelanggan resmi Adobe Creative Cloud yang membutuhkan sinkronisasi cloud Adobe).*
* **`IPv6 - Disable`:** ❌ **Jangan Dicentang** kecuali koneksi Wi-Fi Anda bermasalah dengan jaringan IPv6[cite: 1].

#### C. Kolom Sebelah Kanan: `Customize Preferences` (Sakelar Langsung / Live Toggles)[cite: 1]
Berbeda dengan kolom kiri yang baru bekerja setelah menekan tombol *Run Tweaks*, deretan sakelar biru/abu-abu di kolom kanan ini adalah **Sakelar Langsung** yang membaca dan mengubah tampilan Windows Anda detik itu juga[cite: 1]:
* **`Dark Theme for Windows`:** Nyalakan (Biru) untuk mode gelap yang nyaman di mata[cite: 1].
* **`Enable Long Paths`:** ✅ **Wajib Nyalakan (Biru).** Menghilangkan batasan panjang nama folder 260 karakter di Windows (mencegah error saat menyalin atau mengekstrak file yang foldernya berlapis-lapis)[cite: 1].
* **`File Explorer File Extensions` & `File Explorer Hidden Files`:** ✅ **Wajib Nyalakan (Biru).** Menampilkan akhiran jenis file (`.exe`, `.pdf`, `.docx`) dan folder tersembunyi di File Explorer[cite: 1].
* **`Start Menu Bing Search` & `Start Menu Recommendations`:** ✅ **Wajib Matikan (Abu-abu).** Mematikan pencarian internet Bing dan iklan rekomendasi di menu Start agar menu Start terasa sangat cepat saat dibuka[cite: 1].
* **`Mouse Acceleration`:** Matikan (Abu-abu) jika Anda seorang *Gamer* (terutama game tembak-menembak/FPS) atau desainer grafis agar pergerakan kursor mouse 100% akurat dan tidak meleset[cite: 1].
* **`Sticky Keys`:** Matikan (Abu-abu) agar tidak muncul kotak peringatan mengganggu saat Anda menekan tombol `Shift` berkali-kali di dalam *game*[cite: 1].
* **`Taskbar Centered Icons`:** Nyalakan (Biru) jika suka ikon Taskbar di tengah khas Windows 11, atau matikan (Abu-abu) jika ingin menggeser tombol Start ke pojok kiri bawah seperti Windows 10[cite: 1].

---

### 4.4. Mengeksekusi `Run Tweaks` (Langkah Pertama Debloat)
1. Setelah selesai memilih centang di kolom kiri (`Essential Tweaks` & `Advanced Tweaks`), lihat ke **pojok kiri bawah** jendela WinUtil[cite: 1].
2. Klik tombol **`Run Tweaks`** (di sebelah kiri tombol *Undo Selected Tweaks*)[cite: 1].
3. Tunggu sekitar 30 detik hingga 2 menit sampai proses di jendela PowerShell belakang selesai dan muncul pemberitahuan bahwa *Tweaks* telah selesai dijalankan.

---

### 4.5. Panduan Detail Menghapus Aplikasi Bawaan di Menu `AppX Removal` (Mana yang Aman & Mana yang Tidak Boleh Dihapus)

Setelah *Run Tweaks* selesai, jangan tutup dulu aplikasinya! Sekarang kita akan membersihkan aplikasi bawaan Windows 11 yang membebani penyimpanan dan menu Start.

1. Lihat kembali ke deretan tombol di **bagian atas sebelah kanan** pada tab `Tweaks`, lalu klik tombol paling ujung kanan yang bernama **`AppX Removal`**[cite: 1].
2. Layar akan berganti menampilkan halaman daftar paket aplikasi Windows yang terbagi menjadi **6 kategori rapi**[cite: 2].
3. Di bagian atas di bawah tulisan **`Selections:`**, terdapat 4 tombol bantu: **`Default`**, **`Select Installed`**, **`Select All`**, dan **`Clear Selection`**[cite: 2].

> [!WARNING]
> **PERINGATAN KERAS:** **JANGAN PERNAH menekan tombol `Select All`**, karena itu akan menghapus aplikasi penting seperti Kalkulator, Pembuka Foto, dan Notepad[cite: 2]! Anda bisa menekan tombol **`Default`** untuk memilih pilihan standar[cite: 2], atau **pilih secara manual dengan mengikuti panduan per kategori di bawah ini agar 100% sesuai kebutuhan Anda**[cite: 2].

#### Panduan Lengkap 6 Kategori di Layar `AppX Removal`[cite: 2]

| Kategori di Layar | Daftar Aplikasi di Dalamnya | Rekomendasi Centang (Hapus vs Pertahankan) | Alasan Teknis & Efek Samping |
| :--- | :--- | :--- | :--- |
| **1. `Microsoft Apps`** *(Kiri Atas)*[cite: 2] | • `Feedback Hub`<br>• `Get Help`<br>• `Microsoft 365`<br>• `Microsoft Teams`<br>• `Outlook for Windows`[cite: 2] | ✅ **AMAN DICENTANG SEMUA (Hapus Semua)**[cite: 2] | • `Feedback Hub` & `Get Help` hanya aplikasi pelapor masalah ke Microsoft[cite: 2].<br>• `Microsoft 365` di sini **bukan** aplikasi Word/Excel/PowerPoint asli, melainkan hanya aplikasi portal iklan web Office[cite: 2].<br>• `Outlook for Windows` & `Teams` bawaan sering berjalan diam-diam di latar belakang[cite: 2]. *(Hanya biarkan tidak dicentang jika Anda memang memakai aplikasi Outlook/Teams bawaan tersebut setiap hari).* |
| **2. `Microsoft Ecosystem`** *(Kiri Tengah)*[cite: 2] | • `Mobile Devices`<br>• `Phone Link`[cite: 2] | ✅ **Aman Dicentang (Hapus)** jika tidak pernah menyambungkan layar/notifikasi HP Android ke laptop secara nirkabel[cite: 2]. | `Phone Link` dan `Mobile Devices` selalu menjalankan layanan latar belakang untuk mencari koneksi HP[cite: 2]. Jika Anda menghubungkan HP hanya lewat kabel data atau WhatsApp Web, hapus saja agar hemat RAM[cite: 2]. |
| **3. `Utilities & Productivity`** *(Kiri Bawah)*[cite: 2] | • `Calculator`, `Clock`, `Notepad`, `Paint`, `Photos`, `Snipping Tool`, `Camera`, `Sound Recorder`, `Media Player`[cite: 2]<br>• `Clipchamp`, `Movies & TV`, `Quick Assist`, `Sticky Notes`, `To Do`[cite: 2] | ❌ **JANGAN HAPUS (Biarkan Kosong):**<br>`Calculator`, `Camera`, `Notepad`, `Paint`, `Photos`, `Snipping Tool`, `Sound Recorder`, `Clock`, `Media Player`[cite: 2].<br><br>✅ **AMAN DIHAPUS (Centang):**<br>`Clipchamp`, `Movies & TV`, `Quick Assist`, `Sticky Notes`, `To Do`[cite: 2]. | • Jika Anda menghapus `Calculator`, `Notepad`, `Photos`, atau `Snipping Tool`, Anda akan kesulitan saat ingin menghitung cepat, membuka gambar, mencatat teks, atau mengambil *screenshot* layar (`Win + Shift + S`)[cite: 2]!<br>• Sedangkan `Clipchamp` (editor video berat berbasis web) dan `Movies & TV` sangat aman dihapus[cite: 2]. |
| **4. `Bing & Web Services`** *(Kanan Atas)*[cite: 2] | • `Bing Search`<br>• `Copilot`<br>• `News`<br>• `Start Experiences App`<br>• `Weather`[cite: 2] | ✅ **SANGAT DIREKOMENDASIKAN DICENTANG SEMUA (Hapus Semua!)**[cite: 2] | Inilah sumber utama iklan, berita pop-up, dan asisten AI (`Copilot`) yang paling membebani RAM dan koneksi internet di Windows 11[cite: 2]. Menghapus kelimanya akan membuat sistem sangat bersih dan tenang[cite: 2]. *(Hanya sisakan `Weather` jika Anda suka melihat ramalan cuaca bawaan)*[cite: 2]. |
| **5. `Developer Tools`** *(Kanan Tengah)*[cite: 2] | • `Dev Home`<br>• `Power Automate`[cite: 2] | ✅ **AMAN DICENTANG SEMUA (Hapus Semua)** — *Bahkan untuk seorang Programmer/Software Engineer sekalipun!*[cite: 2] | Jangan tertipu namanya: `Dev Home` dan `Power Automate` adalah aplikasi dasbor dan otomatisasi bawaan Microsoft yang berat dan **sama sekali tidak ada hubungannya** dengan aplikasi koding seperti VS Code, Git, Docker, Android Studio, maupun Laragon[cite: 2]. Sangat aman dihapus oleh siapa saja[cite: 2]. |
| **6. `Xbox & Gaming`** *(Kanan Bawah)*[cite: 2] | • `Solitaire Collection`[cite: 2]<br>• `Xbox App`<br>• `Xbox Game Bar`<br>• `Xbox Identity Provider`<br>• `Xbox Speech To Text Overlay`<br>• `Xbox TCUI`[cite: 2] | ✅ **Wajib Centang (Hapus):** `Solitaire Collection` (Game kartu iklan bawaan)[cite: 2].<br><br>⚠️ **Untuk 5 Opsi `Xbox ...` Lainnya:**<br>• **JIKA ANDA GAMER:** ❌ **JANGAN DICENTANG SAMA SEKALI!**[cite: 2]<br>• **Jika 100% Laptop Kerja/Ketik Tanpa Game:** ✅ Boleh dicentang[cite: 2]. | Jika Anda bermain *game* (terutama *Minecraft*, *Forza*, *PC Game Pass*, atau merekam layar game dengan `Win + G`), menghapus `Xbox Identity Provider`, `Xbox TCUI`, dan `Xbox Game Bar` akan membuat Anda **tidak bisa login ke dalam game** dan memunculkan error *Gaming Services*[cite: 2]! |

#### Cara Mengeksekusi Penghapusan di Layar `AppX Removal`:
1. Setelah Anda mencentang aplikasi yang ingin dibuang sesuai tabel di atas, lihat ke **deretan 3 tombol di bagian paling bawah** jendela[cite: 2].
2. Klik tombol paling kanan yang bertuliskan **`Remove Selected`**[cite: 2].
3. Tunggu beberapa detik hingga proses penghapusan di layar belakang selesai.
   * *(Catatan Penyelamat: Sesuai keterangan di bagian bawah layar WinUtil, jika suatu saat Anda berubah pikiran atau tidak sengaja menghapus aplikasi seperti Calculator/Xbox, Anda cukup membuka kembali menu `AppX Removal` ini, beri tanda centang pada aplikasi tersebut, lalu klik tombol tengah **`Install Selected`** untuk mengembalikannya seperti semula!)*[cite: 2]
4. Klik tombol **`Back to Tweaks`** di **pojok kiri bawah**[cite: 2], tutup jendela WinUtil (klik tanda silang `X` di pojok kanan atas)[cite: 1, 2], lalu **Restart laptop Anda** satu kali.

---

### 4.6. Opsional (Khusus Pengguna SSD 128 GB / 256 GB dengan 1 Partisi C): Membuat Folder Pengganti Drive D
Jika pada tahap partisi tadi Anda memilih menggunakan **1 Partisi C Penuh** (tanpa membuat Drive D), buatlah struktur folder yang rapi langsung di dalam `Local Disk (C:)` agar data pribadi Anda tidak bercampur dengan folder sistem Windows:
1. Buka **File Explorer** (`Windows + E`) → klik **`This PC`** → buka **`Local Disk (C:)`**.
2. Klik kanan di area kosong → **New** → **Folder**, lalu buat folder khusus sesuai kebutuhan Anda, misalnya:
   * **`C:\Data-Pribadi`** (Untuk menaruh semua dokumen kuliah, kerja, foto, dan mentahan aplikasi).
   * **`C:\Workspace`** dan **`C:\DevTools`** (Khusus jika Anda seorang programmer untuk menaruh file kodingan dan SDK agar alamat *path*-nya pendek dan bebas dari spasi).
3. **Memindahkan Lokasi Unduhan (Downloads) Bawaan ke Dalam Folder Baru:**
   * Buka `C:\Data-Pribadi`, lalu buat folder bernama **`Downloads`** di dalamnya.
   * Di panel kiri File Explorer, **Klik Kanan** pada menu **Downloads** bawaan Windows → pilih **Properties** → buka tab **Location** di bagian atas → klik tombol **Move...** → arahkan ke `C:\Data-Pribadi\Downloads` → klik **Select Folder** → klik **Apply** → klik **Yes** → **OK**.

---

## ✅ PENUTUP: Tabel Verifikasi Hasil Akhir (Berhasil vs Gagal) & Kesimpulan

Setelah seluruh langkah selesai dan laptop telah di-*restart*, lakukan pemeriksaan akhir menggunakan tabel ceklis di bawah ini untuk memastikan Windows 11 Anda sudah 100% siap digunakan:

| Komponen yang Diperiksa | Cara Memeriksa di Laptop | Tanda Berhasil (Kondisi Ideal) | Tanda Gagal & Cara Mengatasinya |
| :--- | :--- | :--- | :--- |
| **1. Kelancaran Booting (Single Boot)** | Matikan laptop lalu nyalakan kembali dengan tombol Power | Laptop langsung masuk ke logo merek & halaman *Desktop* Windows 11 dalam 10–20 detik tanpa mampir ke layar hitam pilihan OS lain (seperti GRUB Linux). | **Gagal:** Masih muncul layar hitam `grub rescue` atau pilihan OS lama.<br>**Solusi:** Masuk ke BIOS (`F2`), pindah ke tab **Boot**, pastikan urutan nomor 1 adalah **`Windows Boot Manager`**, atau tekan `Windows + R` → ketik `msconfig` → tab **Boot** → hapus baris OS lama. |
| **2. Pembagian Partisi Penyimpanan** | Buka **File Explorer** (`Windows + E`) → klik **`This PC`** di bilah kiri | Jumlah partisi (`Local Disk C:` saja, atau `C:` dan `D:`) serta total kapasitas GB-nya tampil utuh sesuai ukuran SSD/HDD Anda. | **Gagal:** Partisi D yang baru dibuat belum muncul di File Explorer.<br>**Solusi:** Klik kanan tombol **Start** → pilih **Disk Management**. Jika kotak partisi D bergaris hitam (*Unallocated*) atau belum memiliki huruf (`D:`), klik kanan pada kotak tersebut → pilih **New Simple Volume** (atau **Change Drive Letter and Paths**) → klik *Next* sampai *Finish*. |
| **3. Status Aktivasi Lisensi Windows 11** | Buka `Settings` (`Windows + I`) → `System` → `Activation` | Pada baris *Activation state* tertulis **`Active`** (*Windows is activated with a digital license*). | **Gagal:** Tertulis *Not active* berwarna merah.<br>**Solusi:** Pastikan internet menyala, lalu klik tombol **`Troubleshoot`** di halaman Activation tersebut agar Windows membaca lisensi resmi yang tertanam di *motherboard* laptop. |
| **4. Kesehatan Seluruh Driver Hardware** | Klik kanan tombol **Start** → pilih **`Device Manager`** | Seluruh daftar perangkat rapi dari atas ke bawah, **tidak ada** ikon segitiga kuning bertanda seru (`!`). Pengaturan kecerahan layar, suara speaker, Wi-Fi, dan Bluetooth berfungsi normal. | **Gagal:** Ada baris di bagian *Other devices* dengan ikon segitiga kuning.<br>**Solusi:** Buka `Settings` → `Windows Update` → klik `Resume updates` sebentar → masuk ke `Advanced options` → `Optional updates` → unduh driver yang tertinggal, lalu ubah kembali tahun tanggal `EndTime` dan `ExpiryTime` di `regedit`[cite: 3]. |
| **5. Status Kunci Tanggal Windows Update** | Buka `Settings` → `Windows Update` (atau cek di `regedit`)[cite: 3] | Di halaman *Windows Update* tertulis pembaruan dijeda hingga tahun yang Anda masukkan (misal **2240** atau **2099**), sesuai dengan angka pada `PauseFeatureUpdatesEndTime`, `PauseQualityUpdatesEndTime`, dan `PauseUpdatesExpiryTime`[cite: 3]. | **Gagal:** Tanggal kembali ke minggu depan.<br>**Solusi:** Pastikan ketiga baris (`PauseFeatureUpdatesEndTime`, `PauseQualityUpdatesEndTime`, dan `PauseUpdatesExpiryTime`) di `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsUpdate\UX\Settings` sudah diubah semua tahunnya dan ditekan **OK**[cite: 3]. |
| **6. Hasil Debloat (Pemakaian RAM Idle)** | Tekan **`Ctrl + Shift + Esc`** untuk membuka **Task Manager** → klik tab **`Performance`** → klik **`Memory`** | Saat tidak membuka aplikasi apa pun, pemakaian RAM berada di kisaran **1,7 GB – 2,4 GB** (turun drastis dari bawaan pabrik yang mencapai 3,8 GB – 4,5 GB), dan jumlah *Processes* di tab CPU berkisar di angka **85 – 125 proses**. | **Gagal:** Pemakaian RAM saat diam masih di atas 3,5 GB.<br>**Solusi:** Pastikan Anda sudah menekan tombol **`Run Tweaks`** di pojok kiri bawah WinUtil[cite: 1], serta buka tab **`Startup apps`** di *Task Manager* untuk menonaktifkan (*Disable*) aplikasi yang ikut menyala saat laptop baru hidup. |

### Kesimpulan Akhir
Melakukan instalasi ulang (*clean install*) Windows 11 yang dipadukan dengan penataan partisi yang tepat, pembaruan *driver* secara menyeluruh, pembekuan tanggal *Windows Update* melalui *Registry Editor*[cite: 3], serta pembersihan sistem menggunakan **Chris Titus Tech WinUtil**[cite: 1, 2] adalah solusi paling efektif untuk mengembalikan performa laptop ke titik tertingginya. Dengan mengikuti panduan ini secara berurutan, pengguna dari latar belakang profesi apa pun dan dengan spesifikasi laptop apa pun akan mendapatkan sistem operasi yang stabil, hemat kuota internet, bebas dari gangguan *bloatware*, serta memiliki ruang penyimpanan dan RAM yang jauh lebih lega untuk penggunaan jangka panjang.