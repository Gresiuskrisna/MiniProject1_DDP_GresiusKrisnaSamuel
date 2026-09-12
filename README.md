*Nama: Gresius Krisna Samuel
NIM: 2609116058
Kelas: B*

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


# Hasil Pengujian Program

# 1. Menampilkan Daftar Latihan (Read)

*Gambar 1. Menampilkan seluruh daftar latihan yang tersimpan.*

Program menampilkan tabel data latihan awal yang mencakup ID, nama latihan, kategori otot, target latihan, dan beban (kg).


# 2. Menambahkan Data Latihan Baru (Create)

*Gambar 2. Pengujian penambahan data baru dan validasi input.*

Pengujian mencakup:
Validasi ID Duplikat: Menolak ID yang sudah terdaftar (misal `EX01`) dan meminta pengguna memasukkan ID lain (`EX04`).

Validasi Beban: Menolak input teks/huruf saat meminta beban (`berat`) dan baru memproses data setelah dimasukkan angka (`60`).

Pesan Sukses: Data `Deadlift` berhasil ditambahkan ke dalam daftar.



# 3. Memperbarui Data Latihan (Update)

*Gambar 3. Pengujian pembaruan data dan pencarian ID.*

Pengujian mencakup:
Validasi ID Tidak Ditemukan: Menampilkan pesan error saat memasukkan ID yang tidak ada (`EX99`).
Fitur Skip (ENTER): Memasukkan ID valid (`EX01`) lalu menekan ENTER untuk mempertahankan nilai lama pada kolom nama dan kategori, serta hanya memperbarui target dan beban.


# 4. Menghapus Data Latihan (Delete)

*Gambar 4. Pengujian penghapusan data dengan konfirmasi.*

Program mencari ID `EX04`, meminta konfirmasi `(y/n)` sebelum menghapus, dan menghapus data dari sistem setelah dikonfirmasi `y`.


# 5. Keluar Program (Exit)

*Gambar 5. Menampilkan pesan penutup saat memilih menu keluar.*

Program menghentikan perulangan (loop) dan menampilkan pesan penutup saat pengguna memilih opsi `5`.


# Flowchart Program
<img width="4135" height="3508" alt="1789204181138_0" src="https://github.com/user-attachments/assets/1c482cb7-5af4-4aa1-8865-e6aa25f11664" />

