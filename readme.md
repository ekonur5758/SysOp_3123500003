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

1. Download ISO debian 12 pada (https://www.debian.org/download)
   ![stepvd2](assets/Debian/step1.png)

2. Masuk dalam tampilan virtual box dan klik **"New"**
   ![stepvd2](assets/Debian/step12.png)
3. Masukan name "BEBAS" (Debian12) Sesuaikan Type dan versi Debian sesuai arsitektur CPU kemudian Klik **"Next"**
   ![stepvd3](assets/Debian/step13.png)

4. **Alokasikan** Cpu & Ram Usage sesuai arahan (4096MB RAM & 2 CORE CPU)
   ![stepvd4](assets/Debian/step14.png)

5. **Alokasikan** Storage 25GB (Akan otomatis generate 26gb) dan klik **"NEXT"**
   ![stepvd5](assets/Debian//step15.png)

6. Pada summary / preview silahkan klik **"finish"**
   ![stepvd6](assets/Debian/step16.png)

7. Pada tampilan utama arahkan serta klik tools yang sudah dibuat dan klik **"setting"**
   ![stepvd7](assets/Debian/step17.png)

8. Pada general ubah shared **Clipboard** menjadi bidirectional
   ![stepvd8](assets/Debian/step18.png)

9. Pada Display atur video memory sebaik mungkin, bila akan membutuhkan rendering yang cukup berat maka opsi paling maksimal adalah yang terbaik
   ![stepvd8](assets/Debian/step19.png)

10. Pada Storage > Empty > Silahkan cari iso yang telah Didownload
    ![stepvd10](assets/Debian/step21.png)

11. Cari iso yang telah didownload serta klik open
    ![stepvd11](assets/Debian/step22.png)

12. Setelah menyeting, silahkan kembali ke halaman utama dan Klik **"Start"**
    ![stepvd13](assets/Debian/step23.png)

13. Setelah terbuka silahkan enter pada **Grapich Install**
    ![stepvd14](assets/Debian/step24.png)

14. Pilih bahasa yang di inginkan dan Klik **Continue**
    ![stepvd15](assets/Debian/step25.png)

15. Pilih Lokasi yang di inginkan (bisa yang terdekat dengan kalian) dan Klik **Continue**
    ![stepvd15](assets/Debian/step26.png)

16. Pilih Layout keyboard yang di inginkan dan Klik **Continue**
    ![stepvd16](assets/Debian/step27.png)

17. Silahkan tunggu proses-proses persiapannya
    ![stepvd17](assets/Debian/step28.png)

18. Masukan hostname sesuai saran Administrator Protocol dan Klik **Continue**
    ![stepvd18](assets/Debian/step29.png)

19. Masukan Password sesuai keinginan dan Klik **Continue**
    ![stepvd19](assets/Debian/step30.png)

20. Masukan User account sesuai keinginan dan Klik **Continue** dan tunggu proses-prosesnya
    ![stepvd20](assets/Debian/step31.png)

21. Pilih Partisi disk yang sudah dibuat dan ditetapkan diawal langkah tadi dan Klik **Continue**
    ![stepvd20](assets/Debian/step32.png)

22. Pilih all files in one partisi.
    ![stepvd20](assets/Debian/step33.png)

23. Partisi untuk di pisah-pisah.
    ![stepvd20](assets/Debian/step34.png)

24. Pilih Primary, untuk / dan Klik **Continue**
    ![stepvd20](assets/Debian/step45.png)

25. Masukan sesuai arahan yaitu / (20GB) dan klik **Continue**
    ![stepvd20](assets/Debian/step37.png)

26. Pilih Ext4 & karna sudah GRUB sehingga tidak perlu bootflag ON, untuk / dan Klik **Continue**
    ![stepvd20](assets/Debian/step36.png)

27. Kemudian klik aja langsung bagian done setting up the partition dan Klik **Continue**
    ![stepvd20](assets/Debian/step38.png)

28. Lakukan hal berulang dengan pilih partisi yang belum dibagi dan Klik **Continue**
    ![stepvd20](assets/Debian/step39.png)

29. Lalu klik crete a new partition dan Klik **Continue**
    ![stepvd20](assets/Debian/step40.png)

30. Masukan size sebesar 5GB untuk /Storage dan klik **Continue**
    ![stepvd20](assets/Debian/step41.png)

31. Pilih Primary untuk /Storage dan klik **Continue**
    ![stepvd20](assets/Debian/step42.png)

32. Pilih beginning dan klik **Continue**
    ![stepvd20](assets/Debian/step43.png)

33. Gunakan ext4 dan jangan lupa ubah Mount point dengan cara enter manually menjadi /Storage dan Klik **Continue**
    ![stepvd20](assets/Debian/step44.png)

34. Pilih lagi dengan paritisi yang belum di inisialisasi
    ![stepvd20](assets/Debian/step46.png)

35. Lalu klik crete a new partition dan Klik **Continue**
    ![stepvd20](assets/Debian/step40.png)

36. Masukan size partisi sebesar 1.5GB untuk SWAP dan klik **Continue**
    ![stepvd20](assets/Debian/step47.png)

37. Plih Logical dan Klik **Continue**
    ![stepvd20](assets/Debian/step48.png)

38. Pilih beginning dan klik **Continue**
    ![stepvd20](assets/Debian/step43.png)

39. Pilihlah use As klik **Continue**
    ![stepvd20](assets/Debian/step44.png)

40. Pada use As gantilah menjadi SWAP dan klik **Continue**
    ![stepvd20](assets/Debian/step49.png)

41. Kemudian klik aja langsung bagian done setting up the partition dan Klik **Continue**
    ![stepvd20](assets/Debian/step50.png)

42. Jika sudah silahkan pilih finish partisioning dan Klik **Continue**
    ![stepvd20](assets/Debian/step51.png)

43. Pilih yes dan Klik **continue** pada pertanyaan write the change to disk.
    ![stepvd20](assets/Debian/step52.png)

44. Pilih No pada scan Extra installation media
    ![stepvd20](assets/Debian/step54.png)

45. Pilih Configure the package manager country ke negara "Indonesia" dan Klik **continue**
    ![stepvd20](assets/Debian/step55.png)

46. Pilih Debian archive mirror ke Kebo.pens.ac.id dan Klik **continue**
    ![stepvd20](assets/Debian/step56.png)

47. Kosongkan bagian http proxy dan Klik **continue**
    ![stepvd20](assets/Debian/step57.png)

48. Pada tahap configuring popularity pilih NO dan Klik **continue**
    ![stepvd20](assets/Debian/step58.png)

49. Tunggu Proses Installasi
    ![stepvd20](assets/Debian/step59.png)

50. Pilih yes pada pertanyaan apakah install GRUB dan Klik **Continue**
    ![stepvd20](assets/Debian/step60.png)

51. Tunggu Installasi GRUB hingga selesai
    ![stepvd20](assets/Debian/step61.png)

52. Pilihlah bootloader GRUB pada device awal yang tadi kita buat.
    ![stepvd20](assets/Debian/step64.png)
53. Pada Permintaan reboot silahkan klik **Continue**
    ![stepvd20](assets/Debian/step65.png)

54. Dan Akhirnya OS linux debian kita siap digunakan!
    ![stepvd20](assets/Debian/step62.png)

## Kesimpulan

setelah praktikum Percobaan instal debian pada virtualbox menjadikan mahasiswa paham bagaimana cara menginstall OS pada VM (Virtual Machine) & Memberikan wawasan tentang konsep sederhana jalannya Operating Sistem selain itu, hal yang menarik ialah OS dapat berjalan tanpa harus menjadi Boot prioritas pada suatu BIOS / UEFI tapi OS juga dapat berjalan dan dijalankan pada Virtual Machine, sebagai Contoh adalah Oracle Virtualbox ini, bisa menjalankan Debian. mungkin bila di Machintos (MacOS) ada windows Pararel yang dapat menjalankan OS windows pada macbook / iMac dengan menggunakan Virtual Machine. sehingga dapat kita simpulkan bersama pada intinya OS adalah suatu perangkat lunak yang sangat penting pada keberlangsungan fungsi suatu barang elektronik tidak terkecuali sedikitpun.

### Referensi

Buku 'Operating System Concepts' [🔗](https://os.ecci.ucr.ac.cr/slides/Abraham-Silberschatz-Operating-System-Concepts-10th-2018.pdf)

Mengenal debian oleh telkom university [🔗](https://it.telkomuniversity.ac.id/mengenal-debian-os-sejarah-kelebihan-dan-kekurangan/)

Apa itu Virtual Box oleh jagongoding[🔗](https://jagongoding.com/others/apa-itu-virtual-box/)

Install virtual box oleh solmet kemendikbud [🔗](https://solmet.kemdikbud.go.id/?p=2660)

Link Download Debian [🔗](https://www.debian.org/download)

Link Virtual Box[🔗](https://www.virtualbox.org/)

Video Tutorail How to Download & Instal debian 12 on VirtualBox[🔗](https://www.youtube.com/watch?v=zfOWKG2QPB0)

</div>
