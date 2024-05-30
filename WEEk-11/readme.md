<div align="center">
  <h1 class="text-align: center;font-weight: bold">Praktikum 11<br>Praktek System Operasi</h1>
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

## Scheduling Algorithm

#### First-Come First-Serve Algorithm

##### Contoh perhitungan secara teori :

![App Screenshot](assets/1.png)

##### Hasil running

![App Screenshot](assets/2.png)

##### Flowchart

![App Screenshot](assets/flowfcfs.png)

##### Analisa

Berdasarkan gambar hasil percobaan di atas, dapat disimpulkan bahwa Algoritma First-Come First-Serve telah berfungsi sesuai dengan teori. Algoritma ini bekerja dengan prinsip antrian, di mana proses yang datang pertama (waktu kedatangan paling awal) akan dijalankan terlebih dahulu, kemudian proses berikutnya dijalankan setelah proses sebelumnya selesai, dan seterusnya seperti dalam konsep antrian. Konsep antrian yang dimaksud adalah proses yang datang lebih awal dilayani terlebih dahulu, sehingga semua proses berjalan secara berurutan.

#### Round Robin Algorithm

##### Contoh perhitungan secara teori :

![alt text](assets/4.png)

##### Hasil running

![alt text](assets/5.png)

##### Flowchart

![alt text](assets/6.png)

##### Analisa

Algoritma Round Robin beroperasi dengan menggunakan time quantum, yang pada dasarnya adalah batas waktu bagi sebuah proses untuk berjalan. Jika burst time suatu proses lebih kecil dari time quantum, proses tersebut akan berjalan selama burst time. Jika burst time suatu proses lebih besar dari time quantum, proses tersebut akan berjalan selama time quantum, dan burst time akan diperbarui menjadi sisa burst time setelah berjalan selama time quantum (Burst time - Quantum time = Sisa Burst Time), lalu proses tersebut akan dikembalikan ke ready queue. Proses ini terus berlanjut hingga semua proses selesai. Pada percobaan di atas, detail output dari queue menunjukkan urutan proses berjalan, dimulai dari P1 -> P2 -> P1 -> P3 -> P2 -> P1.

#### Shortest Job First Algorithm

##### Contoh perhitungan secara teori :

![alt text](assets/7.png)

##### Hasil running

![alt text](assets/8.png)

##### Flowchart

![App Screenshot](assets/SJF-Flowchart.jpg)

##### Analisa

Algoritma Shortest Job First bekerja dengan memprioritaskan proses yang memiliki burst time paling pendek, sambil mempertimbangkan arrival time. Proses yang pertama datang akan dieksekusi sampai selesai terlebih dahulu. Kemudian, proses yang ada di ready queue akan dibandingkan untuk menentukan mana yang memiliki burst time paling singkat, dan proses tersebut yang akan dieksekusi selanjutnya. Jika ada beberapa proses dengan burst time yang sama, maka proses dengan arrival time lebih awal (yang datang lebih dulu) akan diprioritaskan.
