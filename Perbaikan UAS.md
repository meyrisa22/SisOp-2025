SISTEM OPERASI
PERBAIKAN UAS
Minggu ke-15 : Selasa, 3 Juni 2025
 
Oleh :
Mey Risa Handayani
D3 Teknik Informatika (A) PENS LA
NRP 3124521011

Dosen Pengampu :
Dr Ferry Astika Saputra ST, M.Sc
NIP : 197708232001121002


POLITEKNIK ELEKTRONIKA NEGERI SURABAYA
PSDKU LAMONGAN
TAHUN 2025


1.	Jelaskan (disertai dengan gambar) apa yang dimasud dengan short-term scheduler, medium-term scheduler dan long-term scheduler pada penjadwalan CPU !
Jawab :
1)	Long-Term Scheduler (Penjadwal Jangka Panjang) Long-Term Scheduler (atau sering disebut Job Scheduler) bertanggung jawab untuk memilih proses dari kumpulan program (job pool) di penyimpanan sekunder (hard disk) dan memuatnya ke memori utama (RAM) untuk eksekusi. Tugas utamanya adalah mengontrol tingkat multiprogramming, yaitu jumlah proses yang ada di memori utama pada satu waktu.  Fungsi utama: Memilih proses yang akan masuk ke antrian "siap" (ready queue) di memori utama. Kecepatan: Paling lambat di antara ketiga jenis penjadwal karena jarang beroperasi (hanya ketika proses baru masuk atau selesai). Tujuan: Menciptakan campuran yang baik antara proses yang terikat I/O (lebih banyak waktu di I/O) dan proses yang terikat CPU (lebih banyak waktu di CPU) untuk menjaga CPU tetap sibuk. Contoh: Ketika Anda membuka banyak aplikasi sekaligus, long-term scheduler menentukan aplikasi mana yang akan dimuat ke RAM.

2)	Medium-Term Scheduler (Penjadwal Jangka Menengah) Medium-Term Scheduler adalah bagian dari proses swapping. Ini bertanggung jawab untuk menghapus proses dari memori utama (swapping out) dan kemudian dapat memasukkannya kembali (swapping in). Swapping terjadi ketika memori utama menjadi penuh, atau ketika sebuah proses menjadi "diblokir" (misalnya, menunggu I/O) dan sistem operasi ingin mengosongkan memori untuk proses lain yang siap berjalan.  Fungsi utama: Menangguhkan dan melanjutkan proses dengan memindahkannya antara memori utama dan penyimpanan sekunder. Ini mengurangi tingkat multiprogramming untuk sementara. Kecepatan: Lebih cepat dari long-term scheduler, tetapi lebih lambat dari short-term scheduler. Tujuan: Meningkatkan efisiensi memori dan mengoptimalkan campuran proses, terutama dalam sistem berbagi waktu (time-sharing systems). Contoh: Ketika memori komputer hampir penuh, sistem operasi mungkin "menukar" (swap out) beberapa aplikasi yang tidak aktif ke hard disk untuk membebaskan RAM.

3)	Short-Term Scheduler (Penjadwal Jangka Pendek) Short-Term Scheduler (atau sering disebut CPU Scheduler atau Dispatcher) adalah penjadwal yang paling sering beroperasi dan paling cepat. Tugas utamanya adalah memilih salah satu proses dari antrian "siap" di memori utama dan mengalokasikan CPU kepadanya.  Fungsi utama: Memilih proses berikutnya yang akan dieksekusi oleh CPU dari antrian proses yang siap. Kecepatan: Paling cepat di antara ketiganya karena keputusan harus dibuat sangat sering (setiap milidetik atau kurang). Tujuan: Memaksimalkan penggunaan CPU dan memberikan respons yang cepat kepada pengguna. Ini bekerja dengan algoritma penjadwalan CPU (misalnya, First-Come, First-Served, Shortest Job First, Round Robin, Priority Scheduling). Contoh: Ketika Anda mengetik di keyboard, short-term scheduler memastikan bahwa proses penanganan input keyboard segera mendapatkan waktu CPU.

+----------------+       +-------------------+       +-------------------+       +-------------+       +-------------+
| Job Pool       | ----> | Long-Term         | ----> | Ready Queue       | ----> | Short-Term  | ----> |             |
| (Secondary     |       | Scheduler         |       | (Main Memory)     |       | Scheduler   |       |     CPU     |
| Storage)       |       | (Job Admission)   |       |                   |       | (CPU        |       |             |
+----------------+       +-------------------+       +-------------------+       | Dispatcher) |       +-------------+
                                  ^   |                                          +-------------+              |
                                  |   |                                                                       |
                                  |   |                                                                       |
                                  |   v                                                                       v
                             +-------------------+                                                      +-------------+
                             | Medium-Term       | <--------------------------------------------------- | Waiting/    |
                             | Scheduler         |                                                      | Suspended   |
                             | (Swapping)        |                                                      | State       |
                             +-------------------+                                                      +-------------+

2.	Proses Burst time P1 7 P2 4 P3 1 P4 4 P5 5 P6 3 Diketahui arrival time dari P1, P2, P3,P4, dan P5, P6 adalah 0,3,6,7,9,10,12 dengan menggunakan algoritma SJF pre-emptive dan Round Robin dengan QT=4, bandingkan average waiting time, turn aroud time, completion time dan jumlah context switchingnya.
Jawab :
1.	Shortest Job First (SJF) Preemptive
•	Proses dan Burst Time P1: 7 P2: 4 P3: 1 P4: 4 P5: 5 P6: 3
•	Arrival Time: P1: 0 P2: 3 P3: 6 P4: 7 P5: 9 P6: 10 12
•	Gantt Chart untuk SJF Pre-emptive:
| P1 | P2 | P3 | P1 | P4 | P5 | P6 | P1 |
0     3     4     5     7     9    12   15
•	Completion Time (CT):
P1: 15 P2: 5 P3: 4 P4: 11
P5: 15 P6: 12
•	Average WT: (17 + 1 + 0 + 0 + 5 + 1) / 6 = 24 / 6 = 4
•	Average TAT: (24 + 5 + 1 + 4 + 10 + 4) / 6 = 48 / 6 = 8
•	Process	AT	BT	CT	TAT	WT P1		0	7	24	24	17 P2		3	4	8	5	1 P3		6	1	7	1	0 P4		7	4	11	4	0 P5		9	5	19	10	5 P6		10	3	14	4	1
•	Jumlah Context Switching:  Context switching terjadi setiap kali proses berpindah dari satu proses ke proses lain. Dalam Gantt Chart di atas, terdapat 6 context switches.
2.	Round Robin
•	Gantt Chart untuk Round Robin:
| P1 | P2 | P3 | P1 | P4 | P5 | P6 | P1 | P5 |
0     4    8     9     11   12   15   19   20
•	Completion Time (CT): P1: 19 P2: 8 P3: 9 P4: 11 P5: 20 P6: 15
•	Average WT: (16 + 0 + 1 + 1 + 3 + 6) / 6 = 27 / 6 = 4.5
•	Average TAT: (23 + 4 + 2 + 5 + 8 + 9) / 6 = 51 / 6 = 8.5
•	Process	AT	BT	CT	TAT	WT P1		0	7	23	23	16 P2		3	4	7	4	0 P3		6	1	8	2	1 P4		7	4	12	5	1 P5		9	5	17	8	3 P6		10	3	19	9	6
•	Context switching terjadi setiap kali proses berpindah dari satu proses ke proses lain. Dalam Gantt Chart di atas, terdapat 7 context switches.
Berdasarkan perhitungan di atas:
•	SJF Pre-emptive memiliki Average Waiting Time, Average Turnaround Time, dan Average Completion Time yang lebih rendah dibandingkan Round Robin (QT=4). Ini sesuai dengan sifat SJF yang cenderung optimal dalam meminimalkan waktu tunggu dan turnaround karena selalu memprioritaskan proses terpendek.
•	Round Robin (QT=4) menghasilkan jumlah context switching yang sedikit lebih banyak dibandingkan SJF Pre-emptive (7 vs 6). Ini wajar karena Round Robin dirancang untuk memberikan responsivitas yang baik dengan bergantian antar proses, yang tentu saja melibatkan lebih banyak context switching.
Secara keseluruhan, untuk kasus ini, SJF Pre-emptive menunjukkan kinerja yang lebih baik dalam hal efisiensi waktu (waiting time, turnaround time, completion time). Namun, penting untuk diingat bahwa Round Robin lebih adil dalam pembagian waktu CPU kepada semua proses dan memberikan responsivitas yang lebih konsisten, yang mungkin lebih diinginkan dalam sistem interaktif.
