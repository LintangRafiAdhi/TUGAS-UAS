# TUGAS-UAS

<h1>PROGRAM SEDERHANA MENU PECEL LELE<h1></h1>

  
| NAMA   | LINTANG RAFI ADHI  |
| --- | --- |
| NIM    | 312310697 |
| KELAS  | TI.23.A6 |
| DOSEN  | Agung Nugroho,S.Kom.,M.Kom |
| LINK VIDEO YT  |  https://youtu.be/31aWQ3Uk7dY?si=TcWepsKyytz8l-Ig |

 
1. **Import Modul:**
   ```python
   from prettytable import PrettyTable
   ```
   Import modul `PrettyTable` yang digunakan untuk membuat tabel yang rapi dan cantik.

2. **Menu dan Harga:**
   ```python
   menu = {
       'Pecel Lele Pakai Nasi': 15000,
       'Pecel Lele Pakai Mie Goreng': 17000,
       'Pecel Lele + Nasi + Lalapan': 20000,
       'Pecel Lele + Mie Goreng + Lalapan': 22000,
       'Es Teh': 5000,
       'Es Jeruk': 6000,
       'Air Mineral': 3000
   }
   ```
   Inisialisasi dictionary `menu` yang berisi opsi makanan/minuman beserta harganya.

3. **Fungsi Tampilkan Menu:**
   ```python
   def tampilkan_menu():
       print("Menu Makanan/Minuman:")
       for item, harga in menu.items():
           print(f"{item}: Rp {harga}")
   ```
   Fungsi ini digunakan untuk menampilkan menu makanan/minuman beserta harganya.

4. **Fungsi Hitung Total:**
   ```python
   def hitung_total(harga, jumlah):
       return harga * jumlah
   ```
   Fungsi ini menerima harga dan jumlah sebagai argumen dan mengembalikan total harga dengan mengalikan keduanya.

5. **Fungsi Utama (Main):**
   ```python
   def main():
       pesanan = {}

       while True:
           tampilkan_menu()
           pilihan = input("Masukkan nama makanan/minuman yang ingin dipesan (ketik 'sudah' untuk menampilkan struk): ")

           if pilihan.lower() == 'sudah':
               break

           if pilihan in menu:
               jumlah = int(input(f"Masukkan jumlah {pilihan}: "))
               harga_total = hitung_total(menu[pilihan], jumlah)
               pesanan[pilihan] = {'jumlah': jumlah, 'harga_total': harga_total}
           else:
               print("Menu tidak ada. Silakan pilih menu yang tersedia.")
   ```
   Fungsi utama ini melakukan loop untuk meminta pengguna memasukkan pesanan. Jika pengguna memasukkan 'sudah', loop berhenti. Jika pengguna memilih menu yang ada, program meminta jumlah pesanan dan menghitung total harga pesanan.

6. **Tampilkan Struk Pembelian:**
   ```python
   tabel_struk = PrettyTable()
   tabel_struk.field_names = ["Menu", "Jumlah", "Harga Total"]

   total_pembelian = 0
   for item, detail in pesanan.items():
       tabel_struk.add_row([item, f"x{detail['jumlah']}", f"Rp {detail['harga_total']}"])
       total_pembelian += detail['harga_total']
   ```
   Sebuah objek PrettyTable dibuat untuk menyimpan struk pembelian. Loop kemudian digunakan untuk menambahkan setiap pesanan ke tabel struk dan menghitung total pembelian.

7. **Tampilkan Total Pembelian:**
   ```python
   print("\nStruk Pembelian:")
   print(tabel_struk)
   print(f"\nTotal Pembelian: Rp {total_pembelian}")
   ```
   Akhirnya, struk pembelian beserta total pembelian ditampilkan kepada pengguna.

8. **Eksekusi Program:**
   ```python
   if __name__ == "__main__":
       main()
   ```
   Program dieksekusi jika script dijalankan langsung (bukan di-import sebagai modul). Fungsi `main()` akan dijalankan, memulai proses pemesanan makanan/minuman.
