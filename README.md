# IDENTITAS

**Nama: Hidayatul Mangunah**  
**NIM: H1D023009**  
**Shift KRS: F**  
**Shift Baru: E**

# Praktikum-1-Flutter
28 Oktober 2025

# Penjelasan
**1. Kelas Inti: Matrix**
Kelas Matrix adalah representasi data matriks. Ia menyimpan elemen dalam List<List<num>> (data) dan dimensinya (rows dan cols).
Konstruktor dan Validasi
Konstruktor Utama: Menerima data dan memvalidasi bahwa semua baris memiliki jumlah kolom yang sama (matriks harus teratur). Ia akan melempar ArgumentError jika matriks tidak valid.
Factory Matrix.zeros: Digunakan untuk membuat matriks yang semua elemennya nol dengan dimensi yang diminta.

Operasi Matriks
Kelas ini menggunakan Operator Overloading untuk membuat sintaks operasi matriks lebih intuitif:

Penjumlahan (operator +) & Pengurangan (operator -): Memastikan kedua matriks memiliki dimensi yang sama sebelum melakukan operasi elemen per elemen. Jika dimensi tidak cocok, ArgumentError dilemparkan.

Perkalian Skalar (operator * dengan num scalar): Mengalikan setiap elemen matriks dengan nilai skalar yang diberikan.

Perkalian Matriks (multiplyMatrix): Mengimplementasikan perkalian matriks standar. Memeriksa kompatibilitas: jumlah kolom matriks pertama harus sama dengan jumlah baris matriks kedua. Jika tidak, ArgumentError dilempar.

Transpose (transpose): Menukar posisi baris dan kolom matriks.

toString(): Digunakan untuk menghasilkan output matriks yang terformat rapi di konsol, dengan padding dan pembulatan dua desimal untuk keterbacaan yang baik.

**2. Fungsi Pembantu dan Input Interaktif**
Fungsi-fungsi privat (diawali _) bertanggung jawab mengelola interaksi pengguna di konsol.

Validasi Input:

_readNumber: Memastikan input adalah angka (int atau double) yang valid.

_readPositiveInt: Memastikan input adalah bilangan bulat positif (digunakan untuk menentukan dimensi matriks).

Kedua fungsi ini menggunakan loop while untuk terus meminta input hingga pengguna memberikan nilai yang valid, menjadikan aplikasi tahan terhadap kesalahan input pengguna.

Input Matriks (_readMatrix): Meminta pengguna memasukkan setiap elemen matriks secara individual berdasarkan dimensi yang sudah ditentukan, menggunakan _readNumber untuk memproses setiap nilai.

Output Matriks (_printMatrix): Mencetak matriks yang dihasilkan ke konsol dengan label yang jelas.

**3. Logika Aplikasi Utama (main)**
Fungsi main mengatur alur interaktif aplikasi.

Menu dan Loop: Program menampilkan menu operasi dan berjalan dalam loop do-while hingga pengguna memilih opsi '0' (Keluar).

Fungsi Handler Operasi:
_handleBinaryMatrixOperation: Fungsi umum untuk operasi yang melibatkan dua matriks (Penjumlahan, Pengurangan, Perkalian Matriks). Ia menerima fungsi operasi sebagai parameter, meminta input Matriks A dan B, dan melakukan pemeriksaan kompatibilitas dimensi akhir sebelum memanggil operasi matriks.
_handleScalarMultiplication dan _handleTranspose: Fungsi yang lebih sederhana untuk operasi satu matriks.

Penanganan Kesalahan Global: Seluruh blok operasi dalam main dibungkus dalam try-catch. Ini sangat penting untuk menangkap ArgumentError (misalnya, matriks tidak memiliki dimensi yang sama) yang dilemparkan dari kelas Matrix atau handler validasi. Saat kesalahan ditangkap, program mencetak pesan kesalahan yang jelas dan kembali ke menu utama alih-alih crash.

Singkatnya, kode ini adalah implementasi OOP yang solid, menyediakan fungsionalitas aljabar linear dasar dengan antarmuka konsol interaktif yang kuat dan memiliki penanganan kesalahan yang memadai.


**NB: Kalo misal pakai yang dart online maka bisa di run tapi tidak menggunakan import, bisa dilakukan import ketika menggunakan vscode**
