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

 ## 2.	Implementasi Threading
 Java Fork/Join Framework (SumTask.java)
 /**
 * Fork/join parallelism in Java
 *
 * Figure 4.18
 *
 * @author Gagne, Galvin, Silberschatz
 * Operating System Concepts  - Tenth Edition
 * Copyright John Wiley & Sons - 2018
  
 * /  import java.util.concurrent.*;
   public class SumTask extends RecursiveTask<Integer>
   {     static final int SIZE = 10000;
   static final int THRESHOLD = 1000;
   private int begin;
   private int end;
   private int[] array;
   public SumTask(int begin, int end, int[] array) {
   this.begin = begin;
   this.end = end;
   this.array = array;
   }
   protected Integer compute() {
   if (end - begin < THRESHOLD) {
   // conquer stage
   int sum = 0;
   for (int i = begin; i <= end; i++)
   sum += array[i];
   return sum;
   }
   else {
   // divide stage 
   int mid = begin + (end - begin) / 2;
   SumTask leftTask = new SumTask(begin, mid, array);
   SumTask rightTask = new SumTask(mid + 1, end, array);              leftTask.fork();
   rightTask.fork();
   return rightTask.join() + leftTask.join();
   }
   }
   public static void main(String[] args) {
   ForkJoinPool pool = new ForkJoinPool();
   int[] array = new int[SIZE];
   // create SIZE random integers between 0 and 9
   java.util.Random rand = new java.util.Random();
   for (int i = 0; i < SIZE; i++) {
   array[i] = rand.nextInt(10);
   }
   // use fork-join parallelism to sum the array
   SumTask task = new SumTask(0, SIZE-1, array);
   int sum = pool.invoke(task);
   System.out.println("The sum is " + sum);
   }
   } 
 

