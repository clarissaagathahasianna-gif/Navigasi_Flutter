# Praktikum Navigasi Flutter

Project ini merupakan aplikasi Flutter yang dibuat untuk mempraktikkan konsep **navigasi, routing, dan responsive layout** menggunakan **Flutter Material 3**. Aplikasi mencakup beberapa jenis navigasi serta pengiriman data antarhalaman.

## Fitur Utama

* **Named Route** untuk mengatur perpindahan dari satu halaman ke halaman lainnya.
* **onGenerateRoute** untuk menangani routing yang membutuhkan parameter atau data tertentu.
* **onUnknownRoute** untuk memberikan penanganan ketika route yang diakses tidak tersedia.
* **Navigation Bar** yang digunakan pada tampilan dengan ukuran layar kecil.
* **Navigation Rail** yang digunakan pada perangkat dengan layar lebih lebar.
* **Navigation Drawer** sebagai menu navigasi yang muncul dari sisi layar.
* **TabBar dan TabBarView** untuk menampilkan jadwal berdasarkan kategori hari.
* **Passing data** untuk mengirim informasi dari satu halaman ke halaman detail.
* **Return value** untuk mengirim data dari halaman detail kembali ke halaman sebelumnya.
* **Halaman Catatan** yang dilengkapi dengan Floating Action Button.
* **Halaman Pengaturan dan Profil** sebagai bagian dari navigasi aplikasi.

## Teknologi yang Digunakan

* **Flutter**
* **Dart**
* **Material 3**
* **Navigator / Named Routes**

## Struktur Folder

```text
lib/
├── main.dart
├── navigation/
│   ├── app_routes.dart
│   └── kerangka_navigasi.dart
└── pages/
    ├── halaman_beranda.dart
    ├── halaman_catatan.dart
    ├── halaman_detail.dart
    ├── halaman_jadwal.dart
    ├── halaman_pengaturan.dart
    └── halaman_profil.dart
```

## Penjelasan File

| File                      | Fungsi                                                                                  |
| ------------------------- | --------------------------------------------------------------------------------------- |
| `main.dart`               | Menjadi entry point aplikasi serta mengatur konfigurasi utama `MaterialApp`.            |
| `app_routes.dart`         | Mengelola named route, route yang memiliki parameter, serta route yang tidak ditemukan. |
| `kerangka_navigasi.dart`  | Mengatur navigasi utama aplikasi, termasuk Drawer, Navigation Bar, dan Navigation Rail. |
| `halaman_beranda.dart`    | Menampilkan halaman utama serta contoh perpindahan menuju halaman detail.               |
| `halaman_jadwal.dart`     | Menampilkan informasi jadwal berdasarkan hari dengan menggunakan `TabBar`.              |
| `halaman_profil.dart`     | Menampilkan informasi profil mahasiswa dan menyediakan akses menuju halaman catatan.    |
| `halaman_detail.dart`     | Menampilkan informasi detail sekaligus mengirimkan data kembali ke halaman sebelumnya.  |
| `halaman_catatan.dart`    | Menampilkan halaman catatan dengan `Floating Action Button` dan `BottomAppBar`.         |
| `halaman_pengaturan.dart` | Menampilkan berbagai pengaturan yang tersedia pada aplikasi.                            |

## Struktur Navigasi

```text
                    Kerangka Navigasi
                           │
             ┌─────────────┼─────────────┐
             │             │             │
          Beranda        Jadwal        Profil
                                         │
                                         ▼
                                      Catatan

Drawer
  └── Pengaturan

Beranda / Jadwal
      │
      ▼
    Detail
```

## Routing

Beberapa route utama yang digunakan dalam aplikasi yaitu:

```text
/              → KerangkaNavigasi
/detail        → HalamanDetail
/pengaturan    → HalamanPengaturan
/catatan       → HalamanCatatan
```

Route `/detail` dapat menerima data berupa:

```dart
{
  'judul': '...',
  'keterangan': '...'
}
```

Selain menerima data, halaman detail juga dapat mengembalikan nilai ke halaman sebelumnya menggunakan:

```dart
Navigator.pop(context, 'Data dari halaman detail');
```

## Responsive Layout

Tampilan aplikasi dibuat agar dapat menyesuaikan dengan ukuran layar perangkat.

* **Lebar layar < 600 px** → menggunakan `NavigationBar`.
* **Lebar layar ≥ 600 px** → menggunakan `NavigationRail`.
* **NavigationDrawer** tetap tersedia sebagai alternatif menu navigasi dari sisi layar.

Dengan penerapan responsive layout, tampilan navigasi dapat menyesuaikan perangkat dengan ukuran layar yang berbeda.

## Cara Menjalankan

Pastikan Flutter telah terpasang dan dikonfigurasi pada perangkat. Setelah itu, jalankan perintah berikut:

```bash
flutter pub get
flutter run
```

Untuk memeriksa apakah environment Flutter sudah dikonfigurasi dengan baik, gunakan:

```bash
flutter doctor
```

## Status Project

Project ini merupakan **project praktikum Flutter Modul 2** yang berfokus pada penerapan berbagai konsep navigasi dan routing, meliputi:

* Navigasi antarhalaman
* Named Route
* Passing arguments
* Return value dari halaman
* Navigation Drawer
* Navigation Bar
* Navigation Rail
* Responsive layout
* TabBar dan TabBarView
* Error handling pada route
