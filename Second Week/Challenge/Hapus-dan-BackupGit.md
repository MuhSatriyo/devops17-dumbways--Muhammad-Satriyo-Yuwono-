## Proses Menghapus File di Account Github Lalu Dikembalikan Lagi

Kita cek di github account kita bahwa file kita masih lengkap, lalu saya akan menghapus file1.
![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/CG0.png?raw=true)

1. Menghapus file1 dengan cara memberikan command ```git rm file1``` lalu kita cek statusnya dengan ```git status``` untuk melihat status file1 apakah sudah deleted atau belum.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/CG1.png?raw=true)

2. Kemudian kita commit dan kita push origin di branch master, karena file1 berada di branch master.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/CG2.png?raw=true)

   jika sudah kita refresh web github account kita, maka file1 sudah hilang dari repository kita.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/CG3.png?raw=true)

3. Setelah itu lakukan pengecekan aktifitas yang telah kita lakukan dengan account git kita menggunakan command ```git log```

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/CG4.png?raw=true)

4. Kemudian kita copy log yang judul commitnya 'second commit' karena itu adalah keadaan sebelum file1 di hapus dan pastinya file1 masih terdapat di situ. lalu kita berikan command ```git checkout -b nama-branch-baru-untuk-backup log-sebelum-file1-dihapus``` atau lebih jelas commandnya dituliskan begini ```git checkout -b backup f2f39fb549c6b76101bb3e868f1fa5d44c4c4ede```. Setelah itu kita ketikkan comman ```git branch -a``` untuk melihat apakah kita sudah membuat branch backup dan pindah ke branchnya. Kemudian jangan lupa kita push branch backupnya agar file1 ada di repository github account kita lagi ```git push origin backup```.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/CG5.png?raw=true)

5. Jika sudah selesai kita cek repository github account kita dan masuk ke branch backup, maka file1 sudah ada kembali.

   ![alt text](https://github.com/MuhSatriyo/devops17-dumbways--Muhammad-Satriyo-Yuwono-/blob/main/Second%20Week/Image/CG6.png?raw=true)
