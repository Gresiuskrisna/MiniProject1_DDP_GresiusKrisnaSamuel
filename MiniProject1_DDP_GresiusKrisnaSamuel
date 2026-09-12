# Program Manajemen Latihan Fisik (FitLog)

data_latihan = [
    ("EX01", "Bench Press", "Dada", "4 x 10", 40),
    ("EX02", "Barbell Squat", "Kaki", "3 x 12", 50),
    ("EX03", "Pull Up", "Punggung", "3 x 8", 0)
]

while True:
    print("\n  MENU UTAMA FITLOG ")
    print("1. Lihat Data Latihan")
    print("2. Tambah Data Latihan")
    print("3. Ubah Data Latihan")
    print("4. Hapus Data Latihan")
    print("5. Keluar")
    
    pilihan = input("Pilih menu (1-5): ")

    #READ (Menampilkan Data)
    if pilihan == "1":
        print("\n             DAFTAR RENCANA LATIHAN         ")
        if len(data_latihan) == 0:
            print("Data latihan masih kosong.")
        else:
            print("No | ID | Nama Latihan | Kategori | Target | Beban")
            print("-" * 50)
            no = 1
            for item in data_latihan:
                print(f"{no}. {item[0]} | {item[1]} | {item[2]} | {item[3]} | {item[4]} kg")
                no += 1



    #CREATE (Menambah Data)
    elif pilihan == "2":
        print("\n  TAMBAH DATA LATIHAN ")
        
        #Validasi ID
        while True:
            id_baru = input("Masukkan ID Latihan: ").upper()
            if id_baru == "":
                print("ID tidak boleh kosong.")
                continue
            
            sudah_ada = False
            for item in data_latihan:
                if item[0] == id_baru:
                    sudah_ada = True
            
            if sudah_ada:
                print("ID sudah digunakan, Silahkan gunakan ID lain.")
            else:
                break

        nama = input("Masukkan Nama Latihan: ")
        kategori = input("Masukkan Kategori Otot: ")
        target = input("Masukkan Target (contoh: 4 x 10): ")

        #Validasi Beban
        while True:
            beban = input("Masukkan Beban (kg): ")
            if beban.isdigit():
                beban = int(beban)
                break
            print("Harus pakai angka!")
              
        data_latihan.append((id_baru, nama, kategori, target, beban))
        print("Data latihan berhasil ditambahkan.")


    #UPDATE (Mengubah Data)
    elif pilihan == "3":
        print("\n  UBAH DATA LATIHAN ")
        if len(data_latihan) == 0:
            print("Data masih kosong.")
        else:
            cari_id = input("Masukkan ID yang mau diubah: ").upper()
            ada = False

            for i in range(len(data_latihan)):
                item = data_latihan[i]
                if item[0] == cari_id:
                    ada = True
                    print(f"\nData lama: {item[1]} | {item[2]} | {item[3]} | {item[4]} kg")
                    print("(Tekan ENTER jika tidak ingin mengubah data)")

                    nama = input(f"Nama baru: ")
                    if nama == "":
                        nama = item[1]

                    kategori = input(f"Kategori baru: ")
                    if kategori == "":
                        kategori = item[2]

                    target = input(f"Target baru: ")
                    if target == "":
                        target = item[3]

                    while True:
                        beban = input(f"Beban baru: ")
                        if beban == "":
                            beban = item[4]
                            break
                        if beban.isdigit():
                            beban = int(beban)
                            break
                        print("Harus pakai angka!")

                    data_latihan[i] = (cari_id, nama, kategori, target, beban)
                    print("Data berhasil diperbarui.")
                    break

            if not ada:
                print("ID tidak ditemukan.")
                

    #DELETE (Menghapus Data)
    elif pilihan == "4":
        print("\n  HAPUS DATA LATIHAN ")
        if len(data_latihan) == 0:
            print("Data masih kosong.")
        else:
            id_hapus = input("Masukkan ID yang mau dihapus: ").upper()
            ada = False

            for i in range(len(data_latihan)):
                if data_latihan[i][0] == id_hapus:
                    ada = True
                    nama = data_latihan[i][1]
                    validasi = input(f"Yakin ingin menghapus {nama}? (y/n): ").lower()
                    if validasi == 'y':
                        data_latihan.pop(i)
                        print("Data berhasil dihapus.")
                    else:
                        print("Penghapusan dibatalkan.")
                    break

            if not ada:
                print("ID tidak ditemukan.")


    #Exit
    elif pilihan == "5":
        print("Program selesai")
        break


    else:
        print("Pilihan menu tidak valid, silakan coba lagi.")
