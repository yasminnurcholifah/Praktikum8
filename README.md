# Praktikum8
Nama : Siti Yasmin Nurcholifah Kelas : TI.22.C1 NIM : 312210057

# TUGAS PRAKTIKUM 8
Buat program sederhana dengan mengaplikasikan penggunaan class. Buatlah class untuk menampilkan daftar nilai mahasiswa, dengan ketentuan:
- Method tambah() untuk menambah data
- Method tampilkan() untuk menampilkan data
- Method hapus(nama) untuk menghapus data berdasarkan nama
- Method ubah(nama) untuk mengubah data berdasarkan nama
- Buat diagram class, flowchart dan penjelasan programnya pada README.md.
- Commit dan Push repository ke Github

# SOURCE CODE :
class mahasiswa:
    def __init__(self, nim, nama, tugas, uts, uas):
        self.nim = nim
        self.nama = nama
        self.tugas = tugas
        self.uts = uts
        self.uas = uas

    def tambah(self,nim,nama,tugas,uts,uas):
        data.nim.append(nim)
        data.nama.append(nama)
        data.tugas.append(tugas)
        data.uts.append(uts)
        data.uas.append(uas)

    def lihat(self):
        for i in range(len(data.nama)):
            print("|", i+1, "  |", end="")
            print('{0:<25}'.format(self.nama[i]), end="")
            print("|", self.nim[i], end="")
            print(" |", self.tugas[i], end="")
            print("    |", self.uts[i], end="")
            print("  |", self.uas[i], " | ", end="")
            print(f'{((self.tugas[i]*30/100) + (self.uts[i]*35/100) + (self.uas[i]*35/100)) :.2f}', " |")

    def ubah(self,nim,nama,tugas,uts,uas):
        self.nim[no] = nim
        self.nama[no] = nama
        self.tugas[no] = tugas
        self.uts[no] = uts
        self.uas[no] = uas

    def hapus(self):
        del self.nim[no]
        del self.nama[no]
        del self.tugas[no]
        del self.uts[no]
        del self.uas[no]

data = mahasiswa([] , [] , [] , [] , [])

while True :
    menu = input("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (K)eluar]:")
    if menu == "t" or menu == "T":
    print("\nTambah Data")
    
    data.tambah(
        input("Masukkan NIM : "),
        input("Masukkan Nama : "),
        int(input("Nilai Tugas : ")),
        int(input("Nilai UTS : ")),
        int(input("Nilai UAS : "))
        )
    print("\nData berhasil ditambahkan")

    elif menu == "l" or menu == "L":
        print("\nDaftar Nilai")
        print("==========================================================================")
        print("| No  |          Nama           |    NIM    | TUGAS | UTS | UAS |  AKHIR |")
        print("==========================================================================")
        if len(data.nama) != 0:
            data.lihat()
        else:
            print("                         TIDAK ADA DATA                               ")
        print("==========================================================================")

    elif menu == "u" or menu == "U":
        print("\nUbah Data")
        ubah = input("Masukkan Nama : ")
        if ubah in data.nama:
        no = data.nama.index(ubah)
        print("Masukkan Data Yang Baru : ")
        data.ubah(
            input("NIM : "),
            input("Nama : "),
            int(input("Nilai Tugas : ")),
            int(input("Nilai UTS : ")),
            int(input("Nilai UAS : "))
            )
        else:
            print(ubah, "tidak ada di dalam data")

    elif menu == "h" or menu == "H":
        print("\nHapus Data")
        hapus = input("Masukkan Nama : ")
        if hapus in data.nama:
            no = data.nama.index(hapus)
            data.hapus()
            print("Data", hapus, "Berhasil dihapus")
        else:
            print(hapus, "tidak ada di dalam data")

    elif menu == "k" or menu == "K":
        print("\nTerimakasih\n")
        break

    else:
        print("\nPerintah yang dimasukkan salah!\n")

# Penjelasan dan Hasil Run
Pertama kita mendeklarasikan sebuah class mahasiswa yang didalamnya terdapat atribut NIM, Nama, nilai tugas, nilai UTS dan nilai UAS. JANGAN LUPA, untuk mendeklarasikan sebuah class didalam OOP kita harus menggunakan def_init_ dan juga self.
  class mahasiswa:
      def __init__(self, nim, nama, tugas, uts, uas):
          self.nim = nim
          self.nama = nama
          self.tugas = tugas
          self.uts = uts
          self.uas = uas
Seperti biasa, deklarasikan satu dictionary kosong sebagai tempat menyimpan data-data yang sudah kita input. Ada 5 list kosong yang nantinya berisi NIM, Nama, nilai tugas, nilai UTS, dan nilai UAS
  data = mahasiswa([],[],[],[],[])
Kita akan buat beberapa method untuk menambahkan, menampilkan, mengubah, dan menghapus data mahasiswa. Pertama membuat method tambah(), method ini berfungsi untuk menambahkan data. Dalam method ini kita menggunakan append() agar data yang terakhir ditambahkan ada di urutan list paling akhir.
  def tambah(self,nim,nama,tugas,uts,uas):
          data.nim.append(nim)
          data.nama.append(nama)
          data.tugas.append(tugas)
          data.uts.append(uts)
          data.uas.append(uas)

HASIL RUN TAMBAH DATA

![gambar1](Screenshot/gambar1.png)

Fungsi membuat method lihat() yaitu untuk menampilkan seluruh data yang sudah kita tambahkan tadi. Jika tidak ada data sama sekali, maka akan muncul tulisan TIDAK ADA DATA.
  def lihat(self):
          for i in range(len(data.nama)):
              print("|", i+1, "  |", end="")
              print('{0:<25}'.format(self.nama[i]), end="")
              print("|", self.nim[i], end="")
              print(" |", self.tugas[i], end="")
              print("    |", self.uts[i], end="")
              print("  |", self.uas[i], " | ", end="")
              print(f'{((self.tugas[i]*30/100) + (self.uts[i]*35/100) + (self.uas[i]*35/100)) :.2f}', " |")

HASIL RUN LIHAT DATA

![gambar2](Screenshot/gambar2.png)

Fungsi membuat method ubah() yaitu untuk mengubah data. jika method ini diinput, maka data Nama, NIM, nilai tugas, nilai UTS, nilai UAS index nomor - (no) akan diubah sesuai dengan inputan dari user. Index ke - (no) akan dicari secara otomatis sesuai dengan nama yang ingin diubah oleh user.
  def ubah(self,nim,nama,tugas,uts,uas):
          self.nim[no] = nim
          self.nama[no] = nama
          self.tugas[no] = tugas
          self.uts[no] = uts
          self.uas[no] = uas

![gambar3](Screenshot/gambar3.png)

Terakhir kita membuat method hapus(), yang berfungsi untuk menghapus data berdasarkan nama. Kita bisa menggunakan del untuk menghapus datanya. Seperti sebelumnya, nomor index list yang akan dihapus disesuaikan dengan inputan dari user. Yaitu index nomor ke - (no).
  def hapus(self):
          del self.nim[no]
          del self.nama[no]
          del self.tugas[no]
          del self.uts[no]
          del self.uas[no]

![gambar](Screenshot/gambar4.png)

# Diagram class Praktikum 8

![gambar](Screenshot/gambar5.png)

# Flowchart Praktikum 8

![gambar](Screenshot/gambar6.png)

Thanks for reading