<!-- JUDUL -->
<div align="center">
  <h1 style="text-align: center; font-weight: bold">Praktikum 1<br>Praktek System Operasi</h1>
  <h3 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h3>
</div>
<br />
<!-- END JUDUL -->

<!-- LOGO -->
<div align="center">
  <img src="assets/logopens.png" alt="PENS">
</div>
<!-- END LOGO -->

<!-- MEMBER -->
<div align="center">
  <h3 style="text-align: center;">Disusun Oleh :</h3>
  <p style="text-align: center;">
    <em>Muhammad Eko Nur Sholeh (3123500003)</em><br>
    <em>Ghaly Abrarian Putra (3123500018)</em><br>
    <em>Muhammad Rasyid Rafif (3122500030)</em>
  </p>
</div>
<!-- END MEMBER -->

<!-- K -->
<div align="center">
  <h3 style="line-height: 1.3; font-weight: 600;">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr><hr>
</div>
<!-- END K -->

<!-- DAFTAR ISI -->
<div style="float: left;">
  
## Daftar isi

1. [Daftar Isi](#daftar-isi)
2. [Pendahuluan](#pendahuluan)
3. [Sistematis Booting](#proses-booting)
4. [Soal Praktikum](#soal)
5. [Instalasi](#instalasi)
   - [Instalasi Virtual Machine](#instalasi-virtual-machine)
   - [Instalasi Debian 12 pada Virtual Machine](#instal-os)
6. [Kesimpulan](#kesimpulan)
7. [Refrensi](#referensi)

<!-- END DAFTAR ISI -->

<!-- KONTEN -->

### Pendahuluan

**Sistem Operasi** adalah perangkat lunak yang mengatur dan mengelola semua operasi dasar komputer, seperti menjalankan program, mengelola memori, dan menyediakan antarmuka pengguna. Ini merupakan fondasi dari pengoperasian setiap perangkat komputer modern.

### Proses Booting

**Proses booting** merupakan serangkaian tahap yang dilakukan sebuah perangkat elektronik saat pertama kali dinyalakan setelah mati total, pada tahap proses booting berlangsung perangkat akan mempersiapkan inisialisasi serta konfigurasi hardware juga mempersiapkan perangkat lunak (OS) yang akan di Jalankan.

Berikut merupakan langkah - langkah pada saat proses booting :

1. _Power On_ : perangkat mengirim tegangan maupun sinyal pada seluruh komponen hardware yang terkait.
2. _Post (Power-On Self-Test)_ : Perangkat akan melakukan testing awal pada perangkat kerasnya, di komputer mencakup processor ,ram , gpu , dan storage yang tertanam. biasanya tahap ini ditandai pada saat muncul logo produsen motherboardnya.
3. _Inisialisasi_ : Setelah tahap POST dan masuk kedalam boot priority, komputer akan melakukan inisialisasi perangkat keras eksternal. (Keyboard, Mouse , Printer , Headseat , Monitor ,Kabel Lan )
4. _Loading Bootloader_ : bootloader merupakan sebuah proses dimana ketika storage penyimpanan memulai sebuah sistem operasi ke dalam memori (RAM).
5. _Loading Kernel_ : merupakan sebuah tahap dimana sistem operasi secara aktif mulai memasuki tahap berikutnya (inisialisai sistem)
6. _Init porcess_ : setelah kernel dimuat, sistem opereasi akan melakukan insialisasi. memuat layanan siste, mengatur konfigurasi jaringan, mempersiapkan environment user.
7. _User Login_ : tahap terakhir, pengguna diminta untuk melakukan login ke sistem.
8. _GUI_ : render tampilan antarmuka grafis serta masuk kedalam sistem.

### SOAL

laporankan hasil pengerjaan sebuah instalisasi debian 12 menggunakan virtual machine (VMbox) dengan syarat :

- Setting CPU usage : 2 Core
- Setting Ram : 4096MB / 4GB
- HDD 25GB dengan partisi :
  / : 20GB
  /storage : 5GB
  /swap :1.5GB

### Instalasi

##### Instalasi Virtual Machine

1. Kunjungi website resmi Virtual Box (https://www.virtualbox.org/wiki/Downloads)

   <p align="center">
     <img src="assets/VirtualBox/step1.png" alt="stepvm1">
   </p>

2. Pilih versi VM packages yang sesuai dengan OS yang sekarang dijalankan dan tekan versi maka file Virtual box akan otomatis ter-download.

   <p align="center">
     <img src="assets/VirtualBox/step2.png" alt="stepvm2">
   </p>

3. Tunggu Download file hingga selesai.

   <p align="center">
     <img src="assets/VirtualBox/step3fix.png" alt="stepvm3">
   </p>

4. Buka File Aplikasi VirtualBox.exe (pada windows) yang telah didownload tadi

   <p align="center">
     <img src="assets/VirtualBox/step4.png" alt="stepvm4">
   </p>

5. Setelah aplikasi telah terbuka bisa Klik **"Next"**

   <p align="center">
     <img src="assets/VirtualBox/step5.png" alt="stepvm5">
   </p>

6. Setup instalasi & Klik **"Next"**

   <p align="center">
     <img src="assets/VirtualBox/step6.png" alt="stepvm6">
   </p>

7. Pada tahap warning network interface Klik **"YES"**

   <p align="center">
     <img src="assets/VirtualBox/step7.png" alt="stepvm7">
   </p>

8. Pada tahap missing dependencies klik **"YES"**

   <p align="center">
     <img src="assets/VirtualBox/step8.png" alt="stepvm8">
   </p>

9. Pada tahap siap install Klik **"Instal"**

   <p align="center">
     <img src="assets/VirtualBox/step9.png" alt="stepvm9">
   </p>

10. Tunggu proses intalasi aplikasi hingga **selesai**

    <p align="center">
      <img src="assets/VirtualBox/step10.png" alt="stepvm10">
    </p>

11. Setelah proses install selesai centang pada 'Start Virtual machine'

    <p align="center">
      <img src="assets/VirtualBox/step11.png" alt="stepvm11">
    </p>

### instalasi os

1. **Download ISO Debian 12** dari [website resmi Debian](https://www.debian.org/download)
   <div align="center">
     <img src="assets/Debian/step1.png" alt="stepvd1">
   </div>

2. Masuk dalam tampilan VirtualBox dan klik **"New"**
   <div align="center">
     <img src="assets/Debian/step12.png" alt="stepvd2">
   </div>

3. Masukkan nama "BEBAS" (Debian12), sesuaikan Type dan versi Debian sesuai arsitektur CPU, kemudian klik **"Next"**
   <div align="center">
     <img src="assets/Debian/step13.png" alt="stepvd3">
   </div>

4. **Alokasikan** CPU & RAM sesuai arahan (4096MB RAM & 2 CORE CPU)
   <div align="center">
     <img src="assets/Debian/step14.png" alt="stepvd4">
   </div>

5. **Alokasikan** Storage sebesar 25GB (Akan otomatis menjadi 26GB) dan klik **"NEXT"**
   <div align="center">
     <img src="assets/Debian/step15.png" alt="stepvd5">
   </div>

6. Pada summary/preview, silahkan klik **"Finish"**
   <div align="center">
     <img src="assets/Debian/step16.png" alt="stepvd6">
   </div>

7. Pada tampilan utama, arahkan ke tools yang sudah dibuat dan klik **"Settings"**
   <div align="center">
     <img src="assets/Debian/step17.png" alt="stepvd7">
   </div>

8. Pada General, ubah **Shared Clipboard** menjadi bidirectional
   <div align="center">
     <img src="assets/Debian/step18.png" alt="stepvd8">
   </div>

9. Pada Display, atur **Video Memory** sebaik mungkin; untuk rendering berat, pilih opsi paling maksimal
   <div align="center">
     <img src="assets/Debian/step19.png" alt="stepvd9">
   </div>

10. Pada Storage > Empty, cari ISO yang telah diunduh
    <div align="center">
      <img src="assets/Debian/step21.png" alt="stepvd10">
    </div>

11. Cari ISO yang telah diunduh dan klik "Open"
    <div align="center">
      <img src="assets/Debian/step22.png" alt="stepvd11">
    </div>
11. Cari ISO yang telah diunduh dan klik "Open"
    <div align="center">
      <img src="assets/Debian/step22.png" alt="stepvd11">
    </div>

12. Setelah menyeting, kembali ke halaman utama dan Klik **"Start"**
    <div align="center">
      <img src="assets/Debian/step23.png" alt="stepvd12">
    </div>

13. Setelah terbuka, silahkan tekan tombol "Enter" untuk memilih **Graphical Install**
    <div align="center">
      <img src="assets/Debian/step24.png" alt="stepvd13">
    </div>

14. Pilih bahasa yang diinginkan dan Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step25.png" alt="stepvd14">
    </div>

15. Pilih Lokasi yang diinginkan (bisa yang terdekat dengan Anda) dan Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step26.png" alt="stepvd15">
    </div>

16. Pilih Layout keyboard yang diinginkan dan Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step27.png" alt="stepvd16">
    </div>

17. Tunggu proses persiapan
    <div align="center">
      <img src="assets/Debian/step28.png" alt="stepvd17">
    </div>

18. Masukkan hostname sesuai saran Administrator Protocol dan Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step29.png" alt="stepvd18">
    </div>

19. Masukkan Password sesuai keinginan dan Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step30.png" alt="stepvd19">
    </div>

20. Masukkan User account sesuai keinginan dan Klik **"Continue"**, kemudian tunggu prosesnya
    <div align="center">
      <img src="assets/Debian/step31.png" alt="stepvd20">
    </div>

21. Pilih Partisi disk yang sudah dibuat dan ditetapkan di awal langkah tadi dan Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step32.png" alt="stepvd21">
    </div>

22. Pilih **"All files in one partition"**
    <div align="center">
      <img src="assets/Debian/step33.png" alt="stepvd22">
    </div>

23. Pilih **"Finish partitioning and write changes to disk"** dan Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step38.png" alt="stepvd23">
    </div>

24. Pilih **"Yes"** pada konfirmasi pembuatan partisi baru
    <div align="center">
      <img src="assets/Debian/step52.png" alt="stepvd24">
    </div>

25. Pilih **"No"** pada scan Extra installation media
    <div align="center">
      <img src="assets/Debian/step54.png" alt="stepvd25">
    </div>

26. Pilih **"Configure the package manager"**, pilih negara "Indonesia", lalu Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step55.png" alt="stepvd26">
    </div>

27. Pilih Debian archive mirror ke **"Kebo.pens.ac.id"** dan Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step56.png" alt="stepvd27">
    </div>

28. Kosongkan bagian **HTTP proxy** dan Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step57.png" alt="stepvd28">
    </div>

29. Pilih **"No"** pada konfirmasi configuring popularity-contest dan Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step58.png" alt="stepvd29">
    </div>

30. Tunggu Proses Installasi
    <div align="center">
      <img src="assets/Debian/step59.png" alt="stepvd30">
    </div>

31. Pilih **"Yes"** pada pertanyaan apakah install GRUB dan Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step60.png" alt="stepvd31">
    </div>

32. Tunggu Installasi GRUB hingga selesai
    <div align="center">
      <img src="assets/Debian/step61.png" alt="stepvd32">
    </div>

33. Pilih bootloader GRUB pada device awal yang telah dibuat dan Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step64.png" alt="stepvd33">
    </div>

34. Pada permintaan reboot, Klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step65.png" alt="stepvd34">
    </div>

35. Dan akhirnya, OS Linux Debian 12 Anda siap digunakan!
    <div align="center">
      <img src="assets/Debian/step62.png" alt="stepvd35">
    </div>


## Kesimpulan

setelah praktikum Percobaan instal debian pada virtualbox menjadikan mahasiswa paham bagaimana cara menginstall OS pada VM (Virtual Machine) & Memberikan wawasan tentang konsep sederhana jalannya Operating Sistem selain itu, hal yang menarik ialah bahwa sistem operasi (OS) dapat berjalan baik melalui boot langsung pada BIOS/UEFI atau melalui lingkungan virtual seperti mesin virtual (VM). sebagai Contohnya adalah Oracle Virtualbox ini, bisa menjalankan Debian. mungkin bila di Machintos (MacOS) ada windows Pararel yang dapat menjalankan OS windows pada macbook / iMac dengan menggunakan Virtual Machine. sehingga dapat kita simpulkan yaitu intinya OS adalah suatu perangkat lunak yang sangat diperlukan pada keberlangsungan fungsi suatu barang elektronik.

### Referensi

Buku 'Operating System Concepts' [🔗](https://os.ecci.ucr.ac.cr/slides/Abraham-Silberschatz-Operating-System-Concepts-10th-2018.pdf)

Mengenal debian oleh telkom university [🔗](https://it.telkomuniversity.ac.id/mengenal-debian-os-sejarah-kelebihan-dan-kekurangan/)

Apa itu Virtual Box oleh jagongoding[🔗](https://jagongoding.com/others/apa-itu-virtual-box/)

Install virtual box oleh solmet kemendikbud [🔗](https://solmet.kemdikbud.go.id/?p=2660)

Link Download Debian [🔗](https://www.debian.org/download)

Link Virtual Box[🔗](https://www.virtualbox.org/)

Video Tutorail How to Download & Instal debian 12 on VirtualBox[🔗](https://www.youtube.com/watch?v=zfOWKG2QPB0)

</div>
