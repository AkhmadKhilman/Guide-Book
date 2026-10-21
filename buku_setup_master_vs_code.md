# 📘 Buku Setup Master Visual Studio Code (Multi-Language)

Visual Studio Code (VS Code) adalah *text editor* (ruang kerja digital) tempat *programmer* menulis kode. Saat pertama kali diinstal, aplikasi ini masih kosong. Agar bisa digunakan untuk berbagai bahasa pemrograman, kita harus menambahkan "Ekstensi" (fitur tambahan) dan melakukan pengaturan khusus.

Panduan ini disusun sangat rinci agar pemula dapat merakit VS Code menjadi alat profesional tanpa *error*.

---

## 🛠️ TAHAP 1: Instalasi & Konfigurasi Dasar VS Code

**A. Cara Download & Install**
1. Buka *browser* dan kunjungi web resmi: **[code.visualstudio.com](https://code.visualstudio.com/)**
2. Klik tombol biru **Download for Windows**.
3. Buka file *installer* yang terunduh dan ikuti instruksi *Next*.
4. **SANGAT PENTING:** Saat Anda tiba di halaman yang menampilkan beberapa kotak centang (*checkboxes*), **CENTANG SEMUA KOTAKNYA**. Terutama opsi *"Add to PATH"* dan *"Add 'Open with Code' action to Windows Explorer"*. Ini memastikan VS Code terhubung ke sistem komputer Anda.
5. Lanjut klik *Next* dan *Install*. Buka VS Code setelah selesai.

**B. Konfigurasi Awal (Wajib Sebelum Mulai Ngoding)**
Agar VS Code nyaman digunakan, kita harus mengatur perilaku dasarnya:
1. Tekan tombol `Ctrl + ,` (Control dan Koma) secara bersamaan untuk membuka menu **Settings**.
2. Di kolom pencarian *Settings* (di atas), ketik dan aktifkan tiga fitur ini:
   * **Format On Save:** Centang kotaknya. (Fungsi: VS Code akan otomatis merapikan spasi dan indentasi kode yang berantakan setiap kali Anda menyimpan file dengan `Ctrl + S`).
   * **Word Wrap:** Ubah nilainya menjadi `on`. (Fungsi: Agar teks kode yang sangat panjang tidak menembus ke luar batas kanan layar, melainkan otomatis turun ke baris bawah).
   * **Bracket Pair Colorization:** Pastikan fitur ini aktif. (Fungsi: Mewarnai pasangan tanda kurung `{ }` atau `( )` agar Anda tidak bingung saat kode mulai bertumpuk).

---

## 📑 TAHAP 2: SETUP BAHASA PEMROGRAMAN
Pilih bahasa pemrograman yang ingin Anda siapkan di bawah ini. Anda tidak perlu menginstal semuanya, cukup instal yang sedang Anda pelajari.

### 1. 🌐 Setup Frontend Web (HTML, CSS, JS)

*   **Ekstensi yang Diinstal:** (Buka menu *Extensions* / ikon kotak-kotak di menu kiri VS Code, lalu cari dan instal)
    1. **Live Server** *(oleh Ritwick Dey)*: Membuka *server* lokal. Saat Anda menyimpan kode HTML/CSS, tampilan di *browser* akan otomatis memuat ulang (*refresh*) tanpa perlu ditekan manual.
    2. **Prettier - Code formatter** *(oleh Prettier)*: Standar industri untuk merapikan struktur kode HTML, CSS, dan JS.
    3. **Tailwind CSS IntelliSense** *(Opsional)*: Berfungsi memberi saran *autocomplete* jika Anda menggunakan *framework* Tailwind CSS.
*   **Pengaturan Formatter (Perapi Kode):**
    1. Buka atau buat sembarang file berakhiran `.html` atau `.js`.
    2. Tekan `Ctrl + Shift + P` di *keyboard*.
    3. Ketik dan pilih: **`Configure Default Formatter`**.
    4. Pilih **Prettier - Code formatter**.

---

### 2. 🐍 Setup Python

Ada dua cara menyiapkan mesin Python di laptop Anda. Pilih salah satu:

**Opsi A: Bagi yang SUDAH menginstal Laragon (Full)**
Anda tidak perlu *download* Python lagi, karena Laragon sudah membawanya.
*   **Cara Set di VS Code:** Buka VS Code > tekan `Ctrl + Shift + P` > ketik `Python: Select Interpreter` > Pilih `Enter interpreter path...` > Cari file `python.exe` di dalam folder instalasi Laragon Anda (misal: `C:\laragon\bin\python\python-3.x\python.exe`).

**Opsi B: Bagi yang BELUM pakai Laragon (Install Mandiri)**
1. Kunjungi situs resmi: **[python.org/downloads](https://www.python.org/downloads/)** dan klik *Download Python*.
2. Buka *installer*-nya. 
3. **KRUSIAL:** Di layar paling awal sebelum klik Install, lihat ke pojok kiri bawah. **WAJIB Centang kotak "Add Python to PATH"**. (Jika lupa dicentang, VS Code tidak akan bisa mendeteksi Python).
4. Klik *Install Now* dan tunggu selesai.

*   **Ekstensi yang Diinstal di VS Code:**
    1. **Python** *(oleh Microsoft)*: Otak utama untuk menjalankan dan mendeteksi *error* Python.
    2. **Black Formatter** *(oleh Microsoft)*: Standar perapi kode Python otomatis.
*   **Pengaturan Formatter (Perapi Kode):**
    Buka file `.py` > tekan `Ctrl + Shift + P` > ketik `Configure Default Formatter` > Pilih **Black Formatter**.

---

### 3. 🐘 Setup PHP (Native, CodeIgniter, Laravel)

**⚠️ Penjelasan Versi Stabil (Perhatikan Sebelum Mulai):**
*   **PHP Dasar/Native:** Gunakan PHP 8.x dan MySQL 8.x.
*   **CodeIgniter 3 (CI3):** Ini *framework* lawas. WAJIB menggunakan **PHP 7.4** dan **MySQL 5.7**. Jika memaksa pakai versi baru, layar Anda akan penuh *error*.
*   **CodeIgniter 4 (CI4) & Laravel 11:** WAJIB pakai versi terbaru, minimal **PHP 8.2 / 8.3** dan **MySQL 8.x**.

**A. Ekstensi yang Diinstal (JANGAN INSTAL SEMUA, Pilih Sesuai Kebutuhan):**
*   **PHP Intelephense** *(oleh Ben Mewburn)* - **WAJIB:** Mesin utama pencari *error* dan *autocomplete* PHP.
*   **Laravel Blade Snippets** *(Khusus pengguna Laravel)*: Memberi warna dan merapikan file tampilan Laravel (`.blade.php`) agar tidak berwarna putih polos.
*   **Laravel Extra Intellisense** *(Khusus pengguna Laravel)*: Membuat VS Code pintar menebak otomatis nama *Route* dan *Controller* saat Anda mengetik.
*   **Codeigniter 4 Snippets** *(Khusus pengguna CI4)*: Jalan pintas; cukup ketik beberapa huruf, VS Code otomatis membuatkan kerangka utuh untuk *Model* atau *Controller*.
*   **PHP Namespace Resolver** *(Wajib untuk pengguna CI4 & Laravel)*: Mengimpor jalur *Class* (menambahkan baris `use App\Models\...` di atas dokumen) secara otomatis hanya dengan klik kanan.

**B. Pengaturan Krusial (Mencegah Error Garis Merah Palsu):**
1. **Matikan PHP Bawaan VS Code:** Di menu Extensions, ketik `@builtin php`. Cari **PHP Language Features**, klik ikon gerigi (*gear*), lalu klik **Disable**. (Ini wajib agar tidak bentrok dengan Intelephense).
2. **Sambungkan Mesin PHP:** Buka Settings (`Ctrl + ,`), ketik `php validate executable path`, klik *Edit in settings.json*. Tambahkan lokasi mesin PHP Anda (dari XAMPP/Laragon), contoh: 
   `"php.validate.executablePath": "C:\\laragon\\bin\\php\\php-8.3.x\\php.exe"`

**C. Pengaturan Formatter:**
Buka file `.php` > tekan `Ctrl + Shift + P` > ketik `Configure Default Formatter` > Pilih **PHP Intelephense**.

---

### 4. 🎯 Setup C# (.NET Desktop & Backend)

**A. Cara Install .NET SDK:**
1. Kunjungi **[dotnet.microsoft.com/download](https://dotnet.microsoft.com/download)**.
2. Unduh **.NET SDK** (Pilih versi LTS terbaru, misal .NET 8). Pilih *Windows x64 Installer*.
3. Buka file `.exe`-nya, klik *Install* dan tunggu sampai selesai.

**B. Ekstensi yang Diinstal di VS Code:**
1. **C# Dev Kit** *(oleh Microsoft)*: Menghadirkan fitur setara Visual Studio raksasa.
2. **NuGet Gallery** *(oleh pcislo)*: Alat visual untuk menginstal pustaka/paket tambahan.
3. **Avalonia for VS Code** atau **.NET MAUI** *(Pilih sesuai framework UI yang Anda pakai)*.

**C. Pengaturan Formatter:**
Buka file `.cs` > tekan `Ctrl + Shift + P` > ketik `Configure Default Formatter` > Pilih **C#**.

**D. Catatan Wajib C# Dev Kit:** 
*   Klik ikon akun di pojok kiri bawah VS Code dan *login* menggunakan akun Microsoft/GitHub agar fitur Dev Kit aktif penuh.
*   Saat Anda membuka folder proyek C#, jika muncul *pop-up* peringatan keamanan (*Do you trust the authors?*), **WAJIB klik "Yes, I trust the authors"**. Jika ditolak, fitur C# tidak akan menyala.

---

### 5. ☕ Setup Java

**A. Cara Install Java SDK (JDK):**
1. Kunjungi **[adoptium.net](https://adoptium.net/)** (Penyedia Java resmi yang sangat aman).
2. Unduh rilis **Temurin LTS** terbaru (misal Java 21) berformat **.msi**.
3. Buka file `.msi`-nya. 
4. **KRUSIAL SAAT INSTALASI:** Di halaman *Custom Setup*, Anda akan melihat opsi *"Set JAVA_HOME variable"* dan *"Registry keys"* yang ditandai dengan **silang merah (X)**. Klik tanda silang merah itu, lalu ubah menjadi **"Will be installed on local hard drive"**. Baru klik *Next* dan *Install*.
   > **Catatan (Troubleshooting Error 32-bit):** Jika proses instalasi gagal dengan pesan perangkat tidak didukung, itu karena laptop Anda masih menggunakan sistem 32-bit lawas. **Solusinya:** Kunjungi halaman arsip Adoptium, cari Java versi 17 atau 11, lalu unduh *installer* berlabel **x86** (32-bit). Cara instalasinya sama persis.

**B. Ekstensi yang Diinstal di VS Code:**
1. **Extension Pack for Java** *(oleh Microsoft)*: Berisi 6 alat penting termasuk *debugger* dan pembaca tata bahasa.
2. **Spring Boot Extension Pack** *(oleh VMware)*: Instal ini hanya jika Anda ingin membuat *website backend* berbasis Spring.

**C. Pengaturan Formatter:**
Buka file `.java` > tekan `Ctrl + Shift + P` > ketik `Configure Default Formatter` > Pilih **Language Support for Java(TM) by Red Hat**.

---

### 6. 📱 Setup Flutter (Mobile & Web)

*(Perhatian: Proses ini cukup panjang, ikuti langkah demi langkah secara teliti)*.

**Langkah 1: Install Git**
Kunjungi **[git-scm.com/download/win](https://git-scm.com/download/win)**, unduh dan instal (cukup klik *Next* sampai selesai). Git berfungsi agar Flutter bisa mengunduh *file* pendukung dari internet.

**Langkah 2: Install Flutter SDK**
1. Kunjungi **[flutter.dev/docs/get-started/install/windows](https://flutter.dev/docs/get-started/install/windows)**, unduh file `.zip` Flutter SDK.
2. Buat folder baru bernama **`src`** di Local Disk C Anda (menjadi `C:\src`).
3. Ekstrak isi file `.zip` Flutter tadi ke dalam folder tersebut. Susunan akhirnya harus menjadi `C:\src\flutter`.
4. **Daftarkan ke Sistem:** Klik logo Start Windows > ketik *Environment Variables* > pilih *Edit the system environment variables* > klik tombol *Environment Variables*. Di kotak atas (*User variables*), cari tulisan **Path**, klik *Edit*, klik *New*, lalu ketik: **`C:\src\flutter\bin`**. Klik OK.

**Langkah 3: Install Android SDK (Tanpa Android Studio yang Berat)**
1. Kunjungi **[developer.android.com/studio](https://developer.android.com/studio)**. Geser perlahan ke paling bawah hingga menemukan tabel **Command line tools only**. Unduh file `.zip` untuk Windows.
2. Buat folder baru di Drive C secara berurutan seperti ini: **`C:\Android\cmdline-tools\latest`**.
3. Ekstrak isi file `.zip` tadi ke dalam folder `latest` tersebut. (Pastikan di dalamnya langsung ada folder bernama `bin`).
4. Daftarkan lagi ke Sistem (*Environment Variables - Path*). Klik *New*, lalu ketik: **`C:\Android\cmdline-tools\latest\bin`**.
5. Buka Command Prompt (CMD) biasa, lalu *copy-paste* perintah ini untuk mengunduh mesin Android:
   `sdkmanager "platform-tools" "platforms;android-34" "build-tools;34.0.0"`
   Tunggu hingga proses *download* selesai 100%.
6. Terakhir, ketik di CMD: `flutter doctor --android-licenses`. Tekan tombol **`y`** lalu *Enter* berulang kali hingga semua lisensi disetujui.

**Langkah 4: Membaca Pemeriksaan `flutter doctor`**
Ketik `flutter doctor` di CMD. Jika muncul pesan *error* di bawah ini, **Jangan Panik, Ini Solusinya:**
*   ❌ **[X] Visual Studio:** Tanda silang merah ini wajar karena Anda tidak menginstal program *Visual Studio C++* sebesar 10GB. **Solusi:** Abaikan saja! Fitur ini hanya untuk membuat aplikasi Windows (.exe). Untuk membuat aplikasi Android (HP) dan Web, Flutter tetap jalan 100% normal.
*   ❗ **[!] Android Studio (not installed):** Tanda seru ini muncul karena Anda menginstal Android lewat *Command Line* (Langkah 3), bukan men-download aplikasi Android Studio utuh. **Solusi:** Abaikan saja, toh kita akan mengoding menggunakan VS Code.

**Langkah 5: Ekstensi di VS Code & Formatter**
1. Buka VS Code, instal ekstensi: **Flutter**, **Dart**, dan **Awesome Flutter Snippets** (untuk jalan pintas penulisan kode cepat).
2. Buka file `.dart` > tekan `Ctrl + Shift + P` > ketik `Configure Default Formatter` > Pilih **Dart**.

---

## ⚙️ TAHAP 3: File Konfigurasi Pusat (settings.json)

VS Code menyimpan seluruh konfigurasi yang Anda klik di atas ke dalam satu file teks berformat JSON. Anda bisa melihat (atau menimpa) pengaturan VS Code Anda secara instan dengan cara ini:

1. Tekan `Ctrl + Shift + P` di VS Code.
2. Ketik **`Preferences: Open User Settings (JSON)`** lalu tekan Enter.
3. Anda akan melihat file bernama `settings.json`. Jika Anda ingin memindahkan settingan VS Code ini ke komputer lain, cukup salin (`copy`) semua teks yang ada di dalam file tersebut dan tempel (`paste`) di VS Code komputer baru.