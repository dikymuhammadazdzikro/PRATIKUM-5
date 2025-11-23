# Praktikum 5 – Dictionary  
Program Daftar Nilai Mahasiswa (Python)

Program ini dibuat untuk memenuhi Tugas Praktikum 5 pada mata kuliah Pemrograman Dasar.  
Tujuan tugas ini adalah memahami penggunaan **Dictionary** di Python untuk menyimpan data  
berdasarkan pasangan **key–value**, serta mengelola data mahasiswa melalui berbagai operasi.

---

## Deskripsi Program

Program ini digunakan untuk mengelola **daftar nilai mahasiswa** dengan fitur:

- Menambah data mahasiswa  
- Mengubah data mahasiswa  
- Menghapus data mahasiswa  
- Menampilkan seluruh data  
- Mencari data berdasarkan NIM atau nama  
- Keluar program  

Setiap mahasiswa disimpan menggunakan struktur dictionary sebagai berikut:
data_mahasiswa = {
'NIM': {
'nama': 'Nama Mahasiswa',
'tugas': nilai,
'uts': nilai,
'uas': nilai,
'akhir': nilai_akhir
}
}

**Perhitungan Nilai Akhir:**
Nilai Akhir = (Tugas × 30%) + (UTS × 35%) + (UAS × 35%)

---

## kode program

data = {}

while True:
    print("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari (K)eluar]")
    menu = input("Pilih menu: ").lower()

    # TAMBAH
    if menu == "t":
        print("\nTambah Data")
        nim = input("NIM       : ")
        nama = input("Nama      : ")
        uts = int(input("Nilai UTS : "))
        uas = int(input("Nilai UAS : "))
        tugas = int(input("Nilai Tugas : "))

        akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
        data[nim] = [nama, tugas, uts, uas, akhir]

    # LIHAT
    elif menu == "l":
        print("\nDaftar Nilai")
        print("==========================================================================")
        print("| NO |   NIM   |    NAMA    | TUGAS | UTS | UAS | AKHIR |")
        print("==========================================================================")

        if data:
            no = 1
            for nim, nilai in data.items():
                nama, tugas, uts, uas, akhir = nilai
                print(f"| {no:<2} | {nim:<7} | {nama:<10} | {tugas:<5} | {uts:<3} | {uas:<3} | {akhir:<5.2f} |")
                no += 1
        else:
            print("|                           TIDAK ADA DATA                              |")

        print("==========================================================================")

    # UBAH
    elif menu == "u":
        nim = input("Masukkan NIM yang ingin diubah: ")
        if nim in data:
            print("Data ditemukan. Silakan ubah.")
            nama = input("Nama baru      : ")
            tugas = int(input("Nilai Tugas    : "))
            uts = int(input("Nilai UTS      : "))
            uas = int(input("Nilai UAS      : "))
            akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
            data[nim] = [nama, tugas, uts, uas, akhir]
        else:
            print("Data tidak ditemukan.")

    # HAPUS
    elif menu == "h":
        nim = input("Masukkan NIM yang ingin dihapus: ")
        if nim in data:
            del data[nim]
            print("Data berhasil dihapus.")
        else:
            print("Data tidak ditemukan.")

    # CARI
    elif menu == "c":
        nim = input("Masukkan NIM yang dicari: ")
        if nim in data:
            nama, tugas, uts, uas, akhir = data[nim]
            print("\nData Ditemukan:")
            print(f"NIM   : {nim}")
            print(f"Nama  : {nama}")
            print(f"Tugas : {tugas}")
            print(f"UTS   : {uts}")
            print(f"UAS   : {uas}")
            print(f"Akhir : {akhir:.2f}")
        else:
            print("Data tidak ditemukan.")

    # KELUAR
    elif menu == "k":
        break

    else:
        print("Menu tidak valid!")

## Hasil Run
<img width="244" height="318" alt="Hasil program" src="https://github.com/user-attachments/assets/283b3d49-25cc-4af4-89fa-6e28cd27d0ab" />


## Flowchart Program

<img width="1024" height="1536" alt="ChatGPT Image Nov 23, 2025, 10_39_41 AM" src="https://github.com/user-attachments/assets/451b33c2-c277-43a0-b12e-e45ab5807a86" />
