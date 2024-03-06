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

1. _Insialiasasi tegangan_ : pada tahap pertama power pada suatu laptop atau komputer akan standby dan menyalurkan tegangan rendah untuk persiapan langkah berikutnya.

 <p align="center">
     <img src="assets/Booting/booting.jpg" alt="stepvm1">
   </p>

2. _Power On_ : perangkat mengirim sinyal kepada front panel motherboard guna memngirimkan perintah menyalakan motherboard dan power mengirimkan tegangan kepada seluruh komponen.

 <p align="center">
     <img src="assets/Booting/booting2.jpeg" alt="stepvm1">
   </p>

3. _Inisialisasi BIOS_ : Pada tahap ini BIOS yang tertanam pada motherboard akan mengatur sistem berjalannya POST , Setting Hardware hingga BOOT Prioritas.

 <p align="center">
     <img src="assets/Booting/booting3.jpeg" alt="stepvm1">
   </p>

4. _Post (Power-On Self-Test)_ : Perangkat akan melakukan testing awal pada perangkat kerasnya, di komputer mencakup processor ,ram , gpu , storage yang tertanam dan hardwdare lainnya yang tertancam, Namun biasanya tahap ini pada motherboard modern tidak ditampilkan dan diganti dengan showlogo, hal tersebut ditandai pada saat muncul logo produsen motherboardnya. akan tetapi sekalipun motherboard modern yang belum terInstall OS dan tidak memiliki prioritas boot Biasanya BIOS akan tetap menampilkan POST seperti pada gambar

  <p align="center">
     <img src="assets/Booting/booting22.jpeg" alt="stepvm1">
   </p>

5. _Boot Sector_ : Setelah tahap POST bios akan mengeksekusi prioritas BOOTING, sehingga pada tahap ini juga merupakan suatu tahap yang penting untuk penentuan manakah OS yang ingin dijalankan. semakin prioritas urutan maka OS yang di prioritaskan yang akan dijalankan.

  <p align="center">
     <img src="assets/Booting/bootng4.jpeg" alt="stepvm1">
   </p>

6. _Loading Bootloader_ : bootloader merupakan sebuah proses dimana ketika storage penyimpanan memulai sebuah sistem operasi ke dalam memori (RAM).

<p align="center">
     <img src="assets/Booting/bootingloader.jpg" alt="stepvm1">
   </p>

7. _Loading Kernel_ : merupakan sebuah tahap dimana sistem operasi secara aktif mulai memasuki tahap berikutnya (inisialisai sistem)

<p align="center">
     <img src="assets/Booting/bootingkernel.png" alt="stepvm1">
   </p>

8. _Init Proses_ : setelah kernel dimuat, sistem opereasi akan melakukan insialisasi. memuat layanan sistem, mengatur konfigurasi jaringan, mempersiapkan environment user.

<p align="center">
     <img src="assets/Booting/init.png" alt="stepvm1">
   </p>

9. _GUI_ : render tampilan antarmuka grafis serta masuk kedalam sistem.

<p align="center">
     <img src="assets/Booting/GUI.jpeg~~" alt="stepvm1">
   </p>

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

1. Download ISO Debian 12 dari [website resmi Debian](https://www.debian.org/download)
   <div align="center">
     <img src="assets/Debian/step1.png" alt="stepvd1">
   </div>

2. Masuk ke tampilan VirtualBox dan klik **"New"**
   <div align="center">
     <img src="assets/Debian/step12.png" alt="stepvd2">
   </div>

3. Masukkan nama "BEBAS" (Debian12), sesuaikan Type dan versi Debian sesuai arsitektur CPU, lalu klik **"Next"**
   <div align="center">
     <img src="assets/Debian/step13.png" alt="stepvd3">
   </div>

4. Alokasikan CPU & RAM Usage sesuai arahan (4096MB RAM & 2 CORE CPU)
   <div align="center">
     <img src="assets/Debian/step14.png" alt="stepvd4">
   </div>

5. Alokasikan Storage sebesar 25GB (akan otomatis menjadi 26GB) dan klik **"Next"**
   <div align="center">
     <img src="assets/Debian/step15.png" alt="stepvd5">
   </div>

6. Pada summary / preview, klik **"Finish"**
   <div align="center">
     <img src="assets/Debian/step16.png" alt="stepvd6">
   </div>

7. Pada tampilan utama, arahkan ke tools yang sudah dibuat dan klik **"Settings"**
   <div align="center">
     <img src="assets/Debian/step17.png" alt="stepvd7">
   </div>

8. Pada bagian General, ubah Shared Clipboard menjadi bidirectional
   <div align="center">
     <img src="assets/Debian/step18.png" alt="stepvd8">
   </div>

9. Pada Display, atur video memory sebaik mungkin
   <div align="center">
     <img src="assets/Debian/step19.png" alt="stepvd9">
   </div>

10. Pada Storage > Empty, cari ISO yang sudah diunduh
    <div align="center">
      <img src="assets/Debian/step21.png" alt="stepvd10">
    </div>

11. Setelah menyetel, kembali ke halaman utama dan klik **"Start"**
    <div align="center">
      <img src="assets/Debian/step23.png" alt="stepvd11">
    </div>

12. Setelah terbuka, tekan Enter pada **"Graphical Install"**
    <div align="center">
      <img src="assets/Debian/step24.png" alt="stepvd12">
    </div>

13. Pilih bahasa yang diinginkan dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step25.png" alt="stepvd13">
    </div>

14. Pilih lokasi yang diinginkan dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step26.png" alt="stepvd14">
    </div>

15. Pilih layout keyboard yang diinginkan dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step27.png" alt="stepvd15">
    </div>

16. Tunggu proses persiapan
    <div align="center">
      <img src="assets/Debian/step28.png" alt="stepvd16">
    </div>

17. Masukkan hostname sesuai saran Administrator Protocol dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step29.png" alt="stepvd17">
    </div>

18. Masukkan Password sesuai keinginan dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step30.png" alt="stepvd18">
    </div>

19. Masukkan User account sesuai keinginan dan klik **"Continue"** dan tunggu prosesnya
    <div align="center">
      <img src="assets/Debian/step31.png" alt="stepvd19">
    </div>

20. Pilih partisi disk yang sudah dibuat dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step32.png" alt="stepvd20">
    </div>

21. Pilih "All files in one partition"
    <div align="center">
      <img src="assets/Debian/step33.png" alt="stepvd21">
    </div>

22. Pilih "Primary" untuk / dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step45.png" alt="stepvd22">
    </div>

23. Masukkan / (20GB) dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step37.png" alt="stepvd23">
    </div>

24. Pilih Ext4 untuk / dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step36.png" alt="stepvd24">
    </div>

25. Klik "Done setting up the partition" dan **"Continue"**
    <div align="center">
      <img src="assets/Debian/step38.png" alt="stepvd25">
    </div>

26. Lakukan hal yang sama untuk partisi yang belum dibagi dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step39.png" alt="stepvd26">
    </div>

27. Klik "Create a new partition" dan **"Continue"**
    <div align="center">
      <img src="assets/Debian/step40.png" alt="stepvd27">
    </div>

28. Masukkan ukuran 5GB untuk /Storage dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step41.png" alt="stepvd28">
    </div>

29. Pilih "Primary" untuk /Storage dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step42.png" alt="stepvd29">
    </div>

30. Klik "Beginning" dan **"Continue"**
    <div align="center">
      <img src="assets/Debian/step43.png" alt="stepvd30">
    </div>

31. Pilih ext4 dan ubah Mount point menjadi /Storage, klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step44.png" alt="stepvd31">
    </div>

32. Pilih partisi yang belum diinisialisasi, klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step46.png" alt="stepvd32">
    </div>

33. Klik "Create a new partition" dan **"Continue"**
    <div align="center">
      <img src="assets/Debian/step40.png" alt="stepvd33">
    </div>

34. Masukkan ukuran 1.5GB untuk SWAP dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step47.png" alt="stepvd34">
    </div>

35. Pilih "Logical" dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step48.png" alt="stepvd35">
    </div>

36. Klik "Beginning" dan **"Continue"**
    <div align="center">
      <img src="assets/Debian/step43.png" alt="stepvd36">
    </div>

37. Pilih "Use as" dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step44.png" alt="stepvd37">
    </div>

38. Pilih "SWAP" untuk "Use as" dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step49.png" alt="stepvd38">
    </div>

39. Klik "Done setting up the partition" dan **"Continue"**
    <div align="center">
      <img src="assets/Debian/step50.png" alt="stepvd39">
    </div>

40. Pilih "Finish partitioning and write changes to disk" dan **"Continue"**
    <div align="center">
      <img src="assets/Debian/step51.png" alt="stepvd40">
    </div>

41. Pilih "Yes" dan klik **"Continue"** pada pertanyaan write the changes to disk
    <div align="center">
      <img src="assets/Debian/step52.png" alt="stepvd41">
    </div>

42. Pilih "No" pada scan Extra installation media
    <div align="center">
      <img src="assets/Debian/step54.png" alt="stepvd42">
    </div>

43. Pilih "Configure the package manager" country menjadi "Indonesia" dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step55.png" alt="stepvd43">
    </div>

44. Pilih Debian archive mirror ke "Kebo.pens.ac.id" dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step56.png" alt="stepvd44">
    </div>

45. Kosongkan bagian http proxy dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step57.png" alt="stepvd45">
    </div>

46. Pada tahap configuring popularity, pilih NO dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step58.png" alt="stepvd46">
    </div>

47. Tunggu proses instalasi
    <div align="center">
      <img src="assets/Debian/step59.png" alt="stepvd47">
    </div>

48. Pilih "Yes" pada pertanyaan apakah install GRUB dan klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step60.png" alt="stepvd48">
    </div>

49. Tunggu instalasi GRUB hingga selesai
    <div align="center">
      <img src="assets/Debian/step61.png" alt="stepvd49">
    </div>

50. Pilih bootloader GRUB pada device awal yang telah dibuat
    <div align="center">
      <img src="assets/Debian/step64.png" alt="stepvd50">
    </div>

51. Pada permintaan reboot, klik **"Continue"**
    <div align="center">
      <img src="assets/Debian/step65.png" alt="stepvd51">
    </div>

52. Dan akhirnya, OS Linux Debian 12 Anda siap digunakan!
    <div align="center">
      <img src="assets/Debian/step62.png" alt="stepvd52">
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
