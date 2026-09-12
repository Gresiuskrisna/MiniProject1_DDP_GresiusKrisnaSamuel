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



Flowchart Program
<img width="600" height="339" alt="Copied_Item_1789195621318" src="https://github.com/user-attachments/assets/82784dfe-7813-4c44-a005-11d2696143e7" />

