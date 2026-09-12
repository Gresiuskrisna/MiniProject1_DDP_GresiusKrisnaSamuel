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

Berikut adalah dokumentasi pengujian fitur program FitLog menggunakan Pydroid 3:

# 1. Pengujian Lihat Data & Tambah Data (Create + Validasi Error)
<img width="719" height="944" alt="1789206475034_0" src="https://github.com/user-attachments/assets/0f2411eb-0c43-49a8-8513-80b7eb3b303b" />

*Gambar 1. Pengujian menampilkan data awal, penolakan ID duplikat, dan penolakan input beban non-angka.*

*Menu 1 (Read): Menampilkan daftar 3 data awal yang tersimpan.*

*Validasi ID Duplikat: Saat memasukkan ID `ex01`, sistem mendeteksi ID sudah digunakan dan meminta input ulang secara berulang.*

*Validasi Beban Non-Angka: Saat memasukkan beban berupa huruf (`dua puluh`), sistem menampilkan pesan error `"Harus pakai angka!"` dan mengulang permintaan input.*

*Sukses Create:Data latihan `EX04` (Deadlift) berhasil ditambahkan setelah input valid (`20` kg).*


# 2. Pengujian Ubah Data (Update + Validasi Enter/Skip)
<img width="720" height="1172" alt="1789206475099_1" src="https://github.com/user-attachments/assets/ab091273-74f1-4de9-89be-8f220db98321" />


*Gambar 2. Pengujian pencarian ID tidak ada dan pembaruan data dengan fitur skip ENTER.*

*Validasi ID Tidak Ditemukan: Memasukkan ID `ex05` menampilkan pesan `"ID tidak ditemukan."` dan kembali ke menu utama.*

*Fitur Skip (ENTER):Memperbarui data `ex02` (Barbell Squat) dengan menekan ENTER pada baris Nama dan Kategori untuk mempertahankan nilai lama, serta hanya mengubah Target (`4 x 12`) dan Beban (`60` kg).*


# 3. Pengujian Hapus Data & Keluar Program (Delete & Exit)
<img width="719" height="1479" alt="1789206475165_2" src="https://github.com/user-attachments/assets/57fed22c-5de0-4881-a5ba-8f5e0a0b5a93" />

*Gambar 3. Pengujian konfirmasi hapus data, verifikasi tabel akhir, dan keluar program.*

*Menu 4 (Delete): Menghapus data `ex03` (Pull Up) dengan konfirmasi `y`.*

*Verifikasi Data: Memilih Menu 1 untuk memastikan data `EX03` sudah terhapus dan urutan nomor/data diperbarui.*

*Menu 5 (Exit): Program menghentikan perulangan dan menampilkan pesan `"Program selesai"` serta `[Program finished]`.*



# Flowchart Program
<img width="3022" height="2301" alt="1789204389573_1" src="https://github.com/user-attachments/assets/8b7df663-10a5-48c8-8a35-bfe4bac075c0" />


