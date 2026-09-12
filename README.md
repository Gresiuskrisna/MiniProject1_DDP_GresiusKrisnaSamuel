# Dokumentasi Program FitLog

FitLog adalah program yang dibuat untuk mencatat dan mengelola rencana latihan fisik. Program ini memakai konsep CRUD (Create, Read, Update, Delete) sederhana dengan menggunakan struktur data list dan tuple.


# Fitur Program

1. Lihat Data Latihan (Read)
   Menampilkan seluruh daftar rencana latihan yang sudah tersimpan dalam tabel ringkas.

2. Tambah Data Latihan (Create)
   Menambahkan data latihan baru ke dalam sistem. Fitur ini dilengkapi validasi agar ID tidak boleh kosong atau duplikat, serta memastikan input beban berbentuk angka.

3. Ubah Data Latihan (Update)
   Memperbarui data latihan berdasarkan ID. Pengguna dapat menekan tombol ENTER jika tidak ingin mengubah nilai dari kolom tertentu.

4. Hapus Data Latihan (Delete)
   Menghapus data latihan tertentu dari sistem berdasarkan ID dengan konfirmasi terlebih dahulu.

5. Keluar (Exit)
   Menghentikan jalannya program.



# Struktur Data

Data disimpan menggunakan variabel list bernama data_latihan. Setiap elemen di dalamnya berupa tuple yang memuat ID, nama latihan, kategori otot, target latihan, dan beban (kg).

Format tuple:
(ID, Nama Latihan, Kategori Otot, Target, Beban)

Contoh data awal:
data_latihan = 
[
    ("EX01", "Bench Press", "Dada", "4 x 10", 40),
    ("EX02", "Barbell Squat", "Kaki", "3 x 12", 50),
    ("EX03", "Pull Up", "Punggung", "3 x 8", 0)
]

# Penjelasan Sintaks dan Fungsi Utama

# 1. len(data_latihan)
Mengembalikan jumlah total elemen dalam variabel `data_latihan`. 
Penggunaan: Digunakan pada kondisi `len(data_latihan) == 0` untuk mengecek apakah daftar latihan masih kosong sebelum menjalankan operasi Read, Update, atau Delete.

# 2. .isdigit()
Metode string untuk mengecek apakah seluruh karakter dalam suatu string berupa angka (0–9).
Penggunaan: Digunakan pada validasi input beban (`beban.isdigit()`). Jika pengguna memasukkan huruf atau karakter non-angka, program akan menampilkan pesan error dan meminta input ulang.

# 4. .lower() dan .upper()
.lower(): Mengubah seluruh huruf menjadi kecil. Digunakan pada konfirmasi penghapusan `konfirmasi.lower() == 'y'` agar input seperti `'Y'` maupun `'y'` tetap terbaca valid.
  
.upper(): Mengubah seluruh huruf menjadi kapital. Digunakan pada input ID agar format ID konsisten (misalnya `ex01` otomatis diubah menjadi `EX01`).

# 5. data_latihan.append(...)
Menambahkan elemen baru dalam bentuk `tuple` ke baris paling akhir dari `list`.
Penggunaan: Digunakan pada fitur Create setelah semua validasi ID dan beban terpenuhi.

# 6. data_latihan.pop(i)
Menghapus elemen pada indeks tertentu (i) dari list sekaligus mengembalikan nilai elemen yang dihapus.
Penggunaan: Digunakan pada fitur Delete setelah ID ditemukan dan pengguna memberikan konfirmasi `y`.

# 7. Perulangan while True dan break
while True: Membikin program berjalan terus-menerus (sistem looping menu utama).
break: Menghentikan perulangan dan keluar dari program saat pengguna memilih menu nomor 5.


# Flowchart Program
<img width="4135" height="2338" alt="1789196847046_0" src="https://github.com/user-attachments/assets/aac2c392-169b-4128-8a85-cc1d866b5190" />

