# SISTEM OPERASI
## Minggu ke-4 : Selasa, 11 Maret 2025
 
# Oleh :
## Mey Risa Handayani
## D3 Teknik Informatika (A) PENS LA
## NRP 3124521011

# Dosen Pengampu :
## Dr Ferry Astika Saputra ST, M.Sc
## NIP : 197708232001121002

# POLITEKNIK ELEKTRONIKA NEGERI SURABAYA
# PSDKU LAMONGAN
# TAHUN 2025

1. Apa yang Dilakukan Sistem Operasi?
   Sistem Operasi berperan sebagai pengelola sumber daya (resource allocator) dan program kontrol yang mengatur penggunaan hardware secara efisien.

   Tujuan:
   Pengguna: Kemudahan penggunaan dan kinerja yang baik.
   Sistem Terbagi (Shared Computer): Menjaga kepuasan semua pengguna.
   Perangkat Mobile: Optimalisasi penggunaan baterai dan antarmuka pengguna (touch screen, voice recognition).
   Embedded Systems: Berjalan tanpa intervensi pengguna.

2. Definisi Sistem Operasi
   Sistem Operasi adalah program yang selalu berjalan di komputer (kernel) dan mengelola sumber daya sistem.
   
   Komponen:
   System Program: Program yang disertakan dengan OS tetapi bukan bagian dari kernel.
   Application Program: Program yang tidak terkait dengan OS.
   Middleware: Framework yang menyediakan layanan tambahan untuk pengembang aplikasi (database, multimedia, dll).

3. Organisasi Sistem Komputer
   Komponen Utama:
   Hardware: CPU, memori, perangkat I/O.
   Operating System: Mengontrol dan mengkoordinasikan penggunaan hardware.
   Application Programs: Program yang menggunakan sumber daya sistem.
   Users: Pengguna sistem (manusia, mesin, komputer lain).

4. Operasi Sistem Komputer
   I/O Devices dan CPU dapat berjalan secara bersamaan.
   
   Device Controller: Mengelola perangkat I/O dan memiliki buffer lokal.
   Interrupt: Mekanisme yang menginformasikan CPU bahwa operasi I/O telah selesai.

5. Manajemen Penyimpanan
   Hierarki Penyimpanan:
   Primary Storage: Register, cache, memori utama.
   Secondary Storage: Disk, SSD.
   Tertiary Storage: Tape, optical disk.
   Caching: Menyalin data ke penyimpanan yang lebih cepat untuk meningkatkan kinerja.

6. Arsitektur Sistem Komputer
   Single Processor: Satu CPU umum.
   Multiprocessor: Beberapa CPU yang bekerja bersama (parallel systems).
   Keuntungan: Peningkatan throughput, ekonomi skala, peningkatan keandalan.
   Jenis: Asymmetric Multiprocessing (setiap processor memiliki tugas khusus) dan Symmetric Multiprocessing (setiap processor melakukan semua tugas).

7. Operasi Sistem Operasi
   Bootstrap Program: Program sederhana yang memuat kernel.
   Interrupt Driven: OS merespons interrupt dari hardware atau software (system call).
   Dual-mode Operation: Mode user dan kernel untuk melindungi sistem.
   Mode Bit: Membedakan antara kode user dan kernel.

8. Manajemen Proses
   Proses: Program yang sedang dieksekusi.
   
   Aktivitas Manajemen Proses:
   Membuat dan menghapus proses.
   Menangguhkan dan melanjutkan proses.
   Sinkronisasi dan komunikasi proses.
   Penanganan deadlock.

9. Manajemen Memori
   Memori: Menyimpan instruksi dan data yang diperlukan untuk eksekusi program.
   
   Aktivitas Manajemen Memori:
   Melacak penggunaan memori.
   Memutuskan proses mana yang akan dimuat ke memori.
   Mengalokasikan dan membebaskan memori.

10. Manajemen File dan Penyimpanan Massal
    File-System Management: Menyediakan tampilan logis penyimpanan.
    Aktivitas: Membuat dan menghapus file, mengontrol akses, backup.
    Mass-Storage Management: Mengelola disk dan penyimpanan lain untuk memastikan kinerja optimal.

11. Virtualisasi
    Virtualisasi: Memungkinkan OS menjalankan aplikasi dalam OS lain.
    Emulasi: Ketika CPU sumber berbeda dengan target.
    Virtual Machine Manager (VMM): Menyediakan layanan virtualisasi.

13. Sistem Terdistribusi
    Sistem Terdistribusi: Kumpulan sistem yang terhubung melalui jaringan.
    Network Operating System: Menyediakan fitur komunikasi antar sistem.
    Clustered Systems: Beberapa sistem bekerja bersama untuk meningkatkan ketersediaan dan kinerja.

13. Lingkungan Komputasi Modern
    Mobile Computing: Smartphone dan tablet dengan fitur tambahan (GPS, gyroscope).
    Cloud Computing: Menyediakan komputasi, penyimpanan, dan aplikasi sebagai layanan.
    Jenis: Public cloud, private cloud, hybrid cloud, SaaS, PaaS, IaaS.
    Real-Time Embedded Systems: Sistem dengan batasan waktu yang ketat.

14. Sistem Operasi Open-Source
    Open-Source: Sistem operasi yang tersedia dalam format source-code.
    Contoh: GNU/Linux, BSD UNIX.
    Keuntungan: Memungkinkan studi dan pengembangan OS secara mendalam.
