## Web Server dan Load Balancing

### Task Untuk Day 3 
1. Instalasi nginx melalui apt
2. menjalankan aplikasi dumbflix menggunakan PM2
3. buatlah konfigurasi reverse proxy!
Referensi :
- Nama Domain - dumbflix-(nama panggilan).xyz
- Dumbflix-FE - ```https://github.com/dumbwaysdev/dumbflix-frontend```

#### Berikut ini proses instalasinya
1. Sebelumnya kita harus menginstal nginx melalui apt dengan command (sudo apt install nginx), setelah itu kita cek status nginx nya di ubuntu kita.
   Jika sudah ter install, jika kita buka browser kita dengan ip address kita maka akan muncul tampilan nginx.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S1.png?raw=true)

2. Jangan lupa untuk mendownload file dumbflixnya di ```https://github.com/dumbwaysdev/dumbflix-frontend```. Jika sudah kita akan masuk ke folder dumbflixnya dan kita install npm nya ```npm install```. Setelah itu kita bundle npm nya dengan perintah ```npm run build```

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S3.png?raw=true)

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S4.png?raw=true)

3. Kemudian kita install kan command untuk menjalankan server pm2 kita dengan command ```sudo snap install serve``` dan ```npm install -g serve``` di dalam folder ```dumbflix-frontend```.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S5.png?raw=true)

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S6.png?raw=true)
   
4. Setelah itu jalankan pm2 di dalam folder ```dumbflix-frontend``` dengan memberikan command ```npm serve build```

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S8.png?raw=true)

   Maaf untuk ip nya masih yang ```192.168.58.35```, karena ini kalau tidak salah saya masih terus mencoba berkali kali di kantor dengan menggunakan hotspot hp. Jadi saya cek hasil screenshootan adanya yang menggunakan ip ini bukan ```192.168.1.35``` yang saya gunakan untuk nantinya saya inputkan ke file hosts.

5. Lanjut, kita akan masuk ke dalam folder nginx nya dan masuk lagi ke folder sites-enabled dengan cara mengetik ```cd /etc/ngingx/sites-enabled```

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S16.png?raw=true)

   Jika sudah masuk kita akan melakukan setting di file myproxy.conf dengan command ```sudo nano myproxy.conf``` seperti diatas, kemudian kita berikan command ```sudo nginx -t``` untuk mengecek apakah configurasinya sudah berhasil kita bisa reload nginx nya ```sudo systemctl reload nginx``` kemudian kita cek status nginx nya ```sudo systemctl status nginx```. Jika paling bawah sudah ada keterangan ```Jun 17 09:21:28 satriyo systemd[1]: Reloaded A high performance web server and a reverse proxy server``` maka telah berhasil menambahkan proxy server.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S17.png?raw=true)

6. Setelah kita membuat dan mengedit file myproxy.conf, lalu kita mundur 1 folder dan masuk ke folder nginx. Lalu kita edit file nginx.conf dengan command ```sudo nano nginx.conf``` dan inputkan atau masukkan lokasi tempat kita mengedit proxy server kita dengan mengetik ```include /etc/nginx/sites-enabled/*;```

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S10.png?raw=true)
   
8. Kemudian kita kembali ke folder utama maksudnya ke home kita. Dan kita edit file hosts nya dengan menggunakan command ```sudo nano /etc/hosts``` lalu tambahkan server proxy yang telah kita buat sebelumnya.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S11.png?raw=true)

9. Setelah selesai kita masuk ke komputer kita dan cari file hosts kita di folder ```C:\Windows\System32\drivers\etc```

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S13.png?raw=true)

   Jangan lupa untuk mengeditnya kita ubah dulu settingan permmisionnya

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S14.png?raw=true)

   Jika sudah kita buka filenya dengan format .txt kemudian tambahkan virtual hosts kita di dalamnya dan terakhir kita save.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S12.png?raw=true)

10. Langkah terkahir kita masuk ke browser kita dan kita ketikkan di kolom url ```dumbflix-satriyo.xyz``` kemudian akan terbuka tampilan dumbflix menggunakan virtual host kita yang sudah kita jalankan dengan pm2 di latar belakang.

    ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/S15.png?raw=true)
