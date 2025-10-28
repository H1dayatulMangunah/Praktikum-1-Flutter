# IDENTITAS

**Nama: Hidayatul Mangunah**  
**NIM: H1D023009**  
**Shift KRS: F**  
**Shift Baru: E**

# Praktikum-1-Flutter
28 Oktober 2025

# Penjelasan
#1. Import dan Fungsi Operasi Dasar
import 'dart:io';
Meskipun di program ini tidak ada input/output interaktif yang menggunakan dart:io, baris ini sering disertakan dalam program Dart. Pada contoh ini, baris ini tidak memiliki fungsi yang relevan karena tidak ada penggunaan kelas atau fungsi dari dart:io (seperti stdin.readLineSync()).
Fungsi Operasi Matematika
Empat fungsi ini mendefinisikan operasi dasar, semuanya menggunakan bahasa Indonesia (tambah, kurang, kali, bagi):
FungsiTipe Nilai KembaliParameterDeskripsitambah(int a, int b)intDua bilangan bulat (int)Mengembalikan hasil penambahan $a + b$.kurang(int a, int b)intDua bilangan bulat (int)Mengembalikan hasil pengurangan $a - b$.kali(int a, int b)intDua bilangan bulat (int)Mengembalikan hasil perkalian $a \times b$.bagi(num a, num b)doubleDua bilangan (num)Mengembalikan hasil pembagian $a / b$ sebagai bilangan pecahan (double).
Catatan: Fungsi bagi menggunakan tipe num untuk parameternya. Tipe num adalah supertipe untuk int dan double, memungkinkan fungsi ini menerima bilangan bulat atau bilangan pecahan sebagai input. Hasilnya selalu double untuk akurasi pembagian.

#2. Penanganan Kesalahan (Error Handling) pada Pembagian
Fungsi bagi memiliki logika penting untuk mencegah pembagian dengan nol, yang secara matematis tidak terdefinisi dan akan menyebabkan crash pada program jika tidak ditangani.
Dart
double bagi(num a, num b) {
  if (b == 0) {
    throw ArgumentError('Pembagian oleh nol tidak diizinkan.');
  }
  return a / b;
}
Pengecekan: Baris if (b == 0) memeriksa apakah pembagi ($b$) adalah nol. Pengecualian: Jika pembagi nol, program melemparkan (throw) sebuah objek ArgumentError dengan pesan kesalahan yang jelas. Ini menghentikan eksekusi normal fungsi dan memberitahu bagian program yang memanggilnya bahwa ada masalah.

#3. Fungsi Utama (main) dan Eksekusi
Fungsi main adalah titik awal eksekusi program. Bagian ini berisi contoh-contoh penggunaan dari keempat fungsi kalkulator tersebut.
Contoh Operasi Sukses
Program menampilkan hasil dari operasi tambah, kurang, kali, dan satu contoh sukses dari bagi.
Dart
// Addition example
int num1Add = 10;
int num2Add = 5;
int hasilTambah = tambah(num1Add, num2Add);
print('$num1Add + $num2Add = $hasilTambah'); // Output: 10 + 5 = 15
// ... dan seterusnya untuk kurang dan kali
Penanganan try-catch
Untuk operasi bagi, kode menggunakan blok try-catch untuk mengantisipasi kesalahan pembagian dengan nol yang mungkin terjadi.Contoh Pembagian Sukses

try {
  double hasilBagi = bagi(num1Bagi, num2Bagi);
  print('$num1Bagi / $num2Bagi = $hasilBagi'); // Output: 20 / 4 = 5.0
} on ArgumentError catch (e) {
  print('Error: ${e.message}');
}
Blok try mencoba menjalankan operasi bagi(20, 4). Karena pembagi bukan nol, operasi berhasil dan hasilnya dicetak.
Blok catch diabaikan karena tidak ada kesalahan yang dilempar.

Contoh Pembagian dengan Nol (Error Handling)
num num3Bagi = 10;
num num4Bagi = 0;
try {
  double hasilBagiNol = bagi(num3Bagi, num4Bagi); // Ini akan melempar ArgumentError
  // ...
} on ArgumentError catch (e) {
  print('Error pembagian 10 / 0: Pembagian oleh nol tidak diizinkan.');
}

Blok try mencoba menjalankan bagi(10, 0).
Fungsi bagi mendeteksi $b=0$ dan melemparkan ArgumentError.
Eksekusi melompat ke blok catch.
Blok catch menangkap kesalahan yang bertipe ArgumentError dan mencetak pesan kesalahannya, mencegah program crash.

Output Program

Jika kode ini dijalankan, output yang akan dihasilkan adalah:Aplikasi Kalkulator Sederhana
-----------------------------
10 + 5 = 15
15 - 7 = 8
4 * 6 = 24
20 / 4 = 5.0
Error pembagian 10 / 0: Pembagian oleh nol tidak diizinkan.

-----------------------------
Selesai.
