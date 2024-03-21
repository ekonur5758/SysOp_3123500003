<div align="center">
  <h1 class="text-align: center;font-weight: bold">Praktikum 3<br>Praktek System Operasi</h1>
  <h3 class="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h3>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <div align="center">
  <h3 style="text-align: center;">Disusun Oleh :</h3>
  <p style="text-align: center;">
    <em>Muhammad Eko Nur Sholeh (3123500003)</em><br>
    <em>Ghaly Abrarian Putra (3123500018)</em><br>
    <em>Muhammad Rasyid Rafif (3122500030)</em>
  </p>
</div>

<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr><hr>
</div>

## Daftar Isi

1. [PPT](#ppt)
2. [FLOPS dan IOPS](#iops-dan-flops)<br>
   - [Install gcc](#instalasi-gcc)<br>
   - [Install make](#instalasi-make)<br>
   - [Install GIT](#instalasi-git)<br>
   - [Clone GIT flops&iops](#git-clone)<br>
   - [Tabel Pengujian](#tabel-pengujian)<br>
   - [Analisa](#analisa)
3. [Referensi](#referensi)

## PPT

**[Link PPT 🔗]([https://www.canva.com/design/DAF_WiIYVxg/RGJFWfZrDohJ6Ga9WcEA3g/edit](https://www.canva.com/design/DAF_XW_UZwk/Nu7KdnHiqvdVecegtiWBUQ/edit?utm_content=DAF_XW_UZwk&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton))**
            


### Instalasi GCC

1. **<p align="justify">Melakukan Instalasi Package GCC<p>**

 <p align="center">
     <img src="assets/gcc/gcc-1.png" alt="step1">
   </p>

<p align="justify">Masuklah dalam mode root pada terminal dengan cara su - dan masukkan password user, kemudian masukan perintah "sudo apt install GCC" dan bila ada pertanyaan do you want to continue? "masukan Y" </p>

2. **<p align="justify">Instalasi GCC<p>**

 <p align="center">
     <img src="assets/gcc/gcc-2.png" alt="step1">
   </p>
   <p align="center">
     <img src="assets/gcc/gcc-3.png" alt="step1">
   </p>

<p align="Justify">Tunggu proses penginstallan GCC hingga selesai</p>


3. **<p align="justify">Cek Versi GCC<p>**

 
   <p align="center">
     <img src="assets/gcc/gcc-4.png" alt="step1">
   </p>

<p align="justify">Setelah proses intallasi selesai guna memastikan instalasi berhasil, maka kita bisa melakukan cek versi GCC dengan cara "gcc --version"</p>

### <h1 align="center">Instalasi make<h1>

1. **<p align="justify">Melakukan Instalasi Make**<p>
 <p align="center">
     <img src="assets/make/mk-1.png" alt="step1">
   </p>

<p align="justify">Masuklah dalam mode root pada terminal dengan cara su - dan masukkan password user, kemudian masukan perintah "sudo apt install make" dan Tunggu hingga install berhasil</p>

2. **<p align="justify">Cek Versi Make</p>**
 <p align="center">
     <img src="assets/make/mk-2.png" alt="step1">
   </p>

<p align="justify">untuk memastikan keberhasilan instalasi make, kita bisa melakukan validasi cek versi, dengan cara "make --version"</p>


### <h1 align="center">Instalasi GIT<h1>

1. **<p align="justify">Melakukan Instalasi GIT**<p>
 <p align="center">
     <img src="assets/git/git-1.png" alt="step1">
   </p>

<p align="justify">Masuklah dalam mode root pada terminal dengan cara su - dan masukkan password user, kemudian masukan perintah "sudo apt install git" dan bila muncul pertanyaan "Do you want to continue?" silahkan masukan Y</p>

2. **<p align="justify">Download dan Install GIT**<p>
 <p align="center">
     <img src="assets/git/git-2.png" alt="step1">
   </p>

<p align="justify">setelah memasukan eksekusi Y, tunggu donwload & installasi git berjalan hingga selesai</p>

3. **<p align="justify">Melakukan cek versi**<p>
 <p align="center">
     <img src="assets/git/git-3.png" alt="step1">
   </p>

<p align="justify">setelah memasukan  donwload & installasi git berjalan hingga selesai, untuk memastikan installasi berhasil kita bisa melakukan checking versi git dengan cara "git --version"</p></p>
            
## <h1 align="center">Iops Dan Flops<h1>

<h2>Iops</h2>
<p align="justify">IOPS adalah jumlah permintaan yang dikirim aplikasi Anda ke disk penyimpanan dalam satu detik.</p>

<h3>Flops</h3>
<p>FLOPS adalah singkatan dari istilah dalam bahasa Inggris Floating point Operations Per Second yang merujuk pada satuan untuk jumlah perhitungan yang dapat dilakukan oleh sebuah perangkat komputasi (dalam hal ini adalah komputer) terhadap bilangan pecahan (floating point) tiap satu satuan waktu.</p>


<h2 align="center">Melakukan Benchmarking pada PC</h2>




#### GIT CLONE

1. **<p align="justify">Setelah melakukan instalasi GCC , GIT , MAKE**<p>

 <p align="center">
     <img src="assets/make/gitawl.png" alt="step1">
   </p>


<p>Lakukan perintah "$ sudo apt update" pada terminal kemudian ketik "$ sudo apt install gcc" untuk menginstall compile dan "$ sudo apt install git" untuk menginstall git pada debian</p>


**<p align="justify">2. Melakukan Git clone pada Debian 12**<p>

 <p align="center">
     <img src="assets/git/cl-1.png" alt="step1">
   </p>

<p>Arahkan direktori pada terminal yang ingin dituju lalu ketik "$ git clone (paste link github) lalu tekan enter</p>

**<p align="justify">3. Membuat Folder untuk tempat clone file**<p>

<p>Buka file manager layaknya di windows cari tempat untuk menampung folder dan buat foldernya serta open terminal</p>
 <p align="center">
     <img src="assets/git/cl-2.png" alt="step1">
   </p>



 <p align="center">
     <img src="assets/git/cl-3.png" alt="step1">
   </p>

<p>Kemudian lakukan perintah "git clone link_url_tujuan" pada terminal </p>

**<p align="justify">4. Melakukan Proses sebelum Benchmarking Iops dan Flops**<p>
 <p align="center">
     <img src="assets/git/cl-4.png" alt="step1">
   </p>
    <p align="center">
     <img src="assets/flop/fl1.png" alt="step1">
   </p>
<p align=justify>setelah file yang ada pada repository benchmark telah terclone pada folder, langkah berikutnya bisa langsung mengekskusi dengan "make" pada terminal folder flops-iops tadi</p>


**<p align="justify">5. Implementasi make install**<p>

<img src="assets/flop/fl3.png" alt="">

<p align=justify>setelah eksekusi make selanjutnya kita menginstall file benchmark yang telah kita clone tadi dengan perintah "sudo make install"</p>


**<p align="justify">6. Benchmark  Flops**<p>
<img src="assets/flop/flops.png" alt="">
<p align=justify>setelah berhasil install menggunakan make instal pada file2 hasil clone selanjutnya kita bisa langsung mengetest score benchmark flops dengan cara menuliskan "flops64 $(nproc)"</p>



**<p align="justify">7. Benchmark  Iops**<p>
<img src="assets/flop/iops.png" alt="">
<p align=justify>setelah berhasil install menggunakan make instal pada file2 hasil clone selanjutnya kita bisa langsung mengetest score benchmark iops dengan cara menuliskan "iops64 $(nproc)"</p>


**ANALISA** 
<h2 align="center">Analisa Hasil Benchmarking</h2>

***TABEL PENGUJIAN*** 
<p justify-content="center">

|                      | IOPS64 (Integer)         | FLOPS64 (Floating Point)    |
|----------------------|------------------------|---------------------------|
| Total Throughput     | 11.376083 Gigaiops     | 12.1991997Gigaflops       |
| Single Core Throughput | 5.698112 Gigaiops   | 6.109621Gigaflops       |
</p>

<p>Dengan melihat tabel di atas, Processor yang kita gunakan adalah ryzen 5 5600H dengan pembagian 2 core dapat dilihat bahwa IOPS memiliki total throughput dan throughput single core yang lebih tinggi dibandingkan dengan FLOPS. Namun demikian, perbedaan antara total throughput dan throughput single core juga penting untuk diperhatikan karena menunjukkan seberapa baik CPU dapat mengalokasikan dan memanfaatkan sumber daya secara efisien antara inti tunggal dan total throughput.</p>

**REFERENSI** 

[MICROSOFT IOPS](https://learn.microsoft.com/id-id/azure/virtual-machines/premium-storage-performance)

[WIKIPEDIA FLOPS](https://id.wikipedia.org/wiki/FLOPS)
