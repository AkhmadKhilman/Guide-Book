# 📘 Buku Setup Master Visual Studio Code (Multi-Language)

Visual Studio Code (VS Code) adalah *text editor* (ruang kerja digital) tempat *programmer* menulis kode. Saat pertama kali diinstal, aplikasi ini masih kosong. Agar bisa digunakan untuk berbagai bahasa pemrograman, kita harus menambahkan "Ekstensi" (fitur tambahan) dan melakukan pengaturan khusus.

Panduan ini disusun sangat rinci agar pemula dapat merakit VS Code menjadi alat profesional tanpa *error*.

---

## 🛠️ TAHAP 1: Instalasi & Konfigurasi Dasar VS Code

**A. Cara Download & Install**
1. Buka *browser* dan kunjungi web resmi: [**code.visualstudio.com**](https://code.visualstudio.com/)
2. Klik tombol biru **Download for Windows**.
3. Buka file *installer* yang terunduh dan ikuti instruksi *Next*.
4. **SANGAT PENTING:** Saat Anda tiba di halaman yang menampilkan beberapa kotak centang (*checkboxes*), **CENTANG SEMUA KOTAKNYA**. Terutama opsi *"Add to PATH"* dan *"Add 'Open with Code' action to Windows Explorer"*. Ini memastikan VS Code terhubung ke sistem komputer Anda.
5. Lanjut klik *Next* dan *Install*. Buka VS Code setelah selesai.

**B. Konfigurasi Awal (Wajib Sebelum Mulai Ngoding)**
Agar VS Code nyaman digunakan, kita harus mengatur perilaku dasarnya:
1. Tekan tombol `Ctrl + ,` (Control dan Koma) secara bersamaan untuk membuka menu **Settings**.
2. Di kolom pencarian *Settings* (di atas), ketik dan aktifkan tiga fitur ini:
   * **Format On Save:** Centang kotaknya. *(Fungsi: VS Code otomatis merapikan spasi dan indentasi kode yang berantakan setiap kali Anda menekan `Ctrl + S`)*.
   * **Word Wrap:** Ubah nilainya menjadi `on`. *(Fungsi: Agar teks kode yang sangat panjang tidak menembus ke luar batas kanan layar, melainkan otomatis turun ke baris bawah)*.
   * **Bracket Pair Colorization:** Pastikan fitur ini aktif. *(Fungsi: Mewarnai pasangan tanda kurung `{}` atau `()` agar Anda tidak bingung saat kode mulai bertumpuk)*.

---

## 📑 TAHAP 2 - 7: SETUP BAHASA PEMROGRAMAN

Pilih bahasa pemrograman yang ingin Anda siapkan di bawah ini. Anda tidak perlu menginstal semuanya sekaligus, cukup instal yang sedang Anda pelajari.

### 🌐 TAHAP 2: Setup Frontend Web (HTML, CSS, JS)
**A. Ekstensi yang Diinstal:** *(Buka menu Extensions / ikon kotak-kotak di menu kiri VS Code, lalu cari)*
1. **Live Server** *(oleh Ritwick Dey)*: Membuka *server* lokal. Saat Anda menyimpan kode HTML/CSS, tampilan di *browser* otomatis memuat ulang (*refresh*) tanpa ditekan manual.
2. **Prettier - Code formatter** *(oleh Prettier)*: Standar industri untuk merapikan struktur kode web.
3. **Tailwind CSS IntelliSense** *(Opsional)*: Memberi saran *autocomplete* khusus *framework* Tailwind CSS.

**B. Pengaturan Formatter (Perapi Kode):**
Buka atau buat sembarang file berakhiran `.html` atau `.js` > Tekan `Ctrl + Shift + P` > Ketik dan pilih **`Configure Default Formatter`** > Pilih **Prettier - Code formatter**.

---

### 🐍 TAHAP 3: Setup Python
Pilih salah satu cara menyiapkan mesin Python:
* **Opsi A: Bagi yang SUDAH menginstal Laragon (Full)**
  Buka VS Code > tekan `Ctrl + Shift + P` > ketik `Python: Select Interpreter` > Pilih `Enter interpreter path...` > Cari file `python.exe` di folder Laragon (misal: `C:\laragon\bin\python\python-3.x\python.exe`).
* **Opsi B: Bagi yang BELUM pakai Laragon (Install Mandiri)**
  1. Kunjungi [**python.org/downloads**](https://www.python.org/downloads/) > Download Python.
  2. Buka *installer*. **KRUSIAL: Di pojok kiri bawah, WAJIB centang "Add Python to PATH"**. Lanjut *Install Now*.

**A. Ekstensi yang Diinstal:**
1. **Python** *(oleh Microsoft)*: Otak utama pendeteksi *error* Python.
2. **Black Formatter** *(oleh Microsoft)*: Standar perapi kode Python otomatis.

**B. Pengaturan Formatter:**
Buka file `.py` > tekan `Ctrl + Shift + P` > ketik `Configure Default Formatter` > Pilih **Black Formatter**.

---

### 🐘 TAHAP 4: Setup PHP (Native, CodeIgniter, Laravel)
**⚠️ Panduan Versi Stabil:**
* *PHP Dasar/Native:* Bebas, disarankan PHP 8.x dan MySQL 8.x.
* *CodeIgniter 3 (CI3):* WAJIB PHP 7.4 dan MySQL 5.7 (Jika pakai versi baru, akan banyak *error*).
* *CodeIgniter 4 & Laravel 11:* WAJIB versi terbaru (Minimal PHP 8.2 / 8.3 dan MySQL 8.x).

**A. Ekstensi yang Diinstal (Pilih Sesuai Kebutuhan):**
* **PHP Intelephense** *(oleh Ben Mewburn)* - **WAJIB:** Mesin pencari *error* dan *autocomplete* PHP.
* **Laravel Blade Snippets:** Mewarnai dan merapikan file tampilan Laravel (`.blade.php`).
* **Laravel Extra Intellisense:** Menebak otomatis nama *Route* dan *Controller* saat Anda mengetik di Laravel.
* **Codeigniter 4 Snippets:** Jalan pintas; ketik beberapa huruf, otomatis menjadi kerangka *Model/Controller*.
* **PHP Namespace Resolver:** Memasukkan jalur *Class* (`use App\Models\...`) otomatis hanya dengan klik kanan.

**B. Pengaturan Krusial (Mencegah Error Palsu):**
1. **Matikan PHP Bawaan VS Code:** Di menu Extensions, ketik `@builtin php`. Cari **PHP Language Features**, klik ikon *gear*, lalu **Disable**.
2. **Sambungkan Mesin PHP:** Buka Settings (`Ctrl + ,`), ketik `php validate executable path`, klik *Edit in settings.json*. Tambahkan lokasi PHP Anda:
   `"php.validate.executablePath": "C:\\laragon\\bin\\php\\php-8.3.x\\php.exe"`

**C. Pengaturan Formatter:**
Buka file `.php` > `Ctrl + Shift + P` > `Configure Default Formatter` > **PHP Intelephense**.

---

### 🎯 TAHAP 5: Setup C# (.NET Desktop & Backend)
**A. Instalasi .NET SDK:**
Kunjungi [**dotnet.microsoft.com/download**](https://dotnet.microsoft.com/download) > Unduh versi LTS terbaru (misal .NET 8) berformat *Windows x64 Installer* > Jalankan *installer* hingga selesai.

**B. Ekstensi yang Diinstal:**
1. **C# Dev Kit** *(oleh Microsoft)*: Fitur super setara Visual Studio raksasa.
2. **NuGet Gallery** *(oleh pcislo)*: Alat visual pasang pustaka eksternal (Library).
3. **Avalonia for VS Code** atau **.NET MAUI** *(Pilih sesuai framework Desktop yang Anda pakai)*.

**C. Catatan Wajib & Formatter:**
* **Login:** Klik ikon akun di pojok kiri bawah VS Code, *login* pakai akun Microsoft/GitHub.
* **Keamanan:** Jika muncul *pop-up "Do you trust the authors?"* saat buka folder, **WAJIB klik "Yes, I trust the authors"**.
* **Formatter:** Buka file `.cs` > `Ctrl + Shift + P` > `Configure Default Formatter` > **C#**.

---

### ☕ TAHAP 6: Setup Java
**A. Instalasi Java SDK (JDK):**
1. Kunjungi [**adoptium.net**](https://adoptium.net/) > Unduh **Temurin LTS** terbaru (misal Java 21) berformat `.msi`.
2. Buka *installer*. **KRUSIAL: Pada halaman Custom Setup, ubah ikon silang merah (X) di samping "Set JAVA_HOME variable" dan "Registry keys" menjadi "Will be installed on local hard drive"**.
3. *(Troubleshooting: Jika instalasi gagal karena perangkat tidak didukung, artinya Windows Anda masih 32-bit. Kunjungi halaman arsip, unduh installer berlabel **x86**).*

**B. Ekstensi & Formatter:**
1. Instal: **Extension Pack for Java** *(oleh Microsoft)* & **Spring Boot Extension Pack** *(opsional untuk web)*.
2. Formatter: Buka file `.java` > `Ctrl + Shift + P` > `Configure Default Formatter` > **Language Support for Java(TM) by Red Hat**.

---

### 📱 TAHAP 7: Setup Flutter (Mobile & Web)
*(Ikuti langkah ini perlahan)*

**1. Install Git:** Unduh dari [**git-scm.com/download/win**](https://git-scm.com/download/win), instal dengan klik *Next* sampai selesai.
**2. Install Flutter SDK:** 
* Unduh `.zip` dari [**flutter.dev/docs/get-started/install/windows**](https://flutter.dev/docs/get-started/install/windows).
* Ekstrak ke folder `C:\src\flutter`.
* Daftarkan ke sistem: Buka *Environment Variables* > *Edit System Environment Variables* > *Path* (di User variables) > *New* > Ketik: `C:\src\flutter\bin` > OK.
**3. Install Android SDK (Tanpa Android Studio):**
* Kunjungi web Android Studio, unduh `.zip` **Command line tools only**.
* Ekstrak ke `C:\Android\cmdline-tools\latest\` (pastikan di dalamnya ada folder `bin`).
* Daftarkan ke *Environment Variables* > *Path* > *New* > Ketik: `C:\Android\cmdline-tools\latest\bin`.
* Buka CMD, ketik: `sdkmanager "platform-tools" "platforms;android-34" "build-tools;34.0.0"`
* Selesai download, ketik: `flutter doctor --android-licenses` (Ketik `y` berulang kali sampai selesai).
**4. Membaca `flutter doctor`:**
* Tanda silang (X) di Visual Studio: **Abaikan!** (Itu hanya untuk aplikasi Windows .exe).
* Tanda seru (!) di Android Studio: **Abaikan!** (Kita pakai VS Code).
**5. Ekstensi & Formatter:**
* Instal: **Flutter**, **Dart**, dan **Awesome Flutter Snippets**.
* Formatter: Buka file `.dart` > `Ctrl + Shift + P` > `Configure Default Formatter` > **Dart**.

---

## ⚙️ TAHAP 8: File Konfigurasi Pusat (settings.json)
Anda bisa menyatukan seluruh *settingan* di atas via kode:
1. Tekan `Ctrl + Shift + P` > Ketik `Preferences: Open User Settings (JSON)`.
2. Jika Anda ingin memindahkan settingan VS Code ke komputer lain, cukup *copy* semua teks di file `settings.json` ini dan *paste* di VS Code komputer baru.

---

## 🚀 TAHAP 9: PANDUAN CEPAT (Membuat, Running & Backup Project)

Saat VS Code Anda sudah siap, ikuti contekkan berstandar industri ini untuk mulai membuat program dan mem-backup kode secara bersih (*clean backup*). **Aturan Emas: Jangan pernah mem-backup file yang bisa di-download ulang!**

### 1. 🎨 TAILWIND CSS
* **Membuat Project Lokal:** Buka terminal di folder kosong:
  `npm init -y` ➔ `npm install -D tailwindcss` ➔ `npx tailwindcss init`
* **Konfigurasi & Eksekusi:** Ubah `content` di file `tailwind.config.js` menjadi `["./*.{html,js}"]`. Jalankan perintah ini agar CSS otomatis ter-update saat ngoding:
  `npx tailwindcss -i ./input.css -o ./output.css --watch`
* **🧹 Backup Bersih:** Hapus folder `node_modules` sebelum di-ZIP. *(Jika ingin dipakai lagi, ketik `npm install`).*

### 2. 🐘 PHP (Laravel & CodeIgniter)
* **Membuat Project (Pilih Versi):**
  * *Laravel:* `composer create-project laravel/laravel:^10.0 nama_project` (Ubah 10.0 sesuai versi).
  * *CI4:* `composer create-project codeigniter4/appstarter:^4.3 nama_project`.
  * *CI3:* Ekstrak manual file zip CI3 ke `laragon/www`.
* **Eksekusi:** 
  * Laravel ➔ `php artisan serve` (Buka `localhost:8000`).
  * CI4 ➔ `php spark serve` (Buka `localhost:8080`).
* **🧹 Backup Bersih:** Hapus folder `vendor`. Untuk Laravel, jalankan `php artisan optimize:clear` di terminal lalu hapus `vendor`. *(Jika ingin dipakai lagi, ketik `composer install`).*

### 3. 🐍 PYTHON (Ubah ke .exe)
* **Build Project:** Instal alatnya: `pip install pyinstaller`. Ubah file ke .exe mandiri dengan perintah:
  `pyinstaller --onefile --windowed nama_file.py` *(Hapus --windowed jika aplikasi Anda berbasis terminal layar hitam).*
* **🧹 Backup Bersih:** Hapus folder `build/`, folder `dist/`, folder `__pycache__`, dan file `.spec`. Simpan file `.py` aslinya saja.

### 4. 🎯 C# .NET (Desktop & Web)
* **Membuat Project:** Di terminal ketik:
  * Web: `dotnet new webapp -o NamaWeb`
  * WinForms: `dotnet new winforms -o NamaDesktop`
  * Avalonia: Instal dulu kerangkanya (`dotnet new install Avalonia.Templates`), lalu `dotnet new avalonia.app -o NamaApp`.
* **Menambah Library (NuGet):** Tekan `Ctrl + Shift + P` > ketik `NuGet: Open NuGet Gallery` > Cari dan klik instal.
* **Eksekusi & Export ke .exe:** 
  * Run ➔ `dotnet run`.
  * Build .exe ➔ `dotnet publish -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true`.
* **🧹 Backup Bersih:** Di terminal, jalankan `dotnet clean`. Hapus manual folder `bin` dan `obj` sebelum men-ZIP project.

### 5. ☕ JAVA (Maven & JavaFX)
* **Membuat Project:** Tekan `Ctrl + Shift + P` > ketik `Java: Create Java Project` > Pilih **Maven** > Pilih `maven-archetype-quickstart` (Biasa) atau `javafx-archetype-simple` (GUI JavaFX).
* **Menambah Library:** Buka file `pom.xml`, tambahkan kode dependensi di dalam tag `<dependencies>`, dan *save*.
* **Eksekusi & Export ke .exe:** 
  * Run ➔ Klik tombol kecil "Run" di atas kode `public static void main`.
  * Build .exe ➔ Buka terminal, ketik `mvn clean package`. Lalu jadikan `.exe` dengan: `jpackage --type app-image --input target/ --main-jar nama.jar --name AplikasiKu --win-shortcut`.
* **🧹 Backup Bersih:** Di terminal, ketik `mvn clean`. Ini otomatis menghancurkan folder `target/` yang berat.

### 6. 📱 FLUTTER (Mobile & Web)
* **Membuat Project:** Ketik di terminal: `flutter create nama_app`.
* **Menambah/Menghapus Library:** Ketik `flutter pub add nama_package` atau `flutter pub remove nama_package`.
* **Eksekusi & Export:** 
  * Run ➔ Pilih perangkat di pojok kanan bawah VS Code (Chrome/Android), lalu tekan **F5**.
  * Build APK ➔ Ketik `flutter build apk --release` (File berada di `build/app/outputs/flutter-apk/`).
* **🧹 Backup Bersih:** Ketik perintah `flutter clean`. Ini akan menghapus folder `build/` dan `.dart_tool/` secara instan, menghemat kapasitas hingga bergiga-giga! *(Jika ingin dipakai lagi, ketik `flutter pub get`).*