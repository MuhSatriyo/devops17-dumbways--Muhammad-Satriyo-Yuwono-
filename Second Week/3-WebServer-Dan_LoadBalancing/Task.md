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
   
