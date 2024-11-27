# Dwi Okta Ramadhani
# TI.24.A.1

# Program Menampilkan Daftar Nilai Mahasiswa
# Deskripsi Program
Program ini dibuat menggunakan bahasa python Dictionary dengan fitur:
pengguna untuk mengelola data mahasiswa, termasuk menambah, mengubah, menghapus, dan menampilkan nilai mahasiswa
## Flowchart Programan
![Flowchart](https://github.com/Dwiokta10/Praktikum6/blob/main/flowchartprak6.png)
# Kode Program
```python
# Program Input Nilai Mahasiswa
# Program ini berfungsi untuk mengelola data nilai mahasiswa, termasuk menambah, mengubah, menghapus, menampilkan, dan mencari data.

# Dictionary untuk menyimpan data mahasiswa
data_mahasiswa = {}

# Fungsi untuk menambah data mahasiswa baru
def tambah_data():
    print("\nTambah Data Mahasiswa")
    nim = input("NIM: ")  # Input NIM mahasiswa
    nama = input("Nama: ")  # Input nama mahasiswa
    nilai_tugas = float(input("Nilai Tugas: "))  # Input nilai tugas (float)
    nilai_uts = float(input("Nilai UTS: "))  # Input nilai UTS (float)
    nilai_uas = float(input("Nilai UAS: "))  # Input nilai UAS (float)
    
    # Hitung nilai akhir dengan bobot 30% tugas, 35% UTS, 35% UAS
    nilai_akhir = (nilai_tugas * 0.3) + (nilai_uts * 0.35) + (nilai_uas * 0.35)
    
    # Simpan data ke dictionary
    data_mahasiswa[nim] = {
        "nama": nama,
        "tugas": nilai_tugas,
        "uts": nilai_uts,
        "uas": nilai_uas,
        "akhir": nilai_akhir,
    }
    print("Data berhasil ditambahkan!")

# Fungsi untuk mengubah data mahasiswa berdasarkan NIM
def ubah_data():
    print("\nUbah Data Mahasiswa")
    nim = input("Masukkan NIM yang akan diubah: ")
    if nim in data_mahasiswa:  # Cek apakah NIM ada dalam data
        print("Data ditemukan. Masukkan data baru:")
        nama = input("Nama: ")
        nilai_tugas = float(input("Nilai Tugas: "))
        nilai_uts = float(input("Nilai UTS: "))
        nilai_uas = float(input("Nilai UAS: "))
        
        # Hitung nilai akhir baru
        nilai_akhir = (nilai_tugas * 0.3) + (nilai_uts * 0.35) + (nilai_uas * 0.35)
        
        # Perbarui data di dictionary
        data_mahasiswa[nim] = {
            "nama": nama,
            "tugas": nilai_tugas,
            "uts": nilai_uts,
            "uas": nilai_uas,
            "akhir": nilai_akhir,
        }
        print("Data berhasil diubah!")
    else:
        print("Data tidak ditemukan.")

# Fungsi untuk menghapus data mahasiswa berdasarkan NIM
def hapus_data():
    print("\nHapus Data Mahasiswa")
    nim = input("Masukkan NIM yang akan dihapus: ")
    if nim in data_mahasiswa:  # Cek apakah NIM ada dalam data
        del data_mahasiswa[nim]  # Hapus data dari dictionary
        print("Data berhasil dihapus!")
    else:
        print("Data tidak ditemukan.")

# Fungsi untuk menampilkan semua data mahasiswa
def tampilkan_data():
    print("\nDaftar Nilai Mahasiswa")
    if data_mahasiswa:  # Cek apakah ada data mahasiswa
        print("="*60)
        print("| NO |    NIM    |    NAMA    | TUGAS | UTS | UAS | AKHIR |")
        print("="*60)
        for i, (nim, data) in enumerate(data_mahasiswa.items(), start=1):
            # Tampilkan setiap data mahasiswa dengan format tabel
            print(f"| {i:<2} | {nim:<9} | {data['nama']:<10} | {data['tugas']:<5} | {data['uts']:<3} | {data['uas']:<3} | {data['akhir']:<5.2f} |")
        print("="*60)
    else:
        print("Tidak ada data.")

# Fungsi untuk mencari data mahasiswa berdasarkan NIM
def cari_data():
    print("\nCari Data Mahasiswa")
    nim = input("Masukkan NIM yang dicari: ")
    if nim in data_mahasiswa:  # Cek apakah NIM ada dalam data
        data = data_mahasiswa[nim]
        print("="*40)
        print(f"NIM    : {nim}")
        print(f"Nama   : {data['nama']}")
        print(f"Tugas  : {data['tugas']}")
        print(f"UTS    : {data['uts']}")
        print(f"UAS    : {data['uas']}")
        print(f"Akhir  : {data['akhir']:.2f}")
        print("="*40)
    else:
        print("Data tidak ditemukan.")

# Program utama dengan menu pilihan
while True:
    print("\nMenu Utama:")
    print("(T)ambah Data")
    print("(U)bah Data")
    print("(H)apus Data")
    print("(L)ihat Data")
    print("(C)ari Data")
    print("(K)eluar")
    pilihan = input("Pilih menu: ").lower()  # Input pilihan menu

    # Kondisi untuk mengeksekusi fungsi sesuai pilihan menu
    if pilihan == 't':
        tambah_data()
    elif pilihan == 'u':
        ubah_data()
    elif pilihan == 'h':
        hapus_data()
    elif pilihan == 'l':
        tampilkan_data()
    elif pilihan == 'c':
        cari_data()
    elif pilihan == 'k':
        print("Keluar dari program. Terima kasih!")
        break
    else:
        print("Pilihan tidak valid. Silakan coba lagi.")


```
# Output Program
```
PS C:\Users\acer\Documents\KULIAH\PEMROGRAMAN\Pratikum 6 Bahasa Pemrograman> python -u "c:\Users\acer\Documents\KULIAH\PEMROGRAMAN\Pratikum 6 Bahasa Pemrograman\Daftar nilai mhs dictionary.py"

Menu Utama:
(T)ambah Data
(U)bah Data
(H)apus Data
(L)ihat Data
(C)ari Data
(K)eluar
Pilih menu: T

Tambah Data Mahasiswa
NIM: 312410068
Nama: Kenzi
Nilai Tugas: 98
Nilai UTS: 96
Nilai UAS: 99
Data berhasil ditambahkan!

Menu Utama:
(T)ambah Data
(U)bah Data
(H)apus Data
(L)ihat Data
(C)ari Data
(K)eluar
Pilih menu: T

Tambah Data Mahasiswa
NIM: 312410098
Nama: Ayen
Nilai Tugas: 97
Nilai UTS: 98
Nilai UAS: 99
Data berhasil ditambahkan!

Menu Utama:
(T)ambah Data
(U)bah Data
(H)apus Data
(L)ihat Data
(C)ari Data
(K)eluar
Pilih menu: T

Tambah Data Mahasiswa
NIM: 312410053
Nama: Marseal
Nilai Tugas: 98
Nilai UTS: 96
Nilai UAS: 90
Data berhasil ditambahkan!

Menu Utama:
(T)ambah Data
(U)bah Data
(H)apus Data
(L)ihat Data
(C)ari Data
(K)eluar
Pilih menu: T

Tambah Data Mahasiswa
NIM: 312410045
Nama: Budi
Nilai Tugas: 98
Nilai UTS: 96
Nilai UAS: 99
Data berhasil ditambahkan!

Menu Utama:
(T)ambah Data
(U)bah Data
(H)apus Data
(L)ihat Data
(C)ari Data
(K)eluar
Pilih menu: T

Tambah Data Mahasiswa
NIM: 312410042
Nama: Loriska
Nilai Tugas: 87
Nilai UTS: 99
Nilai UAS: 94
Data berhasil ditambahkan!

Menu Utama:
(T)ambah Data
(U)bah Data
(H)apus Data
(L)ihat Data
(C)ari Data
(K)eluar
Pilih menu: T

Tambah Data Mahasiswa
NIM: 312410056
Nama: Dwi
Nilai Tugas: 100
Nilai UTS: 100
Nilai UAS: 100
Data berhasil ditambahkan!

Menu Utama:
(T)ambah Data
(U)bah Data
(H)apus Data
(L)ihat Data
(C)ari Data
(K)eluar
Pilih menu: L

Daftar Nilai Mahasiswa
============================================================
| NO |    NIM    |    NAMA    | TUGAS | UTS | UAS | AKHIR |
============================================================
| 1  | 312410068 | Kenzi      | 98.0  | 96.0 | 99.0 | 97.65 |
| 2  | 312410098 | Ayen       | 97.0  | 98.0 | 99.0 | 98.05 |
| 3  | 312410053 | Marseal    | 98.0  | 96.0 | 90.0 | 94.50 |
| 4  | 312410045 | Budi       | 98.0  | 96.0 | 99.0 | 97.65 |
| 5  | 312410042 | Loriska    | 87.0  | 99.0 | 94.0 | 93.65 |
| 6  | 312410056 | Dwi        | 100.0 | 100.0 | 100.0 | 100.00 |
============================================================

Menu Utama:
(T)ambah Data
(U)bah Data
(H)apus Data
(L)ihat Data
(C)ari Data
(K)eluar
Pilih menu: K
Keluar dari program. Terima kasih!
PS C:\Users\acer\Documents\KULIAH\PEMROGRAMAN\Pratikum 6 Bahasa Pemrograman> 
```
# Cara Kerja Program
1. *Inisialisasi*:
   - Program dimulai dengan mendeklarasikan dictionary kosong mahasiswa untuk menyimpan data mahasiswa.

2. *Menu Utama*:
   - Program menampilkan menu interaktif yang memungkinkan pengguna untuk memilih salah satu dari lima opsi:
     - *Tambah Data*: Menambah data mahasiswa baru ke dalam dictionary.
     - *Tampilkan Data*: Menampilkan seluruh daftar mahasiswa beserta nilai mereka.
     - *Hapus Data*: Menghapus data mahasiswa berdasarkan nama.
     - *Ubah Data*: Mengubah nilai mahasiswa berdasarkan nama.
     - *Keluar*: Keluar dari program.

3. *Fungsi-fungsi Utama*:
   - *tambah(nama, nilai)*: Fungsi ini digunakan untuk menambah data mahasiswa ke dalam dictionary. Nama mahasiswa menjadi key, dan nilai mahasiswa menjadi value.
   - *tampilkan()*: Fungsi ini menampilkan seluruh data mahasiswa dalam dictionary. Jika dictionary kosong, program akan memberi pesan bahwa tidak ada data mahasiswa.
   - *hapus(nama)*: Fungsi ini menghapus data mahasiswa berdasarkan nama yang diberikan. Jika nama ditemukan, data akan dihapus; jika tidak, program memberi pesan bahwa nama tersebut tidak ditemukan.
   - *ubah(nama, nilai_baru)*: Fungsi ini mengubah nilai mahasiswa berdasarkan nama. Jika nama ditemukan, nilai mahasiswa akan diperbarui dengan nilai baru yang diberikan.

4. *Proses Pengguna*:
   - Pengguna akan dipandu melalui menu untuk memilih tindakan yang ingin dilakukan.
   - Setelah memilih tindakan, pengguna akan diminta untuk memasukkan data yang diperlukan (nama mahasiswa dan nilai).
   - Setelah selesai dengan tindakan yang dipilih, program akan kembali menampilkan menu utama.
   - Program akan terus berjalan hingga pengguna memilih opsi "Keluar" untuk keluar dari aplikasi.
