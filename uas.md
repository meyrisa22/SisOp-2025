uas
1. Algoritma SJF Preemptive
Detail Perhitungan Waktu:

Process	BT	CT	TAT = CT - Arrival Time	WT = TAT - BT
P3	1	8	8 - 6 = 2	2 - 1 = 1
P2	4	14	14 - 3 = 11	11 - 4 = 7
P4	4	17	17 - 7 = 10	10 - 4 = 6
P6	3	20	20 - 10 = 10	10 - 3 = 7
P5	5	22	22 - 9 = 13	13 - 5 = 8
P1	7	24	24 - 0 = 24	24 - 7 = 17

Tabel Proses:

Process	Burst Time (BT)
P1	7
P2	4
P3	1
P4	4
P5	5
P6	3

Gantt Chart:

Copy code
|  P3  |   P2   |   P4   |   P6   |   P5   |   P1   |
0      1        8       14       17       20       24
Average Turnaround Time (TAT):

𝑇
𝐴
𝑇
=
2
+
11
+
10
+
10
+
13
+
24
6
=
8.33
TAT= 
6
2+11+10+10+13+24
​
 =8.33
Average Waiting Time (WT):

𝑊
𝑇
=
1
+
7
+
6
+
7
+
8
+
17
6
=
7.5
WT= 
6
1+7+6+7+8+17
​
 =7.5
2. Algoritma Round Robin (QT=4)
Detail Perhitungan Waktu:

Process	BT	CT	TAT = CT - Arrival Time	WT = TAT - BT
P1	7	19	19 - 0 = 19	19 - 7 = 12
P2	4	18	18 - 3 = 15	15 - 4 = 11
P3	1	14	14 - 6 = 8	8 - 1 = 7
P4	4	24	24 - 7 = 17	17 - 4 = 13
P5	5	22	22 - 9 = 13	13 - 5 = 8
P6	3	23	23 - 10 = 13	13 - 3 = 10

Tabel Proses:

Process	Burst Time (BT)
P1	7
P2	4
P3	1
P4	4
P5	5
P6	3

Gantt Chart:

Copy code
|  P1  |   P2   |   P3   |   P4   |   P5   |   P1   |   P2   |   P4   |   P6   |   P5   |
0      4        8       9       13       17       19       23      24       27      30
Average Turnaround Time (TAT):

𝑇
𝐴
𝑇
=
19
+
15
+
8
+
17
+
13
+
13
6
=
13.5
TAT= 
6
19+15+8+17+13+13
​
 =13.5
Average Waiting Time (WT):

𝑊
𝑇
=
12
+
11
+
7
+
13
+
8
+
10
6
=
10.2
WT= 
6
12+11+7+13+8+10
​
 =10.2
Kesimpulan:
SJF Preemptive memiliki waktu tunggu rata-rata yang lebih rendah (7.5) dibandingkan dengan Round Robin (10.2).

SJF Preemptive juga memiliki waktu putar rata-rata (TAT) yang lebih efisien (8.33) dibandingkan dengan Round Robin (13.5).

Round Robin memiliki lebih banyak context switching karena pemrosesan berulang dan distribusi waktu yang adil, meskipun bisa meningkatkan fairness.
