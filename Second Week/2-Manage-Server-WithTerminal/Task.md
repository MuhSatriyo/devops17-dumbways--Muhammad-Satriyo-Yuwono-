## Manage Server With Terminal

### Penjelasan Text Manipulation Beserta Step by Stepnya
Text manipulation itu sendiri merupakan cara untuk kita dapat melakukan manipulasi text atau perubahan text tanpa menggunakan text editor (nano).
Terdapat beberapa command yang dapat kita gunakan di dalam text manipulation ini, diantaranya yaitu:

1. Command Cat

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/M3.png?raw=true)

   Keterangan:
   - cat namafile = untuk melihat isi dari suatu file.
   - cat > namafile = untuk edit text di dalam file tanpa text editor.
   - cat namafile1 namafile2 > nama file gabungan = untuk menggabungkan text dari 2 file berbeda.

2. Command sed

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/M4.png?raw=true)

   Keterangan:
   - sed -i 's/Yuwono/Kedua/g' file3 = Memerintahkan untuk mereplace kata Yuwono menjadi kata Kedua.

3. Command Grep

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/M5.png?raw=true)

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/M7.png?raw=true)

   Keterangan:
   - grep (kata yg ingin di cari) file3 = untuk mencari kata pada suatu file.
   - grep -c (kata yg ingin di cari) file3 = untuk menghitung jumlah kata pada suatu file.
   - grep (kata yg ingin di cari) * = untuk mencari file yang berisikan kata tersebut.

4. Command Sort
   - sort file3 = untuk mengurutkan berdasarkan abjad dari awal s/d akhir.
   - sort -r file3 = untuk mengurutkan berdasarkan abjad tetapi dari akhir s/d awal.

5. Command awk

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/M9.png?raw=true)

   Keterangan:
   - awk '{print $1}' file3 = untuk menampilkan kata yang terdapat di dalam file yang kita pilih, $1 artinya berarti mengambil kata pertama di tiap tiap baris text yang ada di file kita.

6. Command cut

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/M10.png?raw=true)

   Keterangan:
   - cut -b 1 file3 = untuk mengambil huruf pertama.
   - cut -c 1,2,3 file3 = untuk mengambil beberapa huruf pada urutan yang telah kita tentukan dari file tersebut.
   - cut -d " " -f 3 file3 = untuk mengambil kata berdasarkan urutan yang kita inginkan dari file yang kita pilih.

7. Command echo

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/M11.png?raw=true)

   Keterangan:
   - echo "kata" = untuk mencetak kata.
   - echo "kata" > file3 = untuk mereplace isi file3 dengan kata lain.
   - echo "kata" >> file3 = untuk menambahkan isi file3 dengan kata yang kita inginkan.

### Penjelasan Tool Htop
Tool Htop itu sendiri adalah aplikasi pemantauan proses realtime pada sistem linux. Langkah pertama untuk memunculkan Tool Htop yaitu dengan cara meng-installnya menggunakan command (sudo apt install htop -y)

![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/M12.png?raw=true)

Setelah sudah terinstal, kita dapat memanggilnya dengan command htop lalu klik enter maka akan muncul tampilan seperti berikut.

![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/M13.png?raw=true)

Keterangan:
- Tasks adalah aplikasi yang sedang berjalan di server
- PID adalah nomor proses id setiap proses yang berjalan di linux
- Swp adalah Memory cadangan
- CPU adalah berapa jumlah core yang kita miliki
- Load average adalah rata-rata aplikasi yang berjalan
- Uptime adalah berapa lama server kita hidup
- Mem adalah total penggunaan memory
- VIRT adalah memory yang terpakai
- Command adalah perintah apa yang sedang di jalankan
