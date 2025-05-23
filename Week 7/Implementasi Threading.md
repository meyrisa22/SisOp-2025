## 2.	Implementasi Threading

a. Java Fork/Join Framework (SumTask.java)
Penjelasan Fork/Join Parallelism pada SumTask.java
Kode SumTask.java menggunakan Fork/Join Framework untuk menerapkan multithreading dalam menghitung jumlah seluruh elemen dari sebuah array. Pendekatan ini membagi tugas besar menjadi beberapa tugas kecil (divide and conquer), lalu menjalankannya secara paralel menggunakan thread.
Tahapan Kerja:
Divide:  Jika panjang array dari indeks begin ke end lebih besar dari THRESHOLD (1000), tugas dibagi dua: bagian kiri (begin ke mid) dan kanan (mid+1 ke end). Dua sub-tugas baru dibuat: leftTask dan rightTask.
Fork:  Kedua tugas tersebut dijalankan secara paralel dengan memanggil .fork(). Ini memberi tahu ForkJoinPool agar mengeksekusi sub-task di thread terpisah.
Join:  Setelah fork, hasil sub-tugas diambil dengan .join() dan dijumlahkan untuk memberikan hasil akhir.
Conquer:  Jika ukuran array lebih kecil dari THRESHOLD, penjumlahan dilakukan secara langsung (tanpa pembagian lebih lanjut).
Konteks Threading:  Kelas SumTask mewarisi RecursiveTask<Integer> — artinya, ini adalah tugas yang akan mengembalikan nilai bertipe Integer.
ForkJoinPool secara otomatis mengatur thread pool dan membagi tugas ke berbagai worker thread di balik layar.
Kesimpulan: Dengan ForkJoinPool, program ini dapat memanfaatkan banyak inti CPU untuk memproses array besar secara efisien. Ini adalah bentuk multithreaded programming tingkat tinggi yang mudah dikelola dan scalable di Java. 

b. POSIX Threading di Linux (thrd-posix.c) 
Penjelasan Penerapan Thread di Linux (thrd-posix.c)
Kode ini merupakan contoh sederhana penggunaan POSIX thread untuk menjalankan operasi penjumlahan angka dari 1 hingga n di dalam thread terpisah. Tujuannya adalah untuk menjalankan fungsi tertentu di thread yang berbeda dari thread utama (main thread).
Struktur Program:
Deklarasi Thread & Atribut:  pthread_t tid; digunakan untuk menyimpan ID dari thread yang akan dibuat. pthread_attr_t attr; menyimpan atribut default dari thread.
Validasi Input:  Program menerima satu argumen berupa angka. Dicek apakah angka valid (bukan negatif), lalu dikonversi ke integer.
Inisialisasi & Pembuatan Thread:  pthread_attr_init(&attr); mengambil atribut default. pthread_create(&tid, &attr, runner, argv[1]); membuat thread baru yang menjalankan fungsi runner().
Sinkronisasi:  pthread_join(tid, NULL); menunggu sampai thread selesai dieksekusi sebelum melanjutkan ke bagian printf.
Fungsi runner():  Fungsi inilah yang dijalankan dalam thread terpisah. Mengonversi parameter menjadi int, lalu menjumlahkan bilangan dari 1 sampai n dan menyimpannya di variabel global sum.
Konteks Threading:  Ini adalah multithreading manual: programmer harus menangani atribut, membuat thread, dan menyinkronkannya dengan join.
Variabel sum bersifat shared memory, artinya dapat diakses oleh thread manapun — karena itu, dalam kasus yang kompleks perlu proteksi (misalnya mutex), tapi tidak diperlukan di contoh ini karena hanya satu thread bekerja dengan sum.
Kesimpulan: Program ini menunjukkan bagaimana thread dapat digunakan untuk menjalankan tugas tambahan secara paralel dengan thread utama, meskipun dalam contoh ini thread utama hanya menunggu hasil dari thread runner(). Ini adalah dasar dari multithreading berbasis POSIX standard di Linux.  

c. Win32 Threading di Windows (thrd-win32.c) 
Penjelasan Penerapan Thread di Microsoft Windows (thrd-win32.c)
Kode ini menunjukkan bagaimana sistem operasi Windows menangani pembuatan thread menggunakan API khusus Windows, yaitu CreateThread(). Fungsinya mirip dengan pthread_create() di Linux, namun dengan sintaks dan pendekatan yang berbeda.
Struktur Program:
Deklarasi Variabel:
DWORD Sum; adalah variabel global yang menyimpan hasil penjumlahan, bisa diakses oleh semua thread.
DWORD ThreadId; menyimpan ID thread yang dibuat.
HANDLE ThreadHandle; digunakan untuk mengelola thread yang sedang berjalan.
int Param; menyimpan batas atas penjumlahan.
Validasi Input:  Program menerima satu parameter input dari command line. Dicek apakah input valid dan ≥ 0.
Membuat Thread:  CreateThread(NULL, 0, Summation, &Param, 0, &ThreadId); membuat sebuah thread baru. Summation() adalah fungsi yang akan dijalankan secara paralel oleh thread ini. Parameter &Param dikirim ke fungsi Summation() sebagai nilai batas penjumlahan.
Sinkronisasi dan Output:  WaitForSingleObject(ThreadHandle, INFINITE); memastikan thread utama menunggu hingga thread Summation selesai dieksekusi. Setelah thread selesai, CloseHandle(ThreadHandle); menutup handle untuk melepaskan resource. Hasil Sum ditampilkan ke layar.
Fungsi Thread Summation():  Fungsi ini akan dijalankan oleh thread baru. Melakukan penjumlahan dari 0 sampai Upper dan menyimpan hasilnya di variabel Sum.
Konteks Threading:  Pendekatan Windows menggunakan CreateThread() dari Windows API, berbeda dari POSIX. Fungsi Summation() bertipe DWORD WINAPI dan menerima parameter bertipe PVOID (generic pointer), sesuai konvensi thread di Windows. Tidak digunakan mutex atau synchronization primitive karena hanya satu thread menulis ke Sum, dan tidak ada race condition.
Kesimpulan: Program ini adalah contoh dasar bagaimana menjalankan sebuah fungsi dalam thread terpisah di Windows. Sistem operasi Windows menyediakan kontrol lebih rendah (low-level) melalui CreateThread(), memungkinkan pemrograman multithread dengan cara manual, dibandingkan pendekatan high-level seperti di Java.
