# SISTEM OPERASI
## Minggu ke-8 : Selasa, 6 Mei 2025
 
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
# Tugas Soal 5.17-5.18 S10-Chapter-05

## SOAL
5.17 Diberikan set proses berikut, dengan panjang CPU burst dalam milidetik:

Proses	Waktu Burst	Prioritas
P1	5	4
P2	3	1
P3	1	2
P4	7	2
P5	4	3

Proses-proses tersebut diasumsikan tiba dalam urutan P1, P2, P3, P4, P5, pada waktu 0.

a. Gambar empat Gantt chart yang menggambarkan pelaksanaan proses-proses ini menggunakan algoritma penjadwalan berikut: FCFS, SJF, prioritas non-preemptive (angka prioritas yang lebih besar menunjukkan prioritas yang lebih tinggi), dan RR (quantum = 2).

b. Berapakah waktu turnaround untuk setiap proses pada masing-masing algoritma penjadwalan di bagian a?

c. Berapakah waktu tunggu untuk setiap proses pada masing-masing algoritma penjadwalan di bagian a?

d. Algoritma mana yang menghasilkan waktu tunggu rata-rata terendah (untuk semua proses)?

5.18 Proses-proses berikut sedang dijadwalkan menggunakan algoritma penjadwalan prioritas preemptive berbasis round-robin.

Proses	Prioritas	Waktu Burst	Kedatangan
P1	8	15	0
P2	3	20	0
P3	4	20	20
P4	4	20	25
P5	5	5	45
P6	5	15	55

Setiap proses diberikan prioritas numerik, dengan angka yang lebih tinggi menunjukkan prioritas yang lebih tinggi. Penjadwal akan mengeksekusi proses dengan prioritas tertinggi. Untuk proses dengan prioritas yang sama, penjadwal round-robin dengan quantum waktu 10 unit akan digunakan. Jika sebuah proses diganggu oleh proses dengan prioritas lebih tinggi, proses yang diganggu akan dilanjutkan setelah proses dengan prioritas lebih tinggi selesai.

a. Gambarkan urutan proses menggunakan Gantt chart.

b. Berapakah waktu turnaround untuk setiap proses?

c. Berapakah waktu tunggu untuk setiap proses?


## JAWABAN
5.17
a. Gantt Chart untuk empat algoritma penjadwalan:
    1.	FCFS (First Come, First Serve):
    o	Proses dijalankan berdasarkan urutan kedatangannya.
    o	Urutan eksekusi: P1 → P2 → P3 → P4 → P5
    o	Gantt Chart:
    | P1 | P2 | P3 | P4 | P5 |
    0    5    8    9    16   20
    2.	SJF (Shortest Job First):
    •	Proses dijalankan berdasarkan waktu burst terpendek.
    •	Urutan eksekusi: P3 → P2 → P5 → P1 → P4
    •	Gantt Chart:
    | P3 | P2 | P5 | P1 | P4 |
    0    1    4    8    13   20
    3.	Non-preemptive Priority (Semakin besar angka prioritas, semakin tinggi prioritasnya):
    •	Proses dijalankan berdasarkan prioritas yang lebih tinggi.
    •	Urutan eksekusi: P1 → P5 → P4 → P3 → P2
    •	Gantt Chart:
    | P1 | P5 | P4 | P3 | P2 |
    0    5    9    16   17   20
    4.	Round Robin (RR, Quantum = 2):
    •	Setiap proses diberi waktu CPU sebanyak 2ms secara bergilir.
    •	Urutan eksekusi: P1 → P2 → P3 → P4 → P5 (repeat cycle hingga selesai)
    •	Gantt Chart:
    | P1 | P2 | P3 | P4 | P5 | P1 | P4 | P5 | P1 | P4 | P5 |
    0    2    4    5    7    9    11   13   15   17   19
b. Waktu Turnaround:
    Turnaround time = Waktu selesai - Waktu kedatangan
    1.	FCFS:
    o	P1: 5 (selesai) - 0 (kedatangan) = 5
    o	P2: 8 - 0 = 8
    o	P3: 9 - 0 = 9
    o	P4: 16 - 0 = 16
    o	P5: 20 - 0 = 20
    2.	SJF:
    o	P3: 1 - 0 = 1
    o	P2: 4 - 0 = 4
    o	P5: 8 - 0 = 8
    o	P1: 13 - 0 = 13
    o	P4: 20 - 0 = 20
    3.	Non-preemptive Priority:
    o	P1: 5 - 0 = 5
    o	P5: 9 - 0 = 9
    o	P4: 16 - 0 = 16
    o	P3: 17 - 0 = 17
    o	P2: 20 - 0 = 20
    4.	Round Robin:
    o	P1: 15 - 0 = 15
    o	P2: 20 - 0 = 20
    o	P3: 19 - 0 = 19
    o	P4: 20 - 0 = 20
    o	P5: 20 - 0 = 20
c. Waktu Tunggu:
    Waiting time = Turnaround time - Burst time
    1.	FCFS:
    o	P1: 5 - 5 = 0
    o	P2: 8 - 3 = 5
    o	P3: 9 - 1 = 8
    o	P4: 16 - 7 = 9
    o	P5: 20 - 4 = 16
    2.	SJF:
    o	P3: 1 - 1 = 0
    o	P2: 4 - 3 = 1
    o	P5: 8 - 4 = 4
    o	P1: 13 - 5 = 8
    o	P4: 20 - 7 = 13
    3.	Non-preemptive Priority:
    o	P1: 5 - 5 = 0
    o	P5: 9 - 4 = 5
    o	P4: 16 - 7 = 9
    o	P3: 17 - 1 = 16
    o	P2: 20 - 3 = 17
    4.	Round Robin:
    o	P1: 15 - 5 = 10
    o	P2: 20 - 3 = 17
    o	P3: 19 - 1 = 18
    o	P4: 20 - 7 = 13
    o	P5: 20 - 4 = 16
d. Algoritma yang Menghasilkan Waktu Tunggu Rata-rata Terendah:
Dari hasil perhitungan waktu tunggu, SJF menghasilkan waktu tunggu rata-rata terendah.

5.18
a. Gambarkan urutan proses menggunakan Gantt chart
   Pada round-robin dengan prioritas preemptive (quantum = 10), proses akan dieksekusi bergilir berdasarkan prioritas. Proses dengan prioritas lebih tinggi akan dieksekusi lebih dulu, dan jika ada proses dengan prioritas yang sama, sistem akan bergiliran menjalankannya.
   
   Urutan proses berdasarkan prioritas tertinggi:
   
   o P1 (Prioritas 8) akan dieksekusi terlebih dahulu, karena memiliki prioritas tertinggi.
   
   o Setelah P1 selesai atau di-preempt oleh proses dengan prioritas lebih tinggi, proses berikutnya adalah P5 dan P6 (prioritas 5).
   
   o Proses P3 dan P4 memiliki prioritas yang lebih rendah, tetapi mereka akan mulai berjalan setelah P2 (prioritas 3) selesai.
   
   Berikut adalah Gantt chart dengan quantum waktu 10 untuk proses:
   | P1 | P2 | P1 | P5 | P1 | P3 | P4 | P5 | P6 |
   0    10   20   30   40   50   60   70   80

b. Waktu Turnaround
   Waktu turnaround adalah waktu total yang diperlukan dari saat proses mulai hingga selesai. Perhitungannya adalah:
   Turnaround Time = Waktu Selesai - Waktu Kedatangan
   
   Berikut adalah perhitungan waktu turnaround untuk setiap proses:
   
   o P1: Waktu selesai = 50, Waktu kedatangan = 0 → Turnaround = 50 - 0 = 50
   
   o P2: Waktu selesai = 30, Waktu kedatangan = 0 → Turnaround = 30 - 0 = 30
   
   o P3: Waktu selesai = 60, Waktu kedatangan = 20 → Turnaround = 60 - 20 = 40
   
   o P4: Waktu selesai = 70, Waktu kedatangan = 25 → Turnaround = 70 - 25 = 45
   
   o P5: Waktu selesai = 75, Waktu kedatangan = 45 → Turnaround = 75 - 45 = 30
   
   o P6: Waktu selesai = 85, Waktu kedatangan = 55 → Turnaround = 85 - 55 = 30

c. Waktu Tunggu
   Waktu tunggu adalah waktu total yang dihabiskan oleh proses dalam antrian sebelum dieksekusi. Perhitungannya adalah:
   Waiting Time = Turnaround Time - Burst Time
   
   Berikut adalah perhitungan waktu tunggu untuk setiap proses:
   
   o P1: Turnaround = 50, Burst Time = 15 → Waiting Time = 50 - 15 = 35
   
   o P2: Turnaround = 30, Burst Time = 20 → Waiting Time = 30 - 20 = 10
   
   o P3: Turnaround = 40, Burst Time = 20 → Waiting Time = 40 - 20 = 20
   
   o P4: Turnaround = 45, Burst Time = 20 → Waiting Time = 45 - 20 = 25
   
   o P5: Turnaround = 30, Burst Time = 5 → Waiting Time = 30 - 5 = 25
   
   o P6: Turnaround = 30, Burst Time = 15 → Waiting Time = 30 - 15 = 15
   
d. Algoritma Mana yang Menghasilkan Waktu Tunggu Rata-rata Terendah
   Untuk menghitung rata-rata waktu tunggu, kita jumlahkan semua waktu tunggu dan bagi dengan jumlah proses:
   Average Waiting Time = (35 + 10 + 20 + 25 + 25 + 15) / 6 = 130 / 6 ≈ 21.67
   
   Jadi, algoritma round-robin berbasis prioritas preemptive ini menghasilkan waktu tunggu rata-rata sekitar 21.67.


## Kesimpulan:
Gantt Chart memberikan gambaran visual urutan eksekusi proses.

Waktu Turnaround dihitung berdasarkan selisih antara waktu selesai dan waktu kedatangan.

Waktu Tunggu dihitung berdasarkan selisih antara waktu turnaround dan waktu burst.

Rata-rata Waktu Tunggu memberikan gambaran efektivitas algoritma.
