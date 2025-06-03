## SISTEM OPERASI
# Minggu ke-15 : Selasa, 3 Juni 2025
 
# Oleh :
# Mey Risa Handayani
# D3 Teknik Informatika (A) PENS LA
# NRP 3124521011

# Dosen Pengampu :
# Dr Ferry Astika Saputra ST, M.Sc
# NIP : 197708232001121002

# POLITEKNIK ELEKTRONIKA NEGERI SURABAYA
# PSDKU LAMONGAN
# TAHUN 2025


# Penugasan
Mencari soal pada **practice exercise S10-Ch05** yang mencangkup algoritma shceduling ini: `SJF Scheduling Algorithm Without Arrival Time (Non-Preemptive)`, `SJF Scheduling Algorithm with Arrival Time (Non-Preemptive)`, & `SRTF (Shortest Remaining Time First) Scheduling Algorithm (Preemptive)`.

Cari 3 soal saja & apabila memungkinkan beri penjelasan logic dari flow program tersebut!
Jawab : Saya membuat ulang kode yang seperti di minggu lalu karena pada PPT `S10-Ch05` tidak relevan dengan perintah penugasan ini.

# Studi Kasus Lanjutan: Analisis Proses *Scheduling*

Pada bagian ini, kita akan membahas beberapa studi kasus dari soal buku sistem operasi (khususnya soal 5.3 sampai 5.5) dan menerapkannya pada algoritma penjadwalan CPU yang berbeda. Simulasi mencakup Gantt Chart, waktu tunggu (*waiting time*), dan waktu penyelesaian (*turnaround time*).

---

## ⚫ Soal 5.3

### Data Proses:

| Process | Arrival Time | Burst Time |
| ------- | ------------ | ---------- |
| P₁      | 0.0          | 8          |
| P₂      | 0.4          | 4          |
| P₃      | 1.0          | 1          |

Dari soal 5.3 ini, kita akan melakukan simulasi menggunakan 3 algoritma:

1. **SJF Non-Preemptive tanpa arrival time**
2. **SJF Non-Preemptive dengan arrival time**
3. **SRTF (Shortest Remaining Time First)**

Seperti pada kasus pertemuan sebelumnya.

---

## 1. SJF Non-Preemptive (Tanpa Arrival Time)

### Asumsi:

* Semua proses diasumsikan datang pada waktu 0.
* Pemilihan proses berdasarkan burst time terkecil terlebih dahulu.

### Urutan Eksekusi Berdasarkan Burst Time:

| Process | Burst Time |
| ------- | ---------- |
| P₃      | 1          |
| P₂      | 4          |
| P₁      | 8          |

### Gantt Chart:

```
| 0 |--P₃--| 1 |--P₂--| 5 |--P₁--| 13 |
```

### Perhitungan:

| Process | Waiting Time | Turnaround Time |
| ------- | ------------ | --------------- |
| P₃      | 0            | 1               |
| P₂      | 1            | 5               |
| P₁      | 5            | 13              |

**Rata-rata:**

* Waiting Time: (0 + 1 + 5) / 3 = **2.0**
* Turnaround Time: (1 + 5 + 13) / 3 = **6.33**

---

## 2. SJF Non-Preemptive (Dengan Arrival Time)

### Pertimbangan Arrival Time:

| Process | Arrival | Burst |
| ------- | ------- | ----- |
| P₁      | 0.0     | 8     |
| P₂      | 0.4     | 4     |
| P₃      | 1.0     | 1     |

### Gantt Chart:

```
| 0 |--P₁--| 8 |--P₃--| 9 |--P₂--| 13 |
```

### Perhitungan:

| Process | Arrival | Start | Waiting | Completion | Turnaround |
| ------- | ------- | ----- | ------- | ---------- | ---------- |
| P₁      | 0.0     | 0.0   | 0.0     | 8.0        | 8.0        |
| P₃      | 1.0     | 8.0   | 7.0     | 9.0        | 8.0        |
| P₂      | 0.4     | 9.0   | 8.6     | 13.0       | 12.6       |

**Rata-rata:**

* Waiting Time: (0 + 7 + 8.6) / 3 = **5.2**
* Turnaround Time: (8 + 8 + 12.6) / 3 = **9.53**

---

## 3. SRTF (Shortest Remaining Time First - Preemptive)

### Gantt Chart:

```
| 0.0 |--P₁--| 0.4 |--P₂--| 1.0 |--P₃--| 2.0 |--P₂--| 6.0 |--P₁--| 14.0 |
```

### Perhitungan:

| Process | Arrival | Completion | Turnaround | Waiting |
| ------- | ------- | ---------- | ---------- | ------- |
| P₁      | 0.0     | 14.0       | 14.0       | 6.0     |
| P₂      | 0.4     | 6.0        | 5.6        | 1.6     |
| P₃      | 1.0     | 2.0        | 1.0        | 0.0     |

**Rata-rata:**

* Waiting Time: (6 + 1.6 + 0) / 3 = **2.53**
* Turnaround Time: (14 + 5.6 + 1) / 3 = **6.87**

---

## ⚫ Soal 5.4: Priority Scheduling (Non-Preemptive)

### Data Proses:

| Process | Burst Time | Priority |
| ------- | ---------- | -------- |
| P₁      | 2          | 2        |
| P₂      | 1          | 1 (🔼)   |
| P₃      | 8          | 4        |
| P₄      | 4          | 2        |
| P₅      | 5          | 3        |

> *Semakin kecil angka priority, semakin tinggi prioritasnya.*

### Urutan Eksekusi Berdasarkan Prioritas:

1. P₂ (Priority 1)
2. P₁ (Priority 2)
3. P₄ (Priority 2)
4. P₅ (Priority 3)
5. P₃ (Priority 4)

### Gantt Chart:

```
| 0 |--P₂--| 1 |--P₁--| 3 |--P₄--| 7 |--P₅--| 12 |--P₃--| 20 |
```

### Perhitungan:

| Process | Burst | Priority | Start | Completion | Waiting | Turnaround |
| ------- | ----- | -------- | ----- | ---------- | ------- | ---------- |
| P₂      | 1     | 1        | 0     | 1          | 0       | 1          |
| P₁      | 2     | 2        | 1     | 3          | 1       | 3          |
| P₄      | 4     | 2        | 3     | 7          | 3       | 7          |
| P₅      | 5     | 3        | 7     | 12         | 7       | 12         |
| P₃      | 8     | 4        | 12    | 20         | 12      | 20         |

**Rata-rata:**

* Waiting Time: (0 + 1 + 3 + 7 + 12) / 5 = **4.6**
* Turnaround Time: (1 + 3 + 7 + 12 + 20) / 5 = **8.6**

---

## ⚫ Soal 5.5: Round Robin Scheduling

### Data Proses:

| Process | Priority | Burst Time | Arrival Time |
| ------- | -------- | ---------- | ------------ |
| P₁      | 40       | 20         | 0            |
| P₂      | 30       | 25         | 25           |
| P₃      | 30       | 25         | 30           |
| P₄      | 35       | 15         | 60           |
| P₅      | 5        | 10         | 100          |
| P₆      | 10       | 10         | 105          |

> Algoritma **Round Robin** *mengabaikan prioritas*, hanya mempertimbangkan arrival time dan time quantum (TQ).

> **Asumsi Time Quantum = 10**

### Gantt Chart (Simulasi Eksekusi):

```
0   | P₁  | 10  
10  | P₁  | 10 (selesai)  
20  idle  
25  | P₂  | 10  
35  | P₃  | 10  
45  | P₂  | 10  
55  | P₃  | 10  
65  | P₄  | 10  
75  | P₂  | 5  (selesai)  
80  | P₃  | 5  (selesai)  
85  | P₄  | 5  (selesai)  
90  idle  
100 | P₅  | 10 (selesai)  
110 | P₆  | 10 (selesai)  
```

### Perhitungan:

| Process | Arrival | Burst | Completion | Turnaround | Waiting |
| ------- | ------- | ----- | ---------- | ---------- | ------- |
| P₁      | 0       | 20    | 20         | 20         | 0       |
| P₂      | 25      | 25    | 80         | 55         | 30      |
| P₃      | 30      | 25    | 85         | 55         | 30      |
| P₄      | 60      | 15    | 90         | 30         | 15      |
| P₅      | 100     | 10    | 110        | 10         | 0       |
| P₆      | 105     | 10    | 120        | 15         | 5       |

**Rata-rata:**

* Waiting Time: (0 + 30 + 30 + 15 + 0 + 5) / 6 = **13.33**
* Turnaround Time: (20 + 55 + 55 + 30 + 10 + 15) / 6 = **30.83**

---

# ©️ Berikut Implementasi Seluruh Soal Tersebut Ke Bahasa `C`

Yang dimana pada program ini mencangkup seluruh ***algorithm scheduling*** dari seluruh soal diatas. Program ini dijadikan bentuk opsi, lalu meminta input user berupa jumlah *process* & total nominal *process* tersebut.

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX 100

typedef struct {
    int id;
    float arrival_time;
    int burst_time;
    int remaining_time;
    int priority;
    float start_time;
    float completion_time;
    float waiting_time;
    float turnaround_time;
} Process;

void input_processes(Process p[], int *n, int with_arrival, int with_priority) {
    printf("Masukkan jumlah proses: ");
    scanf("%d", n);

    for (int i = 0; i < *n; i++) {
        p[i].id = i + 1;
        if (with_arrival) {
            printf("Arrival time P%d: ", i + 1);
            scanf("%f", &p[i].arrival_time);
        } else {
            p[i].arrival_time = 0;
        }

        printf("Burst time P%d: ", i + 1);
        scanf("%d", &p[i].burst_time);

        if (with_priority) {
            printf("Priority P%d (angka kecil = lebih prioritas): ", i + 1);
            scanf("%d", &p[i].priority);
        } else {
            p[i].priority = 0;
        }

        p[i].remaining_time = p[i].burst_time;
    }
}

void sjf_no_arrival(Process p[], int n) {
    for (int i = 0; i < n - 1; i++)
        for (int j = i + 1; j < n; j++)
            if (p[i].burst_time > p[j].burst_time) {
                Process temp = p[i]; p[i] = p[j]; p[j] = temp;
            }

    float time = 0, total_wt = 0, total_tat = 0;
    printf("\nSJF Non-Preemptive (tanpa Arrival Time):\n");
    printf("P\tBT\tWT\tTAT\n");
    for (int i = 0; i < n; i++) {
        p[i].waiting_time = time;
        p[i].turnaround_time = time + p[i].burst_time;
        time += p[i].burst_time;
        total_wt += p[i].waiting_time;
        total_tat += p[i].turnaround_time;
        printf("P%d\t%d\t%.1f\t%.1f\n", p[i].id, p[i].burst_time, p[i].waiting_time, p[i].turnaround_time);
    }
    printf("Avg WT = %.2f, Avg TAT = %.2f\n", total_wt / n, total_tat / n);
}

void sjf_with_arrival(Process p[], int n) {
    int completed = 0, visited[n];
    memset(visited, 0, sizeof(visited));
    float time = 0, total_wt = 0, total_tat = 0;
    printf("\nSJF Non-Preemptive (dengan Arrival Time):\n");
    printf("P\tAT\tBT\tWT\tTAT\n");

    while (completed < n) {
        int idx = -1, min_bt = 1e9;
        for (int i = 0; i < n; i++) {
            if (!visited[i] && p[i].arrival_time <= time && p[i].burst_time < min_bt) {
                min_bt = p[i].burst_time;
                idx = i;
            }
        }
        if (idx == -1) {
            time++;
            continue;
        }
        p[idx].waiting_time = time - p[idx].arrival_time;
        time += p[idx].burst_time;
        p[idx].turnaround_time = time - p[idx].arrival_time;
        total_wt += p[idx].waiting_time;
        total_tat += p[idx].turnaround_time;
        visited[idx] = 1;
        completed++;
        printf("P%d\t%.1f\t%d\t%.1f\t%.1f\n", p[idx].id, p[idx].arrival_time, p[idx].burst_time, p[idx].waiting_time, p[idx].turnaround_time);
    }
    printf("Avg WT = %.2f, Avg TAT = %.2f\n", total_wt / n, total_tat / n);
}

void srtf(Process p[], int n) {
    float time = 0;
    int completed = 0;
    float total_wt = 0, total_tat = 0;

    for (int i = 0; i < n; i++)
        p[i].remaining_time = p[i].burst_time;

    while (completed < n) {
        int idx = -1, min = 1e9;
        for (int i = 0; i < n; i++) {
            if (p[i].arrival_time <= time && p[i].remaining_time > 0 && p[i].remaining_time < min) {
                min = p[i].remaining_time;
                idx = i;
            }
        }
        if (idx == -1) {
            time++;
            continue;
        }
        p[idx].remaining_time--;
        time++;
        if (p[idx].remaining_time == 0) {
            p[idx].completion_time = time;
            p[idx].turnaround_time = time - p[idx].arrival_time;
            p[idx].waiting_time = p[idx].turnaround_time - p[idx].burst_time;
            total_wt += p[idx].waiting_time;
            total_tat += p[idx].turnaround_time;
            completed++;
        }
    }

    printf("\nSRTF (Preemptive):\n");
    printf("P\tWT\tTAT\n");
    for (int i = 0; i < n; i++)
        printf("P%d\t%.1f\t%.1f\n", p[i].id, p[i].waiting_time, p[i].turnaround_time);

    printf("Avg WT = %.2f, Avg TAT = %.2f\n", total_wt / n, total_tat / n);
}

void priority_scheduling(Process p[], int n) {
    for (int i = 0; i < n - 1; i++)
        for (int j = i + 1; j < n; j++)
            if (p[i].priority > p[j].priority) {
                Process temp = p[i]; p[i] = p[j]; p[j] = temp;
            }
    float time = 0, total_wt = 0, total_tat = 0;
    printf("\nPriority Scheduling (Non-Preemptive):\n");
    printf("P\tPri\tBT\tWT\tTAT\n");
    for (int i = 0; i < n; i++) {
        p[i].waiting_time = time;
        p[i].turnaround_time = time + p[i].burst_time;
        time += p[i].burst_time;
        total_wt += p[i].waiting_time;
        total_tat += p[i].turnaround_time;
        printf("P%d\t%d\t%d\t%.1f\t%.1f\n", p[i].id, p[i].priority, p[i].burst_time, p[i].waiting_time, p[i].turnaround_time);
    }
    printf("Avg WT = %.2f, Avg TAT = %.2f\n", total_wt / n, total_tat / n);
}

void round_robin(Process p[], int n, int tq) {
    float time = 0;
    int completed = 0;
    int remaining[n];
    float total_wt = 0, total_tat = 0;

    for (int i = 0; i < n; i++)
        remaining[i] = p[i].burst_time;

    while (completed < n) {
        int progress = 0;
        for (int i = 0; i < n; i++) {
            if (p[i].arrival_time <= time && remaining[i] > 0) {
                progress = 1;
                if (remaining[i] > tq) {
                    time += tq;
                    remaining[i] -= tq;
                } else {
                    time += remaining[i];
                    remaining[i] = 0;
                    p[i].completion_time = time;
                    p[i].turnaround_time = time - p[i].arrival_time;
                    p[i].waiting_time = p[i].turnaround_time - p[i].burst_time;
                    total_wt += p[i].waiting_time;
                    total_tat += p[i].turnaround_time;
                    completed++;
                }
            }
        }
        if (!progress) time++;
    }

    printf("\nRound Robin:\n");
    printf("P\tAT\tBT\tWT\tTAT\n");
    for (int i = 0; i < n; i++)
        printf("P%d\t%.1f\t%d\t%.1f\t%.1f\n", p[i].id, p[i].arrival_time, p[i].burst_time, p[i].waiting_time, p[i].turnaround_time);

    printf("Avg WT = %.2f, Avg TAT = %.2f\n", total_wt / n, total_tat / n);
}

int main() {
    Process p[MAX];
    int n, tq, pilihan;

    while (1) {
        printf("\n\nMenu:\n");
        printf("1. SJF tanpa Arrival Time\n");
        printf("2. SJF dengan Arrival Time\n");
        printf("3. SRTF\n");
        printf("4. Priority Scheduling\n");
        printf("5. Round Robin\n");
        printf("0. Keluar\n");
        printf("Pilih algoritma: ");
        scanf("%d", &pilihan);

        if (pilihan == 0) break;

        if (pilihan == 1) {
            input_processes(p, &n, 0, 0);
            sjf_no_arrival(p, n);
        } else if (pilihan == 2) {
            input_processes(p, &n, 1, 0);
            sjf_with_arrival(p, n);
        } else if (pilihan == 3) {
            input_processes(p, &n, 1, 0);
            srtf(p, n);
        } else if (pilihan == 4) {
            input_processes(p, &n, 0, 1);
            priority_scheduling(p, n);
        } else if (pilihan == 5) {
            input_processes(p, &n, 1, 0);
            printf("Masukkan Time Quantum: ");
            scanf("%d", &tq);
            round_robin(p, n, tq);
        } else {
            printf("Pilihan tidak valid!\n");
        }
    }
    return 0;
}
```
