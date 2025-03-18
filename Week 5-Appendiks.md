1. Migrasi Fitur Sistem Operasi
•	Fitur yang awalnya hanya ada di sistem besar (seperti mainframe) akhirnya diadopsi oleh sistem yang lebih kecil (seperti mikrokomputer dan perangkat genggam).
•	Contoh: MULTICS, sistem operasi yang dikembangkan pada 1960-an, memperkenalkan konsep seperti proteksi memori dan sistem file hierarkis yang kemudian diadopsi oleh sistem modern seperti UNIX.
________________________________________
2. Sistem Komputer Awal
•	Komputer pertama (seperti Manchester Mark 1, 1949) dioperasikan secara manual oleh programmer melalui konsol.
•	Batch Systems: Sistem awal menggunakan resident monitor untuk mengotomatisasi urutan pekerjaan (jobs) dan mengurangi waktu setup.
•	Spooling: Teknik yang memungkinkan overlap antara I/O dan komputasi, meningkatkan utilisasi CPU.
________________________________________
3. Sistem Operasi yang Berpengaruh
Atlas (1950-1960an)
•	Spooling: Memungkinkan penjadwalan pekerjaan berdasarkan ketersediaan perangkat I/O.
•	Manajemen Memori: Menggunakan demand paging dan algoritma penggantian halaman yang canggih.
XDS-940 (1960an)
•	Time-Sharing: Sistem pertama yang mendukung time-sharing, memungkinkan beberapa pengguna berinteraksi dengan sistem secara bersamaan.
•	Paging: Digunakan untuk relokasi memori, bukan demand paging.
THE (1960an)
•	Layered Design: Sistem operasi dirancang sebagai lapisan-lapisan yang terstruktur.
•	Deadlock Control: Menggunakan algoritma banker untuk menghindari deadlock.
RC 4000 (1960an)
•	Kernel: Dirancang sebagai kernel yang dapat digunakan untuk membangun sistem operasi lengkap.
•	Komunikasi Antar Proses: Menggunakan sistem pesan untuk komunikasi dan sinkronisasi.
CTSS (1961)
•	Time-Sharing: Sistem time-sharing pertama yang sukses, memungkinkan interaksi pengguna secara real-time.
•	Multilevel Feedback Queue: Algoritma penjadwalan CPU yang canggih.
MULTICS (1965-1970)
•	Time-Sharing Utility: Dirancang sebagai sistem time-sharing besar dengan sistem file hierarkis.
•	Segmented-Paged Memory: Menggunakan segmentasi dan paging untuk manajemen memori.
IBM OS/360 (1960an)
•	Family of Computers: Dirancang untuk berbagai jenis komputer, dari bisnis kecil hingga ilmiah besar.
•	Virtual Memory: Ditambahkan dengan arsitektur IBM/370.
________________________________________
4. Sistem Operasi Modern Awal
CP/M dan MS-DOS (1970-1980an)
•	CP/M: Sistem operasi awal untuk mikrokomputer 8-bit.
•	MS-DOS: Dikembangkan untuk IBM PC, menjadi sistem operasi dominan untuk PC.
Macintosh dan Windows (1980an)
•	Macintosh: Memperkenalkan GUI (Graphical User Interface) untuk pengguna rumahan.
•	Windows: Menjadi sistem operasi dominan untuk PC, bersaing dengan Mac OS.
Mach (1980an)
•	Microkernel: Dirancang untuk mendukung berbagai model memori dan komputasi paralel.
•	Kompatibilitas dengan UNIX: Mach menjadi dasar untuk sistem operasi modern seperti macOS dan iOS.
________________________________________
5. Sistem Berbasis Kemampuan (Capability-Based Systems)
Hydra
•	Capability-Based Protection: Sistem proteksi yang fleksibel, memungkinkan pengguna mendefinisikan hak akses sendiri.
•	Rights Amplification: Memungkinkan prosedur tertentu untuk mendapatkan hak akses tambahan sementara.
Cambridge CAP
•	Data dan Software Capabilities: Menggunakan dua jenis kemampuan untuk proteksi objek.
•	Protected Procedures: Prosedur yang dilindungi dapat menginterpretasikan kemampuan software.
________________________________________
6. Sistem Lain yang Berpengaruh
•	MCP (Burroughs): Sistem operasi pertama yang ditulis dalam bahasa pemrograman sistem.
•	SCOPE (CDC 6600): Sistem multi-CPU dengan desain koordinasi proses yang baik.
________________________________________
7. Kesimpulan
•	Evolusi Sistem Operasi: Dari sistem batch sederhana hingga sistem time-sharing dan GUI modern.
•	Pengaruh Sistem Awal: Banyak konsep dari sistem awal (seperti MULTICS, THE, dan Mach) masih digunakan dalam sistem operasi modern.
•	Tren Masa Depan: Sistem operasi terus berkembang dengan fitur baru, dukungan hardware, dan peningkatan usability.
