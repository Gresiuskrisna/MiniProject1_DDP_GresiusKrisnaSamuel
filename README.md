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
%%{init: {
  'theme': 'base',
  'themeVariables': {
    'primaryColor': '#ffffff',
    'primaryTextColor': '#000000',
    'primaryBorderColor': '#000000',
    'lineColor': '#000000',
    'secondaryColor': '#ffffff',
    'tertiaryColor': '#ffffff'
  },
  'flowchart': {
    'curve': 'stepBefore'
  }
}}%%
flowchart TD
    Start([Mulai]) --> InitData[Inisialisasi data_latihan]
    InitData --> Menu[Tampilkan Menu FitLog]
    Menu --> InputPilihan[/Input pilihan 1-5/]
    InputPilihan --> CondPilihan{Pilihan Menu?}

    CondPilihan -- "1" --> M1_Check{len data_latihan == 0?}
    M1_Check -- Ya --> M1_Empty[/Cetak Data Kosong/]
    M1_Check -- Tidak --> M1_Print[/Print Semua Data Latihan/]
    M1_Empty --> Menu
    M1_Print --> Menu

    CondPilihan -- "2" --> M2_ID[/Input ID Baru/]
    M2_ID --> M2_CekID{Kosong / Duplikat?}
    M2_CekID -- Ya --> M2_ID
    M2_CekID -- Tidak --> M2_InputData[/Input Nama, Kategori, Target/]
    M2_InputData --> M2_Beban[/Input Beban kg/]
    M2_Beban --> M2_CekBeban{beban.isdigit?}
    M2_CekBeban -- Tidak --> M2_Beban
    M2_CekBeban -- Ya --> M2_Append[data_latihan.append]
    M2_Append --> Menu

    CondPilihan -- "3" --> M3_Check{len data_latihan == 0?}
    M3_Check -- Ya --> Menu
    M3_Check -- Tidak --> M3_InputCari[/Input cari_id/]
    M3_InputCari --> M3_CekID{ID Ketemu?}
    M3_CekID -- Tidak --> M3_Err[/Cetak ID Tidak Ditemukan/] --> Menu
    M3_CekID -- Ya --> M3_InputBaru[/Input Nama, Kategori, Target Baru/]
    M3_InputBaru --> M3_InputBeban[/Input Beban Baru Kosong/Digit/]
    M3_InputBeban --> M3_Update[Update Index data_latihan i]
    M3_Update --> Menu

    CondPilihan -- "4" --> M4_Check{len data_latihan == 0?}
    M4_Check -- Ya --> Menu
    M4_Check -- Tidak --> M4_InputHapus[/Input id_hapus/]
    M4_InputHapus --> M4_CekID{ID Ketemu?}
    M4_CekID -- Tidak --> M4_Err[/Cetak ID Tidak Ditemukan/] --> Menu
    M4_CekID -- Ya --> M4_Konfirm[/Konfirmasi y/n/]
    M4_Konfirm --> M4_CekY{Yakin 'y'?}
    M4_CekY -- Tidak --> M4_Batal[/Penghapusan Dibatalkan/] --> Menu
    M4_CekY -- Ya --> M4_Pop[data_latihan.pop i]
    M4_Pop --> Menu

    CondPilihan -- "5" --> M5_Exit[/Cetak Program Selesai/] --> End([Selesai])
    
