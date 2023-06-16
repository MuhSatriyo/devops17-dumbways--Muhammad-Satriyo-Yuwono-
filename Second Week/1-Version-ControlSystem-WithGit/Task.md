## Version Control System With Git

### Penjelasan Tentang Distributed Version Control
Berdasarkan penjelasan dari 'verion control' itu sendiri adalah sebuah sistem yang merekam perubahan-perubahan dari sebuah berkas penyimpanan dari waktu ke waktu sehingga Anda dapat menilik kembali versi khusus suatu saat nanti. Lalu 'distributed' itu sendiri artinya terdistribusi atau secara sederhana pembagian atau penyaluran.
Maka arti dari 'Distributed Version Control' adalah proses monitoring perubahan perubahan dari suatu berkas penyimpanan yang dapat di monitoring oleh setiap orang yang diberikan izin untuk mengolah penyimpanan tersebut.

### Buat Repository Sederhana Yang Berisi 3 File Berbeda
Proses membuat repository di sini saya sarankan untuk menyambungkan ubuntu kita ke windows poweshall menggunakan ssh, dengan cara mengetikkan "ssh satriyo@192.168.50.35". 

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/M6.png?raw=true)

Kemudian kita mengatur konfigurasi global akun github kita dengan memasukkan username dan email github kita menggunakan command.
-git config --global user.name "MuhSatriyo"
-git config --global user.email "muhamadsatriyo05@gmail.com"
jika sudah di inputkan, maka dapat kita lihat username dan email kita dengan mengetikkan "git config --list".
Kemudian untuk perintah 'ssh' tersebut di sesuaikan dengan nama server kita dan ip address kita. Setelah itu kita lanjut ke langkah berikutnya:

1. Kita harus melakukan aktivasi pada github kita terlebih dahulu menggunakan terminal dengan cara mengatus 'ssh key' nya terlebih dahulu. Caranya yaitu kita ketik command "ssh-keygen".

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A2.png?raw=true)

2. Membuat folder '.ssh' kemudian masuk ke dalam folder '.ssh'nya. Lalu kita cek di dalam folder '.ssh' tersebut terdapat file apa saja.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A3.png?raw=true)

   Keterangan file:
   id_rsa = Merupakan key yang berguna untuk mengakses private key.
   id_rsa.pub = Merupakan key yang berguna untuk mengakses public key.

3. Setelah kita mendapatkan key nya maka kita copykan ke dalam SSH Key Github kita, dengan cara buka pengaturan account github kita lalu pilih new SSH Key.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A4.png?raw=true)

4. Selanjutnya kita cek apakah SSH sudah berhasil terkoneksi dengan command "ssh -T git@github.com". (Hi 'username'! You've successfully authenticated) seperti gambar berikut:

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A5.png?raw=true)

5. Jika berhasil kita koneksikan maka kita akan membuat repository yang ada pada file lokal dan berlokasi di folder .git dengan command (git init 'nama reposirtory kita'). Kemudian kita cek list configurasi yang sebelumnya kita buat yang ber-isikan username dan email.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A6.png?raw=true)

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A7.png?raw=true)

6. Selanjutnya kita add 3 file yang ingin kita buat dengan command (git add 'namafile' 'namafile' 'namafile') lalu kita cek statusnya sudah ditambahkan atau belum dengan command "git status". Setelah sudah berhasil di tambahkan maka kita lakukan commit pada 3 file tersebut dengan command (git commit -m "comment terserah")

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A9.png?raw=true)

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A10.png?raw=true)

7. Kemudian kita lakukan gitu push origin master untuk mengupload file ke github account kita. Lalu kita refresh web github kita maka 3 file tersebut sudah ada di github account kita.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A11.png?raw=true)

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A12.png?raw=true)

8. Setelah 3 file telah di buat maka kita akan membuat 2 branch dengan nama staging dan production dengan command (git branch 'nama branch') dan dapat kita cek dengan command (git branch -a).

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A13.png?raw=true)

9. Kemudian kita akan mengedit file index.py dan kita pindah ke branch production terlebih dahulu dengan command (git checkout production) lalu pastikan dengan command (git branch -a) lalu kita edit file index.py (nano indec.py) setelah itu tambahkan file index.py dengan command (git add index.py) lalu cek statusnya (git status).

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A14.png?raw=true)

10. Setelah itu kita commit file yang sudah kita edit tersebut dengan command (git commit -m "production commit"). Lalu kita push semua branch agar terupload di account github kita dengan command (git push --all). Selanjutnya kita merge file dari branch production ke branch master dengan pindah ke branch master terlebih dahulu dengan command (git checkout master) lalu jalankan command (git merge production). *Maaf kak ade untuk langkah ini saya lupa screenshoot heheheh :D

11. Terakhir kita refresh github kita yang berada di browser dan kita dapat mengecek terdapat 2 branch dan 3 file baru serta terdapat perubahan pada file index.py

    ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A17.png?raw=true)

    ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A16.png?raw=true)

    ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/A18.png?raw=true)

### Berikan 3 Command Git Yang Belum Dijelaskan
1. git config --list = Untuk mengecek configurasi apa saja yang sudah kita inputkan di git.
2. git config --global --edit = Untuk mengedit configurasi atau menghapus configurasi yang tidak kita inginkan, seperti kita mau berganti email dan username github.
3. git log = Untuk mengecek perubahan apa saja yang terjadi pada repository git kita.
