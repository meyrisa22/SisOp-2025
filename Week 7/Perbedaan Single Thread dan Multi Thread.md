## 1.	Jelaskan dalam 2 paragraph disertai dengan gambar tentang konsep single thread dan multithread ! ada pada materi ch4.
Jawab : 

a.	Single Thread adalah model eksekusi di mana sebuah proses hanya memiliki satu alur eksekusi (thread) yang menjalankan instruksi secara berurutan. Dalam single thread, hanya satu tugas yang dapat diproses pada satu waktu, sehingga jika terjadi blocking (misalnya menunggu I/O), seluruh proses akan terhenti hingga tugas tersebut selesai. Contohnya adalah program sederhana yang membaca input, memprosesnya, lalu menampilkan output tanpa kemampuan untuk menangani tugas lain secara bersamaan. Single thread cocok untuk aplikasi yang tidak membutuhkan paralelisme, seperti kalkulator atau skrip kecil.

Contoh ilustrasi :
[Proses] → [Thread 1] → Tugas 1 → Tugas 2 → Tugas 3

 

b.	Multithread memungkinkan sebuah proses memiliki beberapa thread yang berjalan secara bersamaan dalam ruang alamat memori yang sama. Setiap thread dapat mengeksekusi tugas berbeda secara independen, sehingga meningkatkan responsivitas dan efisiensi. Misalnya, dalam aplikasi web browser, satu thread dapat menangani antarmuka pengguna, sementara thread lain mengunduh data atau memproses konten. Multithread sangat bermanfaat dalam sistem multicore karena memungkinkan paralelisme sejati. Namun, tantangannya adalah sinkronisasi dan manajemen sumber daya bersama untuk menghindari race condition atau deadlock.

Contoh ilustrasi :
[Proses] →	[Thread 1] → Tugas 1  
            [Thread 2] → Tugas 2  
            [Thread 3] → Tugas 3

