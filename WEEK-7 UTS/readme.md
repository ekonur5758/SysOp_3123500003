<div align="center">
  <h1 class="text-align: center;font-weight: bold">Ujian Tengah Semester 2<br>Praktek System Operasi</h1>
  <h3 class="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h3>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <div align="center">
  <h3 style="text-align: center;">Disusun Oleh :</h3>
  <p style="text-align: center;">
    <em>Muhammad Eko Nur Sholeh Ahadullail (3123500003)</em><br>
  </p>
</div>

<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr><hr>
</div>

# Process - Fork - Multithread

Setiap program atau bagian dari program yang sedang dieksekusi oleh CPU disebut dengan proses. Proses dapat berjalan secara _foreground_ atau _background_.

Untuk melihat seluruh proses yang sedang berjalan gunakan perintah `$ ps -e` .
Bisa juga menggunakan perintah `$pstree | more` untuk melihat secara detil proses yang sefan berjalan dengan format **tree**.

Setiap proses akan memilik **PID** Process ID). Apabila dibutuhkan Sebuah proses bisa memiliki proses anakan. Dalam hubungan tersebut proses dapat diibaratkan seperti orang tua (_parent_) dengan anak (_child_) yang turun temurun.

- Setiap proses memiliki parent dan child.
- Setiap proses memiliki ID (_pid_) dan parent ID (_ppid_), kecuali proses `init` atau `systemd`.
- _ppid_ dari sebuah proses adalah ID dari parent proses tersebut.

```mermaid
classDiagram
      Parent_Process --|> Child_Process
      Parent_Process : PID =4900
      Parent_Process : PPID = 4
      Parent_Process: bash
      class Child_Process{
          PID=4901
          PPID = 4900
          fork01
      }
```

Perhatikan, ppid dari proses `fork01` adalah pid dari proses `bash`.

**fork** digunakan untuk menduplikasi proses. Proses yang baru disebut dengan child proses, sedangkan proses pemanggil disebut dengan parent proses. Spesifikasi fork bisa dilihat dengan `$ man 2 fork`.

```
int main() {
                            pid: 2308, ppid: 10
                             [Main process]
                                 |
  fork();              > Child process created <
                                 +
                               /   \
                             /       \
               pid: 2308, ppid: 10    pid: 30, ppid: 2308
                [Parent Process]    [Child Process]

  return 0;
}
```

perhatikan bahwa :

- `pid` Parent Process == `ppid` Child
- `child_id` Parent Process == `pid` Child Process

**Exec** adalah function yang digunakan untuk menjalankan program baru dan mengganti program yang sedang berlangsung. `exec` adalah program family yang memiliki berbagai fungsi variasi, yaitu `execvp`, `execlp`, `execv`, dan lain lain.

**wait** adalah function yang digunakan untuk mendapatkan informasi ketika child proses berganti _state_-nya. Pergantian state dapat berupa _termination_, _resume_, atau _stop_.

Manual: `$ man 3 exec`

## 1. Fork : Parent - Child Process

- Buat tulisan tentang konsep **fork** dan implementasinya dengan menggunakan bahasa pemrograman C! (minimal 2 paragraf disertai dengan gambar)

---

<h3 style="text-align: center; font-weight: semi-bold; margin-top: 0; margin-bottom: 0; text-decoration: underline">Konsep Fork</h3>
<br><br>

<p align="justify">
  Fork() dalam sistem operasi Linux atau Unix merupakan sebuah proses baru untuk menduplikasi proses pemanggilan. Proses baru ini biasa disebut dengan proses anak / menganak / melahirkan, proses pemanggilanya dapat dikatakan sebagai Proses induk (parent) sedangkan proses yang diduplikasikan (child),
  proses child yang dihasilkan merupakan hasil replika proses parent pada saat fork di Panggil, hal ini meliput kode program , nilai variabel dan ruang alamat pada memori, fork sangat berguna untuk aplikasi multi-threading dan pemrosesan secara pararel. kalau didalam bahasa pemrograman C, fungsi fork() di terapkan untuk memanfaatkan mekanisme ini, Fungsi ini, ketika dipanggil,meminta sistem operasi untuk membuat proses baru. dan proses baru ini atau child akan memulai eksekusinya dari titik yang sama dimana fork() di inisialisasi.
  tetapi bisa diidentifikasi dengan nilai pengembalian yang unik yaitu PID positif di parent untuk mengidentifikasi proses child, dan nilai 0 dalam proses child, memungkinkan keuda proses tersebut untuk mengeksekusi logika kondisional yang berbeda berdasarkan identitas.

Contoh Parent Proses (pstree)

<p align="center">
  <img src="assets/1.png" alt="App Screenshot">
</p>

<br><br>

Penggunaan Fork() dalam bahasa C, pemrogram harus memperhatikan pengelolaan proses child dan parent secara seksama untuk menghindari kondisi seperti zombie, proses zombie dimana sebuah anak (child) telah menyelesaikan eksekusinya namun induk belum mematikan proses child tersebut, maka dari itu pemrogram harus menggunakan waitid() hal tersebut diperuntukan agar si child tidak menjadi Zombie, waitid() akan menghalangi parent berakhir sebelum child dan memungkinkan Sistem operasi untuk menghentikan semua sumber daya yang digunakan oleh child.




- Deskripsikan dan visualisasikan pohon proses hasil eksekusi dari kode program `fork01.c`, `fork02.c`, `fork03.c`, `fork04.c`, `fork05.c`dan `fork06.c`.

---

```
fork01.c :
using namespace std;

#include <stdio.h>
#include <unistd.h>

int main(void) {
  pid_t mypid;
  uid_t myuid;
  for (int i = 0; i < 3; i++) {
    mypid = getpid();
    printf("I am process %d\n", mypid);
    printf("My parent process ID is %d\n", getppid());
    printf("The owner of this process has uid %d\n", getuid());
    /* sleep adalah system call atau fungsi library
    yang menghentikan proses ini dalam detik
    */
    sleep(3);
  }
  return 0;
}
```

![App Screenshot](assets/2.png)

_1. Header Files:_

`<unistd.h> untuk panggil sistem seperti getpid(), getppid(), getuid(), dan sleep()..`

_2. Deklarasi using namespace :_

`untuk menggunakan semua elemen dari std`

_3. Fungsi main_

`awal permulaan masuk program`

_4.Deklarasi Variabel :_

```
ada berberapa variabel antara lain :
pid_t = untuk menyimpan ID proses
uid_t = untuk menyimpan user ID
```

_5.Loop For :_

```
program dibatasi i < 3 yaitu 3x loop
dalam setiap kali loop :
- memanggil getpid() untuk menyimpan id proses dan di simpan divariabel
- mencetak id proses
- memanggil getppid() untuk mendapatkan dan mencetak ID proses induk / parent
- memanggil getuid() untuk mendapatkan dan mencetak UID pemilik proses
- Memanggil sleep() untuk menunda / memberhentikan sementara eksekusi
```

<br><br>
Visualisasi Program :

```
                          Proses Program
                                 |
                                 |
                                 |
                            max 3x loop
                                 |
            CETAK & SLEEP 3 [PID : 1234, PPID : 5678, UID: 1000]

```

proses akan menjalankan loop sebanyak I > 3 yang artinya akan melakukan loop maksimal 3x, dan fungsi sleep akan membuat tidur selama 3 detik sebelum melakukan looping.

---

```
Fork02.c :
#include <stdio.h>
#include <unistd.h>

int main(void) {
  pid_t childpid;
  int x = 5;
  childpid = fork();

  while (1) {
    printf("This is process ID %d\n", getpid());
    printf("In this process the value of x becomes %d\n", x);
    sleep(2);
    x++;
  }
  return 0;
}
```

![App Screenshot](assets/3.png)

_1. Header Files:_

`<unistd.h> untuk panggil sistem seperti getpid(),fork(),sleep()`

_2. Deklarasi using namespace :_

`untuk menggunakan semua elemen dari std`

_3. Fungsi main_

`awal permulaan masuk program`

_4.Deklarasi Variabel :_

```
ada berberapa variabel antara lain :
pid_t = untuk menyimpan ID proses
int x = 5 = mendeklarasi serta memberi value / nilai 5 pada variabel X
```

_5. Panggilan Fungsi fork():_

```
childpid = fork(); untuk memanggil fork(),
serta membuat proses anak (child),
fork() akan mengembalikan nilai 0 menuju proses child
dan ID proses anak ke proses induk.
```

_6. Loop while :_

```
- Loop ini akan berjalan tanpa henti
- mencetak ID proses saat itu langsung dengan getpid()
- Mencetak nilai dari variabel X
- Menunda eksekusi dengan sleep 2 yaitu nunda 2 detik
- menginkeremen / menambahkan var X
```

Visualisasi program :

```
                               Parent Process
                                      |
                                  fork()
                    [loop getpid(), inkeremen x, sleep 2 detik]
                                      |
                                Child Process


```

Program akan berjalan terus atau melooping terus tidak berhenti, dan selalu mengulang ngulang ID proses dari induk maupun anak.

---

```
Fork03.c :
#include <stdio.h>
#include <unistd.h>

int main(void) {
  pid_t childpid;
  childpid = fork();

  for (int i = 0; i < 5; i++) {
    printf("This is process %d\n", getpid());
    sleep(2);
  }

  return 0;
}
```

![App Screenshot](assets/4.png)

_1. Header Files:_

`<unistd.h> untuk panggil sistem seperti getpid(), fork()`

_2. Deklarasi using namespace :_

`untuk menggunakan semua elemen dari std`

_3. Fungsi main_

`awal permulaan masuk program`

_4.Deklarasi Variabel :_

```
ada berberapa variabel antara lain :
pid_t = childpid = untuk menyimpan ID proses dari panggilan fork()

```

_6. Panggilan fork()_

```
membuat proses anak / child
```

_7.Loop For :_

```
program dibatasi i < 5 yaitu 5x loop
dalam setiap kali loop :
- memanggil pid_t() untuk menyimpan id proses dan di simpan childpid
- mencetak id proses
- Memanggil sleep(2) untuk menunda / memberhentikan sementara eksekusi

hal diatas terjadi pada proses Induk dan anak.
```

Visualisasi program :

```
Mulai
 │
 ├─> Proses Induk
 │    │
 │    ├─ fork() ───> Gagal (-1)? ──> Keluar
 │    │
 │    └─> Sukses
 │         │
 │         ├─> Proses Anak (childpid = 0)
 │         │    │
 │         │    ├─ Loop 5 kali:
 │         │    │   ├─ Cetak "This is process [ID Proses Anak]"
 │         │    │   └─ Tidur 2 detik
 │         │    └─> Keluar
 │         │
 │         └─> Proses Induk (childpid = [ID Proses Anak])
 │              │
 │              ├─ Loop 5 kali:
 │              │   ├─ Cetak "This is process [ID Proses Induk]"
 │              │   └─ Tidur 2 detik
 │              └─> Keluar
 └─> Keluar


```

jadi program tersebut akan melakukan fork dan akan melooping sebanyak 5x serta pid_t yaitu mengambil id proses yang sedang berlangsung baik induk maupun child.

---

```
Fork04.c :
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/wait.h>

int main(void) {
  pid_t child_pid;
  int status;
  pid_t wait_result;

  child_pid = fork();
  if (child_pid == 0) {
    /* kode ini hanya dieksekusi proses child */
    printf("I am a child and my pid = %d\n", getpid());
    printf("My parent is %d\n", getppid());
    /* keluar if akan menghentikan hanya proses child */
  } else if (child_pid > 0) {
    /* kode ini hanya mengeksekusi proses parent */
    printf("I am the parent and my pid = %d\n", getpid());
    printf("My child has pid = %d\n", child_pid);
  } else {
    printf("The fork system call failed to create a new process\n");
    exit(1);
  }

  /* kode ini dieksekusi baik oleh proses parent dan child */
  printf("I am a happy, healthy process and my pid = %d\n", getpid());

  if (child_pid == 0) {
    /* kode ini hanya dieksekusi oleh proses child */
    printf("I am a child and I am quitting work now!\n");
  } else {
    /* kode ini hanya dieksekusi oleh proses parent */
    printf("I am a parent and I am going to wait for my child\n");

    do {
      /* parent menunggu sinyal SIGCHLD mengirim tanda bahwa proses child diterminasi */
      wait_result = wait(&status);
    } while (wait_result != child_pid);

    printf("I am a parent and I am quitting.\n");
  }

  return 0;
}
```

![App Screenshot](assets/5.png)

_1. Header Files:_

`<iostream> untuk operasi input dan output.`

`<sys/types.h> untuk menyediakan definisi berbagai tipe data yang berkaitan dengan OS.`

`<unistd.h> untuk panggil sistem seperti getpid(), fork()`

`<sys/wait.h> untuk panggil sistem seperti wait()`

_2. Deklarasi using namespace :_

`untuk menggunakan semua elemen dari std`

_3. Fungsi main_

`awal permulaan masuk program`

_4.Deklarasi Variabel :_

```
ada berberapa variabel antara lain :
pid_t = childpid = untuk menyimpan ID proses anak dari panggilan fork()
int = status = untuk menyimpan status keluar dari proses child.
pid_t = wait_result = untuk menyimpan hasil dari pemanggilan wait(),

```

_5. Panggilan fork()_

```
membuat proses anak / child
```

_6.Percabangan (if else) :_

```
pada proses anak (child_pid == 0)
- mencetak id proses dan Id proses induk
- mencetak pesan sebelum keluar

pada proses induk (child_pid > 0)
- mencetak ID prosesnya dan ID proses anaknya
- Menunggu proses anak selesai dengan menggunakan fitur wait()
- wait(&status) untuk menunggu proses anak kelar dan menyimpannya
pada variabel status
- mencetak pesan sebelum keluar

kalau child_pid kurang dari 0 maka mencetak pesan error
```

Visualisasi program :

```
Mulai
 │
 ├─ fork()
 │  │
 │  ├─ Gagal (-1)
 │  │   └─ Cetak error ──> exit(1)
 │  │
 │  ├─ Proses Anak (0)
 │  │   ├─ Cetak "I am a child..." dan "My parent is..."
 │  │   ├─ Cetak "I am a happy, healthy process..."
 │  │   └─ Cetak "I am a child and I am quitting work now!" ──> Keluar
 │  │
 │  └─ Proses Induk (>0)
 │      ├─ Cetak "I am the parent..." dan "My child has pid..."
 │      ├─ Cetak "I am a happy, healthy process..."
 │      ├─ Cetak "I am a parent and I am going to wait for my child"
 │      ├─ wait() ──> Tunggu proses anak selesai
 │      └─ Cetak "I am a parent and I am quitting." ──> Keluar
 │
 └─> Keluar



```

jadi program tersebut akan melakukan fork dan menunggu proses anak selesai sebelum induk melanjutkan eksekusinya.

---

```
Fork05.c :
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/wait.h>

int main(void) {
    pid_t child_pid;
    int status;
    pid_t wait_result;
    child_pid = fork();
    if (child_pid == 0) {
        /* kode ini hanya dieksekusi proses child */
        printf("I am a child and my pid = %d\n", getpid());
        execl("/bin/ls", "ls", "-l", "/home", NULL);
        /* jika execl berhasil, kode setelahnya tidak pernah dieksekusi */
        printf("Could not execl file /bin/ls\n");
        exit(1);
        /* exit menghentikan hanya proses child */
    } else if (child_pid > 0) {
        /* kode ini hanya mengeksekusi proses parent */
        printf("I am the parent and my pid = %d\n", getpid());
        printf("My child has pid = %d\n", child_pid);
    } else {
        printf("The fork system call failed to create a new process\n");
        exit(1);
    }
    /* kode ini hanya dieksekusi oleh proses parent karena
    child mengeksekusi dari “/bin/ls” atau keluar */
    printf("I am a happy, healthy process and my pid = %d\n", getpid());
    if (child_pid == 0) {
        /* kode ini tidak pernah dieksekusi */
        printf("This code will never be executed!\n");
    } else {
        /* kode ini hanya dieksekusi oleh proses parent */
        printf("I am a parent and I am going to wait for my child\n");
        do {
            /* parent menunggu sinyal SIGCHLD mengirim tanda bila proses child diterminasi */
            wait_result = wait(&status);
        } while (wait_result != child_pid);
        printf("I am a parent and I am quitting.\n");
    }
    return 0;
}

```

![App Screenshot](assets/6.png)

_1. Header Files:_


`<sys/types.h> untuk menyediakan definisi berbagai tipe data yang berkaitan dengan OS.`

`<unistd.h> untuk panggil sistem seperti getpid(), fork()`

`<sys/wait.h> untuk panggil sistem seperti wait()`

_2. Deklarasi using namespace :_

`untuk menggunakan semua elemen dari std`

_3. Fungsi main_

`awal permulaan masuk program`

_4.Deklarasi Variabel :_

```
ada berberapa variabel antara lain :
pid_t = childpid = untuk menyimpan ID proses anak dari panggilan fork()
int = status = untuk menyimpan status keluar dari proses child.
pid_t = wait_result = untuk menyimpan hasil dari pemanggilan wait(),

```

_6. Panggilan fork()_

```
membuat proses anak / child
```

_7.Percabangan (if else) :_

```
pada proses anak (child_pid == 0)
- mencetak id proses sendiri
- menjalakan ls -l /home
- jika execl gagal akan mencetak error

pada proses induk (child_pid > 0)
- mencetak ID prosesnya dan ID proses anaknya
- Mencetak bahwa ini adalah proses .......
- wait(&status) untuk menunggu proses anak kelar Do while dipanggil untuk memastikan terus sampai proses anak selesai
- setelah proses anak selesai akan mencetak pesan keluar

kalau child_pid kurang dari 0 maka mencetak pesan error
```

Visualisasi program :

```
Mulai
 │
 ├─ fork()
 │  │
 │  ├─ Gagal (-1)
 │  │   └─ Cetak error ──> exit(1)
 │  │
 │  ├─ Proses Anak (0)
 │  │   ├─ Cetak "I am a child..."
 │  │   ├─ execl("/bin/ls", "ls", "-l", "/home", NULL)
 │  │   │   └─ Gagal? ──> Cetak "Could not execl..." ──> exit(1)
 │  │   └─ (Proses digantikan oleh /bin/ls, tidak ada kode lebih lanjut yang dijalankan)
 │  │
 │  └─ Proses Induk (>0)
 │      ├─ Cetak "I am the parent..." dan "My child has pid..."
 │      ├─ Cetak "I am a happy, healthy process..."
 │      ├─ Cetak "I am a parent and I am going to wait for my child"
 │      ├─ wait(&status) ──> Tunggu proses anak selesai
 │      └─ Cetak "I am a parent and I am quitting." ──> Keluar
 │
 └─> Keluar




```

jadi program tersebut akan melakukan fork dan mengkeskusi progam lain menggunakan execl setelah melakukan fork, dan menciptakan proses anak yang menjalakan -ls -l

---

```
Fork06.c :
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/wait.h>

int main(void) {
    pid_t child_pid;
    int status;
    pid_t wait_result;
    child_pid = fork();

    if (child_pid == 0) {
        /* kode ini hanya dieksekusi proses child */
        printf("I am a child and my pid = %d\n", getpid());
        execl("./fork03", "goose", NULL);
        /* jika execl berhasil, kode setelahnya tidak pernah dieksekusi */
        printf("Could not execl file fork3\n");
        exit(1);
        /* exit menghentikan hanya proses child */
    } else if (child_pid > 0) {
        /* kode ini hanya mengeksekusi proses parent */
        printf("I am the parent and my pid = %d\n", getpid());
        printf("My child has pid = %d\n", child_pid);
    } else {
        printf("The fork system call failed to create a new process\n");
        exit(1);
    }
    /* kode ini hanya dieksekusi oleh proses parent karena
    child mengeksekusi dari “fork3” atau keluar */
    printf("I am a happy, healthy process and my pid = %d\n", getpid());
    if (child_pid == 0) {
        /* kode ini tidak pernah dieksekusi */
        printf("This code will never be executed!\n");
    } else {
        /* kode ini hanya dieksekusi oleh proses parent */
        printf("I am a parent and I am going to wait for my child\n");
        do {
            /* parent menunggu sinyal SIGCHLD mengirim tanda
            bila proses child diterminasi */
            wait_result = wait(&status);
        } while (wait_result != child_pid);
        printf("I am a parent and I am quitting.\n");
    }
    return 0;
}
```

![App Screenshot](assets/7.png)

_1. Header Files:_

`<sys/types.h> untuk menyediakan definisi berbagai tipe data yang berkaitan dengan OS.`

`<unistd.h> untuk panggil sistem seperti getpid(), fork()`

`<sys/wait.h> untuk panggil sistem seperti wait()`

_2. Deklarasi using namespace :_

`untuk menggunakan semua elemen dari std`

_3. Fungsi main_

`awal permulaan masuk program`

_4.Deklarasi Variabel :_

```
ada berberapa variabel antara lain :
pid_t = childpid = untuk menyimpan ID proses anak dari panggilan fork()
int = status = untuk menyimpan status keluar dari proses child.
pid_t = wait_result = untuk menyimpan hasil dari pemanggilan wait(),

```

_5. Panggilan fork()_

```
membuat proses anak / child
```

_6.Percabangan (if else) :_

```
pada proses anak (child_pid == 0)

- mencetak id anak
- mencoba menjalankan program ./fork03 menggunakan execl()
jika berhasil kode akan berjalan,
jika gagal maka akan mencetak "Could not execl file fork3"


pada proses induk (child_pid > 0)
- mencetak ID prosesnya dan ID proses anaknya
- Mencetak bahwa ini adalah proses .......
- wait(&status) untuk menunggu proses anak kelar Do while dipanggil untuk memastikan terus sampai proses anak selesai
- setelah proses anak selesai akan mencetak pesan keluar

kalau child_pid kurang dari 0 maka mencetak pesan error
```

Visualisasi program :

```
Mulai
 │
 ├─ fork()
 │  │
 │  ├─ Gagal (-1)
 │  │   └─ Cetak error ──> exit(1)
 │  │
 │  ├─ Proses Anak (0)
 │  │   ├─ Cetak "I am a child..."
 │  │   ├─ execl("fork03", "goose", NULL)
 │  │   │   └─ Gagal? ──> Cetak "Could not execl fork3" ──> exit(1)
 │  │   └─ (Proses digantikan oleh fork03, tidak ada kode lebih lanjut yang dijalankan)
 │  │
 │  └─ Proses Induk (>0)
 │      ├─ Cetak "I am the parent..." dan "My child has pid..."
 │      ├─ Cetak "I am a happy, healthy process..."
 │      ├─ Cetak "I am a parent and I am going to wait for my child"
 │      ├─ Menunggu proses anak selesai
 │      └─ Cetak "I am a parent and I am quitting." ──> Keluar
 │
 └─> Keluar

```

jadi program tersebut akan melakukan fork dan mengkeskusi progam lain menggunakan execl setelah melakukan fork, dan menciptakan proses anak yang menjalakan kode program fork03 yang telah dicompaile.

---

## 2. Tugas

Buatlah program perkalian 2 matriks [4 x 4] dalam bahasa C yang memanfaatkan `fork()`.

---

[Program Matriks C](matriks.c)

```
#include <stdio.h>
#include <unistd.h>
#include <sys/wait.h>

#define N 4


void baskom(int mat1[N][N], int mat2[N][N], int hasil[N][N], int row, int col) {
    for (int k = 0; k < N; k++) {
        hasil[row][col] += mat1[row][k] * mat2[k][col];
    }
}

int main() {
    int main() {
    int a[N][N] = {
        {1, 3, 2, 5},
        {4, 8, 9, 7},
       {13, 11, 15, 17},
        {17, 14, 19, 12}
    };
    
    int b[N][N] = {
        {1, 0, 0, 1},
        {0, 1, 1, 0},
        {0, 1, 1, 0},
        {1, 0, 0, 1}
    };

    int hasil[N][N] = {0};

    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            pid_t pid = fork();
            if (pid == 0) {

                baskom(mat1, mat2, hasil, i, j);
                printf("Proses anak untuk elemen [%d][%d] selesai\n", i, j);
                _exit(0);
            }
        }
    }


    while (wait(NULL) > 0);


    printf("Hasil Perkalian Matriks :\n");
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            printf("%d ", hasil[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```

![App Screenshot](assets/9.png)
![App Screenshot](assets/10.png)


**OUTPUT :**
![App Screenshot](assets/8.png)

```
analisa :
Progam tersebut untuk mengalika dua matriks 4x4
dengan menggunakan proses
anak untuk menghitung pada setiap elemen hal ini menggunakan
fungsi fork()
```

Visualisasi Program

```
Proses Induk
│
├─> Fork Proses Anak 1 (untuk elemen [0][0])
│   └─ Hitung elemen [0][0] --> Keluar
│
├─> Fork Proses Anak 2 (untuk elemen [0][1])
│   └─ Hitung elemen [0][1] --> Keluar
│
...
│
└─> Fork Proses Anak 16 (untuk elemen [3][3])
    └─ Hitung elemen [3][3] --> Keluar
```
