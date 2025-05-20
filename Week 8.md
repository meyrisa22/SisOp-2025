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
a. Gantt Chart:
•	Menggunakan algoritma round-robin (quantum = 10).
•	Proses dijalankan secara bergilir sesuai dengan waktu arrival dan prioritasnya.
b. Deskripsi Proses:
•	P1 akan dieksekusi terlebih dahulu karena prioritasnya lebih tinggi dibandingkan proses lainnya (prioritas 8).
•	Jika proses lebih rendah prioritasnya, proses tersebut akan digilir berdasarkan time quantum yang telah ditentukan (10 unit waktu).
